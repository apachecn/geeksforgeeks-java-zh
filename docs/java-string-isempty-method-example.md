# Java String isEmpty()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-string-isempty-method-example/](https://www.geeksforgeeks.org/java-string-isempty-method-example/)

**Java . lang . String . isempty()**String 方法检查字符串是否为空。如果给定的字符串为空，此方法返回 true，否则返回 false。自从 JDK 1.6 以来，字符串类的 isEmpty()方法就包含在 java 字符串中。换句话说，如果字符串的长度为 0，则可以说此方法返回 true。
**例:**

```
Input String1 : Hello_Gfg
Input String2 :
Output for String1 : false
Output for String2 : true

```

**语法:**

```
public boolean isEmpty()
Returns : true if the length of the string is 0.
```

```
// Java program to demonstrate working of 
// isEmpty() method
class Gfg {
    public static void main(String args[])
    {
        // non-empty string
        String str1 = "Hello_Gfg";

        // empty string
        String str2 = "";

        // prints false
        System.out.println(str1.isEmpty());

        // prints true
        System.out.println(str2.isEmpty());
    }
}
```

**输出:**

```
false
true

```