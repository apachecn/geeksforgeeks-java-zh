# Java system . nanotime()vs . system . currenttimemillis

> 原文:[https://www . geesforgeks . org/Java-system-nano time-vs-system-current timemillis/](https://www.geeksforgeeks.org/java-system-nanotime-vs-system-currenttimemillis/)

Java 提供了两种计时操作的方法，System.nanoTime()和 System.currentTimeMillis()。但是哪一个应该在什么条件下使用呢？哪个效率更高？

从第一眼看上去，似乎应该使用 nanoTime()，因为它给出了更精确的时间值(以纳米秒为单位，而另一种方法返回的是毫秒)。但是在 CPU 上使用 nanoTime 总是高效的吗？让我们看看使用这两种方法的利弊:

**system . CurrentMemillis()**

```
public static long currentTimeMillis()
// Returns the current time in milliseconds.

```

**优点:**

1.  是*线程安全*。线程安全意味着，如果在两个或多个不同的线程之间调用此方法，它将不会返回错误的结果。
2.  始终返回自*纪元*以来经过的绝对时间(自 1970 年 1 月 1 日 00:00 以来的毫秒数)。
3.  执行消耗较少的时钟周期(大约 5-6 个 cpu 时钟)。
4.  给出更多 ***精确的*** 时间，因为参考点(历元)是固定的。

cons:t1]

1.  少 ***精*** 。结果在 1/1000 到 15/1000 秒之间。在某些机器上，分辨率甚至低于 50 毫秒，最高只能达到 10 毫秒。
2.  如果用户更改系统时间、达到闰秒或 NTP 同步有变化，可能会给出错误的结果。

**System.nanoTime()**

```
public static long nanoTime()
// Returns the current value of the running JVM's high-resolution
// time source, in nanoseconds.

```

**优点:**

1.  高度 ***精确*** 。返回的时间大约是 1/1000000 秒。
2.  分辨率远高于*currentimemillis()*。

cons:t1]

1.  反映的结果没有任何固定的参考点。根据 Java 文档，

    ```
    The value returned represents nanoseconds since some fixed
    but arbitrary time (perhaps in the future, so values may be negative).
    ```

2.  少 ***准*** 。该方法提供纳秒精度，但不一定是纳秒精度。无法保证值更改的频率。
3.  根据系统的不同，执行可能需要 100 多个 cpu 周期。
4.  不是*线程安全*。如果在多个线程之间使用，可能会返回错误的结果。

让我们看一个工作示例来比较这两个函数的结果:

```
// Java program to illustrate
// difference between
// Java System.nanoTime()
// and System.currentTimeMillis
class Main {
    public static void main(String[] args)
    {
        // Get the current system time in
        // both nano and milli-seconds before
        // calling the function.
        long nano_startTime = System.nanoTime();
        long millis_startTime = System.currentTimeMillis();

        // Perform the work whose time is to be measured
        someFunction();

        // Get the current system time in both
        // nano and milli-seconds after
        // the function returns.
        long nano_endTime = System.nanoTime();
        long millis_endTime = System.currentTimeMillis();

        // Print the time taken by subtracting
        // the end-time from the start-time
        System.out.println("Time taken in nano seconds: "
                           + (nano_endTime - nano_startTime));
        System.out.println("Time taken in milli seconds: "
                           + (millis_endTime - millis_startTime));
    }

    // The function whose execution
    // time is to be measured
    public static void someFunction()
    {
        for (int i = 0; i < Integer.MAX_VALUE; i++) {
            for (int j = 0; j < Integer.MAX_VALUE; j++) {
                // Here for example purpose
                // we run an empty loop
            }
        }
    }
}
```

**输出:**

```
Time taken in nano seconds: 2519657
Time taken in milli seconds: 3

```

**总之**、**每当要执行高精度任务**时，都可以/必须使用 System.nanoTime()，因为看起来几毫秒的精度就足够了，但是对于需要快速性能的应用程序(如游戏)来说，nanoTime()会给出更好的结果。
但是，由于计算开销和与线程安全相关的风险，应该尽可能避免这种情况，在这种情况下，将使用 currentTimeMillis()。