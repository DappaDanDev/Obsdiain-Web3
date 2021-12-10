# Lecture 2 - Intro to Blockchain 
**Core** - A blockchain provides a coordination between many parties where there is no single trusted party. No need for a blockchain is there is a trusted party 


## Layers to Blockchain 
### Consensus Layer
Used to for the parties to agree on the certain stage of the chain 

**Append Only Data Structure**
Once something is written to it, that cannot be removed 
	1. Persistence - cannot be removed, achieved by replication
	2. Conensus - all honest participtants agree on the same data. 
	3. Liveness - new transactions can always be added
	4. Open - anyone can add data, (there is a specturm to the openess )
	
#### How are blocks -> Chain (Conensus)
1. Users create a transactions
2. Transactions are sent to the network (collection of miners)
3. Leader Election mechanism -> One miner is elected
4. Leader takes the current pending trancations (mempool) and posts the blocks onto the blockchain
5. Leader is rewareded for adding the blocks
6. All other miners verify if the new block is valid, if not it is thrown away and not added to the chain 

### Compute Layer (blockchain computer)
Where computations are performed once consensus is reached 

Programs are maniuplating state, all maniuplations are written to the Blockchain so anyone can inspect and verify 

Transparent - All code is completely public, no single trusted 3rd part 

The Dapp - executed by parties who create new blocks to the chain every time a new block is written. Can be verified by the public as well 

### Application Layer 
Dapps and Smart Contracts - programs that run on the virutal machine 

### User Facing Tools 
How the public interacts with the blockchain  / end users 
Servers that takes command form users and reads/writes to the  blockchain 

#### How are blocks -> Chain (Conensus)
1. Users create a transactions
2. Transactions are sent to the network (collection of miners)
3. Leader Election mechanism -> One miner is elected
4. Leader takes the current pending trancations (mempool) and posts the blocks onto the blockchain
5. Leader is rewareded for adding the blocks
6. All other miners verify if the new block is valid, if not it is thrown away and not added to the chain 

## Cryptographic Primitives 
### Hash Functions 
Hash Function - a function maps a large domain into a small range . Hashing megabytes of data to a hash value of 32 bytes 

**Collision Resistance**
Collision - A pair of disticnt inputs that H(x) = H(y)
Since the domain is smaller than the range, many inputs will collide with eachother 
Collission Resistance if is hard to find a single collision - Ex SHA256

**Commiting to Data**
User has large amount of data - publishes the hash
Mapping the hash to the message - binding commitment 

**Committing to a list of transcations** 
1. User as a list of messgages = S 
2. User publishes a short binding commitment - S -> h (32 bytes)
3. User sends proof that message at a certain location is correct
4. Reciver verifiys the proof using a verification algorithm 

**Merkle Tree**
Committing a list of messages (m1,m2,m3) -> S
Want to later prove a message at a ceratin location 
Merkle Tree commitment -> turns into a 32 byte (h) 
	- Hashing of hash at each level until a final hash is made 
![[Screenshot 2021-12-08 at 21.19.56.png]]

To make a proof of a certain location, you need to consider the path from the message to the final hash 
![[Screenshot 2021-12-08 at 21.23.59.png]]

**Why is this useful?**
Writing a block of transactions S - only the commitment of (S) to the chain in order to keep the chain small. Then anyone can proof that any transaction is in the block by providing a Merkel Proof. 

A blockchain is just a merkel root commtiment - the tree includes all ot the transactions. If one needs to prove a transaction is on the chain, then it is just provide a Merkel proof 
The next block also includes a hash of the previous block header. 

![[Screenshot 2021-12-08 at 21.34.31.png]]


### Digital Signatures 
Signature depends on the content of the document 
A secret signing key + the data of the document are fed into a signing algorithm and that produces a signature 