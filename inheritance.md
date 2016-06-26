# Inheritance
 In the Java language, classes can be derived from other classes, thereby inheriting fields and methods from those classes.

**Subclass:** A class that is derived from another class is called a subclass (also a derived class, extended class, or child class). The class from which the subclass is derived is called a** superclass** (also a base class or a parent class).

Excepting Object, which has no superclass, every class has one and only one direct superclass (single inheritance). In the absence of any other explicit superclass, every class is implicitly a subclass of Object.

The idea of inheritance is simple but powerful: When you want to create a new class and there is already a class that includes some of the code that you want, you can derive your new class from the existing class. In doing this, you can reuse the fields and methods of the existing class without having to write (and debug!) them yourself.

A subclass inherits all the members (fields, methods, and nested classes) from its superclass. Constructors are not members, so they are not inherited by subclasses, but the constructor of the superclass can be invoked from the subclass.

The** extends** keyword is used in Java to say that a class derives from another class. Here is an example:

If we look at the Employee class we discussed in the previous chapter, we can see that the attributes name and age are not specific to employees. Every Person has a name and age. Thus we can make a Person class and make Employee inherit from Person,
```
public class Person{
  private String name;
  private int age;
  Person(
