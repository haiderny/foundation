## Creating An ID
In order to create an ID, you can simple call the createId function.  It must be called with a byte32 valid name.


```javascript
  function createId(bytes32 _name) idCreator isNewName(_name) payable { }
```

The attached modifiers check the following, if they check fail the function will throw:

##### Arguments 
* _name: The 

##### Modifiers
* idCreator: Makes sure the amount of wei sent matches the amount of wei required to create.  (Currently the amount of wei require to create is set to 0).
* isNeName: Makes sure that no other ID already exists with the same name.
* payable: this function can receive ethereum.

Once the action is completed you will have a foundationId with the msg.sender added as the address.


## Add an Address
Adding addresses to an ID is a two step process.  You first must add an address from an existing FoundationID address and then you must confirm from that new address.



To add an address simply call the addPendingUnification function from an address already held within the FoundationId.  Call it with the address you wish to add.


```javascript
  function addPendingUnification(address _addr) isNewNameAddrPair(addrToName[msg.sender], _addr) isNewAddr(_addr) {}
  ```

##### Modifiers
* addrHasId: Makes sure address doesn't already exist in a foundationId

## Confirm the Address

After adding an address from an associated address of the FoundationId you must confirm the address from the actual address.  Use the confirmPendingUnification function for this.

```javascript
  function confirmPendingUnification(bytes32 _name) addrHasId(msg.sender) {}
```

##### Modifiers
* addrHasId: Makes sure address doesn't already exist in a foundationId
