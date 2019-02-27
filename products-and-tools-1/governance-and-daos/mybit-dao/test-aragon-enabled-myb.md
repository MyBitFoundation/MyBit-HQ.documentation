---
description: 'Released February 15, 2019 (This version is deprecated)'
---

# Test MyBit DAO v0.1

This guide will show you how to test Aragon-enabled MYB voting by interacting directly with the smart contracts. We are working to create a web-interface to enable easier testing and visualisation to release in the near future.

**Overview of voting**

Everyone that has 1 MYB receives 1 vote. The number of votes does not increase based on how many MYB you hold. You can however receive a multiplier for locking tokens. The amount required to lock is exactly 100,000 \(less is not allowed, more has no impact on multiplier\). Then based on how long you lock for you receive a voting multiplier on your 1 vote \(amounts TBD\).

**There are 4 main steps**

1. Get 100,000 testnet MYB
2. Approve the contract to use MYB
3. Lock Tokens
4. Vote

**Step 1 - Testnet MYB**

1. First you will need 100,000 Rinkeby testnet MYB. We suggest storing it in metamask. We are developing a faucet for this, in the mean time ping Peter Phillips on t.me/mybit.io to receive the tokens.

**Step 2 - Approve Contract to use MYB**

1. Go to [https://mycrypto.com](https://mycrypto.com)
2. Choose "tools" and interact with contracts from the dropdown menu [https://mycrypto.com/contracts/interact](https://mycrypto.com/contracts/interact)
3. Choose custom contract and enter 0x027d8BBfd98F9965DFc4B2793De4fEA0173124f8 into the contract address field
4. Paste the following in the ABI section:                                                                       \[{"constant":true,"inputs":\[\],"name":"name","outputs":\[{"name":"","type":"string"}\],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":\[{"name":"\_spender","type":"address"},{"name":"\_value","type":"uint256"}\],"name":"approve","outputs":\[{"name":"","type":"bool"}\],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":\[\],"name":"totalSupply","outputs":\[{"name":"","type":"uint256"}\],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":\[{"name":"\_from","type":"address"},{"name":"\_to","type":"address"},{"name":"\_value","type":"uint256"}\],"name":"transferFrom","outputs":\[{"name":"","type":"bool"}\],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":\[\],"name":"decimals","outputs":\[{"name":"","type":"uint8"}\],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":\[{"name":"\_spender","type":"address"},{"name":"\_subtractedValue","type":"uint256"}\],"name":"decreaseApproval","outputs":\[{"name":"","type":"bool"}\],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":\[{"name":"\_owner","type":"address"}\],"name":"balanceOf","outputs":\[{"name":"","type":"uint256"}\],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":\[\],"name":"symbol","outputs":\[{"name":"","type":"string"}\],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":\[{"name":"\_to","type":"address"},{"name":"\_value","type":"uint256"}\],"name":"transfer","outputs":\[{"name":"","type":"bool"}\],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":\[{"name":"\_spender","type":"address"},{"name":"\_addedValue","type":"uint256"}\],"name":"increaseApproval","outputs":\[{"name":"","type":"bool"}\],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":\[{"name":"\_owner","type":"address"},{"name":"\_spender","type":"address"}\],"name":"allowance","outputs":\[{"name":"","type":"uint256"}\],"payable":false,"stateMutability":"view","type":"function"},{"inputs":\[{"name":"\_name","type":"string"},{"name":"\_symbol","type":"string"},{"name":"\_decimals","type":"uint8"},{"name":"\_totalSupply","type":"uint256"}\],"payable":false,"stateMutability":"nonpayable","type":"constructor"},{"anonymous":false,"inputs":\[{"indexed":true,"name":"from","type":"address"},{"indexed":true,"name":"to","type":"address"},{"indexed":false,"name":"value","type":"uint256"}\],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":\[{"indexed":true,"name":"owner","type":"address"},{"indexed":true,"name":"spender","type":"address"},{"indexed":false,"name":"value","type":"uint256"}\],"name":"Approval","type":"event"}\]
5. Click "access" and in the dropdown select "approve"
6. Enter 0x0c15ba8D2514F65f5b6bEb3D6623FBe964a892D6 in \_spender address
7. Enter amount 100000000000000000000000 in \_value uint256
8. Choose your wallet which holds the testnet MYB \(we suggest using metamask for testing\)
9. Click "write" then "generate transaction" then "send transaction"
10. Sign in metamask by choosing "confirm" - your tokens are now approve to use.

**Step 3 - Lock Tokens**

1. Go to the DAO [https://rinkeby.aragon.org/\#/0xCE03775BCeA4760923cfDA2f2BD9f295e28e8AB3/0x0c15ba8d2514f65f5b6beb3d6623fbe964a892d6](https://rinkeby.aragon.org/#/0xCE03775BCeA4760923cfDA2f2BD9f295e28e8AB3/0x0c15ba8d2514f65f5b6beb3d6623fbe964a892d6)
2. Go to token Locker on the sidebar, Choose Lock on the top right corner and choose the time period to lock for. Do not choose 0 months \(there is a bug in it we are fixing\) 
3. Sign in metamask by choosing "confirm" - your tokens are now locked and you should see your voting token balance \(weight\) in Token Locker next to your ETH address.

**Step 4 - Propose & Vote \(Not yet functional\)**

1. Select the "Voting" tab located on the left side navigation. Here you will be able to initiate a new proposal to be voted on or vote on existing proposals. 
2. To vote on a proposal simply choose "view vote," select yes or no, and sign in metamask.
3. To propose a new vote choose "New Vote" in the top right corner, enter question, select "Begin Vote," then "Create Transaction," then sign in metamask. Wait a few minutes and the proposal should be live for others to vote on.

