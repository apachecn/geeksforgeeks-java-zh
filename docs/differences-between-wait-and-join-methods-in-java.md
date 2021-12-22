# Java 中 wait()和 join()方法的区别

> 原文:[https://www . geesforgeks . org/wait-and-join-methods-in-Java/](https://www.geeksforgeeks.org/differences-between-wait-and-join-methods-in-java/)

> wait()和 join()方法用于暂停当前线程。wait()与 notifyAll()和 notifyAll()方法一起使用，但 join()在 Java 中用于等待直到一个线程完成其执行。
> wait()主要用于共享资源，一个线程在资源空闲时通知其他等待线程。另一方面，join()用于等待线程死亡。

【wait()和 join() 的相似之处

*   方法 wait()和 join()都用于在 Java 中暂停当前线程。
*   wait()和 join()都可以通过在 Java 中调用 interrupt()方法来中断。
*   wait()和 join()都是非静态方法。
*   在 Java 中，wait()和 join()都是重载的。wait()和 join()没有超时，并且接受超时参数。

【wait()和 join()方法的区别

*   最明显的区别是，两者呈现不同的包，wait()方法在 java.lang.Object 类中声明，而 join()在 java.lang.Thread 类中声明。
*   wait()用于线程间通信，join()用于在多个线程之间添加排序，一个线程在第一个线程执行完成后开始执行。
*   我们可以通过使用 notify()和 notifyAll()方法启动一个等待线程(通过调用 wait()进入这种状态)，但是我们不能毫无中断地中断 join 强加的等待，除非调用 join 的线程已经执行完毕。
*   One most important difference between wait() and join() that is wait() must be called from synchronized context i.e. synchronized block or method otherwise it will throw IllegalMonitorStateException but On the other hand, we can call join() method with and without synchronized context in Java.

    **加入示例**

    ```
    // Java program to explain the use of join()

    class A extends Thread {

        @Override
        public void run()
        {
            for (int i = 1; i <= 4; i++) {
                try {
                    Thread.sleep(100);
                }
                catch (Exception e) {
                    System.out.println(e);
                }
                System.out.print(i + " ");
            }
        }
    }

    class B extends Thread {

        @Override
        public void run()
        {
            for (char i = 'a'; i <= 'd'; i++) {
                try {
                    Thread.sleep(100);
                }
                catch (Exception e) {
                    System.out.println(e);
                }
                System.out.print(i + " ");
            }
        }
    }

    class GFG extends Thread {

        public static void main(String args[])
        {
            // creating two threads
            A a1 = new A();
            B b1 = new B();

            // starts second thread after when
            // first thread a1 is died.
            a1.start();
            try {
                a1.join();
            }
            catch (Exception e) {
                System.out.println(e);
            }

            // after thread a1 execution finished
            // then b1 thread start
            b1.start();
        }
    }
    ```

    **输出:**

    ```
    1 2 3 4 a b c d 

    ```

    **等待示例**

    ```
    // Java program to explain the
    // concept of Waiting a thread.

    class PNBCustomer {

        // let a initial amount is 9000
        int amount = 9000;

        // synchronized function because i wil use for
        // waiting thread. Here synchronized means inter-
        // thread communication
        synchronized void withdraw(int amount)
        {
            System.out.println("withdrawing...");

            // check if balance amount is less than withdraw
            // amount in this condition. deposit()  synchronized 
            // method call and deposit amount after that this 
            // thread again execute
            if (this.amount < amount) {

                System.out.println("Amount is not enough; waiting + 
                                               " for deposit...");
                try {
                    wait();
                }
                catch (Exception e) {
                }
            }

            System.out.println("after deposit, balance is available: " +
                                                         this.amount);
            this.amount -= amount;
            System.out.println("withdraw completed...");
            System.out.println("after Withdraw, balance is available: " + 
                                                         this.amount);
        }

        synchronized void deposit(int amount)
        {
            System.out.println("going to deposit...");
            this.amount += amount;
            System.out.println("deposit completed... ");
            notify();
        }
    }

    public class Wait {

        public static void main(String args[])
        {
            final PNBCustomer c = new PNBCustomer();
            // create two new thread and start
            // them simultaneously
            new Thread() {
                @Override
                public void run()
                {
                    c.withdraw(15000);
                }
            }.start();
            new Thread() {
                @Override
                public void run()
                {
                    c.deposit(10000);
                }
            }.start();
        }
    }
    ```

    **输出:**

    ```
    withdrawing...
    Amount is not enough; waiting for deposit...
    going to deposit...
    deposit completed... 
    after deposit, balance is available: 19000
    withdraw completed...
    after Withdraw, balance is available: 4000

    ```