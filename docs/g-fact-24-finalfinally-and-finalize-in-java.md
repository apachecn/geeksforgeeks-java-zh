# 最终，最后用 Java

定案

> 原文:[https://www . geesforgeks . org/g-fact-24-final-final-和-final-in-Java/](https://www.geeksforgeeks.org/g-fact-24-finalfinally-and-finalize-in-java/)

这是一个关于面试观点的重要问题。

[**最终关键词**](https://www.geeksforgeeks.org/final-keyword-java/)

final(小写)是 java 中的保留关键字。我们不能将其用作标识符，因为它是保留的。我们可以在变量、方法和类中使用这个关键字。java 中的 final 关键字有不同的含义，这取决于它应用于变量、类或方法。

*   **最终变量:**变量的值一旦初始化就不能更改。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class A {
    public static void main(String[] args)
    {
        // Non final variable
        int a = 5;

        // final variable
        final int b = 6;

        // modifying the non final variable : Allowed
        a++;

        // modifying the final variable : 
        // Immediately gives Compile Time error.
        b++;
    }
}
```