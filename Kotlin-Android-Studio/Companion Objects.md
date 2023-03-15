Companion Objects are similar to static classes and methods. In java, to call a method from a class without creating an instance of the class, the method has a type static. To call the method you would write ClassName.Method to call the Method with static type. Companion objects perform in a similar manner without using the static keyword. 

In Kotlin if one wants to write a function that can be called without an instance of the class, you can write a companion object within the class. You can access the members of the class by class name only 

```Kotlin
class ToBeCalled {
    companion object {
        var someInteger: Int = 10
        fun callMe() = println("You are calling me :)")
    }
}

fun main(args: Array<String>) {
    print(ToBeCalled.someInteger)
    ToBeCalled.callme()
}
```