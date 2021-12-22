# Java . util . concurrent . exchange 类，带示例

> 原文:[https://www . geesforgeks . org/Java-util-concurrent-exchange-class-with-examples/](https://www.geeksforgeeks.org/java-util-concurrent-exchanger-class-with-examples/)

**交换器**是 [Java](https://www.geeksforgeeks.org/java/) 最有意思的**同步类**。它通过创建一个同步点，方便了一对线程之间的**元素交换。它简化了两个线程之间的数据交换。它的操作很简单:只需等待两个独立的线程调用它的 **exchange()** 方法。当这种情况发生时，它交换线程提供的数据。也可以看作是**双向同步队列**。它是一个泛型类，声明如下。**

**类语法:**

```
Exchanger<V>
```

这里，V 指定正在交换的数据类型。

**等级体系**

```
java.lang.Object
↳ java.util.concurrent.Exchanger<V>

```

**构造函数:**

1.  **[switch ()]** –Create a new switch object with default values for its members.

**方法:**

1.  **交换(V x)**–当调用此函数时，会导致当前线程暂停其执行，并等待另一个线程调用其交换方法。当另一个线程调用它的交换方法时，线程交换它们的数据，执行继续。

    **语法:**

    ```
    public V exchange(V x)
    throws InterruptedException

    ```

2.  **交换(V x，长超时，time unit unit)**–当调用此函数时，会导致当前线程暂停其执行，等待另一个线程调用其交换方法。当另一个线程调用它的交换方法时，线程交换它们的数据，执行继续。线程只等待超时参数指定的持续时间，如果超时持续时间已过，将引发超时异常。

    **语法:**

    ```
    public V exchange(V x, long timeout, TimeUnit unit)
    throws InterruptedException, TimeoutException

    ```

**示例演示交换机类的工作:**

```
import java.util.concurrent.Exchanger;
import java.util.concurrent.TimeUnit;
import java.util.concurrent.TimeoutException;

public class ExchangerDemo {
    public static void main(String[] args)
    {
        Exchanger<String> exchanger = new Exchanger<>();

        new UseString(exchanger);
        new MakeString(exchanger);
    }
}

// A thread that makes a string
class MakeString implements Runnable {
    Exchanger<String> ex;
    String str;

    MakeString(Exchanger<String> ex)
    {
        this.ex = ex;
        str = new String();

        new Thread(this).start();
    }

    public void run()
    {
        char ch = 'A';
        try {
            for (int i = 0; i < 3; i++) {
                for (int j = 0; j < 5; j++) {
                    str += ch++;
                }
                if (i == 2) {
                    // Exchange the buffer and
                    // only wait for 250 milliseconds
                    str
                        = ex.exchange(str,
                                      250,
                                      TimeUnit.MILLISECONDS);
                    continue;
                }

                // Exchange a full buffer for an empty one
                str = ex.exchange(str);
            }
        }
        catch (InterruptedException e) {
            System.out.println(e);
        }
        catch (TimeoutException t) {
            System.out.println("Timeout Occurred");
        }
    }
}

// A thread that uses a string
class UseString implements Runnable {

    Exchanger<String> ex;
    String str;

    UseString(Exchanger<String> ex)
    {
        this.ex = ex;

        new Thread(this).start();
    }

    public void run()
    {
        try {
            for (int i = 0; i < 3; i++) {
                if (i == 2) {
                    // Thread sleeps for 500 milliseconds
                    // causing timeout
                    Thread.sleep(500);
                    continue;
                }

                // Exchange an empty buffer for a full one
                str = ex.exchange(new String());
                System.out.println("Got: " + str);
            }
        }
        catch (InterruptedException e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Got: ABCDE
Got: FGHIJ
Timeout Occurred

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/exchange . html](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/Exchanger.html)