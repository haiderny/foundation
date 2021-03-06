Removing addresses from your FoundationId is a straightforward process

To delete an address from a FoundationId run the deleteAddr function passing as a parameter the address to be removed.  This function must be run by an address that exists within the same FoundationId as the address to be deleted.

```javascript
  function deleteAddr(address _addr) nameExists(addrToName[_addr]) isOwner(addrToName[_addr]) hasTwoAddress(addrToName[_addr]) {}
```
##### Arguments
* _addr: The address to delete from your foundationId

##### Modifiers
* nameExists: Checks to make sure there is an ID associated with the address.
* isOwner: Checks to make sure msg.sender is the owner of FoundationId associated with the address being deleted
* hasTwoAddress: makes sure the foundationId has at least two addresses so that deleting one still leaves at least one existing address.
