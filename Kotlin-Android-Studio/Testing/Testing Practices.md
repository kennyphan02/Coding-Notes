- Tests should not contain logic
- Tests should not manipulate variables (most of the time) because the tests itself could fail in the same way that our app could fail 
- Unit tests should only call pieces of code from our app that is necessary for the test and the test the values or the state of the code that results from calling the code. 