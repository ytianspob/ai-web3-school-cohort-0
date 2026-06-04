# SafeAgent Wallet Assistant

## Problem

Web3 用户在进行链上操作时，通常需要自行研究协议、理解复杂交易流程并承担操作风险。现有钱包虽然提供执行能力，但无法理解用户意图，也缺乏自动化协助。

本项目希望通过 AI Agent 帮助用户理解需求、生成执行计划、进行风险提示，并在用户授权后安全完成链上操作。

## Track

**AI × Web3**

细分方向：

* Agent Wallet
* AI Agent
* Wallet Infrastructure
* AI Security
* Account Abstraction

## MVP Flow

```text
用户输入自然语言任务
↓
Agent理解需求
↓
生成执行计划
↓
风险分析与提示
↓
用户确认
↓
交易模拟
↓
生成链上交易
↓
执行并记录日志
↓
返回执行结果
```

示例：

用户输入：

"帮我把 50 USDC 存入 Aave"

系统流程：

1. 识别目标协议
2. 查询链上信息
3. 分析潜在风险
4. 展示执行步骤
5. 用户确认
6. 模拟交易
7. 执行交易
8. 返回结果

## Tech Stack

### Frontend

* Next.js
* React
* TailwindCSS

### Backend

* Node.js
* TypeScript

### AI Layer

* Z.AI API / OpenAI API
* MCP (Model Context Protocol)

### Web3 Layer

* ethers.js
* viem
* Safe Smart Account
* ERC-4337 Smart Account

### Infrastructure

* Vercel
* GitHub

## Risks

### Security Risks

* Prompt Injection
* Tool Injection
* Malicious Contract Interaction
* Permission Escalation

### Wallet Risks

* Unlimited Approve
* Excessive Spending
* Session Key Leakage

### Product Risks

* AI Hallucination
* Incorrect Risk Assessment
* User Overtrust in Automation

## Validation Plan

### Goal

验证用户是否能够通过自然语言完成安全链上操作。

### Test Users

5-10 名有基础 Web3 经验的用户。

### Test Scenario

任务：

"将 50 USDC 存入指定协议"

### Success Metrics

* 成功完成任务
* 用户理解执行步骤
* 用户理解风险提示
* 所有交易均有审计记录
* 无超预算执行

### Expected Outcome

80% 以上测试用户能够在无需查看复杂合约交互细节的情况下完成链上操作，并理解系统给出的风险说明。

## Current Status

Week 2：

* 完成方向选择
* 完成问题拆解
* 完成系统流程设计

Next Step（Week 3）：

* Agent Profile Design
* Permission Model Design
* Transaction Simulation Flow
* MVP Prototype
