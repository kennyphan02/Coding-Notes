- List is a collection of items with a specific order
	- Two types:
		- Read-only list: **List** cannot be modified after you create it
		- Mutuable list: **MutableList** can be modified after creating it
	- When using **List** or **MutableList** It must specify the type of elements it contain
		- I.E `List<Int>` holds a list of Integers
		- Use the standard kotlin library function listOf() to declare a list
		- `val numbers: List<Int> = listOf(1, 2, 3, 4, 5, 6)` creates a read-only list of numbers 1-6.
			- If the type on the right side of the equal operator can be inferred, we can shorten it by removing the type so it would be `val numbers = listOf(1,2,3,4,5,6)`
- Kotlin has default methods for List 
	- First: returns the first index of a list
	- Last: returns the last index of a list
	- Contains() checks to see if the parameter passed into contains() methods exists in a list 
	- reversed() returns a list in reversed order
	- sorted() returns a list in ascending order
- methods for MutableList 
	- add() method returns true if an item has been successfully added to the list
	- you can add multiple elements using addAll() and pass in a list
	- remove() removes an element. It can pass in the same data type as the mutable list or the index of the element to remove
	- clear() clears the whole list
	- isEmpty() returns a boolean type to check to see if a list is empty 
- When declaring a MutableList use `mutableListOf<Type>()`
	- `val entrees: MutableList<String> = mutableListOf()` or `val entrees = mutableListOf<String>`
		- you can use val for a MutableList because the entrees variable contains a reference to the list and that reference doesn't change even if the contents of the list do. 
- Looping through a list
	```Kotlin
	for(item in items){
		println(item)
	}
	```
- Instead of having multiple properties to pass in as an argument(s) into a class, A class can utilize a variable with type `List<Type>` 
	- A better way to do this is use vararg modifier 
	- vararg - allows one to pass a variable number of arguments of the same type into a function/constructor
		- I.e `class Vegetables(vararg val toppings: String) : Item("Vegetables", 5)`
		- `val vegetables = Vegetables("Cabbage", "Sprouts", "Onion")`
		- To print the strings of vegetables, use the joinToString() method to join all the toppings into a single string 

Example code:
```Kotlin
open class Item(val name: String, val price: Int)

class Noodles : Item("Noodles", 10) {
    override fun toString(): String {
        return name
    }
}

class Vegetables(vararg val toppings: String) : Item("Vegetables", 5) {
    override fun toString(): String {
        if (toppings.isEmpty()) {
            return "$name Chef's Choice"
        } else {
            return name + " " + toppings.joinToString()
        }
    }
}

class Order(val orderNumber: Int) {
    private val itemList = mutableListOf<Item>()

    fun addItem(newItem: Item): Order {
        itemList.add(newItem)
        return this
    }

    fun addAll(newItems: List<Item>): Order {
        itemList.addAll(newItems)
        return this
    }

    fun print() {
        println("Order #${orderNumber}")
        var total = 0
        for (item in itemList) {
            println("${item}: $${item.price}")
            total += item.price
        }
        println("Total: $${total}")
    }
}

fun main() {
    val ordersList = mutableListOf<Order>()

    // Add an item to an order
    val order1 = Order(1)
    order1.addItem(Noodles())
    ordersList.add(order1)

    // Add multiple items individually
    val order2 = Order(2)
    order2.addItem(Noodles())
    order2.addItem(Vegetables())
    ordersList.add(order2)

    // Add a list of items at one time
    val order3 = Order(3)
    val items = listOf(Noodles(), Vegetables("Carrots", "Beans", "Celery"))
    order3.addAll(items)
    ordersList.add(order3)

    // Use builder pattern
    val order4 = Order(4)
        .addItem(Noodles())
        .addItem(Vegetables("Cabbage", "Onion"))
    ordersList.add(order4)

    // Create and add order directly
    ordersList.add(
        Order(5)
            .addItem(Noodles())
            .addItem(Noodles())
            .addItem(Vegetables("Spinach"))
    )

    // Print out each order
    for (order in ordersList) {
        order.print()
        println()
    }
}
```
