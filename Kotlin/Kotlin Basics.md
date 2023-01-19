## Kotlin Basics ##

- **Why choose Kotlin?**
	- Modern language to help developers write code efficiently and with as few errors as possible
	- Robust code - i.e Kotlin catches null-pointer exceptions. Kotlin distinguishes between nullable and non-nullable data types, which catches more errors at compile type.
	- Type inference
	- Lambdas, coroutines, and properties (write lesser code and fewer bugs)
	- Used to build android apps
	- Interoperable with Java
		- Kotlin code compiles so you can use java and kotlin side-by-side. Utilizes java libraries
		- IntelliJ and Android Studio has tools to migrate existing java code to Kotlin code
- **Casting**
	- Assigning a value of a data type to another type
	- **![](https://lh5.googleusercontent.com/i0aYkGsyRE7GuTBtdgzTL_3fyPvohKwrpcK1MyYzH513C3wKIQaf3pdQGwthuuDQejVxAlRyQBVbAcVVjxYb2ChBR-vdTJc5o9gyIrN8uCyDpZVx--80H-kTUSmfvxb_RjNlgWL7yL9NXlAM0Jkgba_LAoVZ2zBcDaYsIz62Zp1UkGOAFJs7aLauxEg8LQ)**
- **Initializing a variable**
	- Val x: Int = 5
	- Val x: Int = variable.toByte()
- **What does Android Studio have?**
	- Virtual Device, or emulator, that simulates an android device
		- Has its own system requirements
		- Uses up a lot of disk space
- **Operators and Types**
	- Mutable (Changeable)
		- Values you can change using the keyword "var"
	- Immutable (Unchangeable)
		- Values you cant change after being initialized using “val”
	- String interpolation
		- String template inserts a variable or expression into a string (using $)
		- $ specifies the part of the string that will be a variable or expression
		- Use curly braces to define an expression
		- **![](https://lh6.googleusercontent.com/vNvM0KagAf2-q4Q01F9KWR3jf4-2SDyhQbk5z5FXoJdKIr2ZQAk5fywjfzTo0ejK02K4Wc6RVnpMAJamJyJxqOL3DqvmZ5uM8KV9ImkbaYbHbE2sG8kPZt7gZI5K9fZjJS4EhMX4KnbKvnYfXtRdsiy7A6bs5_5jJs4d1YDrhB9tlkUYos6kHga1ZRCwYw)**
	- When statement
		- Similar to a switch statement in java
		- **![](https://lh6.googleusercontent.com/VaTUwQ1byO5os9O_K4hyjh3n_FGNLyahnYGCdQuY7hNLfueCF6HBOqhnKuhEFXOca7RLgytYbzLzkFri-_flxpZOsk_rCgZ4gSc0Q74RqjdeG1Si5xemhuZAY2wzzH0aRvqxyFKJmUs3JP08_MxGQLPXEHnntTv05u2ZBNmLeCvs8fK_Q13nwRvF83k2jA)**
	- Nullability 
		- In Kotlin, variables can not be null by default
		- I.E: var rocks: Int = null will produce an error 
		- To allow variables that holds a null value, use the ? operator
			- var marbles: Int? = null will compile
		- ?: (elvis operator)
			- If the object reference is not null, it is returned. Otherwise, the value to the right of the elvis operator is returned (which may be null). Can throw an exception if null is returned
		- Example: fishFoodTreats = fishFoodTreats?.dec()
			- shorthand for "if fishFoodTreats is not null, decrement and use it"
			- Can chain null tests with ?: operator
				- Example: fishFoodTreats = fishFoodTreats?.dec() ?: 0
					- shorthand for "if fishFoodTreats is not null, decrement and use it. otherwise, use the value after the ?: which is 0". if fishFoodTreats is null, evaluation is stopped and dec() method is not called, so use the value after the elvis operator (in this case, 0)
			- !! operator converts any value to a non-null type and throws an exception if the value is null
- **Arrays, Lists and Loops**
	- listOf declares a list
	- example:
This text is indented.

  
  
Source: [How to Indent in HTML? (Simple Guide)](https://www.dopinger.com/blog/how-to-indent-in-html-simple-guide) (https://www.dopinger.com/blog/how-to-indent-in-html-simple-guide)

`for
`
