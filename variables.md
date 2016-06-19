# Variables
For this chapter consider the following class definition:
```
class Student{
  static int numberOfStudents;
  private String name;
  private int age;
  public static void main(String[] args){
    int day;
    System.out.println("hello");
  }
  ```
  

The Java programming language defines the following kinds of variables:
* **Instance Variables (Non-Static Fields):** Technically speaking, objects store their individual states in "non-static fields", that is, fields declared without the static keyword. Non-static fields are also known as instance variables because their values are unique to each instance of a class (to each object, in other words); The variables ```name``` and ```age```  are instance variables.
* **Class Variables (Static Fields):** A class variable is any field declared with the ```static``` modifier; this tells the compiler that there is exactly one copy of this variable in existence, regardless of how many times the class has been instantiated.In our example, the ```numberOfStudents``` is a class variable. We can access it as ```Student.numberOfStudents```
* **Local variables: **Similar to how an object stores its state in fields, a method(function) will often store its temporary state in local variables. The syntax for declaring a local variable is similar to declaring a field (for example, int count = 0;). There is no special keyword designating a variable as local; that determination comes entirely from the location in which the variable is declared — which is between the opening and closing braces of a method. As such, local variables are only visible to the methods in which they are declared; they are not accessible from the rest of the class.
* **Parameters:** Recall that the signature for the main method is public static void main(String[] args). Here, the args variable is the parameter to this method. The important thing to remember is that parameters are always classified as "variables" not "fields".

**Naming Conventions**

 The rules and conventions for naming your variables can be summarized as follows:
 
 * Variable names are case-sensitive. A variable's name can be any legal identifier — an unlimited-length sequence of Unicode letters and digits, beginning with a letter, the dollar sign "$", or the underscore character "_". The convention, however, is to always begin your variable names with a letter, not "$" or "_". Additionally, the dollar sign character, by convention, is never used at all. You may find some situations where auto-generated names will contain the dollar sign, but your variable names should always avoid using it. A similar convention exists for the underscore character; while it's technically legal to begin your variable's name with "_", this practice is discouraged. White space is not permitted.
 * If variable stores a constant value use full uppercase: Eg. **final double PI = 3.141;**
 * Follow camelcase. For class names Eg. **ClassName**, variable and function names, **doSomething()**
 * 