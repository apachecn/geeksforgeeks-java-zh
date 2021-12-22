# 实现 CAS(比较和交换)算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-cas-比较和交换-算法/](https://www.geeksforgeeks.org/java-program-to-implement-cas-compare-and-swap-algorithm/)

**比较和交换**是设计并发算法时使用的一种技术。方法是将变量的实际值与变量的预期值进行比较，如果实际值与预期值匹配，则用变量的实际值替换传入的新值。

要理解算法，必须具备 Java 中[并发](https://www.geeksforgeeks.org/java-concurrency-yield-sleep-and-join-methods/)和[多线程](https://www.geeksforgeeks.org/multithreading-in-java/)的基础知识。

**算法工作:**

就好像我们知道这个变量应该是 1，我们想把它改成 2。由于这是一个**多线程环境，**我们知道其他人可能正在处理同一个变量。因此，我们应该首先检查变量的值是否如我们所想的是 1，如果是，那么我们将其更改为 2。如果我们现在看到变量是 3，那么这意味着其他人正在处理它，所以我们现在不要碰它。

**检查然后行动接近** :-

并发问题最常见的情况是**“先检查后行动”**的方法。当代码首先检查变量值，然后基于该值进行操作时，就会发生“先检查后操作”的情况。这里有一个简单的例子:

```java
public boolean lock() {
    if(!locked) {
        lock = true;
        return true;
    }
    return false;
}
```

> 上面，伪代码意味着，如果它已经被锁定，你不需要再次锁定。所以你首先**检查**并且只有在需要的时候，**行动**。

上面的代码并不安全，因为如果两个或多个线程可以同时访问 lock()函数并进行检查，那么上面的 **lock()** 函数将不能保证工作，因为所有线程都会锁定资源并将其作为自己的资源使用。

**我们细说一下:**

存在**线程 A** 和**线程 B** ，线程 B 可以在线程 A 已经检查锁定并且看到它是假的之间的任何时间检查锁定，那么线程 A 和线程 B 都可以看到锁定是假的，然后两者都将基于该信息而行动。

上述问题可以通过同步整个代码块来解决。那么一次只有一个线程(线程 A 或线程 B)进行检查并采取行动，只有在进入代码的线程完成检查并采取行动之后，另一个线程才能尝试。现在线程之间不会有误会了。

**同步代码示例:**

```java
class GFG {

    private boolean locked = false;

    public synchronized boolean lock() {
        if(!locked) {
            locked = true;
            return true;
        }
        return false;
    }
}
```

现在 lock()方法是同步的，所以一次只有一个线程可以在同一个 lock()函数上执行它。

**原子操作**

在 Java 5 之后，我们不再需要用 check and act 代码来实现或编写同步块，Java 5 通过**Java . util . concurrent . atomic:**提供了这种支持，这是一个用于对单个变量进行无锁、线程安全编程的类工具包。

**AtomicBoolean** 确保一次只有一个线程可以读取。

下面是一个示例，展示了如何使用**原子工具**实现 lock()方法:

```java
public static class MyLock {
    private AtomicBoolean locked = new AtomicBoolean(false);

    public boolean lock() {
        return locked.compareAndSet(false, true);
    }

}
```

请注意，锁定的变量不再是一个布尔值，而是一个原子对象。这个类有一个 **compareAndSet()** 函数，它会将 AtomicBoolean 实例的值与期望值进行比较，如果有期望值，它会用一个新值交换该值。在这种情况下，它将 locked 的值与 false 进行比较，如果为 false，它将 AtomicBoolean 的新值设置为 true。

如果值被交换，compareAndSet()方法返回 true，否则返回 false。

还有很多其他原子变量，比如:

*   [**atomic integer**](https://www.geeksforgeeks.org/atomicinteger-compareandset-method-in-java-with-examples/)**:**这个变量可以让你自动更新一个 int 值。
*   [**AtomicLong:**](https://www.geeksforgeeks.org/atomiclong-compareandset-method-in-java-with-examples/)**Long 具有线程安全的“比较和交换”功能。**
*   **[**原子引用:**](https://www.geeksforgeeks.org/atomicreference-compareandset-method-in-java-with-examples/) 这个变量提供了一个可以原子读写的对象引用变量。**
*   ****原子闪烁阵列、原子闪烁阵列和原子闪烁阵列****

****原子整数示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to demonstrates 
// the compareAndSet() function 

import java.util.concurrent.atomic.AtomicInteger; 

public class GFG { 
    public static void main(String args[]) 
    { 

        // Initially value as 0 
        AtomicInteger val = new AtomicInteger(0); 

        // Prints the updated value 
        System.out.println("Previous value: "
                           + val); 

        // Checks if previous value was 0 
        // and then updates it 
        boolean res = val.compareAndSet(0, 6); 

        // Checks if the value was updated. 
        if (res) 
            System.out.println("The value was"
                               + " updated and it is "
                               + val); 
        else
            System.out.println("The value was "
                               + "not updated"); 
    } 
}
```

****Output**

```java
Previous value: 0
The value was updated and it is 6

```** 

> **当多个线程试图使用 **CAS** (比较和交换)算法同时更新同一个变量时，一个线程获胜并更新该变量的值，其余线程失败。但是失败者不会因为挂线而受到惩罚。他们可以自由地重试操作，或者干脆什么也不做。**