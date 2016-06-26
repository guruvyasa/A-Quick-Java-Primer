# Simple Class Syntax
For the problem listed, here is a simple class definition in Java which uses 2 classes, here is the Employee class
```
public class Employee{
  private static int numberOfEmployees;
  private int salary;
  private String name;
  private int age;
  Employee(name,age,salary){ //this is constructor
    numberOfEmployees += 1;
    this.name = name;
    this.age = age;
    this.salary = salary;
    }
  public static int getNumberOfEmployees(){ //this is a class method
    return numberOfEmployees;
  }
  public String getName(){
    return name;
    }
  public int getSalary(){
    return salary;
    }
  }
  ```
 This is the blueprint of every employee. There are some things to observe here,
 
 * salary, name, age are attributes of an employee.
 * all three attributes are private.
 * a constructor is a method which has the same name as theh class,Employee class has a method with name Employee.
 * this constructor gets called every time an employee object is created.
 * we had to use "this" in the constructor to disambiguate the variable names and instance names.
 * numberOfEmployees is a static attribute of Employee, which get incremented every time an object is created
 
Now we have another class called Company, which has employees

```
public class Company{
  private Employee[] employees = new Employee[100]; //creates an array of 100 employees
  private String name;
  Company(String name){
    this.name = name;
    }
  public void addEmployee(Employee e){
    if (Employee.getNumberOfEmployees() < employees.length){
      employees[Employee.getNumberOfEmployees() - 1] = e;
    else
      System.out.println("Max employees reached");
  }
```
Here are some points about Company class:
* The company can have a max of 100 employees
* We check if the employees list is full everytime we add an employee to the list.

** Can you identify a flaw with this program?? If yes rectify it!!
**
From the two classes, we can identify the common syntax for a class,
```
modifier class ClassName{
 modifier datatype attrib1;
 ...
 ...
 modifier returnType methodName(Type arg1,...){...}
 ...
 }
```
To create an instance of a class, 
```
Employee e = new Employee('chandan',30,3000);//calls the Employee constructor
```

 