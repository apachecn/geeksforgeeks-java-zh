# Java 数学增量 xact()方法

> 原文:[https://www . geesforgeks . org/Java-math-incrementexact-method/](https://www.geeksforgeeks.org/java-math-incrementexact-method/)

IngrementXact()是 java 中的内置函数，它返回递增 1 的参数，如果结果溢出了指定的数据类型 long 或 int，将引发异常，具体取决于在方法参数上使用了哪种数据类型。

**语法:**

```
int incrementExact(int num)
long incrementExact(long num)
```

**参数:**该函数接受一个如上所示的强制参数，如下所述:

*   **num –** The parameter specifies the number which has to be incremented.

    **返回值:**该函数返回递增 1 的参数，如果结果溢出了指定的数据类型 long 或 int，则抛出异常，具体取决于方法参数使用了哪种数据类型。

    示例:

    ```
    Input : 12
    Output : 13

    Input : -3 
    Output : -2

    ```

    **程序 1:** 演示功能工作的程序

    ```
    // Java program to demonstrate working
    // of java.lang.Math.incrementExact() method
    import java.lang.Math;

    class Gfg1 {

        // driver code
        public static void main(String args[])
        {

            int y = 12;
            System.out.println(Math.incrementExact(y));

            int x = -3;
            System.out.println(Math.incrementExact(x));
        }
    }
    ```

    输出:

    ```
    13
    -2
    ```

    **程序 2:** 演示函数溢出的程序

    ```
    // Java program to demonstrate overflow
    // of java.lang.Math.incrementExact() method
    import java.lang.Math;

    class Gfg1 {

        // driver code
        public static void main(String args[])
        {

            int y = Integer.MAX_VALUE;
            System.out.println(Math.incrementExact(y));
        }
    }
    ```

    输出:

    ```
    Exception in thread "main" java.lang.ArithmeticException: integer overflow
        at java.lang.Math.incrementExact(Math.java:909)
        at Gfg1.main(File.java:12)
    ```