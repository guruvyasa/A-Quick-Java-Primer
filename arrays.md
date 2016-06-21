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

**Multidimensional arrays:**
Here is a simple example showing creation and usage of multidimensional arrays.

```
class MultiDimArrayDemo {
    public static void main(String[] args) {
        String[][] names = {
            {"Mr. ", "Mrs. ", "Ms. "},
            {"Ram", "Janaki"}
        };
        // Mr. Ram
        System.out.println(names[0][0] + names[1][0]);
        // Ms. Janaki
        System.out.println(names[0][2] + names[1][1]);
    }
}
```

** java.util.Arrays**
Java SE provides several methods for performing array manipulations (common tasks, such as copying, sorting and searching arrays) in the java.util.Arrays class. Here is an example to copy an array:
```
class ArrayCopyOfDemo {
    public static void main(String[] args) {
        
        char[] copyFrom = {'d', 'e', 'c', 'a', 'f', 'f', 'e',
            'i', 'n', 'a', 't', 'e', 'd'};
            
        char[] copyTo = java.util.Arrays.copyOfRange(copyFrom, 2, 9);
        
        System.out.println(new String(copyTo));
    }
}
```


