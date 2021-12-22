# Java 中的 Java.lang.ThreadLocal 类

> 原文:[https://www . geesforgeks . org/Java-lang-thread local-class-Java/](https://www.geeksforgeeks.org/java-lang-threadlocal-class-java/)

这个类提供线程局部变量。这些变量不同于正常的对应变量，因为每个访问一个变量的线程(通过其 get 或 set 方法)都有自己独立初始化的变量副本。

*   基本上，除了编写不可变的类之外，这是实现线程安全的另一种方式。
*   由于对象不再被共享，因此不需要同步来提高应用程序的可伸缩性和性能。
*   它扩展了类对象。
*   ThreadLocal 提供线程限制，这是局部变量的扩展。ThreadLocal 仅在单线程中可见。没有两个线程可以看到对方线程的局部变量。
*   这些变量通常是类中私有静态字段，并在线程内部维护其状态。

**构造函数:**
**ThreadLocal():** 这将创建一个线程局部变量。
**方法:**

1.  **Object get():** 这个方法返回这个线程局部变量在当前线程副本中的值。如果变量没有当前线程的值，则首先将其初始化为通过调用 initialValue()方法返回的值。

    ```java
    Syntax: public Object get().
    Returns: the current thread's value of this thread-local.
    Exception: NA.

    ```

2.  **void set(Object 值):**此方法将当前线程对此线程局部变量的副本设置为指定值。大多数子类不需要重写这个方法，只需要依赖 initialValue()方法来设置线程局部变量的值。

```java
Syntax: public void set(T value).
Returns: NA.
Exception: NA.

```

```java
// Java code illustrating get() and set() method

public class ThreadLocalDemo {

public static void main(String[] args)
    {

        ThreadLocal<Number> gfg_local = new ThreadLocal<Number>();

        ThreadLocal<String> gfg = new ThreadLocal<String>();
        // setting the value
        gfg_local.set(100);

        // returns the current thread's value
        System.out.println("value = " + gfg_local.get());

        // setting the value
        gfg_local.set(90);

        // returns the current thread's value of
        System.out.println("value = " + gfg_local.get());

        // setting the value
        gfg_local.set(88.45);

        // returns the current thread's value of
        System.out.println("value = " + gfg_local.get());

        // setting the value
        gfg.set("GeeksforGeeks");

        // returns the current thread's value of
        System.out.println("value = " + gfg.get());
    }
}
```

输出:

```java
value = 100
value = 90
value = 88.45
value = GeeksforGeeks

```

*   **void remove():** This method removes the current thread’s value for this thread-local variable. If this thread-local variable is subsequently read by the current thread, its value will be reinitialized by invoking its initialValue() method, unless its value is set by the current thread in the interim. This may result in multiple invocations of the initialValue method in the current thread.

    ```java
    Syntax: public void remove().
    Returns: NA.
    Exception: NA.

    ```

    ```java
    // Java code illustrating remove() method

    public class ThreadLocalDemo {

    public static void main(String[] args)
        {

            ThreadLocal<Number> gfg_local = new ThreadLocal<Number>();

            ThreadLocal<String> gfg = new ThreadLocal<String>();

            // setting the value
            gfg_local.set(100);

            // returns the current thread's value
            System.out.println("value = " + gfg_local.get());

            // setting the value
            gfg_local.set(90);

            // returns the current thread's value of
            System.out.println("value = " + gfg_local.get());

            // setting the value
            gfg_local.set(88.45);

            // returns the current thread's value of
            System.out.println("value = " + gfg_local.get());

            // setting the value
            gfg.set("GeeksforGeeks");

            // returns the current thread's value of
            System.out.println("value = " + gfg.get());

            // removing value
            gfg.remove();

            // returns the current thread's value of
            System.out.println("value = " + gfg.get());

            // removing vale
            gfg_local.remove();

            // returns the current thread's value of
            System.out.println("value = " + gfg_local.get());
        }
    }
    ```

    输出:

    ```java
    value = 100
    value = 90
    value = 88.45
    value = GeeksforGeeks
    value = null
    value = null

    ```

    *   **Object initialValue():** This method returns the current thread’s initial value for this thread-local variable.

    ```java
    Syntax: protected Object initialValue()
    Returns: the initial value for this thread-local.
    Exception: NA.

    ```

    ```java
    // Java code illustrating initialValue() method
    import java.lang.*;
    class NewThread extends Thread {
    private static ThreadLocal gfg = new ThreadLocal(){
            protected Object initialValue(){
                return new Integer(question--);
    }
    }
    ;

    private static int question = 15;
    NewThread(String name)
    {
        super(name);
        start();
    }

    public void run()
    {
        for (int i = 0; i < 2; i++)
            System.out.println(getName() + " " + gfg.get());
    }
    }

    public class ThreadLocalDemo {

    public static void main(String[] args)
        {

            NewThread t1 = new NewThread("quiz1");
            NewThread t2 = new NewThread("quiz2");
        }
    }
    ```

    输出:

    ```java
    quiz2 14
    quiz1 15
    quiz1 15
    quiz2 14

    ```

    本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。