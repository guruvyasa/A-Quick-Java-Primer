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
* **Instance Variables (Non-Static Fields):** Technically speaking, objects store their individual states in "non-static fields", that is, fields declared without the static keyword. Non-static fields are also known as instance variables because their values are unique to each instance of a class (to each object, in other words); the currentSpeed of one bicycle is independent from the currentSpeed of another.