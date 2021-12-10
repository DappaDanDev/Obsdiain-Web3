## [[Hardhat]]
	**Hardhat** - Used for buliding a local blockchain for testing 

### Commands 

```bash
npx hardhat
```
Setup a sample projecy

```bash
 npx hardhat compile
```
Confirms everything is working 

```bash
npx hardhat test
```
runs the 

```bash
npx hardhat node

```
Start a local blockchain network 


````bash
npx hardhat run scripts/run.js
````
Runs script in the file structure 


```bash 
npx hardhat run scripts/deploy.js --network rinkeby
```
Deploying a smart contract to Rinkeby for testing 