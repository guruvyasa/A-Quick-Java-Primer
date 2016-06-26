# Simple Class Syntax
For the problem listed, here is a simple class definition in Java which uses 2 classes, here is the Employee class
```
public class Employee{
  private int salary;
  private String name;
  private int age;
  Employee(name,age,salary){ //this is constructor
    this.name = name;
    this.age = age;
    this.salary = salary;
    }
  }
  ```
 This is the blueprint of every employee. There are some things to observe here,
 
 * salary, name, age are attributes of an employee.
 * all three attributes are private.