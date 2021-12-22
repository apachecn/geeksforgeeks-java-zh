# 将对象转换为字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到转换对象到字符串/](https://www.geeksforgeeks.org/java-program-to-convert-object-to-string/)

第一个字节需要转换成一个对象字节，这个对象字节可以很容易地转换成字符串。在 java 中使用 Object 类的 [*toString()*](https://www.geeksforgeeks.org/integer-tostring-in-java/) 方法或 String.valueOf(object)方法将 Object 转换为 String。由于 java 中主要有两种类型的类，即用户定义类和预定义类，如 [StringBuilder](https://www.geeksforgeeks.org/string-vs-stringbuilder-vs-stringbuffer-in-java/) 或 [StringBuffer](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) ，其对象可以转换为字符串。

**方法:**

1.  Convert user-defined class objects into strings.
2.  Convert the [*string generator*](https://www.geeksforgeeks.org/string-vs-stringbuilder-vs-stringbuffer-in-java/) (predefined class) object into a string.

**方法 1:** 使用 [toString()](https://www.geeksforgeeks.org/integer-tostring-in-java/) 方法或[*string . value of(object _ name)方法*](https://www.geeksforgeeks.org/data-conversion-using-valueof-method-java/) 。

## Java

```java
// Java Program to convert pre defined class object
// (Helper class) to string using value() method

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Object of helper class
        Helper help = new Helper();

        // converting object to string
        // using toString() method
        String s1 = help.toString();

        // converting object to string
        // using valueOf() method
        String s2 = String.valueOf(help);

        // Printing the converted string
        System.out.println(
            "Converted string object || using toString() Method: " + s1);

        // Printing the converted string
        System.out.println(
            "Converted string object || using valueOf() Method: " + s2);
    }
}

class Helper {
    // To make class object in main
}
```

**输出**

```java
Converted string object || using toString() Method: Helper@214c265e
Converted string object || using valueOf() Method: Helper@214c265e
```