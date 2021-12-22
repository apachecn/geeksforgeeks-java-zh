# Java 中的 longValue()方法

> 原文:[https://www . geesforgeks . org/long-long value-method-in-Java/](https://www.geeksforgeeks.org/long-longvalue-method-in-java/)

java.lang.Long.longValue()是 java 中 Long 类的内置方法，它在转换后将 Long 对象的值作为 Long 返回。
**语法:**

```java
public long longValue()
```

**参数:**该方法不取任何参数。
**返回值:**该方法将该对象表示的数值转换为长类型后返回。
**示例:**

```java
Input: 5366623
Output: (Long) 5366623

Input: -6723887
Output: (Long) -6723887
Explanation:
When the number is passed in this object it will convert that 
to long and gives the value like,
Long lobject = new Long(5366623)
It will return 5366623 as long.
```

下面的程序说明了 java.lang.Long.longValue()方法的工作原理。
**程序 1:** 为正数。

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.Long.longValue() method

import java.lang.*;

public class Geek {

    public static void main(String[] args)
    {

        Long lobject = new Long(77387187);

        // It will return the value of this Long as a long
        long nl = lobject.longValue();
        System.out.println("The Value of nl as long is = " + nl);

        Long lobject2 = new Long(-6723887);

        // It will return the value of this Long as a long
        long nl2 = lobject2.longValue();
        System.out.println("The Value of nl2 as long is = " + nl2);
    }
}
```

**Output:** 

```java
The Value of nl as long is = 77387187
The Value of nl2 as long is = -6723887
```