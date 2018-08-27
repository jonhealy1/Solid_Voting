# Solid Voting

This is a very simple voting application. Addresses are given three choices to allocate. Their first choice is worth 5 votes, the second, 3 votes, and the third is worth 1. All 3 choices can be given to one Candidate. A User can also add a Candidate but the number of Candidates is limited to 8.

__Sources:__ https://truffleframework.com/tutorials/pet-shop /and/ http://www.dappuniversity.com/

__Rinkeby Network:__ This contract is deployed on the Rinkeby Network at address: __0x4f60cfddec702b21e204800725424dd6bc09a4cc__


__Instructions:__ 

1. Install Truffle: __npm install -g truffle__
2. Install Ganache: __npm install -g ganache-cli__
3. Install MetaMask: https://metamask.io/
3. Download this project
4. Navigate to project folder with terminal
5. Install project dependencies: __npm install__
6. Start Ganache: __ganache-cli__
7. Copy Mnemonic shown in ganache: ex. spawn general accident claim pattern immune muscle lube magnet almost display artist
8. Open MetaMask in __Brave__ or Google Chrome
9. Go to network: localhost:8545 in MetaMask (this can be changed in settings if it shows 7545 or something else)
10. In MetaMask select __"restore from seed phrase"__ 
11. Paste in the Mnemonic from Ganache and create a password
12. Compile - In a new terminal window in the project folder: __truffle compile__
13. Migrate: __truffle migrate --reset__
14. Open up a browser window with this project running: __npm run dev__


__Known Issues:__ When adding a candidate, the page may not refresh and a new page would need to opened with the same address to see the changes. Sometimes multiple entries for each candidate are shown in the Candidates table.

__Libraries:__ SafeMath and Pausable are implemented courtesy of OpenZeppelin.

__Circuit-Breaker:__ Using Pausable, the Owner of a contract can pause both the voting functions and the add Candidate functions.

__Development-Server:__ Uses lite-server

__Testing:__ Explanations for the testing logic is provided with the code in the file /test/election.js Note: Ganache or something similar must be running in order to run truffle test.

*expected output:* <br />

MBP:ethElections macowner$ truffle test <br />
<br />
Using network 'development'. <br />
<br />
  Contract: Election <br />
    ✓ initializes with three candidates <br />
    ✓ it initializes the candidates with the correct values (54ms) <br />
    ✓ allows a voter to add a candidate (46ms) <br />
    ✓ allows a voter to cast first place vote (5 votes) (65ms) <br />
    ✓ allows a voter to cast second place vote (3 votes) (61ms) <br />
    ✓ throws an exception for invalid candidates (108ms) <br />
    ✓ throws an exception for double voting (95ms) <br />
<br />
<br />
  7 passing (483ms)<br />



