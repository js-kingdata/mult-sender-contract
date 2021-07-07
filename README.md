# 批量转账ERC20代币

## 注：转账前需要调用 ERC20 代币合约的 'approve' 方法，给该合约进行授权

+ 合约已部署到BSC链：[0xdeC44Cb3318244897BeEEdD03AdB3d7510f7147D](https://bscscan.com/address/0xdeC44Cb3318244897BeEEdD03AdB3d7510f7147D)

## 方法参数说明
- 方法名称: `safeMultiTransfer`
- token: ERC20 Token 的地址
- to: 接收者的钱包地址数组
- amount: 转账金额的数组(需要与接收者的数组数量一致)
- 注意：这里的 amount 中的元素'实际转账的数量 * 10 ** Token的decimals'

## 举个🌰
- 给3个不同账户分别转 1USDT、2USDT、3USDT
- token `0x55d398326f99059ff775485246999027b3197955`
- to 
```json
[
  "0xecb56cf772b5c9a6907fb7d32387da2fcbfb63b4",
  "0xef3cebd77e0c52cb6f60875d9306397b5caca375",
  "0xe499ef4616993730ced0f31fa2703b92b50bb536"
]
```
- amount USDT的decimals是18，那么这里的元素需要`n * 10 ** 18`
```sol
[
  "1000000000000000000",
  "2000000000000000000",
  "3000000000000000000"
]
```
