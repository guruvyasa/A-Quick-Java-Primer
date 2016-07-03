# Exceptions
An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions. 

When an error occurs in a method following steps happen:

1. The method creates an object and hands it off to the runtime system.

2.  This process is called throwing an exception, and the object is called exception object.
Exception object contains: 
information about the error, including its type 
the state of the program when the error occurred

3. After a method throws an exception, the runtime system attempts to find something to handle it. The set of possible "somethings" to handle the exception is the ordered list of methods that had been called to get to the method where the error occurred. The list of methods is known as the call stack.
