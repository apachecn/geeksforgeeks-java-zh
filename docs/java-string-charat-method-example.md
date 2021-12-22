# Java String charAt()方法示例

> 原文:[https://www . geesforgeks . org/Java-string-charat-method-example/](https://www.geeksforgeeks.org/java-string-charat-method-example/)

**Java String charAt()** 方法返回指定索引处的字符。索引值应该介于 0 和 length()-1 之间。
**签名:**

```java
 public char charAt(int index)  

```

**参数:**

```java
 index- Index of the character to be returned.

```

**返回:**

```java
 returns character at the specified position.

```

例外:

```java
 StringIndexOutOfBoundsException- If index is 
 negative or greater then the length of the 
 String.

```

**示例:**展示 **charAt()** 方法的工作

```java
// Java program to demonstrate
// working of charAt() method

class Gfg {
    public static void main(String args[])
    {
        String s = "Welcome! to Geeksforgeeks Planet";

        char ch = s.charAt(3);
        System.out.println(ch);

        ch = s.charAt(0);
        System.out.println(ch);
    }
}
```

**Output:**

```java
c
W

```

```java
// Java program to demonstrate
// working of charAt() method

class Gfg {
    public static void main(String args[])
    {
        String s = "abc";

        char ch = s.charAt(4);
        System.out.println(ch);
    }
}
```

**Output:**

```java
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: String index out of range: 4
    at java.lang.String.charAt(String.java:658)
    at Gfg.main(File.java:9)

```

 **[Java 中的字符串类](https://www.geeksforgeeks.org/string-class-in-java/)**