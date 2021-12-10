 ### Chapter 1 
```rust

fn main() { println!("Hello, world!"); }

```

- println! calls a Rust Macro, println would be calling a function 
- Before running a rust program, must be complied using rustc command
	```bash
	rustc main.rs
	```

### [[Functions]]
	- Defined by fn
	- main is always the first code that is executed in a Rust Program 

Indent with four lines and not a tab 


### [[Cargo]]
	- Cargo is rust build system and pacakge manager 

```bash
$ cargo new hello_cargo
$ cd hello_cargo
```

Cargo TOML - (_Tom’s Obvious, Minimal Language_)
```bash
cargo build
```
Create executable file in _target/debug/hello_cargo_
```bash
./target/debug/hello_cargo
Hello, world!
```

Also can use cargo to complpie the code and run the executable 

.cargo-lock - keeps a list of the versions of dependencis in your project 

```bash
cargo check 
```
Checks code to see if it complis but doens't produce executable 

```bash
cargo build --release 
```
Used when ready to realeas project, built with optimizations to run the code faster and the executable is in target/release 


```bash 
$ git clone example.org/someproject $ cd someproject $ cargo build
```
Running code from git 


### [[Guessing Game]]
```rust 

use std::io;

```
Brings in the io library in order to get inpute from the user 


```rust 
let mut guess = String::new();
````
Storing the value of the user input 


### Defining [[Variables]]

```rust 

let apples = 5; // immuytable
let mut bannase = 5; // mutable 
```
By default all variables are immutable, variables can be converted to mutable using the `mut` keyword.  

```rust 
let mut guess = String::new();
```
new function creates an empty string 

```rust
io::stdin()

.read_line(&mut guess);
``` 
Calling the stdin function from the io module 

If didn't call use std::io can also write std::io::stdin - returns an instance of [`std::io::Stdin`](https://doc.rust-lang.org/std/io/struct.Stdin.html)

```rust 
.read_line(&mut guess);
````
.read_line takes what the user inputes. 
& - indicates that the argument is a reference - all other parts of the code to access it 
.read_line retures an io::Result that either returns a value of Ok or Errot
	- Enums - returs fixed set of vlaues 

```rust
        .expect("Failed to read line");
```
Calling expect method. if the result is an error, expect will crash the program and display an error message 
Without the expect method, you will get a warning 

### Printing Values with Placeholders 
```rust
println!("You guessed: {}", guess);
```
Curly Brackets = placeholder for value 

Can be used for multiple brackets 

```rust 
let x = 5:
let y = 10;

println!("x = {} and y= {}", x, y);
```

**Crate** - A collection of Rust source files 

[dependencies]
rand = "0.8.3"

Semantic versioning = anything from 0.8.3 to 0.9.0. ANything higher is not using the same API 


https://crates.io/ - Where people post open source projects 

```rust 
cargo update
```
ignores Cargo.lock file but folls Cargo.toml file to see what the lasted versions in crate are that work 

### Generating a [[Random Number]]
```rust 
use rand::Rng;
```
Rng is a trait of rand that must be in scope to create a Random Number Generator 

```rust
rand::thread_rng().gen_range(1..101);
```
thread_rng - The particular random number gneerator that is local to the current thread and seeded by the operating system. 

gen_range - takes a range expression as an argument, inclusive of lower bound/exclusive of the upper bound 1-99 

### Comparing the [[Random Number]]
```rust
use std::cmp::Ordering;
```
Ordering is in an enum in the standard library with variants of Less, Greater and Equal 

```rust 
match guess.cmp(&secret_number) {

Ordering::Less => println!("Too small!"),

Ordering::Greater => println!("Too Big!"),

Ordering::Equal => println!("You win!"),

}
````
cmp is method used for comparing 
match= expression made up of arms - arms are what the code should do given a certain condition 


### [[Shadowing]]
```rust 
let mut guess = String::new();

  

io::stdin()

.read_line(&mut guess)

.expect("Failed to read line");

let guess: u32 = guess.trim().parse().expect("Pleast type a number!");
```

Rust allows shadowing of previous variables  - can be used to converty a value from one type to another type. 

.trim - eleminates whitspace
.parse - parses a sting into some kind of number 
u32 - unsigned 32 bit integer 

### Looping

```rust 
loop {

println!("Please input your guess.");

  

let mut guess = String::new();

  

io::stdin()

.read_line(&mut guess)

.expect("Failed to read line");

let guess: u32 = guess.trim().parse().expect("Pleast type a number!");

println!("You guessed: {}", guess);

  

match guess.cmp(&secret_number) {

Ordering::Less => println!("Too small!"),

Ordering::Greater => println!("Too Big!"),

Ordering::Equal => println!("You win!"),

}
```

### Ending the Game on Correct Guess

```rust 
match guess.cmp(&secret_number) {

Ordering::Less => println!("Too small!"),

Ordering::Greater => println!("Too Big!"),

Ordering::Equal => {

println!("You win!");

break;

}
```

### Handling Invalid Input 
```rust
let guess: u32 = match guess.trim().parse() {

Ok(num) => num,

Err(_) => continue,

};
```
parse returns an enum - Ok and Err 
conitune - tells the program to contiue with the loop if the guess is not a nmbumbers 