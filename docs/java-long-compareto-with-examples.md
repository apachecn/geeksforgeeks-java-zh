# Java 长 compareTo()带示例

> 原文:[https://www . geesforgeks . org/Java-long-compare to-with-examples/](https://www.geeksforgeeks.org/java-long-compareto-with-examples/)

java.lang.Long.compareTo()是 java 中的内置方法，用于对两个 Long 对象进行数值比较。如果该对象等于参数对象，则该方法返回 0；如果该对象的数值小于参数对象，则该方法返回小于 0 的值；如果该对象的数值大于参数对象，则该方法返回大于 0 的值。

**语法:**

```java
**public int compareTo(Object obj)**

Parameter: 
obj - The object which is to be compared to.

```

**返回:**函数返回三个值:

*   **等于 0:** 对象等于自变量对象
*   **小于 0:** 对象小于自变量对象
*   **大于 0:** 对象大于自变量对象

**程序 1:** 下面的程序演示了功能的工作。

```java
// Java program to demonstrate
// of java.lang.Long.compareTo() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        // when two objects are different
        Long obj1 = new Long(124);
        Long obj2 = new Long(167);
        int compareValue = obj1.compareTo(obj2);

        if (compareValue == 0)
            System.out.println("object1 and object2 are equal");
        else if (compareValue < 0)
            System.out.println("object1 is less than object2");
        else
            System.out.println("object1 is greater than object2");
    }
}
```

输出:

```java
object1 is less than object2

```

**程序 2:** 下面的程序演示了没有传递参数时函数的工作

```java
// Java program to demonstrate
// of java.lang.Long.compareTo() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // when no argument is passed
        Long obj1 = new Long(124);
        Long obj2 = new Long(167);

        int compareValue = obj1.compareTo();

        if (compareValue == 0)
            System.out.println("object1 and object2 are equal");
        else if (compareValue < 0)
            System.out.println("object1 is less than object2");
        else
            System.out.println("object1 is greater than object2");
    }
}
```

输出:

```java
prog.java:14: error: method compareTo in class Long cannot be applied to given types;
      int compareValue = obj1.compareTo(); 
                             ^
  required: Long
  found: no arguments
  reason: actual and formal argument lists differ in length
1 error

```

**程序 3:** 下面的程序演示了在参数中传递对象以外的任何东西时函数的工作

```java
// Java program to demonstrate
// of java.lang.Long.compareTo() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        // when anything other than object
        // argument is passed
        Long obj1 = new Long(124);

        int compareValue = obj1.compareTo("gfg");

        if (compareValue == 0)
            System.out.println("object1 and object2 are equal");
        else if (compareValue < 0)
            System.out.println("object1 is less than object2");
        else
            System.out.println("object1 is greater than object2");
    }
}
```

输出:

```java
prog.java:14: error: incompatible types: String cannot be converted to Long
      int compareValue = obj1.compareTo("gfg"); 
                                        ^
Note: Some messages have been simplified; recompile with -Xdiags:verbose to get full output
1 error

```