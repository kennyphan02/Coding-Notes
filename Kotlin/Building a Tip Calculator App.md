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
    
    <EditText  
    android:id="@+id/plain_text_input"  
    android:layout_height="wrap_content"  
    android:layout_width="match_parent"  
    android:inputType="text"  
    app:layout_constraintStart_toStartOf="parent"  
    app:layout_constraintTop_toTopOf="parent"/>
</androidx.constraintlayout.widget.ConstraintLayout>
```
- xmlns: - XML name space - each line defines a vocabulary for attributes related to those words 
- android: - android name space - marks attributes that are defined by the android system 
- All of the attributes in the layout XML begin with one of those namespaces 
- The name of the constraints follows the form `layout_constraint<Source>_to<Target>Of`, where `<Source>` refers to the current view. `<Target>` refers to the edge of the target view that the current view is being constrained to, either the parent container or another view.
-  When you manually type out the XML, you need to explicitly declare the resource ID yourself. New view IDs in your XML file must be defined with the `@+id` prefix, which tells Android Studio to add that ID as a new resource ID.
	- multiple words should be separated with an underscore (_)
- When you refer to resource IDs in your app code, use `R.<type>.<name>`; for example, `R.string.roll`. For `View` IDs, the `<type>` is `id`, for example, `R.id.button`.


- EditText - allows user to input text and edit text 
- wrapContent - the height will be as tall as the content inside of it
- Children of the ConstraintLayout must have constraints implemented.