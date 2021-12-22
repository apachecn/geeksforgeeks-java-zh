# 在 Java 中将数组列表转换为逗号分隔的字符串

> 原文:[https://www . geesforgeks . org/convert-ArrayList-to-逗号分隔字符串-in-java/](https://www.geeksforgeeks.org/convert-arraylist-to-comma-separated-string-in-java/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)是 [**集合框架**](https://www.geeksforgeeks.org/collections-in-java-2/) 的一部分，存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中。它为我们提供了 Java 中的动态数组。为了将数组列表转换为逗号分隔的字符串，下面列出了 Java 中可用的方法，建议如下:

在 Java 8 之前，只有标准方法可用于这种转换，但是随着 Streams 和 Lambda 概念的引入，新的方法开始出现，下面列出了所有这些方法:

1.  **使用 StringBuilder 的 append()方法**
2.  **使用 toString()方法**
3.  **使用 Apache Commons StringUtils 类**
4.  **使用流应用编程接口**
5.  **使用字符串类的字符串连接()方法**

让我们讨论上面提出的每一种方法，以便更深入地了解程序，如下所示:

## 方法 1:使用 StringBuilder 的 append()方法

java 中的 [StringBuilder](https://www.geeksforgeeks.org/stringbuilder-class-in-java-with-examples/) 代表一个可变的字符序列。在下面的例子中，我们使用了 StringBuilder 的 [append()](https://www.geeksforgeeks.org/stringbuilder-append-method-in-java-with-examples/) 方法。append 方法用于在现有字符串的最后一个位置连接或添加一组新字符。

**语法:**

```
public StringBuilder append(*char a*)
```

**参数:**该方法接受单个参数 *a* ，这是字符串表示将被追加的字符值。

**返回值:**该方法在执行追加操作后返回一个字符串对象。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert ArrayList to
// Comma Separated String
// Using append() method of StringBuilder

// Importing required classes
import java.util.ArrayList;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of string type
        ArrayList<String> geeklist
            = new ArrayList<String>();

        // Adding elements to ArrayList
        // using add() method
        geeklist.add("Hey");
        geeklist.add("Geek");
        geeklist.add("Welcome");
        geeklist.add("to");
        geeklist.add("geeksforgeeks");
        geeklist.add("!");

        StringBuilder str = new StringBuilder("");

        // Traversing the ArrayList
        for (String eachstring : geeklist) {

            // Each element in ArrayList is appended
            // followed by comma
            str.append(eachstring).append(",");
        }

        // StringBuffer to String conversion
        String commaseparatedlist = str.toString();

        // Condition check to remove the last comma
        if (commaseparatedlist.length() > 0)

            commaseparatedlist
                = commaseparatedlist.substring(
                    0, commaseparatedlist.length() - 1);

        // Printing the comma separated string
        System.out.println(commaseparatedlist);
    }
}
```

**Output**

```
Hey,Geek,Welcome,to,geeksforgeeks,!
```

## 方法 2:使用 toString()方法

**toString()** 是一个内置方法，它以字符串格式返回给它的值。下面的代码使用 toString()方法将[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)转换为[字符串](https://www.geeksforgeeks.org/string-class-in-java/)。方法返回应用替换方法的单个字符串，并替换指定的字符(在本例中是括号和空格)。

**语法:**

```
arraylist.toString()
// arraylist is an object of the ArrayList class
```

**返回值:**返回数组列表的字符串表示形式

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert ArrayList to
// Comma Separated String
// Using toString() method

// Importing required classes
import java.util.ArrayList;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of string type
        ArrayList<String> geekcourses
            = new ArrayList<String>();

        // Adding elements to above empty ArrayList
        // using add() method
        geekcourses.add("Data Structures");
        geekcourses.add("Algorithms");
        geekcourses.add("Operating System");
        geekcourses.add("Computer Networks");
        geekcourses.add("Machine Learning");
        geekcourses.add("Databases");

        // Note: toString() method returns the output as
        // [Data Structure,Algorithms,...]
        // In order to replace '[', ']' and spaces with
        // empty strings to get comma separated values

        String commaseparatedlist = geekcourses.toString();

        commaseparatedlist
            = commaseparatedlist.replace("[", "")
                  .replace("]", "")
                  .replace(" ", "");

        // Printing the comma separated string
        System.out.println(commaseparatedlist);
    }
}
```

**Output**

```
DataStructures,Algorithms,OperatingSystem,ComputerNetworks,MachineLearning,Databases
```

## **方法 3:** 使用 Apache Commons StringUtils 类

Apache Commons 库有一个 **StringUtils** 类，它为字符串提供了一个实用函数。join 方法用于将数组列表转换为逗号分隔的字符串。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert ArrayList to
// Comma Separated String
// Using Apache Commons StringUtils class

// Importing required classes
import java.util.ArrayList;
import org.apache.commons.collections4.CollectionUtils;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of string type
        ArrayList<String> geekcourses
            = new ArrayList<String>();

        // Adding elements to ArrayList
        // using add() method
        geekcourses.add("Data Structures");
        geekcourses.add("Algorithms");
        geekcourses.add("Operating System");
        geekcourses.add("Computer Networks");
        geekcourses.add("Machine Learning");
        geekcourses.add("Databases");

        // Mote: join() method used returns a single string
        // along with defined separator in every iteration

        String commalist
            = StringUtils.join(geekcourses, ",");

        // Printing the comma separated string
        System.out.println(commalist);
    }
}
```

**输出:**

```
OutputDataStructures,Algorithms,OperatingSystem,ComputerNetworks,MachineLearning,Databases
```

## 方法 4:使用流应用编程接口

[Stream API](https://www.geeksforgeeks.org/stream-in-java/) 是在 Java 8 中引入的，用于处理对象的集合。在 Java 中， [Collectors](https://www.geeksforgeeks.org/java-collectors/) 类的 [joining()](https://www.geeksforgeeks.org/java-8-streams-collectors-joining-method-with-examples/) 方法用于将字符或字符串数组的各种元素连接到单个字符串对象中。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert ArrayList to
// Comma Separated String
// Using Stream API

// Importing required classes
import java.util.*;
import java.util.stream.Collectors;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of string type
        ArrayList<String> geeklist
            = new ArrayList<String>();

        // Adding elements to above ArrayList
        // using add() method
        geeklist.add("welcome");
        geeklist.add("to");
        geeklist.add("geeks");
        geeklist.add("for");
        geeklist.add("geeks");

        // collect() method returns the result of the
        // intermediate operations performed on the stream
        String str = geeklist.stream().collect(
            Collectors.joining(","));

        // Printing the comma separated string
        System.out.println(str);
    }
}
```

**Output**

```
welcome,to,geeks,for,geeks
```

## 方法 5:使用字符串类的 join()方法

我们可以使用 [StringJoiner](https://www.geeksforgeeks.org/java-util-stringjoiner-java8/) 将 ArrayList 转换为逗号分隔的字符串，这是 java.util 包中的一个类，用于构造由分隔符分隔的字符(字符串)序列，可选地以提供的前缀开始，以提供的后缀结束。String 类的 [join()](https://www.geeksforgeeks.org/java-string-join-examples/) 方法可以用来构造相同的。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert ArrayList to
// Comma Separated String
// Using String join() method

// Importing required classes
import java.util.*;
import java.util.stream.Collectors;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of string type
        ArrayList<String> geeklist
            = new ArrayList<String>();

        // Adding elements to ArrayList
        // using add() method
        geeklist.add("welcome");
        geeklist.add("to");
        geeklist.add("geeks");
        geeklist.add("for");
        geeklist.add("geeks");

        // Note: String.join() is used with a delimiter
        // comma along with the list
        String str = String.join(",", geeklist);

        // Printing the comma separated string
        System.out.println(str);
    }
}
```

**Output**

```
welcome,to,geeks,for,geeks
```