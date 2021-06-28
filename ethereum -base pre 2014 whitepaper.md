# Ethereum whitepaper
### Introduction:

Ethereum is meant to provide a terminology as a tool of distributed consensus, and attention is shifting towards smart contracts, DAOs, NFTs or smart properties, which are handled via systems such as those generated by Ethereum.

### Introduction to Bitcoin and overview:

There have been previous tries towards creating cryptographic proofs for transactions without involving external parties such as banks, but it was first championed by satoshi for bitcoin.
It was a breakthrough because it solved two problems. First, it provided a simple and effective consensus algorithm to allow nodes to agree on a set of canonical updates to the state of bitcoin ledger. Secondly, it provides a mechanism for free entry into the chain, to decide influence to the consensus while preventing sybil attacks. It does this by introducing a barrier wrt computing power that a node can bring.

### Bitcoin as a state transition system:

From technical point of view, the ledger of bitcoin can be thought of as a state transition system. A state contains the ownership status of all existing bitcoins while state transition function takes a state and transaction to output a new state. Thus, a state is the balance sheet, and a transaction is the conversion of money from one state to another. The state in bitcoin is collection of all coins and its respective owners which is the total amount ever mined and not spent.

### Bitcoin mining:

It is easier to create a centralized trustworthy system, but in the case of bitcoin, the goal is to build a decentralized trustworthy system such as to combine state transition system with a consensus system to ensure everyone agrees in the order of transactions.
In bitcoin, the nodes attempt to create new blocks, which are essentially packages of transactions. The nodes effectively produce a block every 10 mins.
The algo to check validity of a block is:
1. Check previous block is referenced by block and is valid.
2. Check timestamp greater than previous block
3. Check POW is valid.
4. Create the follow-up state for the transaction block

Each transaction in the block must provide a valid state transition method from a canonical state to a new state. [State is only an abstraction to validate a block from the genesis of the chain]

#### What happens when the blockchain is attacked:

Since, the attackers can not attack other parts of the bitcoin system, due to the strong cryptographic hash, the major place where they can attack is the order of transactions.
This is where 51% attack happens. If the user wants to make a change to a specific hashblock, he will need 51% control of the mining ecosystem.

### Where Merkel trees come into picture?

Scalability of bitcoin system is ensured due to the multi-level data structure in bitcoin merkel trees. There is a primary due to the fact that as hashes move forward in time, the hashes are validated by the network. If the attacker tries to change a node of previous time, it affects every child node which is continuing the transaction which fails his block addition.