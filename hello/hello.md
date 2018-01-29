hello

// interact with ABI in JS console

```javascript
await contract // => returns contract ABI; review methods
await contract.password() // => returns password for the level
await contract.authenticate() // => fails with invalid number of arguments
await contract.authenticate("ethernaut0") // try password returned from above (contract.password())
await contract.getCleared() // => returns true after tx mined
```
