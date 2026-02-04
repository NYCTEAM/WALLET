# Eagle Swap (Unstoppable Wallet 核心) 构建指南

此项目基于 [Unstoppable Wallet](https://github.com/horizontalsystems/unstoppable-wallet-android) 进行定制开发。

## 1. 项目状态
*   **代码库**: 已切换至 `Unstoppable_Wallet` 目录。
*   **品牌**:
    *   应用名称已更改为 **Eagle Swap**。
    *   图标已更新为 Eagle Swap Logo (自动适配 Adaptive Icon)。
    *   Deeplink Scheme 已更改为 `eagleswap://`。

## 2. 功能特点 (继承自 Unstoppable)
*   **多链支持**: 原生支持 Bitcoin, Ethereum, BSC, Avalanche, Solana, Zcash 等。
*   **NFT 支持**: **原生支持!** 无需额外跳转浏览器，APP 内直接展示 NFT 画廊。
*   **隐私安全**: 没有任何用户数据收集。
*   **Swap 集成**: 内置 Swap 接口。

## 3. 下一步开发计划
1.  **Swap 集成**:
    *   查找 Unstoppable 内置的 Swap 模块 (通常在 `app/src/main/java/io/horizontalsystems/bankwallet/modules/swap`).
    *   修改其 Provider 为您自己的 Swap 合约或 API。
2.  **节点配置**:
    *   配置 BSC / Arbitrum / Base / X Layer 节点。
    *   实现之前的 "智能节点切换" (HK/US)。
3.  **官方链接**:
    *   修改 `Settings` 页面中的 Twitter, Telegram, Website 链接。

## 4. 编译方法
```bash
cd g:\WALLET\Unstoppable_Wallet
./gradlew assembleRelease
```
或者在 Android Studio 中打开 `g:\WALLET\Unstoppable_Wallet` 目录。
