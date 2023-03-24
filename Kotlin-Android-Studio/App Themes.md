- Material Design - design system created by Google to help teams build high-quality digital experiences for Android.
	- Material Theming allows one to adapt material design for your app. 
	- Color can be represented as 3 hexadecimal numbers `#00-#FF (0-255)` representing the RGB components of that color
- Themes
	- A style can specify attributes for a View, such as font size, color, background color, etc
	- Theme is a collection of styles that's applied to an entire app, activity, or view hierachy and not just an individual view
	- While a theme can affect the color scheme of an application, you can also apply different styles to different widgets in the themes.xml folder
	- Create styles in the values folder and apply it to views (similar to CSS)   
		- for TextView style:
			- android:minHeight - sets minimum height
			- android:gravity
			- android:textAppearance 
			-  If you specify an attribute in a style (e.g. set `android:textSize` to be `18sp`), and also specify that same attribute in the layout file (e.g. set `android:textSize` to be `14sp`), then the value you set in the layout (`14sp`) will actually be applied to what you see on the screen.
	- ![[Pasted image 20230211204940.png]]
	- ![[Pasted image 20230211205000.png]]
- Colors that are not defined will inherit the color from the parent theme
- Color Tool - Provides a palette of predefined colors
