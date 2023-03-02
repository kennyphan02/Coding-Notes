Bug - causes uninteded behavior
- Use logging for logging output rather print statements
- ![[Pasted image 20230202230049.png]]
- Using logs to debug won't impact performance of published apps, whereas println() statement do negatively impact performance
- Exception - stack trace - shows all the functions that were called leading up to the exception starting with the most recently called. 
```Kotlin
val TAG = ...

fun first() {
    second()
    Log.v(TAG, "1")
}

fun second() {
    third()
    Log.v(TAG, "2")
    fourth()
}

fun third() {
    Log.v(TAG, "3")
}

fun fourth() {
    Log.v(TAG, "4")
}

// Prints 3,2,4,1 if u call first()
```