
## [[Learning Resources]]

Layer 1: Base Layer Blockchain Implementation 
Ex: Bitcoin / Etherum 

Layer 2: Any application build on Layer 1. Ex: Chainlink
    - Rollups - Rollup transactions to the Layer 1 
             - Derive security from the base layer and then bulk send the transactions onto layer 1 
             https://ethereum.org/en/developers/docs/scaling/layer-2-rollups/
            
## Lesson 1 - Simple Storage - Remix 

### [[Setup]]

Always define the version of Solidty to be used: 
```sol
pragma solidity >=0.6.0 <0.9.0;
```

Changing Versions is important 

**Contract** is like a class in JS 

```sol
contract SimpleStorgae {
    
    
}
```

### [[Data Types]]
uint - unsigned integer (not positive or negative)
        -uint256 - 256 bits 
int - regulat integer 
bool = boolean 
string = string 

https://docs.soliditylang.org/en/v0.8.7/types.html

```sol
    uint256 favoriteNumber = 5; 
    bool favoriteBool = false; 
    string favoriteString = "String"; 
    int256 favoriteInt = -5;
    address favoriteAddress = 0x24bF6580ED276b6ff33269DD361eE00FE3a2c912;
    bytes32 favortieBytes = "cat"; 
```

Variables are initialized as internal if not declared as public 

**Functions**
```sol
 function store(uint256 _favroriteNumber) public {
        favoriteNumber = _favroriteNumber;
    }

```

Different Types of Contracts - https://docs.soliditylang.org/en/v0.8.7/contracts.html 


View functions - just view some state off the blockchain, find some value. Inlcudes Public variables as well 

```sol
    function retrieve() public view returns(uint256){
        return favoriteNumber;
    }
```

Pure functions - purely do some type of math 
```sol
  function add(uint256 favoriteNumber) public pure {
        favoriteNumber + favoriteNumber;
    }
```


### [[Structs]]

A way to define new types in Solidity 
```sol
   struct People {
        uint256 favoriteNumber; 
        string name; 
    }
    
People public person = People({favoriteNumber: 2, name:"Korey"});

```
Storing two variables into a struct 


### [[Array]]
Stores a list of an object or type 

```sol
 People [] public people;
```

Creating a people array. Dynamic Array which can change size 

```sol
    People1[1] public people1; //Fixed array 

```

Fixed Arrays - Only allows one object in the array 

 ```sol
 require( //require is a keyword to see if some condition is true

prizeAmount <= address(this).balance,

"Trying to withdraw more money than the contract has."

);
```

Require is a to check if is some condition is true 
In this case, it also requires that the prizeAmout is less than the balance of the contract 

```sol
constructor() payable {

console.log("Yo yo, I am a contract and I am smart");

}
```
Adding payable ot the constructor to allow the contract to pay people 


```js 
const waveContract = await waveContractFactory.deploy({

value: hre.ethers.utils.parseEther('0.001'), //funding the contract

});
```
Deploying a funded contract 

### Generating a [[Random Number]]
```sol
//generates a new seed for the next user that sends wave

seed = (block.difficulty + block.timestamp + seed) % 100; //combining block difficutily and timestamp to make a random number

console.log("Random # generated: %d", seed);

  

//Give a 50% chance that the user wins the prize

if (seed <= 50 ) {

console.log("%s won!", msg.sender);

```

### Creating a [[Cooldown]] to Prevent Spammers 
```sol 

//Cooldown feature to prevent spammers - mapping the address of the last user waved at us to a number

mapping(address => uint256) public lastWavedAt;


//verify 15 minutes have passed since the current timestamp

require (

lastWavedAt[msg.sender] + 15 minutes < block.timestamp,

"Wait 15m"

);


```

### [[Emit]]


```solidity
emit NewWave(msg.sender, block.timestamp, _message);
```
events are messages our smart contracts throw out that we can capture on our client in real-time.