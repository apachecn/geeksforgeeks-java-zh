# Java String toCharArray()带示例

> 原文:[https://www . geesforgeks . org/Java-string-tochararray-example/](https://www.geeksforgeeks.org/java-string-tochararray-example/)

**java 字符串 toCharArray()** 方法将给定的字符串转换成一个字符序列。返回的数组长度等于字符串的长度。

**语法:**

```java
public char[] toCharArray() 
Return : It returns a newly allocated character array.

```

```java
// Java program to demonstrate
// working of toCharArray() method

class Gfg {
    public static void main(String args[])
    {
        String s = "GeeksforGeeks";
        char[] gfg = s.toCharArray();
        for (int i = 0; i < gfg.length; i++) {
            System.out.println(gfg[i]);
        }
    }
}
```

**输出:**

```java
G
e
e
k
s
f
o
r
G
e
e
k
s

```