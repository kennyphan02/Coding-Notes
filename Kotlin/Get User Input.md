- Classes and Inheritance
	- When extending from a superclass, you must pass in the required parameters expected by the superclass. `Dwelling` requires the number of `residents` as input. You could pass in a fixed number of residents like 3 
	- override keyword is used to define the implementations of abstract variables in kotlin. override indicates that the property was defined in a parent class and is about to be overridden
- Create a class hierarchy, that is a tree of classes where children inherit functionality from parent classes. Properties and functions are inherited by subclasses.
Create an abstract class where some functionality is left to be implemented by its subclasses. An abstract class can therefore not be instantiated.
Create subclasses of an abstract class.
Use override keyword to override properties and functions in subclasses.
Use the super keyword to reference functions and properties in the parent class.
Make a class open so that it can be subclassed.
Make a property private, so it can only be used inside the class.
Use the with construct to make multiple calls on the same object instance.
Import functionality from the kotlin.math library