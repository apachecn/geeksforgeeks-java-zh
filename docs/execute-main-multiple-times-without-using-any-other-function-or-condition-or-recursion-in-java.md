# 在 Java 中多次执行 main()而不使用任何其他函数或条件或递归

> 原文:[https://www . geesforgeks . org/execute-main-多次不使用任何其他函数或条件或递归的 java/](https://www.geeksforgeeks.org/execute-main-multiple-times-without-using-any-other-function-or-condition-or-recursion-in-java/)

给定的任务是多次执行 main()而不使用任何其他函数，并且不递归()也不出错。给定的条件是，如果执行 main() n 次，那么你只能调用他(n-1)次。

**解:**

```java
class Test {

    // static block
    static
    {
        main(new String[] { "Hello" });
    }
    public static void main(String[] args)
    {
        System.out.println("Hii");
    }
}
```

**输出:**

```java
Hii
Hii

```

**说明:**静态块甚至在 main()执行之前就执行了。这里首先通过静态块调用 main()，然后 JVM(Java 虚拟机)调用 main()。因此，main()只通过调用一次来执行两次。