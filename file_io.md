# File I/O
File operations have undergone quite a change since Java 7. A new IO library was introduced in Java7 and that has made I/O operations much easier. This is the java.nio.file package. However, we will briefly talk about the old way to do file I/O first and then the nio package.


## I/O Streams
An I/O Stream represents an input source or an output destination. A stream can represent many different kinds of sources and destinations, including disk files, devices, other programs, and memory arrays.

Streams support many different kinds of data, including simple bytes, primitive data types, localized characters, and objects. Some streams simply pass on data; others manipulate and transform the data in useful ways.

No matter how they work internally, all streams present the same simple model to programs that use them: A stream is a sequence of data. A program uses an input stream to read data from a source, one item at a time. A program uses an output stream to write data to a destination, one item at time.

##Buffered Streams
The preferred way to perform I/O operations is through the BufferedStream. Buffered input streams read data from a memory area known as a buffer; the native input API is called only when the buffer is empty. Similarly, buffered output streams write data to a buffer, and the native output API is called only when the buffer is full.

### BufferedWriter
This can be used for writing character data to the file.
**Constructors**

* BufferedWriter bw = new BufferedWriter(writer w)
* BufferedWriter bw = new BufferedWriter(writer r, int size)
* BufferedWriter never communicates directly with the file. It should communicate through some writer object only.

Important methods of BufferedWriter Class:

* void write(int ch) thorows IOException
* void write(String s) throws IOException
* void write(char[] ch) throws IOException
* void newLine() for inserting a new line character.
* void flush()
* void close()






