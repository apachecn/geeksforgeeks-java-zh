# Java String to owercase()带示例

> 原文:[https://www . geesforgeks . org/Java-string-tolowercase-examples/](https://www.geeksforgeeks.org/java-string-tolowercase-examples/)

**java 字符串 toLowerCase()** 方法将字符串的所有字符转换为小写字母。**有两种类型的 toLowerCase()** 方法。

**签名:**

```java
public String toLowerCase(Locale loc) 
and
public String toLowerCase() 
Parameter:
loc- locale value to be applied. converts all the characters into 
lowercase using the rules of given Locale.  
Returns: returns string in lowercase letter.

```

```java
// Java program to demonstrate
// working of toLowerCase() method

class Gfg {
    public static void main(String args[])
    {
        String s = "Welcome! to Geeksforgeeks Planet.";

        // converting string s to lowercase letter
        String gfg1 = s.toLowerCase();
        System.out.println(gfg1);
    }
}
```

**输出:**

```java
welcome! to geeksforgeeks planet.

```

```java
// Java program to demonstrate
// working of Locale class in
// toLowerCase() method
import java.util.Locale;
class Gfg {
    public static void main(String args[])
    {
        String s = "I Know YOI Bui You Don't Know ME.";

        // Locales with the language "tr" for TURKISH
        //"en" for ENGLISH is created
        Locale TURKISH = Locale.forLanguageTag("tr");
        Locale ENGLISH = Locale.forLanguageTag("en");

        // converting string s to lowercase letter
        // using TURKISH and ENGLISH language
        String gfg2 = s.toLowerCase(TURKISH);
        String gfg3 = s.toLowerCase(ENGLISH);
        System.out.println(gfg2);
        System.out.println(gfg3);
    }
}
```

**输出:**

```java
? know yo? bui you don't know me.
i know yoi bui you don't know me.

```