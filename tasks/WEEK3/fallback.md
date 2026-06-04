## 一、项目成立依赖的前提（Assumptions）

本项目 SafeAgent Wallet Assistant 成立依赖以下关键前提：

### 1. LLM 能稳定输出结构化交易意图

系统依赖 AI 将自然语言转为可执行的交易 schema（action / token / amount / protocol），且输出具备一致性与可解析性。

### 2. 用户可以接受“半自动执行 + 人工确认”模式

用户不会期望完全自动化交易，而是接受在关键步骤进行确认（Human-in-the-loop）。

### 3. 简化版风险规则足以覆盖 MVP 安全需求

通过基础规则（金额阈值、白名单协议、操作类型）即可模拟真实风险控制逻辑，而不依赖复杂链上风控系统。

### 4. Web3 执行层可以被 mock 或最小化实现

在 Week 4 阶段，即使不接入 ERC-4337 / Safe / MPC，也能通过钱包连接 + 模拟交易完成产品闭环验证。

### 5. 用户理解“Agent ≠ 自动资金控制器”

用户能够理解 AI 是辅助决策工具，而不是完全自主执行资金操作的系统。

## 二、最可能失败的地方（Failure Points）

### 1. AI 输出不稳定导致交易意图错误

风险表现：

* LLM 输出结构不一致
* token / amount / protocol 识别错误
* prompt injection 导致错误执行建议

影响：

* 交易计划错误
* 无法进入可靠执行阶段

### 2. “真实执行 vs Mock 执行”之间的信任断层

风险表现：

* 用户认为系统“只是 demo”
* 或认为系统“不够真实”
* 难以建立可信产品形态

影响：

* demo 价值降低
* 无法验证 product-market fit

### 3. 风险控制过于简单或过于复杂

风险表现：

* 规则太简单 → 不可信
* 规则太复杂 → Week 4 无法完成

影响：

* 安全叙事不成立
* 或系统无法完成 MVP

### 4. Scope 膨胀导致无法完成完整闭环

风险表现：

* 想同时做 wallet + AI + DeFi + AA + MPC
* 每个模块都只做一半

影响：

* 没有 end-to-end demo

## 三、Fallback Plan

### 1. Execution 层

如果链上执行不稳定或集成失败：

* 使用 mock transaction hash
* 模拟 success / fail 状态
* 保留完整 execution log 结构

保证用户体验链路完整，而不是链上真实性

### 2. Wallet / Signing fallback

如果 ERC-4337 / Safe / MPC 无法集成：

* 使用 MetaMask basic wallet connection
* 所有权限控制在 frontend policy layer 实现
* 不依赖链上账户抽象

保证权限逻辑存在，但不依赖复杂基础设施

### 3. AI 输出 fallback

如果结构化输出不稳定：

* 使用 fixed JSON schema prompt template
* 加入 validation layer（regex / rule check）
* fallback to “manual correction UI”

保证intent 可控，即使 AI 不稳定

### 4. Risk Engine fallback

如果 risk engine 过复杂：

* 退化为 rule-based system：

  * amount threshold
  * whitelist protocol
  * approve detection

保证至少有 deterministic safety layer
