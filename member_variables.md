# Member Variables

There are several kinds of variables:

* Member variables in a class—these are called fields.
* Variables in a method or block of code—these are called local variables.
* Variables in method declarations—these are called parameters.

In our Employee class, ```private int salary;``` is a member variable declaration. ```private``` is access-modifier, ```int``` is the data type, salary is the name.

## Controlling Access to Members of a Class
Access level modifiers determine whether other classes can use a particular field or invoke a particular method. There are two levels of access control:

* At the top level—public, or package-private (no explicit modifier). g. public class Employee
* At the member level—public, private, protected, or package-private (no explicit modifier) eg. public void addEmployee().

A class may be declared with the modifier public, in which case that class is visible to all classes everywhere. If a class has no modifier (the default, also known as package-private), it is visible only within its own package (packages are named groups of related classes)

At the member level, you can also use the public modifier or no modifier (package-private) just as with top-level classes, and with the same meaning. For members, there are two additional access modifiers: private and protected. The private modifier specifies that the member can only be accessed in its own class. The protected modifier specifies that the member can only be accessed within its own package (as with package-private) and, in addition, by a subclass of its class in another package.

The following table shows the access to members permitted by each modifier.

| Modifier | Class | Package | Subclass | World |
| -- | -- | -- | -- | -- |
| public | Y | Y | Y | Y |
| protected | Y | Y | Y | N |
| no-modifier | Y | Y | N | N |
| private | Y | N | N | N |

