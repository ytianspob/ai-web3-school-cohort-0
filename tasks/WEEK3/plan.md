# Week 4 目标

## Day 1：项目骨架 + Wallet连接

真实实现

Next.js 项目初始化

钱包连接（MetaMask / WalletConnect）

获取地址 + chainId

基础 UI（输入框 + result panel）


可以 mock / fallback

不接真实 ERC-4337

不接 Safe

不做交易签名


## Day 2：AI Agent + Prompt Parser

真实实现

接入 LLM（Z.AI / OpenAI）

Prompt → JSON structured output：
{
  "action": "deposit",
  "token": "USDC",
  "amount": 50,
  "protocol": "Aave"
}

基础 risk tagging（low / medium / high）


可以 mock / fallback

不调用链上数据

不做真实价格计算

protocol list 用 hardcode


## Day 3：Execution Plan + Risk Engine

真实实现

build execution planner：

step breakdown

transaction simulation logic


risk rules engine：

amount threshold

whitelist protocol

approve detection


可以 mock / fallback

gas estimation → mock value

price feed → static data

slippage → fixed %


## Day 4：Execution Layer（核心链路）

真实实现

ethers.js / viem 发起 transaction（testnet）

transaction status tracking（pending/success/fail）


可以 mock / fallback

不真实上链

用 “fake tx hash” 模拟链上返回

模拟成功/失败状态


## Day 5：Human-in-the-loop + Policy Gate

真实实现

approval modal（人工确认）

policy check layer：

amount > threshold → require approval

new protocol → require approval

approve unlimited → block

可以 mock / fallback

多签 / ERC-4337 不接

MPC 不接

Guard 系统简化为 JS rules


## Day 6：Logging + Audit Trail

真实实现

execution log system：

prompt

parsed intent

risk level

decision (approved/rejected)

tx result

UI audit panel

可以 mock / fallback

不上链存储日志

用 localStorage / JSON file


## Day 7：整合 + Demo Polish

真实实现

end-to-end flow 打通：

Input → AI → Risk → Approval → Execution → Log
UI polish

demo script

可以 mock / fallback

所有链上执行可以 fallback mock

不影响 demo narrative
Day 7 产出
可演示完整 Agent Wallet workflow
Hackathon ready demo
