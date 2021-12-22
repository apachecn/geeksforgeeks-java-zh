# 通过 Java 数组列表获取枚举

> 原文:[https://www . geesforgeks . org/get-enumeration-over-Java-ArrayList/](https://www.geeksforgeeks.org/get-enumeration-over-java-arraylist/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)类是存在于 **java.util** 包中的一个可重定大小的数组。与内置数组不同，数组列表可以动态改变其大小，在数组列表中可以添加和删除元素。

在 java 版本 1 中，枚举不存在。随着版本的升级，java 中引入了 1.5 enum，这与 C/C++中看到的不同，因此功能也不同。Enum 基本上用于限制范围，例如月份、年龄，或者它是一个字符串(考虑公司名称)，最初不能作为最终值本身进行更改。在 java 版本 1 中，枚举是由接口执行的。在 1.5 版本之后，如前所述，它在 java 中被引入，因此简单地导入 enum 类使得通过简单地导入类来使用 enum 变得容易。

数组列表可以是如下所示的任何类型。java.util.Collections 类的枚举方法用于返回指定集合的枚举。

*   整数、字符串、双精度等的数组列表。
*   数组列表的数组列表，或者仅仅是哈希映射的数组列表。
*   任何用户定义对象的数组列表。

**语法:**用于声明枚举

```java
public static  Enumeration enumeration(Collection c) ;
```

**使用的方法:** [*有更多的元素()*](https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/) 方法

实现**枚举接口**的对象生成一系列元素，一次一个。[*hasmorelements()*](https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/)枚举法用于测试该枚举是否包含更多元素。如果枚举包含的元素多于它将返回 true，否则返回 false。

**语法:**

```java
boolean hasMoreElements() ;
```

**参数:**此方法不接受任何内容。

**返回值:**当且仅当此枚举对象至少包含一个要提供的元素时，此方法返回 true 否则为假。

**实施:**

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Getting Enumeration over Java ArrayList

// Importing ArrayList,Collection and Enumeration class
// from java.util package
import java.util.ArrayList;
import java.util.Collections;
import java.util.Enumeration;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of ArrayList
        // String type here- shoppingList
        ArrayList<String> shoppingList = new ArrayList<>();

        // Adding element to ArrayList
        // Custom inputs
        shoppingList.add("Perfume");
        shoppingList.add("Clothes");
        shoppingList.add("Sandal");
        shoppingList.add("Jewellery");
        shoppingList.add("Watch");

        // Creating object of type Enumeration<String>
        Enumeration e
            = Collections.enumeration(shoppingList);

        // Condition check using hasMoreElements() method
        while (e.hasMoreElements())

            // print the enumeration
            System.out.println(e.nextElement());
    }
}
```

**Output**

```java
Perfume
Clothes
Sandal
Jewellery
Watch
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Getting Enumeration over Java ArrayList

// Importing ArrayList,Collection and Enumeration class
// from java.util package
import java.util.ArrayList;
import java.util.Collections;
import java.util.Enumeration;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of ArrayList<String
        ArrayList<String> LanguageList = new ArrayList<>();

        // Adding element to LanguageList
        // Custom inputs
        LanguageList.add("Java");
        LanguageList.add("C++");
        LanguageList.add("Kotlin");
        LanguageList.add("Scala");
        LanguageList.add("Ruby");
        LanguageList.add("Python");
        LanguageList.add("C#");

        // Creating object of type Enumeration<String>
        Enumeration e
            = Collections.enumeration(LanguageList);

        // Condition check using hasMoreElements()
        while (e.hasMoreElements())

            // Print the enumeration
            System.out.println(e.nextElement());
    }
}
```

**Output**

```java
Java
C++
Kotlin
Scala
Ruby
Python
C#
```