- XML (eXensible Markup Language)
	- way of describing data using a text-based document.
	- In this app, the XML will be modified
	- Can define the UI layout
	- ![[Pasted image 20230209014459.png]]
- UI for an android app is built as a hierachy of components (widgets) and the on-screen layouts of those components. 
- Each UI element is represented by an XML element in the XML file 
- Adding comments to XML documents Start <!-- and end with -->.

```Kotlin
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".MainActivity">  
  
</androidx.constraintlayout.widget.ConstraintLayout>
```
- xmlns: - XML name space - each line defines a vocabulary for attributes related to those words 
- android: - android name space - marks attributes that are defined by the android system 
- All of the attributes in the layout XML begin with one of those namespaces 