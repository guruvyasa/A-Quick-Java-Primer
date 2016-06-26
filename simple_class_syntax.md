# Simple Class Syntax
For the problem listed, here is a simple class definition in Java which uses 2 classes, here is the Employee class
```
public class Employee{
  static int numberOfEmployees;
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
 * a constructor is a method which has the same name as theh class,Employee class has a method with name Employee.
 * this constructor gets called every time an employee object is created.
 * we had to use "this" in the constructor to disambiguate the variable names and instance names.
 
Now we have another class called Company, which has employees

```
public class Company{
  private Employee[] employees = new Employee[100]; //creates an array of 100 employees
  public void addEmployee(Employee e){
    employees.
  
 