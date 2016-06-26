# Interfaces
There are a number of situations in software engineering when it is important for disparate groups of programmers to agree to a "contract" that spells out how their software interacts. Each group should be able to write their code without any knowledge of how the other group's code is written. Generally speaking, interfaces are such contracts.

For example, imagine a futuristic society where computer-controlled robotic cars transport passengers through city streets without a human operator. Automobile manufacturers write software (Java, of course) that operates the automobile—stop, start, accelerate, turn left, and so forth. Another industrial group, electronic guidance instrument manufacturers, make computer systems that receive GPS (Global Positioning System) position data and wireless transmission of traffic conditions and use that information to drive the car.

The auto manufacturers must publish an industry-standard interface that spells out in detail what methods can be invoked to make the car move (any car, from any manufacturer). The guidance manufacturers can then write software that invokes the methods described in the interface to command the car. Neither industrial group needs to know how the other group's software is implemented. In fact, each group considers its software highly proprietary and reserves the right to modify it at any time, as long as it continues to adhere to the published interface.

## Defining interfaces
An interface declaration consists of modifiers, the keyword interface, the interface name, a comma-separated list of parent interfaces (if any), and the interface body. For example:
```
public interface GroupedInterface extends Interface1, Interface2, Interface3 {

    // constant declarations
    
    // base of natural logarithms
    double E = 2.718282;
 
    // method signatures
    void doSomething (int i, double x);
    int doSomethingElse(String s);
}
```

* The public access specifier indicates that the interface can be used by any class in any package. 
* If you do not specify that the interface is public, then your interface is accessible only to classes defined in the same package as the interface.
* An interface can extend other interfaces, just as a class subclass or extend another class.
* A class can extend only one other class, an interface can extend any number of interfaces. The interface declaration includes a comma-separated list of all the interfaces that it extends.

##The Interface Body

* The interface body can contain abstract methods, default methods, and static methods. 
* An abstract method within an interface is followed by a semicolon, but no braces (an abstract method does not contain an implementation). 
* Default methods are defined with the default modifier, and static methods with the static keyword. 
* All abstract, default, and static methods in an interface are implicitly public, so you can omit the public modifier.
* An interface can contain constant declarations. All constant values defined in an interface are implicitly public, static, and final. Once again, you can omit these modifiers.

## Implementing an interface
* To declare a class that implements an interface, you include an implements clause in the class declaration. 
* Your class can implement more than one interface, so the implements keyword is followed by a comma-separated list of the interfaces implemented by the class. Eg. ```class MyButton implements Clickable,Moveable{...}```
* By convention, the implements clause follows the extends clause, if there is one. Eg. ```class MyButton extends View implements Clickable,Moveable{...}```

Let us continue the example of Employees. Suppose we want to sort the employees based on their salary. We can do this in multiple ways, one is to use the Comparator interface,
```
import java.util.*;
public class EmployeeSort{
  public static void main(String[] args){
    Company sathvikSoftech = new Company("sathvik softech");
    //add five employees
    sathvikSoftech.addEmployee(new Employee("chandan",30,5000));
    sathvikSoftech.addEmployee(new Employee("vijay",25,2000));
    sathvikSoftech.addEmployee(new Employee("guru",23,3000));
    sathvikSoftech.addEmployee(new Employee("vaibhav",25,4000));
    sathvikSoftech.addEmployee(new Employee(arun",25,2000));
    
    Comparator<Employee> c = new Comparator<>(){
                            public int compare(Employee i1,Employee i2){
                              return Integer.compare(i1.getSalary(),i2.getSalary());
                              };
    Employee[] employees = sathvikSoftech.getEmployees();
    Arrays.sort(employees,c);
    
    for(Employee e:employees){
      System.out.println(e.getName());
      }
    }
   }
  ```
  The Comparator interface is a generic interface which we can use to make objects comparable. When the list of employees is sorted, we need to pass a Comparator object which is an Employee comparator. To create such an object we need to implement the compare function in the Comparator.
  
From this example we have to understand few things about Interfaces,
* Any class which implements an interface must define the functions of the interface.
* Once a class implements an interface, we can store and access the class instances as of the type of the interface. eg. ```List<Integer> i = new LinkedList<>();```
  
    
  