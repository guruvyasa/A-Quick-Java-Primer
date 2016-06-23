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