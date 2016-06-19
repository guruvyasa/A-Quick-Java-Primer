# Variables
For this chapter consider the following class definition:
```
class Student{
  static int numberOfStudents;
  private String name;
  private int age;
  public static void main(String[] args){
    System.out.println("hello");
  }
  ```
  

The Java programming language defines the following kinds of variables:
* **Instance Variables (Non-Static Fields):** Technically speaking, objects store their individual states in "non-static fields", that is, fields declared without the static keyword. Non-static fields are also known as instance variables because their values are unique to each instance of a class (to each object, in other words); The variables ```name``` and ```age```  are instance variables.
* **Class Variables (Static Fields):** A class variable is any field declared with the ```static``` modifier; this tells the compiler that there is exactly one copy of this variable in existence, regardless of how many times the class has been instantiated.In our example, the ```numberOfStudents``` is a class variable. We can access it as ```Student.numberOfStudents```