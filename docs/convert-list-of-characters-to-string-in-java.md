# 在 Java 中将字符列表转换为字符串

> 原文:[https://www . geeksforgeeks . org/convert-list-characters-to-string-in-Java/](https://www.geeksforgeeks.org/convert-list-of-characters-to-string-in-java/)

给定一个字符列表。编写一个 Java 程序，将给定的列表转换成字符串。

```
Input : list = {'g', 'e', 'e', 'k', 's'} 
Output : "geeks"

Input : list = {'a', 'b', 'c'} 
Output : "abc" 
```

**字符串–**Java 中的字符串是由一个字符数组在内部支持的对象。由于数组是不可变的，而字符串也是一种保存字符的特殊数组，因此字符串也是不可变的。

**List–**Java 中的 List 实现了管理有序集合的能力。它包括基于索引的插入、更新、删除和搜索列表元素的技术。它也可以有重复的元素。列表界面位于 **java.util** 包中，继承了**收藏界面。**

### 方法

在 Java 中，有许多方法可以将字符列表转换为字符串。这些是–

*   使用 StringBuilder 类
*   使用 Joiner 类的 join()方法
*   使用 List.toString()、String.substring()和 String.replaceAll()方法
*   使用收集器

### **1。使用** [**StringBuilder 类**T5】](https://www.geeksforgeeks.org/stringbuilder-class-in-java-with-examples/)

一个简单的解决方案是遍历列表，并在 StringBuilder 类的帮助下创建一个新的字符串，如下所示:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for convert character list to string
import java.util.Arrays;
import java.util.List;

// Convert List of Characters to String in Java
class GFG {
    public static void main(String[] args)
    {
        // create character list and initialize
        List<Character> str
            = Arrays.asList('G', 'e', 'e', 'k', 's');

          System.out.println("List - " + str);

        // create object of StringBuilder class
        StringBuilder sb = new StringBuilder();

        // Appends characters one by one
        for (Character ch : str) {
            sb.append(ch);
        }

        // convert in string
        String string = sb.toString();

        // print string
        System.out.println("String - " + string);
    }
}
```

**Output**

```
List - [G, e, e, k, s]
String - Geeks
```

### **2。使用 Joiner 类的 join()方法**

Joiner 类可用于将片段连接到指定为数组的文本，并将结果作为字符串返回。这种方法也被称为番石榴法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for convert character list to string
import com.google.common.base.Joiner;
import java.util.*;

// Convert List of Characters to String in Java
class GFG {
    public static void main(String[] args)
    {
        // create character list and initialize
        List<Character> str
            = Arrays.asList('G', 'e', 'e', 'k');

          System.out.println("List - " + str);

        // convert in string
        // use join() method
        String string = Joiner.on("").join(str);

        // print string
        System.out.println("String - " + string);
    }
}
```

**Output**

```
List - [G, e, e, k]
String - Geek
```

### **3。使用 List.toString()，String.substring()和 String.replaceAll()方法**

列表上的 toString()方法返回一个用方括号括起来的字符串，项目之间用逗号隔开。想法是使用 substring()方法去掉方括号，使用 replaceAll()方法去掉逗号和空格。
上述方法的实施如下–

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for convert character list to string
import java.util.*;

// Convert List of Characters to String in Java
class GFG {
    public static void main(String[] args)
    {
        // create character list and initialize
        List<Character> str
            = Arrays.asList('G', 'e', 'e', 'k');

        System.out.println("List - " + str);

        // convert in string
        // remove [] and spaces
        String string = str.toString()
                  .substring(1, 3 * str.size() - 1)
                  .replaceAll(", ", "");

        // print string
        System.out.println("String - " + string);
    }
}
```

**Output**

```
List - [G, e, e, k]
String - Geek
```

### **4。[使用](https://www.geeksforgeeks.org/java-collectors/)**在爪哇使用**收集器**

在 java 8 中，我们可以利用带有收集器的流 API。
执行上述方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for convert character list to string
import java.util.*;
import java.util.stream.Collectors;

// Convert List of Characters to String in Java
class GFG {
    public static void main(String[] args)
    {
        // create character list and initialize
        List<Character> str
            = Arrays.asList('G', 'e', 'e', 'k');

        System.out.println("List - " + str);

        // convert in string
        // using collect and joining() method
        String string = str.stream()
                            .map(String::valueOf)
                            .collect(Collectors.joining());

        // print string
        System.out.println("String - " + string);
    }
}
```

**Output**

```
List - [G, e, e, k]
String - Geek
```