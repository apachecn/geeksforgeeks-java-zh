# Java 中的 BigInteger hashCode()方法

> 原文:[https://www . geesforgeks . org/big integer-hashcode-method-in-Java/](https://www.geeksforgeeks.org/biginteger-hashcode-method-in-java/)

**Java . math . BigInteger . hashCode()**方法返回这个 BigInteger 的哈希代码。如果对象没有改变，hashcode 总是相同的。
Hashcode 是 JVM 在创建对象时生成的唯一代码。我们可以使用 hashcode 对哈希相关算法进行一些操作，比如[哈希表](https://www.geeksforgeeks.org/java-util-hashtable-class-java/)、[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)等。我们可以用那个唯一的代码搜索一个对象。

**语法:**

```java
public int hashCode()
```

**返回:**该方法返回一个整数值，该整数值代表该大整数的哈希码值。

**示例:**

```java
Input: BigInteger1=32145
Output: 32145
Explanation: BigInteger1.hashCode()=32145.

Input: BigInteger1=7613721467324 
Output: -1255493552
Explanation: BigInteger1.hashCode()=-1255493552.

```

**示例 1:下面的程序说明了 BigInteger 类**的 hashCode()方法

```java
// Java program to demonstrate 
// hashCode() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("32145");
        b2 = new BigInteger("7613721467324");

        // apply hashCode() method
        int hashCodeOfb1 = b1.hashCode();
        int hashCodeOfb2 = b2.hashCode();

        // print hashCode
        System.out.println("hashCode of "
                           + b1 + " : " + hashCodeOfb1);
        System.out.println("hashCode of "
                           + b2 + " : " + hashCodeOfb2);
    }
}
```

**Output:**

```java
hashCode of 32145 : 32145
hashCode of 7613721467324 : -1255493552

```

**例 2:当两个 bigInteger 的值相同时**

```java
// Java program to demonstrate 
// hashCode() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("4326516236135");
        b2 = new BigInteger("4326516236135");

        // apply hashCode() method
        int hashCodeOfb1 = b1.hashCode();
        int hashCodeOfb2 = b2.hashCode();

        // print hashCode
        System.out.println("hashCode of "
                           + b1 + " : " + hashCodeOfb1);
        System.out.println("hashCode of "
                           + b2 + " : " + hashCodeOfb2);
    }
}
```

**Output:**

```java
hashCode of 4326516236135 : 1484200280
hashCode of 4326516236135 : 1484200280

```

**参考:**
[大整数哈希代码()文件](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#hashCode())