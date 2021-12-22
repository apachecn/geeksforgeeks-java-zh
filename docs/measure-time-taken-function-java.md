# 如何在 java 中测量一个函数花费的时间？

> 原文:[https://www . geesforgeks . org/measure-time-take-function-Java/](https://www.geeksforgeeks.org/measure-time-taken-function-java/)

借助**[Java . lang . system . CurrentMemillis()](https://www.geeksforgeeks.org/java-lang-system-class-java/)**方法，我们可以测量一个函数在 [Java](https://www.geeksforgeeks.org/java/) 中花费的时间。此方法以毫秒为单位返回当前时间。我们可以在函数的开始和结束时调用这个方法，并通过这个差值来度量函数所花费的时间。

```java
import java.io.*;

public class Time {
    public static void main(String[] args)
    {
        // starting time
        long start = System.currentTimeMillis();

        // start of function

        count_function(10000000);

        // end of function

        // ending time
        long end = System.currentTimeMillis();
        System.out.println("Counting to 10000000 takes " +
                                    (end - start) + "ms");
    }

    // A dummy function that runs a loop x times
    public static void count_function(long x)
    {
        System.out.println("Loop starts");
        for (long i = 0; i < x; i++)
            ;
        System.out.println("Loop ends");
    }
}
```

输出:

```java
Loop starts
Loop ends
Counting to 10000000 takes 8ms

```

[如何用 C 语言测量一个程序花费的时间？](https://www.geeksforgeeks.org/how-to-measure-time-taken-by-a-program-in-c/)