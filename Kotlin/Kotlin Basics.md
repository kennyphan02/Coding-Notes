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
	```Kotlin
	val school = listOf("Mackerel", "trout", "halibut")
	```
	- arrayOf declares an array and its fixed
	```Kotlin
	val school = arrayOf("a","b","c")
	println(java.util.Arrays.toString(school))
	```
	- can mix types using Arrays
	- Can initalize arrays with code instead of initalizing them to 0
	```Kotlin
	val array = Array (5) {it * 2}
	println(java.util.Arrays.toString(array)) # returns [0,2,4,6,8]
	```
	- **![](https://lh4.googleusercontent.com/kVAMZaVbDZbpdtC1NrIDBC30pzfMBxcwNAgtAKS3mMxSMlVVWI3vWkionIHUESg7PJbEbwrQiIO4I-PiNOOFzLbphg_piWECZ1RZGylPcOEGGgpsFnw7DA2iVuXqVxh3k1FPEYjiuvQeOMZ__ZP-dbL5wIZkMspyYytdE4mgidcw1RfTAXeJrCBaLuxr_A)**
- **Functions**
	- Fun main()
		- Fun - stands for function in kotlin. a **function** is a **section of a program that performs a specific task**
		- Main - name of the function
	- Repeat Statement
		- repeat(int value) {} - repeating over the same code inside the brackets int times
	- When a function does not have a return statement, the function returns Unit (formally kotlin.Unit)
	```Kotlin
	// Will assign kotlin.unit
	val isUnit = println("This is an expression")
	println(isUnit)
	// first println() prints the string this is an expression. the second println() prints the value of the first println() statement, that is, kotlin.Unit
	```
	- Loops do not have values. Trying to assign a loop a value causes the compiler to give an error
	- **![](https://lh6.googleusercontent.com/qywmk5w_jVMHbWq6AKsqQWYZ1XtpcGi3aYJA0XrVpOtYfAUd3M8STT3BdaCiCf1hTiksTWqnQckF6oM3uwRGR9l3buXsvI9lmMc3KqrSXfNgVGTKYPVCE51wY5ELcIeV4-sgm8Rlmno45thdjwR5Oji3sMqRVKX2eCENlwxcUUuSiiNNLHOhg5o76JGmpQ)**



