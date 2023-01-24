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
		- **Map()** performs the same transform on  every item and returns the list
		```Kotlin
		val numbers = setOf(1,2,3)
		println(numbers.map {it * 3*}) 
		// [3,6,9]
		```
		- Flatten() - returns a single list of all the elements of nested collections (i.e combines an array of arrays into an array)
- Lambdas
	- An expression that describes a function.
	- Nameless functions
	- Lambda expressions can be passed as data
	- Also called function literals
	- Parameters go on the left of the ->. 
	- The code on the right of the > gets executed
	- Example: 
	```Kotlin
	var dirtyLevel = 20
	val waterFilter = { dirty : Int -> dirty / 2} //waterFilter is a function
	println(waterFilter(dirtyLevel))
	```
	Kotlin's syntax is:
	```Kotlin
	val waterFilter: (Int) -> Int = { dirty -> dirty / 2}
	// waterFilter can be a function that takes an Int and returns an int
	// assign a lambda to waterFilter
	// lambda returns the value of dirty / 2
	
	```
- Higher-order Functions
	- function that takes other functions as parameters
	- Can pass a lambda to a higher-order function that takes a function as an argument.
	- map is a higher-order function
	- The function you pass doesn't have to be a lambda. Could be a regular function.
		- If specifying the argument as a regular function use the :: operator
	- Kotlin prefers that a function is passed as the last parameter. (utilizes last parameter call syntax making the code more concise)
	```Kotlin
	val waterFilter: (Int) -> Int = { dirty -> dirty / 2}
	fun updateDirty(dirty: Int, operation: (Int) -> Int) : Int {
		return operation(dirty)
	}
	println(updateDirty(30,waterFilter))
	// one cool thing with higher-order functions is that it can take in a function then return a function of that function 
	``` 
- Classes
	- Packages - keeps code organized
	- Can create multiples classes in one file
	- Kotlin automatically creates getters and setters for properties you defined in the class.
	```Kotlin
	class Aquarium {
		var width: Int = 20
		var height: Int = 40
		var length: Int = 100
		fun printSize(){
			println("Width: $width cm + ... (for length and height)")
		}
	}
	// creating a main function
	fun buildAquarium() {
		val myAquarium = Aquarium()
		myAquarium.printSize()
		myAquarium.height = 60
		myAquarium.printSize()
	}
	fun main() {
		buildAquarium()
	}
	// returns Width: 20 cm + Height: 40 cm + Length: 100 cm 
	// returns Height: 60 cm along with the other default values 
	```
	- Creating a default constructor: you define it in the class declaration itself 
	```Kotlin
	class Aquarium(length: Int = 100, width: Int = 20, height: Int = 40){
		var length: Int = length
		var width: Int = width
		var height: Int = height
	}
	// more simplified way in Kotlin is using var/val in the class declaration and removing the body
	class Aquarium(var length: Int = 100, var width: Int = 20, var height: Int = 40)
	
	```
	- Constructors can have init blocks that are initalized and ran. Can have multiple constructors. init blocks are executed in the in order in which they appear in the class definition
		- Why write val or var infront of primary constructor arguments? 
			- Automatically creates fields with the same names which are initalized to the arguments passed to the constructor 
	- One can create different Aquarium objects and initalizing different values of the parameters while keeping the rest its default values by specifying the parameter to be initalized 
		- val aquarium1 = Aquarium()
		- val aquarium2 = Aquarium(width = 25)
		- 
- Visbility Modifiers
	- Private - only visible in that class
	- Protected - visible to subclasses
	- Internal - only visible within that module (module is a set of kotlin files compiled together)
	- public - visible outside the class
- Subclasses/Inheritance
	- By default, kotlin classes can not be subclassed. must declare a class open. the class's properties and variable need to be marked as open too
	- Showing how inheritance is used:
	- ![[Pasted image 20230123221429.png]]
	- Showing how inheritance is used:
	```Kotlin
	open class Aquarium (open var length: Int = 100, open var width: Int = 20, open var height: Int = 40) {
    open var volume: Int
        get() = width * height * length / 1000
        set(value) {
            height = (value * 1000) / (width * length)
        }
    open var water: Double = 0.0
	    get() = volume * 0.9 
	open val shape = "rectangle"
        // get() gets the value of volume. to utilize get, instiante an object of Aquarium i.e val obj1 = Aquarium()
        // obj1.length   //get() gets the value of length
        // set(value) is called automatically. 
        
	

	```
- Getters/setters
	- Automatically created in kotlin by default. If one wants to change the value of the property, a get() or set() must be declared underneath the variable to change the property. 
	- setters set the value of any variable and getter is used to get the value
- Abstract classes and interfaces
	- Abstract classes and interfaces is used to define common behavior/properties to be shared among related classes. 
	- Abstract classes/interfaces can't be instantiated. 
	- Abstract classes can have constructors
	- interfaces can't store state
	- Subclasses that inherit abstract classses must implement the abstract classes methods and properties. Abstract classes are always open (Dont need to markw ith open)
	- **When to use interfaces or abstract classes?**
		- Using interfaces will tend to make code easier to reuse and understand than inheritance from an abstract class. The class functionality utilizes methods from an interface that it must implement. With interfaces, you can implement more than one interface while you can't inherit more than one parent class.  
			- Rule of thumb: favor composition (interfaces and isntance references) over subclassing for readability.
- Interface Delegation
	- Design technique where methods of an interface can be implemented by a helper (delegate) object which is used by a class. 
		- Useful for using an interface in a series of unrelated classes 
		- Implement interface functionality in a separate helper class. each unrelated classes uses an instance of that helper class to obtain the functionality
		- ![[Pasted image 20230124004439.png]]
		- Making a singleton class to create one instance of a class. use the keyword object instead of Class. 
		- Composition leads to better encapsulation, lower coupling (interdependence), cleaner interfaces, and more usable code. 

- Data classes
	- Holds data
	- Copy() method? 
	```Kotlin
	data class Decoration(val rocks: String){
		
	}
	fun makeDecorations() {
		val decoration1 = Decoration("granite") // prints Decoration("granite")
		println(decoration1)
		val decoration2 = Decoration("slate") // prints Decoration(rocks = slate)
		println(decoration2)
		val decoration3 = Decoration("slate")
		println(decoration3)  // prints Decoration(rocks = slate)
		println(deocration1.equals(decoration2)) // false 
		println(deocration2.equals(decoration3)) // true
	}
	fun main(){
		makeDecorations() // prints 
	}
	```




