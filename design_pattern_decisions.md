# Design Pattern Decisions

I chose to do a Voting application because my initial interest in Blockchain related things came about over a year ago after researching voter fraud. I am 2 courses away from finishing my Bachelor's degree in Computer Science. Before being in this program I had almost zero experience in web or Ethereum development. The simplicity of my application reflects this.

While I was doing this program I took a course online in Bootstrap that taught me a little about Git, Node.js, html, css, and JQuery. I tried to add more functionality to my application but mostly because of my inexperience with Javascript I kept breaking things. Some features I wanted to add: 

1. I wanted to give Users the option to vote on issues as well as candidates.
2. Adding an issue or candidate was supposed to cost Ether above the transaction fees.
3. I wanted to have Voters answer general knowledge questions about either the candidates or the issues in order to be delegated votes.

I chose to allow a Voter to have three voting options. A first place choice worth 5 votes, a second place choice worth 3 votes and a third place choice worth 1 vote. A Voter can also add a Candidate. I would like to limit the length of a String for the addCandidate field but have not yet. I do prevent Voters from adding more than 8 Candidates total.

In this application I have imported both SafeMath and Pausable from OpenZeppelin. SafeMath is for integer overflow/ underflow and Pausable is to allow the contract Owner to pause the contract in the case of an emergency. This is 'Circuit Breaker' design. 

I have chosen to make all the functions in my application public. I am using Bootstrap as that is what I have some experience with. The testing is done in the file, 'election.js' with the Mocha testing framework and the Chai assertion library which are both bundled in Truffle. I also use numerous Require statements in my contract to make sure that it operates Bug-free.
  



