# Class members (static)

## Class Variables
In our Employee class, we had a variable which was "static",numberOfEmployees. Because it was static we were able to refer to it without creating an instance of Employee in the Company class. **The use of the static keyword creates fields and methods that belong to the class, rather than to an instance of the class. **. 

## Class Methods 
In our Employee class we had a method called "getNumberOfEmployees". This method was static, thus it is a class method not instance method. To call this method we do not need an instance of Employee.

Not all combinations of instance and class variables and methods are allowed:

* Instance methods can access instance variables and instance methods directly.
* Instance methods can access class variables and class methods directly.
* Class methods can access class variables and class methods directly.
* Class methods cannot access instance variables or instance methods directly—they must use an object reference. Also, class methods cannot use the this keyword as there is no instance for this to refer to.

