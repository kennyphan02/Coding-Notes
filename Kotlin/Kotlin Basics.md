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
		- When "when" statement doesn't have an expression, it acts as multiple if/else statements
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
	- **Compact functions** - aka single-expression fcuntions. 
		- Makes code more compact and concise. (Lesser lines)
		```Kotlin
		fun isPositive(num : Int){
			num > 0 
		}
		// can be translated to
		fun isPositive(num : Int) = num > 0
		```

	- When creating functions, you can create a **default value** for a parameter
		- If no default value is passed, the function must be called with the corresponding argument
		- Default values doesn't have to be a value. it could be another function
		- Example:
	```Kotlin
	fun swim(speed: String = "fast") {
		println(swimming $speed)
	}
	// If the function swim() is called, it will print "fast" as the default parameter is "fast". if swim("slow") is called, it will print "swimming slow"
	```
	- Here is a program that demonstrates the usage of compact functions, setting arguments to default values, and using a when condition
	```Kotlin
	//  Program that utilizes a when condition and setting default values for arguments in a function. Inside the when statement utilizes compact functions
	// If the day is not sunday, or the temperature is > 30, or the dirty level is greater than 20, return true 
	fun main(args: Array<String>) {
	    // test case when boolean expression is evaluated to false
	    var temp: Boolean = shouldChangeWater("Monday",12,13)
	    if(temp) println("Change the water!") else println("Don't change the water!")
	    
	    // test case when boolean expression is evaluated to true
	    var temp2: Boolean = shouldChangeWater("Sunday",12,13)
	    if(temp2) println("Change the water!") else println("Don't change the water!")
	    println("")
	    feedTheFish()
    }
    
    fun feedTheFish() {
	    val day = randomDay()
	    val food = fishFood(day)
	    println ("Today is $day and the fish eat $food")
	    println("Change water: ${shouldChangeWater(day)}");
	}
	
	fun randomDay() : String {
	    val week = arrayOf ("Monday", "Tuesday", "Wednesday", "Thursday",
	        "Friday", "Saturday", "Sunday")
	    return week[Random().nextInt(week.size)]
	}
	
	fun fishFood(day: String) : String {
	    return when (day) {
	        "Monday" -> "flakes"
	        "Wednesday" -> "redworms"
	        "Thursday" -> "granules"
	        "Friday" -> "mosquitoes"
	        "Sunday" -> "plankton"
	        else -> "nothing"
	    }
    }

	// compact functions
	
	fun isTooHot(temperature: Int) = temperature > 30
	fun isDirty(dirty: Int) = dirty > 30
	fun isSunday(day: String) = day == "Sunday"
	
	// code utilizing default parameters and compact functions
	fun shouldChangeWater (day: String, temperature: Int = 22, dirty: Int = 20) : 
	Boolean {
	    return when {
	        isSunday(day) -> true
	        isTooHot(temperature) -> true
	        isDirty(dirty) -> true
	        else -> false
	    }
	}
	```
- Filters
	- Get part of a list based on some condition
	```Kotlin
	fun main() {
		val decorations = listOf ("Rock", "Pagoda", "Plastic Plant", "Alligator")
		println(decorations.filter {it[0] == 'P'})
	}
	// it refers to each item as the filter loops through the list. if the expression returns true, item is included.  it[0] refers to the item[0] i.e Rock[0] = "R"
	```
	- Eager vs Lazy
		- Eager - Is a list created immediately? (eager)
		- Lazy - Is a list created when the list is accessed? (Lazy)
			- More expensive due to resource allocation. Helpful when working with large collections where you want to avoid performing expensive operations when you only need part of the results
		- By default, filter is eager. When you use the filter method, a list is created
		- To make a filter lazy, use the *Sequence* collection. 
		- Simpler terms for Eager vs Lazy
			- Example: ask what the sum of X,Y, and Z is. 
				- In an eager evaluation, one would ask for the values of X,Y,Z and first, then sum it up
				- In a lazy evaluation, one would ask for the values of X and Y, add them together, **then** ask what z then add it to the result.
		- Example of eager code
		```Kotlin
		val decorations = listOf ("Rock", "Pagoda", "Plastic Plant", "Alligator")
		// eager creates a new list 
		val eager = decorations.filter {it[0] == 'p'}
		println("eager: $eager"):
		```
		- Example of lazy code
		```Kotlin
		// lazy, will wait until asked to evaluate
		val filtered = decorations.asSequence().filter { it[0] == 'p'}
		println("filtered: $filtered")
		```




