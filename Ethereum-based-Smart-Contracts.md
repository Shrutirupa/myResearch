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

There is an online IDE i.e. [Remix](https://remix.ethereum.org) for writing smart contracts. This online IDE can compile the contracts automatically as it has an integrating, debugging and testing environment.

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
   As the name suggests, this attack is possible when a malicious user or code is able to reenter the function continuously until and      unless either the ether is over or the gas is trained out. Here another terminology comes into picture which is a fallback function.    A fallback function is triggered when the function signature does not match any of the available functions in a Solidity Contract. 
   So when a victim contract sends ether to an unknown address. This unknown address can be a malicious one. So, the attacker can       	construct a contract at an external address which has a malicious code in the fallback function, defined above. So, if the victim 		sends ethers to the malicious address, the malicoius code gets executed, the code is present in the fallback function. and hence the function is executed on victim contract. For example, call is a function which is used to invoke a function of other contract. But there is a catch. call can trigger a code execution without a gas limit unless it is set manually. This makes it vulnerable to reentrancy attack.

2. Arithmetic Overflow/Underflow
	The vulnerability deals with how an integer vatriable can be manipulated if not used properly. Basically, every integer variable has a range of numbers that it represents such as uint8 can hold numbers upto the range 2^8 = 256 which defines it from 0-255. So if we subtract 1 from uint8  where the value = 0; 
	then value = 0-1 
						 = -1 
						 = 255, which is a large number. 

The above is an example of integer underflow.
 But adding 1 to the value = 256, then
 value = 256 + 1
 			 = 257 
			 = 1


3. Function Visibilities
   There are specifiers that define the visibility of the function. These specifiers define how a function should be called. Basically if a function is specified with the public keyword, it can be called by any external contract. There are four specifies: 
   	1. pubilc
   	2. external
   	3. private
   	4. internal

If the visibility of the function is not defined explicitly, it is set to public as default. And this can actually allow a malicious unknown contract to call the victim contract. 
   
4. Short address
   Parameters being sent to a smart contract can be manpulated as these parameters get encoded according to ABI specification. So, in that case if an attacker is withdrawing some ether from the victim contract to it's account whose address may be of 19 bytes instead of 20, then 00 will be padded to the end of the encoding, and hence may be manupulated. 
   The encoding follows the following way:
   function name + address + encoded value + (any padding if required)
   if x amount of ether is to be withdrawn from the victim's address, and the above scenario is followed, the entired padding would be like  function name + address + x + 00
   So, it will result into withdrawal of x times 100 ethers from the victim's account.
5. Race condition
   Miners can do take advantage of their power into looking into the secret answers which are not supposed to be seen but found out byt solving a mathematical computation, as the code demands. if there is a reward which would be given to the nodes within the network to solve a mathematical problem, and one of the nodes, solve the problem, the malicious miner may see the answer before verifying and it may directly update it's answer and get it verified fast.This comes under race condition which should be taken care of.
6. Unchecked call return values
   EVM has a resource called callstack which is used by the contrat code during it's execution. So there can be a possibility of a previously existing contract code consuming the call stack and hence a function may not get executed. send() function can be a dangerous one in this scenario where the function may get reverted as it only returns boolean values but the state of the variable still get changed. so instead of send(), transfer() function should be used.
7. tx.origin

8. block.timestamp






PS: I have taken help from different videos, links to understand the topic completely and write. The references are given below:
1. [Edureka](https://www.youtube.com/watch?v=58yeu6HtzpM)
2. https://conference.hitb.org/hitbsecconf2018ams/materials/D1T2%20-%20Bernhard%20Mueller%20-%20Smashing%20Ethereum%20Smart%20Contracts%20for%20Fun%20and%20ACTUAL%20Profit.pdf
3. https://hackernoon.com/hackpedia-16-solidity-hacks-vulnerabilities-their-fixes-and-real-world-examples-f3210eba5148
4. https://hackernoon.com/ethereum-for-dummies-af5aeacb13d4
5. https://hackernoon.com/getting-deep-into-ethereum-how-data-is-stored-in-ethereum-e3f669d96033
6. https://arvanaghi.com/blog/reversing-ethereum-smart-contracts/
7. http://patrickventuzelo.com/wp-content/uploads/2018/10/Toorcon_2018_reversing_ETH_smart_contract.pdf
