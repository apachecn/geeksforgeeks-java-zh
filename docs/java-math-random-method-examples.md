# Java 数学随机()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-math-random-method-examples/](https://www.geeksforgeeks.org/java-math-random-method-examples/)

**java.lang.Math.random()** 方法返回一个大于等于 0.0 且小于 1.0 的伪随机双类型数。。当第一次调用这个方法时，它会创建一个新的伪随机数发生器
，就像表达式 new java.util.Random 一样

**语法:**

```
public static double random()

Return :
This method returns a pseudorandom double greater than or equal to 0.0 and less than 1.0.
```

**例 1 :** 展示 **java.lang.Math.random()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.random() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // Generate random number
        double rand = Math.random();

        // Output is different everytime this code is executed
        System.out.println("Random Number:" + rand);
    }
}
```

**输出:**

```
0.5568515217910215

```

**例 2 :** 展示 **java.lang.Math.random()** 方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.random() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        // define the range
        int max = 10;
        int min = 1;
        int range = max - min + 1;

        // generate random numbers within 1 to 10
        for (int i = 0; i < 10; i++) {
            int rand = (int)(Math.random() * range) + min;

            // Output is different everytime this code is executed
            System.out.println(rand);
        }
    }
}
```

**输出:**

```
6
8
10
10
5
3
6
10
4
2

```