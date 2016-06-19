# First  Steps into Java Programming

A simple program to print hello world in java is as follows:
```
class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("Hello World!"); // Display the string.
    }
}
```
This program has 3 main components:
* ** Comments:** Anything between ```/*``` and ```*/``` is comment. This is a multiline comment. Anything after ```//``` is also commented. This is a single line comment.
* **Class Definition:** A basic class defintion looks like
```class ClassName{
....
}
``` . In our example the class name is HelloWorldApp.
* **The *main* Method:** Every Java application must have a method with the name **main**. This is where the app starts. Its signature is:```public static void main(String[] args)```. Here args is the array of command line arguments which can be passed as
```java HelloWorldApp hello hi```. Here we have passed hello and hi as our arguments to the program.

Finally, the line:```System.out.println("Hello World!");```
uses the System class from the core library to print the "Hello World!" message to standard output.

Some simple rules to remember when writing java programs:
* Everything must be within a class. 
* Atleast one file must have a class with a static main function

* A file can have any number of classes, but only one public class.
* If a file has a public class, the name of the file must match name of the public class





