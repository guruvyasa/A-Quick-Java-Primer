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

The join method allows one thread to wait for the completion of another. If t is a Thread object whose thread is currently executing,

t.join();
causes the current thread to pause execution until t's thread terminates. Overloads of join allow the programmer to specify a waiting period. However, as with sleep, join is dependent on the OS for timing, so you should not assume that join will wait exactly as long as you specify.

Like sleep, join responds to an interrupt by exiting with an InterruptedException.


