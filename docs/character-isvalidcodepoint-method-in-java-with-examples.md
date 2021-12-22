# Java 中 Character.isValidCodePoint()方法，带示例

> 原文:[https://www . geesforgeks . org/character-is validacodepoint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-isvalidcodepoint-method-in-java-with-examples/)

**character . isvalidacodepoint()**是 java 中的一个内置方法，用于确定参数中提到的指定代码点是否是有效的 Unicode 代码点值。

**语法:**

```java
public static boolean isValidCodePoint(int codePoint)
```

 **参数:**参数*码点*为整数数据类型，指待测试的 unicode 码点。

**返回值:**如果指定的代码点值在最小代码点和最大代码点之间，则该方法返回真，否则返回假。

以下程序说明了 Character.isValidCodePoint()方法的使用:
**程序 1:**

```java
// Java program to demonstrate the
// Character.isValidCodePoint() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create 2 int primitives c1, c2 and assign values
        int c1 = 0x0125, c2 = 0x123fff;

        boolean bool1 = Character.isValidCodePoint(c1);
        boolean bool2 = Character.isValidCodePoint(c2);

        String str1 = "c1 is a valid Unicode code point is " + bool1;
        String str2 = "c2 is a valid Unicode code point is " + bool2;

        // Print bool1, bool2 values
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**Output:**

```java
c1 is a valid Unicode code point is true
c2 is a valid Unicode code point is false

```

**程序 2:**

```java
// Java program to demonstrate the
// Character.isValidCodePoint() method 
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create 2 int primitives c1, c2 and assign values
        int c1 = 0x0128, c2 = 0x123ddd;

        boolean bool1 = Character.isValidCodePoint(c1);
        boolean bool2 = Character.isValidCodePoint(c2);

        String str1 = "c1 is a valid Unicode code point is " + bool1;
        String str2 = "c2 is a valid Unicode code point is " + bool2;

        // Print bool1, bool2 values
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**Output:**

```java
c1 is a valid Unicode code point is true
c2 is a valid Unicode code point is false

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # isvalidacodepoint(int)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isValidCodePoint(int))