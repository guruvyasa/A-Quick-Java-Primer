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
