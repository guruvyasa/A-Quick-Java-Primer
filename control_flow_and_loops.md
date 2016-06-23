# Control flow and Loops

## The if-then Statement
The if-then statement is the most basic of all the control flow statements. It tells your program to execute a certain section of code only if a particular test evaluates to true. 
Here is a simple program to check whether a number is even or odd.
```
class IfElseDemo{
  public static void main(String[] args){
    int number = 10;
    if (number % 2 == 0){
      System.out.println(number + " is even");
      }
    else{
      System.out.println(number + " is odd");
      }
 }
}
```
One thing to keep in mind here, we cannot write ```if(number % 2){...}```, as Java expects a boolean expression in if's unlike C and C++.
** In Java an expression is allowed in a boolean context  if and only if it evaluates to true or false**

Here is another example which checks if a number is both even and divisible by 4,
```
class NestedIfElseDemo{
  public static void main(String[] args){
    int number = 10;
    if (number % 2 == 0){
      if(number % 4 == 0)
        System.out.println(number + " is even and divisible by 4");
      else
         System.out.println(number + " is even but not divisible by 4");
      }
    else{
      System.out.println(number + " is neither even and(obviously) not divisible by 4");
      }
 }
}
```