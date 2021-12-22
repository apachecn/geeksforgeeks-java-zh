# Java 中可调用和可运行的区别

> 原文:[https://www . geesforgeks . org/Java 中可调用和可运行的区别/](https://www.geeksforgeeks.org/difference-between-callable-and-runnable-in-java/)

[*Java . lang . runnable*](https://www.geeksforgeeks.org/runnable-interface-in-java/)是一个接口，将由一个类实现，该类的实例将由一个线程执行。有两种方法可以开始一个新的线程——子类线程和实现可运行。当一个任务仅通过*run(*)Runnable的方法即可完成时，无需对线程进行子类化。

> [可调用接口](https://www.geeksforgeeks.org/callback-using-interfaces-java/)和[可运行接口](https://www.geeksforgeeks.org/runnable-interface-in-java/)用于封装应该由另一个线程执行的任务。

让我们讨论上述两个接口之间的差异，这是通过稍后以表格形式总结主要差异时单独讨论它们来定义的。

**可调用界面**

在一个可调用的接口中，它会抛出一个选中的异常并返回一些结果。这是即将到来的不返回值的 Runnable 接口的主要区别之一。在这个接口*、*中，它只是计算一个结果，否则如果做不到这一点，就会抛出一个异常。

```java
public interface Callable<V> 
{
  V call() throws exception ;
}
```

1.  它在“[](https://www.geeksforgeeks.org/java-util-concurrent-package/)**包中声明。**
2.  **该接口还包含一个单一的无参数方法，称为 *call()* 方法**
3.  **我们不能通过将 callable 作为参数传递来创建线程。**
4.  **Callable 可以返回结果。Callable 的 call()方法包含“抛出异常”子句，因此我们可以轻松地进一步传播检查过的异常。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
**// Java Program to illustrate Callable interface 

// Importing classes from java.util package 
import java.util.Random;  
import java.util.concurrent.Callable;  
import java.util.concurrent.FutureTask;  

// Class
// Implementing the Callable interface
class CallableExample implements Callable {

  // Main driver method  
   public static void main(String args[])
   {

      // public Object call() throws Exception  

       Random generator = new Random();  

       Integer randomNumber = generator.nextInt(5);  

       Thread.sleep(randomNumber * 1000);  

       return randomNumber;  
       }

}**
```

****可运行界面****

**当实现此接口的对象用于创建线程时，启动线程会导致在单独执行的线程中调用对象运行方法。将军。这个 run()方法的约定是它可以采取任何行动。**

```java
**public interface Runnable 
{
  public abstract void run();
}**
```

*   ***java.lang.Runnable* 是一个接口，只定义了一个名为 *run()的方法。***
*   **它用 Java 表示一个由线程执行的任务。**
*   **使用 Runnable 启动新线程有两种方法，一种是通过实现 Runnable 接口，另一种是通过子类化 thread 类。**
*   **如果您在另一个线程中执行某些计算任务，Runnable 不能返回计算结果，而这是必不可少的，Runnable 也不能抛出检查过的异常。**

****例****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
**// Java Program to implement Runnable interface

// Importing FileNotFound class from
// input output classes bundle
import java.io.FileNotFoundException;

// Class
// Implementing the Runnable interface 
public class RunnableImpl implements Runnable {

    // Main driver method
    public static void main(String[] args)
    {

        // Run method
        public void run()
        {
            // Display message when the thread executes
            System.out.println(
                Thread.currentThread().getName()
                + ", executing run() method!");

            // Try block to check if any exception occurs
            try {
                throw new FileNotFoundException();
            }

            // Catch block to handle the exception
            catch (FileNotFoundException e) {

                // Display message
                System.out.println("Must catch here!");

                // Print the line number
                // where exception occured
                e.printStackTrace();
            }

            // Here forcefully it
            int rem = 1 / 0;
        }
    }**
```

<figure class="table">

| **可运行界面** | **可调用界面** |
| --- | --- |
| 它是从 Java 1.0 开始的 [*java.lang*](https://www.geeksforgeeks.org/object-class-in-java/) 包的一部分 | 它是自 Java 1.5 以来的[](https://www.geeksforgeeks.org/java-util-concurrent-package/)**包的一部分。** |
| 它不能返回计算的返回。 | 它可以返回任务并行处理的结果。 |
| 它不能引发选中的异常。 | 它可以引发选中的异常。 |
| 在可运行的接口中，需要重写 Java 中的 run()方法。 | 为了使用 Callable，您需要重写调用() |

</figure>