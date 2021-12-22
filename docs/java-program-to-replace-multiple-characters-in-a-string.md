# 替换字符串中多个字符的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序替换字符串中的多个字符/](https://www.geeksforgeeks.org/java-program-to-replace-multiple-characters-in-a-string/)

在这个程序中，我们将讨论替换字符串中多个字符的各种方法。这可以使用下列方法完成:

*   使用 String.replace()方法
*   使用 replaceAll()方法
*   使用 replaceFirst()方法

**方法 1:** 使用 String.replace()方法

此方法返回一个新字符串，该字符串是用新字符替换字符串中所有出现的旧字符而得到的。

**语法:**

```
public String replace(char oldch, char newch)
```

**参数:**

*   老角色。
*   新角色。

**返回值:**通过用新字符替换旧字符的每一次出现，返回由此字符串派生的字符串。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate the
// working of replace()
public class rep1 {
public static void main(String args[]) {

    // Initialising String
    String Str = new String("Welcome to geeksforgeeks");

    // Using replace to replace characters
    System.out.print("After replacing all o with T : " );
    System.out.println(Str.replace('o', 'T'));

    // Using replace to replace characters
    System.out.print("After replacing all e with D : " );
    System.out.println(Str.replace('e', 'D'));

}
}
```

**Output**

```
After replacing all o with T : WelcTme tT geeksfTrgeeks
After replacing all e with D : WDlcomD to gDDksforgDDks
```

**方法 2:** 使用 replaceAll()方法

此方法用给定的 replace_str 替换与给定正则表达式匹配的字符串的每个子字符串。

**语法:**

```
public String replaceAll(String regex, String replace_str)
```

**参数:**

*   **正则表达式:**该字符串要匹配的正则表达式。
*   **replace_str:** 将替换找到的表达式的字符串。

**返回值:**这个方法返回结果字符串。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate the
// working of replaceAll()
public class rep2 {
public static void main(String args[]) {

    // Initialising String
    String Str = new String("Welcome to geeksforgeeks");

    // original string
    System.out.print("Original String : " );
    System.out.println(Str);

    // Using replaceAll to replace regex with replace_str
    System.out.print("After replacing regex with replace_str : " );
    System.out.println(Str.replaceAll("(.*)geeks(.*)", "AKSHIT SAXENA"));

}
}
```

**Output**

```
Original String : Welcome to geeksforgeeks
After replacing regex with replace_str : AKSHIT SAXENA
```

**方法 3:** 使用 replaceFirst()方法

此方法用给定的 replace_str 替换与给定正则表达式匹配的字符串的第一个子字符串。

**语法:**

```
public String replaceFirst(String regex, String replace_str)
```

**参数**

*   正则表达式:这个字符串要匹配的正则表达式。
*   替换字符串:将替换找到的表达式的字符串。

**返回值:**这个方法返回一个结果字符串。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate the
// working of replaceFirst()
public class rep3 {
public static void main(String args[]) {

    // Initialising String
    String Str = new String("Welcome to geeksforgeeks");

    // original string
    System.out.print("Original String : " );
    System.out.println(Str);

    // Using replaceFirst to replace regex with replace_str
    // Replaces 1st occurrence of geeks with ASTHA
    System.out.print("After replacing 1st occurrence of regex with replace_str : " );
    System.out.println(Str.replaceFirst("geeks", "Akshit"));

}
}
```

**Output**

```
Original String : Welcome to geeksforgeeks
After replacing 1st occurrence of regex with replace_str : Welcome to Akshitforgeeks
```