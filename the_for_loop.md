# The for loop

The for statement provides a compact way to iterate over a range of values. Programmers often refer to it as the "for loop" because of the way in which it repeatedly loops until a particular condition is satisfied. The general form of the for statement can be expressed as follows:

```
for (initialization; termination;
     increment) {
    statement(s)
}
```

When using this version of the for statement, keep in mind that:
* The initialization expression initializes the loop; it's executed once, as the loop begins.
* When the termination expression evaluates to false, the loop terminates.
* The increment expression is invoked after each iteration through the loop; it is perfectly acceptable for this expression to increment or decrement a value.

The following program, ForDemo, uses the general form of the for statement to print the numbers 1 through 10 to standard output:

```
class ForDemo {
    public static void main(String[] args){
         for(int i=1; i<11; i++){
              System.out.println("Count is: " + i);
         }
    }
```

The variable is declared and defined in the for loop. Thus, it is present only within the scope of the loop.  If the variable that controls a for statement is not needed outside of the loop, it's best to declare the variable in the initialization expression.

The three expressions of the for loop are optional; an infinite loop can be created as follows:

```
// infinite loop
for ( ; ; ) {
    
    // your code goes here
}
```

## Enhanced for loop
The for statement also has another form designed for iteration through Collections and arrays This form is sometimes referred to as the enhanced for statement, and can be used to make your loops more compact and easy to read. To demonstrate, consider the following program which prints numbers from an array, which holds the numbers 1 through 10:

```

class EnhancedForDemo {
    public static void main(String[] args){
         int[] numbers = {1,2,3,4,5,6,7,8,9,10};
         for (int item : numbers) {
             System.out.println("Count is: " + item);
         }
    }
}
```
In this example, the variable item holds the current value from the numbers array. This value gets updated in every iteration of the loop.
    