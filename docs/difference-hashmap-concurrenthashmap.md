# 【HashMap 和 ConcurrentHashMap 的区别

> 原文:[https://www . geesforgeks . org/difference-hashmap-concurrenthashmap/](https://www.geeksforgeeks.org/difference-hashmap-concurrenthashmap/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 是传统集合下的类，ConcurrentHashMap 是并发集合下的类，除此之外，它们之间还有各种不同之处，分别是:

*   HashMap 本质上是非同步的，即 HashMap 不是线程安全的，而 ConcurrentHashMap 本质上是线程安全的。
*   HashMap 的性能相对较高，因为它本质上是非同步的，任何数量的线程都可以同时执行。但是 ConcurrentHashMap 的性能有时很低，因为有时需要线程来等待 ConcurrentHashMap。
*   While one thread is Iterating the HashMap object, if other thread try to add/modify the contents of Object then we will get Run-time exception saying **ConcurrentModificationException**.Whereas In ConcurrentHashMap we wont get any exception while performing any modification at the time of Iteration.

    **使用 HashMap**

    ```
    // Java program to illustrate
    // HashMap drawbacks
    import java.util.HashMap;

    class HashMapDemo extends Thread
    {
        static HashMap<Integer,String> l=new HashMap<Integer,String>();

        public void run()
        {

            try
            {
                Thread.sleep(1000);
                // Child thread trying to add
                // new element in the object
                l.put(103,"D");
            }
            catch(InterruptedException e)
            {
                System.out.println("Child Thread going to add element");
            }
        }

        public static void main(String[] args) throws InterruptedException
        {
            l.put(100,"A");
            l.put(101,"B");
            l.put(102,"C");
            HashMapDemo t=new HashMapDemo();
            t.start();

            for (Object o : l.entrySet()) 
            {
                Object s=o;
                System.out.println(s);
                Thread.sleep(1000);
            }
            System.out.println(l);
        }
    }
    ```

    **输出:**

    ```
    100=A
    Exception in thread "main" java.util.ConcurrentModificationException

    ```

    **使用 ConcurrentHashMap**

    ```
    // Java program to illustrate
    // HashMap drawbacks
    import java.util.HashMap;
    import java.util.concurrent.*;

    class HashMapDemo extends Thread
    {
        static ConcurrentHashMap<Integer,String> l = 
                           new ConcurrentHashMap<Integer,String>();

        public void run()
        {

            // Child add new element in the object
            l.put(103,"D");

            try
            {
                Thread.sleep(2000);
            }
            catch(InterruptedException e)
            {
                System.out.println("Child Thread going to add element");
            }
        }

        public static void main(String[] args) throws InterruptedException
        {
            l.put(100,"A");
            l.put(101,"B");
            l.put(102,"C");
            HashMapDemo t=new HashMapDemo();
            t.start();

            for (Object o : l.entrySet()) 
            {
                Object s=o;
                System.out.println(s);
                Thread.sleep(1000);
            }
            System.out.println(l);
        }
    }
    ```

    **输出:**

    ```
    100=A
    101=B
    102=C
    103=D
    {100=A, 101=B, 102=C, 103=D}

    ```

*   In HashMap, null values are allowed for key and values, whereas in ConcurrentHashMap null value is not allowed for key and value, otherwise we will get Run-time exception saying **NullPointerException.**

    **使用 HashMap**

    ```
    //Java Program to illustrate ConcurrentHashMap behaviour
    import java.util.*;
    class ConcurrentHashMapDemo
    {
        public static void main(String[] args)
        {
            HashMap m=new HashMap();
            m.put(100,"Hello");
            m.put(101,"Geeks");
            m.put(102,"Geeks");
            m.put(null,"World");
            System.out.println(m);
        }
    } 
    ```

    输出:

    ```
    {null=World, 100=Hello, 101=Geeks, 102=Geeks}

    ```

    **使用 ConcurrentHashMap**

    ```
    //Java Program to illustrate HashMap behaviour
    import java.util.concurrent.*;
    class ConcurrentHashMapDemo
    {
        public static void main(String[] args)
        {
            ConcurrentHashMap m=new ConcurrentHashMap();
            m.put(100,"Hello");
            m.put(101,"Geeks");
            m.put(102,"Geeks");
            m.put(null,"World");
            System.out.println(m);
        }
    } 
    ```

    **输出:**

    ```
    Exception in thread "main" java.lang.NullPointerException

    ```

*   HashMap 是在 JDK 1.2 中引入的，而 ConcurrentHashMap 是由 SUN 微系统在 JDK 1.5 中引入的。