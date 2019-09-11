Ethereum is an open-source, public blockchain platform introducing for the very first time, to the concept of "Smart Contracts". The white paper is written by Vitalik Buterin.
It was thought that why should blockchain be used only for financial transactions. So the practical usage of the blockchain applications has been increased.
The platform allows decentralised apps to be built on it with the help of these Contracts. Smart Contracts basically provide an if-not-this-else-that kind of situations to find a solution to a problem. 
The piece of code written in Solidity (there are other languages as well) helps in writing the smart contract for Ethereum based platform.
Ethereum comes under blockchain 2.0 which is 2 nd generation of blockchain. This was the beginning of the era of Smart Contracts. 
ps: bitcoins belonging to the 1st generation of blockchain (blockchain 1.0)

So in gist, ethereum is much more than just a cryptocurrency, but turing complete - i.e. it can solve any computational problem given time and energy

Every cryptocurrency and blockchain platform has an account through which one can send/receive ethers. So, Accounts can be thought of simply as private key/address pairs. 
There are two types of ethereum accounts:
externally owned : owned by people or organisations.
                   controlled by private keys
contract accounts: autonomous in nature. 
                   controlled by code. (smart contracts) - triggered due to other external accounts or other smart contracts.

Users are able to create Smart Contracts by deploying their code (written in Solidity/Viper etc) in the blockchain. 
Also smart contracts are immutable pieces of code. Once deployed on the blockchain and run, they act as self operating computer programs, which automatically executes when specific conditions are met. 

These contracts are written in contract specific language called solidity or vyper. We would be talking about solidity. 
We needed to have a specific contract oriented language and not already existing ones such as C because the aim is to implement smart contracts on the EVM(Ethereum Virtual Machine) for further execution of the code.
So adding any mainstream language might not add value to it. Other than that it costs money for executing instructions so a mainstream language may cost a lot so a specific language focussing on only smart contract will make sure to use only those instructions which can cost less.
Other than that,there are security requirements as these codes are once deployed, can't be changed again.

There is an online IDE i.e. Remix for writing smart contracts. This online IDE can compile the contracts automatically as it has an integrating, debugging and testing environment.

The entire platform runs over Ethereum Virtual Machine(EVM) which is a turing complete software (partially as we can not afford EVM to solve all kinds of computations as it may cost a lot)
So, EVM runs on Ethereum network and hence, any program can be run irrespective of the programming language.
Basically these contracts are written in contract specific programming language and are then compiled into bytecode, which can be read and executed by the EVM. 

Next we are going to understand the working of a smart contract on the Ethereum platform. So, when a sender initiates a transaction, a message code gets executed as well and hence,
as a result we need to pay for each step of the program that gets activated including the computations and the memory storage.
This is paid in ethers and taken from the sender's wallet.
This transaction fee gets collected by every miner node within the network. Basically every node within the network runs the EVM to execute the same instructions.
So the miner nodes execute and verfiy the transaction and once verified, the state of the accounts get updated in the ethereum blockchain. Miners are rewarded for every successful mining.
And this is how, a transaction gets completed. 

Now, we will be getting into a bit more detail on how is the piece of code not running forever and hence, clogging the network. 
That's the beauty of the fuel i.e gas which is the execution fee that the sender has to pay for running a program on the EVM. Basically, every contract has to follow
a gas limit depending on the amount of gas that can be consumed. This gas limit and the price are specified when the transaction is very first initiated.
In case the program requires more gas than the specified amount, the program gets reverted and also the gas is lost. So, the limit has to be set prooperly
and proper instructions should be used to avoid high cost.

There is another concept behind Ethereum blockchain where one can create Dapps(Decentralised Applications), 
which are a set of smart contracts operating on the data in those contracts.
These are basically applications(Eg. web/mobile) at the front end and they have blockchain in the backend along with other database. 
So, a Dapp has to fulfil the following conditions:
1. opensource
2. decentralised
3. tokens fueling for itself
4. generates token
5. inbuilt consensus mechanism

These Dapps actually enable a direct interaction between the users and providers. 
And also comprised of different organisations working together to create one. They are called DAO( Decentralised Autonomous Organisations)
DAOs can be compared to a normal company where there is a third party but rules are not enforced digitally. 
But DAOs tend to make their decisions electronically through the codes written in smart contract or through members' votes.
So, basically people add funds to the DAO and are given tokens to represent their percentage of assets. When DAO starts to operate, members
propose on how to spend the funds and based on the votes, the proposal status is decided. 

Next, after understanding some basics, we are going to look into the security aspects for the Smart Contracts. 
Being immutable, it is very important to take care of the Contract as once it is deployed, one can never undo it. 
You may need to create fork out of it in that situation.
So, we will look into different kinds of vulnerabilities, a contract can be attacked by. 

1. Reentrancy Attack
   As the name suggests, this attack is possible when a malicious user or code is able to reenter the function continuously until and unless 
   either the ether is over or the gas is trained out. 




PS: I have taken help from different videos, links to understand the topic completely and write. The references are given below:
1. *[Edureka](https://www.youtube.com/watch?v=58yeu6HtzpM)
2. https://conference.hitb.org/hitbsecconf2018ams/materials/D1T2%20-%20Bernhard%20Mueller%20-%20Smashing%20Ethereum%20Smart%20Contracts%20for%20Fun%20and%20ACTUAL%20Profit.pdf
3. https://hackernoon.com/hackpedia-16-solidity-hacks-vulnerabilities-their-fixes-and-real-world-examples-f3210eba5148
4. https://hackernoon.com/ethereum-for-dummies-af5aeacb13d4
5. https://hackernoon.com/getting-deep-into-ethereum-how-data-is-stored-in-ethereum-e3f669d96033
6. https://arvanaghi.com/blog/reversing-ethereum-smart-contracts/
7. http://patrickventuzelo.com/wp-content/uploads/2018/10/Toorcon_2018_reversing_ETH_smart_contract.pdf
