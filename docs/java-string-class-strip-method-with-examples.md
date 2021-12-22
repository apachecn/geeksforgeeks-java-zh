# Java 字符串类 strip()方法示例

> 原文:[https://www . geesforgeks . org/Java-string-class-strip-method-with-examples/](https://www.geeksforgeeks.org/java-string-class-strip-method-with-examples/)

Java String Class **strip()** 方法返回一个字符串，该字符串提供了一个去掉了所有前导和尾随空格的字符串。这种方法类似于[弦切()方法](https://www.geeksforgeeks.org/java-string-trim-method-example/)。基本上有 3 种方法可以用不同的方式去除空白。

**strip()方法:**返回一个字符串，去掉所有的前导和尾随空格

**语法:**

```
String strippedString = string.strip()
```

**stripLeading()方法:**返回一个字符串，去掉所有前导空格。

**语法:**

```
String leadingStripString = string.stripLeading()
```

**strip training()方法:**返回一个字符串，去掉所有尾随空格。

**语法:**

```
String trailedStripString = string.stripTrailing()
```

**例:**

## 爪哇

```
// Java Program to demonstrate the use of the strip()
// method,stripLeading() method,stripTrailing() method

public class GFG {
    public static void main(String[] args)
    {
        String str
            = "        Geeks For Geeks Internship    !   ";

        // removing leading and
        // trailing white spaces
        System.out.println(str.strip());

        // removing leading white spaces
        System.out.println(str.stripLeading());

        // removing trailing white spaces
        System.out.println(str.stripTrailing());
    }
}
```

**输出:**

```
Geeks For Geeks Internship    !
Geeks For Geeks Internship    !   
        Geeks For Geeks Internship    !
```