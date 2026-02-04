# 自定义代币配置 (GitHub 托管指南)

您可以将代币配置文件托管在 GitHub 上，无需购买服务器。

## 1. 准备 GitHub 仓库
1.  登录您的 GitHub 账号。
2.  创建一个新的公开仓库 (Public Repository)，建议命名为 `wallet-assets`。
3.  **关键步骤**: 如果您的 GitHub 用户名不是 `EagleswapLLC`，请务必去 `app/build.gradle` 文件中搜索 `EagleswapLLC` 并替换为您自己的 GitHub 用户名！

## 2. 创建配置文件
在您的仓库中创建文件 `provider.coins.json`，内容如下：

```json
[
  {
    "id": "eagle-token-bsc",
    "code": "EAGLE",
    "name": "Eagle Token",
    "description": "Official Eagle Swap Token on BSC",
    "type": "eip20",
    "address": "0x480F12D2ECEFe1660e72149c57327f5E0646E5c4",
    "decimal": 18,
    "blockchain_uid": "binance-smart-chain",
    "active": true
  },
  {
    "id": "eagle-token-xlayer",
    "code": "EAGLE",
    "name": "Eagle Token",
    "description": "Official Eagle Swap Token on X Layer",
    "type": "eip20",
    "address": "0x5a746ee9933627ed79822d35a3fe812eddd5ba37",
    "decimal": 18,
    "blockchain_uid": "x-layer",
    "active": true
  }
]
```

## 3. 获取 Raw 链接
1.  文件上传后，点击该文件。
2.  点击右上角的 **"Raw"** 按钮。
3.  浏览器地址栏中的链接即为我们需要的链接。
    *   格式通常为: `https://raw.githubusercontent.com/用户名/仓库名/main/provider.coins.json`
    *   APP 代码中已预设为: `https://raw.githubusercontent.com/EagleswapLLC/wallet-assets/main/provider.coins.json`

## 4. 关于 Logo (头像)
Unstoppable Wallet 默认从官方仓库拉取图标。如果您想显示自己的 Logo：
1.  **提交 PR**: 向 `horizontalsystems/cryptocurrencies` 仓库提交 Pull Request，上传您的图标。
2.  **或者 (高级)**: 您需要修改 APP 代码中的 `CoinManager` 或相关逻辑，让其支持从 `provider.coins.json` 中读取 `image` 字段（默认逻辑不支持直接从这个 JSON 读图，只读代币定义）。

目前最简单的方式是：确保代币符号 (EAGLE) 与知名代币不冲突，或者通过 Pull Request 提交到 Unstoppable 官方库。
