- Requires an InstrumentalTestRunner to allow the test to be executed
- Test rules run before every test in a test class.
- Espresso is a fundamental component of instrumentation tests. It enables interaction with UI components using code.
```Kotlin
@get:Rule() 
val activity = ActivityScenarioRule(MainActivity::class.java)

// ActivityScenarioRule tells the device to launch an activity specified by the developer
// @get:Rule() specifies the sebsequent rule (i.e launching an activity should execute before every test in the class
```
- First step:
	- find a UI Component to interact with using the onView() function. the onView() function takes a ViewMatcher object parameter. 
		- ViewMatcher - a UI component that matches a particular criteria 
		- How can we pass in a ViewMatcher? use the function withId() which returns a viewMatcher using a resource id that is passed to it.
			- **onView()** returns a ViewInteraction, an object that we can interact with as if we were controlling the devices ourselves. 
			- **perform()** takes a ViewAction object. (example: typetext())
```Kotlin
onView(withId(R.id.cost_of_service_edit_text))
    .perform(typeText("50.00"))
```
- 3 Kinds of implementations for dependencies
	- testImplementation
	- androidTestImplementation
	- implementation

```Kotlin
// withId(R.id.my_view) is a ViewMatcher  
// click() is a ViewAction  
// matches(isDisplayed()) is a ViewAssertion  
onView(withId(R.id.my_view))
.perform(click())    
.check(matches(isDisplayed()))
```
Viewmatchers - locates a view
viewactions - a collection of viewaction objects that can be passed to the viewinteraction.perform() method such as click()
viewassertions - a collection of viewassertion objects that can be passed the viewinteraction.check() method. 

the code above locates the my_view id and performs a click operation and checks for an assertion 