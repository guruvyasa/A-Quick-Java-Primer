# NIO package

##Difference between Standard IO and NIO
 First main difference between the standard IO and NIO is, standard IO is based on streams and NIO is buffer oriented. Buffer oriented operations provide as flexibility in handling data. In buffer oriented NIO, data is first read into a buffer and then it is made available for processing. So we can move back and forth in the buffer. But in the case of streams it is not possible.

Second main difference is, blocking and non-blocking IO operations. In case of streams, a thread will be blocked until it completes the IO operation. Wherein the NIO allows for non-blocking operations. If the data is not available for IO operations, then the thread can do something else and need not stay in blocked mode. With channels and selectors a single thread can manage multiple threads and parallel IO operations.

Here is a simple program to read a file using NIO 2 and Java 8
```
import java.util.*;
import java.nio.file.*;
import java.io.*;
import java.util.stream.*;


class Java8IO{
    public static void main(String[] args) {
        //using java8 stream API
        try(Stream<String> lines = Files.lines(Paths.get("words.txt"))){
            lines.filter(line ->line.startsWith("s"))
                   .forEach(System.out::println);

        }
        catch(IOException e){
            e.printStackTrace();
        }

        //using BufferReader
        try(BufferedReader r = Files.newBufferedReader(Paths.get("words.txt"))){
            String line = r.readLine();
            while(line != null){
                System.out.println(line);
                line = r.readLine();
            }
        }
        catch(IOException e){
            e.printStackTrace();
        }

        //new java8 file writing
        List<String> lines = Arrays.asList("line 1", "line 2", "line 3");
        try{
            Files.write(Paths.get("output.txt"), lines);
        }
        catch(IOException e){
            e.printStackTrace();
        }
    }
}
```

The Files and Paths classes are central to file IO using the new java nio2. In the above example we have used the Files.write() to write lines to the file and Files.lines to get a stream of lines from a file. We also use Files.newBufferedReader to get a BufferedReader instance.

