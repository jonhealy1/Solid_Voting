__Avoiding Common Attacks__

__General Design:__ Via Require statements, the addCandidate function limits the number of candidates that can be added to 8. Similarly, voting more than once in the same voting function is limited additionally with the use of booleans. ex. require(!voters[msg.sender], "User already voted"); Other parameters are also checked to ensure that Voters are voting for Candidates with valid Candidate Ids. 

__Circuit Breaker:__ Pausable is implemented via OpenZeppelin. The three voting functions and the addCandidate function can all be stopped by the contract Owner.

__Integer Overflow/ Underflow:__ The SafeMath library is imported courtesy of OpenZeppelin. This prevents wrap around if integers become too large or small. 

__Logic Bugs:__ Limited by using Truffle testing framework and coding standards to ensure that the logic of the contract behaves as expected. Contract is simple. 

__Recursive Calls/ Reentrancy Attacks:__ The simplicity of this contract ensures that there are no external function calls being made. The only linked contracts and libraries are trusted ones from OpenZeppelin.

__Poison Data:__ A User could implement unexpected data in the addCandidate input field. This contract should check and limit this but does not. 

__Exposure:__ The only functions that are limited to the contract Owner are those from the Pausable library. This contract has nothing to hide in its current form.

__tx.origin/ Gas Limits:__ Ownable uses msg.sender. The simple nature of the Elections contract means that implementing limits on Gas not applicable except in the add Candidate function where limiting string length has not been applied yet.

__Other Attacks:__ This contract does not transfer or store Ether for any purpose and this should limit numerous attack vectors. Forcibly sending Ether to this contract should not be a problem for instance. Also, using pull over push payments in the case of a DoS attack with Block Gas Limit ditto. 

  
