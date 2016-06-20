# Arrays

An array is a container object that holds a fixed number of values of a single type. The length of an array is established when the array is created. After creation, its length is fixed. Here is a simple program to illustrate array usage:
```

class ArrayDemo {
    public static void main(String[] args) {
        // declares an array of integers
        int[] anArray;
        float[] anArrayOfFloats;

        // allocates memory for 10 integers
        anArray = new int[10];
           
        // initialize first element
        anArray[0] = 100;
        
        System.out.println(anArray.length); // prints 10
        System.out.println(anArray[8]); //prints 0
        }
       }
       ```
       
 Here is a shortcut syntax to create an array:
 
 ```
int[] anArray = { 
    100, 200, 300,
    400, 500, 600, 
    700, 800, 900, 1000
};
```