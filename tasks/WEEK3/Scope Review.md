## 1.不做：完整 DeFi 协议集成（真实多协议交互）

### 内容

* 不接入多个真实 DeFi 协议（Aave / Compound / Uniswap 全量集成）
* 不做跨协议自动路由优化
* 不做实时收益率聚合

## 2.不做：ERC-4337 / Safe / MPC 真实生产级集成

### 内容

* 不实现 Account Abstraction 完整流程
* 不接 MPC 或多签真实签名流程
* 不实现真实 Safe transaction execution

## 3.不做：复杂 AI 多 Agent 协作系统

### 内容

* 不做 planner + executor + reviewer 多 agent 架构
* 不做 agent 间通信协议（MCP/A2A 多节点协作）
* 不做长期 memory / learning system
