### Introduction to DeFi
Bitcoin - Self custody of Money 
Ethereum - Programmable Money - allows a new way 

DeFi - financial services built on top of smart contract platform 

**3 Steps to Define DeFi**
1. Custody & Settlment / Transcation execution and Protocol governenance 
	- Do users have full control of their financial assements? Yes
	- Can someone censor a transaction? No
	- Can somone censor the protocol execution? No, fullly Defi. Yes, goverened defi 


**Benefits of DeFi**
1. Effecient - removes rent-seeking / fee taking middlemen
2. Anyone can access it 
3. Public Verfiiability - smart contract code can be verified 
4. Can't be censored 

### DeFi Stack
![[Screenshot 2021-12-07 at 11.52.54.png]]

Protocol Layer are financial services are executed and executed as smart contracts
Application Layer - Where user interact with the layers
Aggregation Layer - Ex Wallet that allows users to use different DeFi Applications 

![[Screenshot 2021-12-07 at 12.31.57.png]]
Bridge - connecting two different blockchains 
Oracle - helps provide information that is off-chain onto the blockchain.Centralizing exchanges or even the weather
Keeper - a bot that sends trigger events to the Blockchain. Example - Liquidation 

**Connecting the CeFi world with the DeFi World**
![[Screenshot 2021-12-07 at 12.30.10.png]]


**DeFi Landscape**
![[Screenshot 2021-12-07 at 12.43.02.png]]

## DeFi Building Blocks and Services 

### Asset tokenization
The process of adding new assets to a blockchain 
Token = blockchain reprsentation of the assest 
Types of Tokens
	- Governance Token - holder can vote on the protcol
	- Security Token - token represent physical items like real estate
	-NFT's - token represent assets like music, art
	- Stable Coin - price is tagged to other assests, can be created by:
		- Offchain - tied to fiat, precious metal 
		- Onchain - tied to other crypto assets
		- Algorithmitc -purely in code 
		
### Exchanges
A marketplace for users to trade different assets 
 - Centralized Exchange - Custodial of assets / Non-transparency - Coinbase
	 - Managed with an order book 
 - Decentralized exchanges - Non-custdial and transperent
	 - Different protocol/methods to  match buyers and sellers ¢
![[Screenshot 2021-12-07 at 19.10.13.png]]
	- Biggest Decentrralized Exchange is Uniswap 

### Decentralized Lending 
- DeFi Lending - over collateralization - creating new tokens using collateral 
	- Types - Collateralized Debate Markets - Compound, Aave 
						- Borrowers put up collateral then borrow funds from lenders of other crypto assest - Example Compund and Aave 

### Flash Loans 
Blockchains enable atomic transactions 
	- Atomic Transactions - Execute entirely in sequence or fail collectively 

Sequence 
 1. Lending provides loans w/o collateral in one transaction
 2. Go-Wild Loan (borrower can do whatever they want like arbirtrage)
 3. Loan is paid back + interest at end of transaction
 4. If borrower cannot repay the loan + interest, transaction will fail so the original state is restored as if the borrower as never borrowed the loan 

Anyone can borrow without any upfront cost 


### Other Building Blocks
Deritives - assets whos values are derived from other underlying assets 
	- Asset-based derivateives - Synthetix, Mirror
	- Event-based derivaties - Augur 
	
	
### Risks in DeFi
### [[Security]]
- Network Attaks - DoS Attacks
- Consensus Attacks - Dobule Spending 
- Smart Contract Code Bugs - Authroization 
- DeFi Protocoal Attacks - Excessive Arbitrage / Oracle Attacks
- Bridge Attacks 
- Governance Attacks 

**2 Different Types of Issues**
Techical Structure - Issues from underlying technical structure of the blockchain. Hackers can take funds in risk-free

Economic Incentive - Hackers exploit the incentive structure of the protocal to reap personal profits 

**Example of an DeFi Attack**
Front Running Attack
	1. Attacker observes a transaction on a blockchain
	2. Attacker creates a transcation pasys a higher gas free to take over a profitable trade
	3. Original transcation is depriotirized and the attacker gets the profit of the transaction 
	
Miner Extractable Value (MEV) - Miner performs attack or helps faciliate the certain attacks so they can also capture value 

### Systemic Risks / Dependecies  
- Siginificant price declines - Crypto Assets being used as collateral can cause ripple effects like liquidation and de-leveraging. 
	- In CeFi - Circuit Breakers in stock markets where loss is too large. Blockchain currently does not have this 

## Open Research Challenges
- Scalability - Transaction Value - transactions are too expensive to executter
- Universal accessibility - how to allow more poeple to use DeFi application 
- Privacy  
- Security - how can design more secure systems 
	- Oracle / Program 
- Incentive Design - ensure players in the ecosystem are incentived to behave properly 
- Miner Extractable Value - Better applications that can reduce this stealing 
- Governance - better mechanisms are decentralized and operating properly in a secure manner 