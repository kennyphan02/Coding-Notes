- Viewgroup (main class)
	- ConstraintLayout (sub class) - arranges views in a flexible way
	- Views have relationships to each other 
		- The layout can change depending on the size and aspect ratio of the android device that the app is running on and the layout can adapt to whether the device is in portrait/landscape mode. 
	```Kotlin
	  <Button android:id="@+id/buttonA" ... />  
	  <Button android:id="@+id/buttonB" ...     
	             app:layout_constraintLeft_toRightOf="@+id/buttonA" />
	```
	- constraintLeft_toRightof means the left side of buttonB is constrained to the rightSide of buttonA
