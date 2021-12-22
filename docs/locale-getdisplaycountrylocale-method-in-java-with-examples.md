# Java 中的 Locale getDisplayCountry(Locale)方法，示例

> 原文:[https://www . geesforgeks . org/locale-getdisplaycountrlocale-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-getdisplaycountrylocale-method-in-java-with-examples/)

Java 中 [**Locale 类**](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/) 的**getDisplayCountry(Locale*****inLoc*****)**方法用于获取指定地区的国家或地区名称。该名称将根据 *inLoc* 进行本地化。

**语法:**

```java
public String getDisplayCountry(Locale *inLoc*)
```

**参数:**该方法取 Locale 类型的一个参数 *inLoc* ，指名称的本地化显示。
**返回值:**该方法返回适合给定地区和用户的国家名称。
**异常:**如果参数 inLoc 为空，则方法抛出**空指针异常**。
以下程序说明 getDisplayCountry()方法的工作:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate getDisplayCountry() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("English", "In");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Displaying the country_name of this locale
        System.out.println("Country: "
                           + first_locale
                                 .getDisplayCountry(
                                     new Locale("Spanish",
                                                "Spain")));
    }
}
```

**Output:** 

```java
First Locale: english_IN
Country: India
```