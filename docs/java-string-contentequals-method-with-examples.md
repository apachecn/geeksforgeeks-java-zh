# Java 字符串 contentEquals()方法示例

> 原文:[https://www . geesforgeks . org/Java-string-content equals-method-with-examples/](https://www.geeksforgeeks.org/java-string-contentequals-method-with-examples/)

**contentEquals()** 方法的 [**字符串**](https://www.geeksforgeeks.org/java-lang-string-class-java-set-2/) 类用来比较字符串。java.lang.String 中有两种不同参数的 contentEquals 方法:

1.  **content equals(string buffer sb)**
2.  **content equals(charsequence cs)**

### 1.contentEquals(字符串缓冲区 sb):

contentEquals(StringBuffer sb)方法将字符串与指定的 StringBuffer 进行比较。如果字符串表示与指定字符串相同的字符序列，它将返回 true 否则，它将返回 false。

**语法:**

```
public boolean contentEquals(StringBuffer sb)
```

**返回类型:**它有一个布尔返回类型，如果这个 String 表示的字符序列与指定的 StringBuffer 相同，则返回 true，否则返回 false。

**方法参数:**它有一个 StringBuffer 类型的参数

### 如何调用 contentEquals(StringBuffer sb)方法？

**步骤 1:** 首先，创建一个 StringBuffer 类的实例来比较它的字符序列

```
StringBuffer stringBuffer = new StringBuffer( "GFG is the best");
```

**步骤 2:** 创建一个 String 的实例，然后调用它的 contentEquals 方法

```
String str= "GFG is the best";
str.contentEquals(stringBuffer)
```

下面的 Java 程序将说明 contentEquals(StringBuffer sb)方法的使用:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the working
// of the contentEquals(StringBuffer sb) method

import java.io.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {
        // creating instance of StringBuffer class
        StringBuffer stringBuffer
            = new StringBuffer("GFG is a portal for geeks");

        String one = "GFG is a portal for geeks";
        String two = "GFG is a portal for gamers";

        // invoking contentEquals method
        // for String one and two
        System.out.println(
            "String one equals to specified StringBuffer : "
            + one.contentEquals(stringBuffer));

        System.out.println(
            "String two equals to specified StringBuffer : "
            + two.contentEquals(stringBuffer));
    }
}
```

**Output**

```
String one equals to specified StringBuffer : true
String two equals to specified StringBuffer : false
```

### 2.contentEquals(CharSequence cs)

方法将字符串与指定的字符序列进行比较。如果字符串表示的字符值序列与指定的字符序列相同，它将返回 true 否则，它将返回 false。

**语法:**

```
public boolean contentEquals(CharSequence cs)
```

**方法返回类型:**它有一个布尔返回类型，如果该字符串表示与指定序列相同的字符值序列，则返回真，否则返回假。

**参数:**它有一个 CharSequence 类型的参数

### 如何调用 contentEquals(CharSequence cs)方法？

**步骤 1:** 首先，创建一个序列来比较字符值的序列

```
CharSequence cs = "portal for geeks"
```

**步骤 2:** 创建一个字符串实例，然后调用其 contentEquals 方法

```
String str= "portal for geeks";
str.contentEquals(cs);
```

下面的 java 程序将说明 contentEquals(CharSequence cs)方法的使用——

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the working
// of contentEquals(CharSequence cs) metgod

import java.io.*;
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {
        // creating instance of StringBuffer class
        CharSequence cs
            = "GFG is best website for programmer";

        String one = "GFG is best website for programmer";
        String two = "GFG is a portal for geeks";

        // invoking contentEquals method 
        // for String one and two
        System.out.println(
            "String one equals to specified sequence : "
            + one.contentEquals(cs));

        System.out.println(
            "String two equals to specified sequence : "
            + two.contentEquals(cs));
    }
}
```

**Output**

```
String one equals to specified sequence : true
String two equals to specified sequence : false
```