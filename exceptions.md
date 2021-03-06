# Exceptions
An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions. 

When an error occurs in a method following steps happen:

1. The method creates an object and hands it off to the runtime system.

2.  This process is called throwing an exception, and the object is called exception object.
Exception object contains: 
information about the error, including its type 
the state of the program when the error occurred

3. After a method throws an exception, the runtime system attempts to find something to handle it. The set of possible "somethings" to handle the exception is the ordered list of methods that had been called to get to the method where the error occurred. The list of methods is known as the call stack.

![](except.jpg)

4)  The runtime system searches the call stack for a method that contains a block of code that can handle the exception. This block of code is called an exception handler.

![](except1.jpg)
5) The exception handler chosen is said to catch the exception. If the runtime system exhaustively searches all the methods on the call stack without finding an appropriate exception handler, as shown in the above figure, the runtime system (and, consequently, the program) terminates.

**Advantages of using exceptions:**

* Separating Error-Handling Code from "Regular" Code
* Propagating errors up the call stack
* Grouping and differentiating error types

**“Catch or specify requirement”
if a block of code may throw an exception which is subjected to this requirement then it must be either within the try-catch block or it must explicitly say that it may throw that exception**

**Types of exceptions**

* **Checked Exception:**
This category of exception is subject to the “catch or specify” requirement. eg.
All exceptions related to file io are checked exceptions. Thus any code which does file io should be written in any of these two ways:

 1) Enclosing in try-catch:
```
try{
//code which throws checked exception
}
catch(Name of exception){
//handling code
}
```
 2) Specifying with the “throws” keyword:
 ```
 public void writeList() throws IOException{
 PrintWriter out = new PrintWriter(new FileWriter("out.txt"));
 for(int i = 0;i<10;i++){
  System.out.println("Value at: "+i+"="+list.get(i));
  }
 }
 ```
 
 * **Unchecked Exceptions: **
 Exceptions that are internal to the application but application cannot recover from it / cant do much about it. Eg. NullPointerException.
 
* **Errors: **These are exceptional conditions that are external to the application, and that the application usually cannot anticipate or recover from. Eg. IOError .

##Multiple catch statements and finally block:
If a block of code can generate many exceptions we can have multiple catch block to handle each kind of exception. 
```
try {
} catch (ExceptionType name) {
//code
} catch (ExceptionType name) {
//code
}
```
Java 7 has introduced another way if a single handler for multiple exceptions is needed:
eg. 
```
try{
//code
}
catch(IOException|SQLException e){
  logger.log(e);
  throw e;
  }
finally{
//this code will always execute
}
  ```
the example above also shows the catch block throwing the exception object with the “throw” keyword. 

The code in finally will always execute irrespective of whether the exception occurs or not. This block is optional and follows the catch blocks.

##Writing your own exceptions
t is possible to create your own exceptions by subclassing the Exception class. It is a good practise to name the class with the word exception. Eg. GameOverException.
```
class GameOverException extends Exception{
private String msg;
public GameOverException(String msg){
this.msg = msg;
}
public String toString(){
  System.out.println(msg);
  }
 }
 ```
 To throw this new exception,
 ```
 throw new GameOverException("Game Over");
 ```
 



 


