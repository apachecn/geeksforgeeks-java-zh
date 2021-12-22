# Java 中 Thread.start()和 Thread.run()的区别

> 原文:[https://www . geesforgeks . org/线程启动和线程运行在 java 中的区别/](https://www.geeksforgeeks.org/difference-between-thread-start-and-thread-run-in-java/)

在 [Java 的多线程概念](https://www.geeksforgeeks.org/multithreading-in-java/)中， **start()** 和 **run()** 是最重要的两种方法。以下是[螺纹启动()](https://www.geeksforgeeks.org/start-function-multithreading-java/)和[螺纹运行()](https://www.geeksforgeeks.org/java-lang-thread-class-java/)方法之间的一些区别:

1.  **New Thread creation:** When a program calls the *start()* method, a new thread is created and then the *run()* method is executed. But if we directly call the *run()* method then no new thread will be created and *run()* method will be executed as a normal method call on the current calling thread itself and no multi-threading will take place.
    Let us understand it with an example:

    ```
    class MyThread extends Thread {
        public void run()
        {
            System.out.println("Current thread name: "
                               + Thread.currentThread().getName());
            System.out.println("run() method called");
        }
    }

    class GeeksforGeeks {
        public static void main(String[] args)
        {
            MyThread t = new MyThread();
            t.start();
        }
    }
    ```

    **Output:**

    ```
    Current thread name: Thread-0
    run() method called

    ```

    从上面的例子中我们可以看到，当我们调用线程类实例的 *start()* 方法时，会创建一个默认名称为 *Thread-0* 的新线程，然后调用 *run()* 方法，并在新创建的线程上执行其中的所有内容。
    现在，让我们尝试直接调用 *run()* 方法，而不是 *start()* 方法:

    ```
    class MyThread extends Thread {
        public void run()
        {
            System.out.println("Current thread name: "
                               + Thread.currentThread().getName());

            System.out.println("run() method called");
        }
    }

    class GeeksforGeeks {
        public static void main(String[] args)
        {
            MyThread t = new MyThread();
            t.run();
        }
    }
    ```

    **Output:**

    ```
    Current thread name: main
    run() method called

    ```

    从上面的例子中我们可以看到，当我们调用我们的 MyThread 类的 *run()* 方法时，没有创建新的线程，并且 *run()* 方法在当前线程即*主*线程上执行。因此，没有发生多线程。 *run()* 方法作为普通函数调用调用。

2.  **Multiple invocation:** In Java’s multi-threading concept, another most important difference between *start()* and *run()* method is that we can’t call the *start()* method twice otherwise it will throw an *IllegalStateException* whereas *run()* method can be called multiple times as it is just a normal method calling.
    Let us understand it with an example:

    ```
    class MyThread extends Thread {
        public void run()
        {
            System.out.println("Current thread name: "
                               + Thread.currentThread().getName());

            System.out.println("run() method called");
        }
    }

    class GeeksforGeeks {
        public static void main(String[] args)
        {
            MyThread t = new MyThread();
            t.start();
            t.start();
        }
    }
    ```

    **输出**:

    ```
    Current thread name: Thread-0
    run() method called
    Exception in thread "main" java.lang.IllegalThreadStateException
        at java.lang.Thread.start(Thread.java:708)
        at GeeksforGeeks.main(File.java:11)

    ```

    从上面的例子中我们可以看到，再次调用 *start()* 方法会引发*Java . lang . illegalthreadstatexception*。
    现在，让我们试着调用 *run()* 方法两次:

    ```
    class MyThread extends Thread {
        public void run()
        {
            System.out.println("Current thread name: "
                               + Thread.currentThread().getName());
            System.out.println("run() method called");
        }
    }

    class GeeksforGeeks {
        public static void main(String[] args)
        {
            MyThread t = new MyThread();
            t.run();
            t.run();
        }
    }
    ```

    **Output:**

    ```
    Current thread name: main
    run() method called
    Current thread name: main
    run() method called

    ```

    正如我们在上面的例子中所看到的，两次调用 *run()* 方法不会引发任何异常，并且它会像预期的那样执行两次，但是是在*主*线程本身上执行的。

    <center>**Summary**</center>

    | 开始() | 运行() |
    | --- | --- |
    | 创建一个新线程，并在新创建的线程上执行 run()方法。 | 不会创建新线程，run()方法会在调用线程本身上执行。 |
    | 不能多次调用，否则抛出*Java . lang . illegalstatexception* | 多次调用是可能的 |
    | 在 *java.lang.Thread* 类中定义。 | 在 *java.lang.Runnable* 接口中定义，必须在实现类中重写。 |