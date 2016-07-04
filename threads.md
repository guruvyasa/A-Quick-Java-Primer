# Threads


A thread sometimes known as an execution context or a lightweight process–is a single sequential flow of control within a process. As a sequential flow of control, a thread must carve out some of its own resources within a running program (it must have its own execution stack and program counter for example). The code running within the thread only works within that context. Thus, other texts use execution context as a synonym for thread.
```
 
public class ThreadDemo {
 

	public static void main(String args[]) {
		new ThreadTest("eBay").start();
		new ThreadTest("Paypal").start();
		new ThreadTest("Google").start();
	}
}
 
class ThreadTest extends Thread {
	public ThreadTest(String str) {
		super(str);
	}
 
	public void run() {
		for (int i = 0; i < 5; i++) {
			System.out.println("Loop " + i + ": " + getName());
			try {
				sleep((int) (Math.random() * 2000));
			} catch (InterruptedException e) {
			}
		}
		System.out.println("Test Finished for: " + getName());
	}
}
```
The run() method is the heart of any Thread–it’s where the action of the Thread takes place. The run() method of the ThreadTest class contains a for loop that iterates 5 times. In each iteration the method displays the iteration number and the name of the Thread then sleeps for a random interval between 0 and 2 seconds. After the loop has finished, the run() method prints “Test Finished For: ” along with the name of the thread.

##Pausing Execution with Sleep
Thread.sleep causes the current thread to suspend execution for a specified period. This is an efficient means of making processor time available to the other threads of an application or other applications that might be running on a computer system. The sleep method can also be used for pacing, as shown in the example that follows, and waiting for another thread with duties that are understood to have time requirements. Here is a simple usage:
```
public class SleepMessages {
    public static void main(String args[])
        throws InterruptedException {
        String importantInfo[] = {
            "Sathvik rocks",
            "Sathvik Softech rocks",
            "Chandan Purohit",
        };

        for (int i = 0;
             i < importantInfo.length;
             i++) {
            //Pause for 4 seconds
            Thread.sleep(4000);
            //Print a message
            System.out.println(importantInfo[i]);
        }
    }
}
```
Notice that main declares that it throws InterruptedException. This is an exception that sleep throws when another thread interrupts the current thread while sleep is active. Since this application has not defined another thread to cause the interrupt, it doesn't bother to catch InterruptedException.

##Joins

The join method allows one thread to wait for the completion of another. If t is a Thread object whose thread is currently executing, **t.join();**
causes the current thread to pause execution until t's thread terminates. Overloads of join allow the programmer to specify a waiting period. However, as with sleep, join is dependent on the OS for timing, so you should not assume that join will wait exactly as long as you specify.

Like sleep, join responds to an interrupt by exiting with an InterruptedException.

##Synchronization

Threads communicate primarily by sharing access to fields and the objects reference fields refer to. This form of communication is extremely efficient, but makes two kinds of errors possible: thread interference and memory consistency errors. The tool needed to prevent these errors is synchronization.

However, synchronization can introduce thread contention, which occurs when two or more threads try to access the same resource simultaneously and cause the Java runtime to execute one or more threads more slowly, or even suspend their execution. Starvation and livelock are forms of thread contention

##Thread Interference

Consider a simple class called Counter

```
class Counter {
    private int c = 0;

    public void increment() {
        c++;
    }

    public void decrement() {
        c--;
    }

    public int value() {
        return c;
    }

}
```
Counter is designed so that each invocation of increment will add 1 to c, and each invocation of decrement will subtract 1 from c. However, if a Counter object is referenced from multiple threads, interference between threads may prevent this from happening as expected.

Interference happens when two operations, running in different threads, but acting on the same data, interleave. This means that the two operations consist of multiple steps, and the sequences of steps overlap.

It might not seem possible for operations on instances of Counter to interleave, since both operations on c are single, simple statements. However, even simple statements can translate to multiple steps by the virtual machine. We won't examine the specific steps the virtual machine takes — it is enough to know that the single expression c++ can be decomposed into three steps:

Retrieve the current value of c.
Increment the retrieved value by 1.
Store the incremented value back in c.
The expression c-- can be decomposed the same way, except that the second step decrements instead of increments.

Suppose Thread A invokes increment at about the same time Thread B invokes decrement. If the initial value of c is 0, their interleaved actions might follow this sequence:

1)Thread A: Retrieve c.

2)Thread B: Retrieve c.

3)Thread A: Increment retrieved value; result is 1.

4)Thread B: Decrement retrieved value; result is -1.

5)Thread A: Store result in c; c is now 1.

6)Thread B: Store result in c; c is now -1.

7)Thread A's result is lost, overwritten by Thread B. 

This particular interleaving is only one possibility. Under different circumstances it might be Thread B's result that gets lost, or there could be no error at all. Because they are unpredictable, thread interference bugs can be difficult to detect and fix.

##Synchronized methods

The Java programming language provides two basic synchronization idioms: synchronized methods and synchronized statements. The more complex of the two, synchronized statements, are described in the next section. This section is about synchronized methods.

To make a method synchronized, simply add the synchronized keyword to its declaration:
```
public class SynchronizedCounter {
    private int c = 0;

    public synchronized void increment() {
        c++;
    }

    public synchronized void decrement() {
        c--;
    }

    public synchronized int value() {
        return c;
    }
}
```
If count is an instance of SynchronizedCounter, then making these methods synchronized has two effects:







