# 演示单例类双重检查锁定的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-program-to-演示-双重检查-锁定单例类/](https://www.geeksforgeeks.org/java-program-to-demonstrate-the-double-check-locking-for-singleton-class/)

初级开发人员面临的关键挑战之一是如何保持 Singleton 类为 Singleton，即如何防止 Singleton 类的多个实例。Singleton 的双重检查锁定是一种确保在应用程序生命周期中只创建 Singleton 类的一个实例的方法。在双重检查锁定中，代码在锁定和不锁定的情况下检查两次 [Singleton 类](https://www.geeksforgeeks.org/singleton-class-java/)的现有实例，以确保只创建一个 Singleton 实例。

**需要对单体类进行双重检查锁定:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
private static Singleton instance;

public static Singleton getInstance1()
{
    if (instance == null) {
        instance = new Singleton();
    }
    return instance;
}
```

*   如果由多个线程并行调用，上面的代码将创建 Singleton 类的多个实例(称为多线程)。
*   当前问题的主要解决方案将是使[**getInstance()**](https://www.geeksforgeeks.org/java-signature-getinstance-method-with-examples/#:~:text=The%20getInstance()%20method%20of,with%20the%20most%20preferred%20Provider.)**方法同步。**
*   **虽然它是线程安全的，并且解决了多个实例的问题，但是效率不是很高。每次调用这个方法都需要承担同步的成本，而同步只需要在创建 Singleton 实例的第一个类上进行。**

**这就把我们带到了**双重检查锁定模式，**只有代码的关键部分被锁定。**

****为什么叫双重检查锁定？****

*   **它被称为双重检查锁定，因为有两个检查，例如== null，一个没有锁定，另一个有锁定(在同步块内部)。**

****双重检查锁定在 Java 中的样子:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
public static Singleton getInstance2()
{   // Single Checked
    if (instance == null) { 

        synchronized (Singleton.class)
        { 
            // Double checked
            if (instance == null) { 
                instance = new Singleton();
            }
        }
    }
    return instance;
}
```

****对 Singleton 类实现双重检查锁定:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to write double checked locking 
// of Singleton class

class Singleton {
    private volatile static Singleton instance;

    private Singleton() {}

    // 1st version: creates multiple instances if two thread
    // access this method simultaneously
    public static Singleton getInstance1()
    {
        if (instance == null) {
            instance = new Singleton();
        }

        return instance;
    }

    // 2nd version : this is thread-safe and only
    // creates one instance of Singleton on concurrent
    // environment but it is unnecessarily expensive due to
    // cost of synchronization at every call.
    public static synchronized Singleton getInstance2()
    {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }

    // 3rd version : An implementation of double checked
    // locking of Singleton. Intention is to reduce cost
    // of synchronization and improve performance, by only
    // locking critical section of code, the code which
    // creates instance of Singleton class.
    public static Singleton getInstance3()
    {
        if (instance == null) {
            synchronized (Singleton.class)
            {
                if (instance == null) {
                    instance = new Singleton();
                }
            }
        }
        return instance;
    }
}
```