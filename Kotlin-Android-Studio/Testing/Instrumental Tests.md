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