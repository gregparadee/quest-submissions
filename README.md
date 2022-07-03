# Quest Submmissions

## Chapter 1

### Day 1

1. Explain what the Blockchain is in your own words. 

A: The Blockchain is a large, public/open, distributed database or ledger that stores information. Databases typically store their information in tables, where a Blockchain stores its informaton in Blocks. Blocks have storage limitations and once full it is considered completed and becomes part of the timeline. A new Block is then created and new data is stored there until that block is full and then becomes part of the timeline. The blocks are linked together once a new one is created hence the term "blockchain".

2. Explain what a Smart Contract is. 

A: Smart contracts are just programs designed to interact with a Blockchain. They typically contrain scripts and functions that are called by users. They are usually used by other languages like Javascript/Python to create a DApp and make the interactions easy for users. 

3. Explain the difference between a script and a transaction.

A: A script, reads data from a Blockchain and does not have any cost associated to it. A transaction, interacts with a Blockchain and changes data. Transactions typically have a cost associated with them. 

### Day 2

1. What are the 5 Cadence Programming Language Pillars?

A: Safety and Security, Clarity, Approachability, Developer Experience, Resource Oriented Programming

2. In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful?

A: Safety and Security - Protects, assuming no bad intent, the end-user and developer while encouraging mass adoption. Safety and Security are always at the top of peoples minds, especially when dealing with money or goods. Clarity - Allows someone with a little but of programming knowledge to understand what they are doing and also makes it easy for new developers to learn the language, increasing adoption. Approachability - Makes it easy to learn for the first time or switch over too if already a developer. Code should be easy, not hard. Developer Experience - Making things easy to understand and develop keeps Developers happy and motivated. Poor error handling can be a turn-off to many developers. 


## Chapter 2

### Day 1

1. Deploy a contract to account 0x03 called "JacobTucker". Inside that contract, declare a constant variable named is, and make it have type String. Initialize it to "the best" when your contract gets deployed.
A:

```cadence
pub contract JacobTucker {

    pub let is: String

    init() {
        self.is = "the best"
    }
}
```
2. Check that your variable is actually equals "the best" by executing a script to read that variable. Include a screenshot of the output.
A:

```cadence
import JacobTucker from 0x03

pub fun main(): String {
    return JacobTucker.is
}
```
![Screen Shot 2022-07-02 at 8 49 14 PM](https://user-images.githubusercontent.com/223535/177020316-52f3f543-f667-413e-b855-9de36d0c31fe.png)

### Day 2

1. Explain why we wouldn't call changeGreeting in a script.

A: Scripts are used to view information on the Blockchain. changeGreeting is a function that update information and therefore requires a transaction.

2. What does the AuthAccount mean in the prepare phase of the transaction?

A: AuthAccount signifies the person who is executing and paying for the transaction. It also allows transaction to access information in your account. 

3. What is the difference between the prepare phase and the execute phase in the transaction?

A: The prepare phase is primarily to access information in your account and "prepare" the transaction. The execute phase can't do this. The execute phase actually performs the instructions (e.g, execute a function).

4. This is the hardest quest so far, so if it takes you some time, do not worry! I can help you in the Discord if you have questions.

A: 

**Contract**
```cadence
pub contract HelloWorld {

    pub var greeting: String

    pub var myNumber: Int


    pub fun changeGreeting(newGreeting: String) {
    self.greeting = newGreeting
    }

    pub fun updateMyNumber(newNumber: Int) {
    self.myNumber = newNumber
    }

    init() {
        self.greeting = "Hello, World!"
        self.myNumber = 0
    }
}
```

**Script**
```cadence
import HelloWorld from 0x01

pub fun main(): Int {
    return HelloWorld.myNumber
}
```

**Transaction**
```cadence
import HelloWorld from 0x01

transaction (myNewNumber: Int) {

  prepare(signer: AuthAccount) {}

  execute {
    HelloWorld.updateMyNumber(newNumber: myNewNumber)
  
  }

 }
 ```
 ![Screen Shot 2022-07-02 at 9 56 45 PM](https://user-images.githubusercontent.com/223535/177021480-0fd246dd-a643-4c18-929e-77477e4514a9.png)

 

# Chapter 3

# Chapter 4

# Chapter 5
