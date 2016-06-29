# NIO package

##Difference between Standard IO and NIO
 First main difference between the standard IO and NIO is, standard IO is based on streams and NIO is buffer oriented. Buffer oriented operations provide as flexibility in handling data. In buffer oriented NIO, data is first read into a buffer and then it is made available for processing. So we can move back and forth in the buffer. But in the case of streams it is not possible.

Second main difference is, blocking and non-blocking IO operations. In case of streams, a thread will be blocked until it completes the IO operation. Wherein the NIO allows for non-blocking operations. If the data is not available for IO operations, then the thread can do something else and need not stay in blocked mode. With channels and selectors a single thread can manage multiple threads and parallel IO operations.

