# voting-dapp
Voting Ethereum Dapp
https://medium.com/@mvmurthy/full-stack-hello-world-voting-ethereum-dapp-tutorial-part-1-40d2d0d807c2

## How to launch
1. $ npm install ethereumjs-testrpc web3@0.20.1
2. $ node_modules/.bin/testrpc
3. $ npm install solc

#### Opening node console
4. $ node
5. $ Web3 = require('web3')
6. $ web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));
7. $ web3.eth.accounts
8. $ code = fs.readFileSync('Voting.sol').toString()
9. $ solc = require('solc')
10. $ compiledCode = solc.compile(code)	
11. $ abiDefinition = JSON.parse(compiledCode.contracts[':Voting'].interface)	
12. $ VotingContract = web3.eth.contract(abiDefinition)	
13. $ byteCode = compiledCode.contracts[':Voting'].bytecode

#### Deploying the contract
14. $ deployedContract = VotingContract.new(['Rama','Nick','Jose'],{data: byteCode, from: web3.eth.accounts[0], gas: 4700000})
15. $ deployedContract.address
16. $ contractInstance = VotingContract.at(deployedContract.address)

#### Check votes
> $ contractInstance.totalVotesFor.call('Rama')

#### Voting
> $ contractInstance.voteForCandidate('Rama', {from: web3.eth.accounts[0]})