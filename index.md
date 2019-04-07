# Tezos Bounty . Design

This website has been created to incentivize developers in creating new Tezos smart contract or new features to be incorporated via Tezos Governance built-in protocol. This will allow for XTZ owners, promoters as well as bakers to fund an account with XTZ that will serve as a bounty or donation to the developer of the project.

# Current Project:

## Delegation Reassignment Smart Contract

### XTZ address for donation: 
tz1WvPcd8Y5gUdN4K5JTpvUgjnXc3crZWtx2
[View on TzScan](https://tzscan.io/tz1WvPcd8Y5gUdN4K5JTpvUgjnXc3crZWtx2)

### Announcement:
https://medium.com/hayek-lab/launching-tezos-bounty-7565f159cafc

### Description

Our first project is a new Delegation smart contract to replace the existing KT1 contract being used to delegate.
This contract will have the exact same behavior as the existing delegation KT1 contract except that in addition, it will allow the current delegate to change the delegation, not just the manager of the KT1 contract.

It could start with KT2 or still with KT1, as long as the Tezos wallet clearly states which one is being used. We recommend that tezos wallets use this new contract as the default version once it becomes available.

### Requirements

Design a new KT contract with the exact same features as the existing delegation KT1 contract but with this one additional feature:

Allow both the owner of the manager of the KT contract as well as the current delegate to which the KT contract is delegating to the ability to change the delegate of the contract.
Once the delegate has been changed to a new delegate, the prior delegate loses the rights to change the delegation for this KT contract. The owner of the newly set delegate now does have this ability. 

### Testing to be done
Legend:  
tz1BakerA  - first delegate
tz1BakerB  - second delegate
KT1delegator - delegator address
tz1manager - manager who owns and created the KT1delegator address

1. Validate only the manager (tz1manager) can set a delegation to a new KT address originated that has the manager itself as the delegate. (Blank slate origination).
   * Try changing the delegation using any other tz delegate address: should fail
   * Try changing the delegation using the manager (tz) of the KT: should succeed
2. Validate only the manager of the KT contract as well as the owner of the delegate can change
   * Try changing the delegation using any other tz delegate address other than the one currently delegating to or the manager: should fail
   * Try changing the delegation as the owner of the tz delegate address: should succeed
   * Try changing the delegation using the manager (tz) of the KT: should succeed
3. Validate prior tz delegate is not able to change the delegation once delegation change is completed
   * Try changing the delegation using the prior tz delegate address: should fail
   * Try changing the delegation using the new tz delegate address: should succeed
   * Try changing the delegation as the manager of the KT address: should succeed

Upon successful testing and code review, the developer will be receiving the bounty held in account 
tz1WvPcd8Y5gUdN4K5JTpvUgjnXc3crZWtx2

(minus 10% to send to the first 2 wallet adopt the change)


### Current submissions:
* We have received information via email for one submission. Still accepting donation.


## Web Page and Project Operated and Maintained by
https://HayekLab.com
