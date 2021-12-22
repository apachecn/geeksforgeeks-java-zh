# Java 8 Streams | collectors . joing()方法示例

> 原文:[https://www . geesforgeks . org/Java-8-streams-collectors-join-method-with-examples/](https://www.geeksforgeeks.org/java-8-streams-collectors-joining-method-with-examples/)

在 Java 中，Collectors 类的 **joining()** 方法用于将字符或字符串数组的各种元素连接到单个字符串对象中。此方法使用流来完成此操作。收集器类中存在各种各样的联接方法重载。

**等级等级:**

```java
java.lang.Object
  ↳ java.util.stream.Collectors

```

### 加入()

**Java . util . stream . collectors . joining()**是最简单的不取任何参数的 joining 方法。它返回一个收集器，该收集器按照出现的顺序将输入流连接或串连成字符串。

**语法:**

```java
public static Collector<CharSequence, ?, String> joining()
```

下面是如何使用 join()方法的图示:

**程序 1:** 使用带有字符数组的 join():

在下面的程序中，在“ch”中创建了一个字符数组。然后使用()的流将该数组转换为流。然后，使用 map()将结果流映射为连续序列。最后，使用 Collectors.joining()方法将包含字符数组的序列流连接成一个字符串。它存储在“chString”变量中。

```java
// Java Program to demonstrate the working
// of the Collectors.joining() method

import java.util.stream.Collectors;
import java.util.stream.Stream;

public class GFG {
    public static void main(String[] args)
    {
        // Create a character array
        char[] ch = { 'G', 'e', 'e', 'k', 's',
                      'f', 'o', 'r',
                      'G', 'e', 'e', 'k', 's' };

        // Convert the character array into String
        // using Collectors.joining() method
        String chString = Stream.of(ch)
                              .map(arr -> new String(arr))
                              .collect(Collectors.joining());

        // Print the concatenated String
        System.out.println(chString);
    }
}
```

**输出:**

```java
GeeksforGeeks
```

**程序 2:** 使用带有字符列表的 join():

在下面的程序中，在“ch”中创建了一个字符列表。然后使用 ch.stream()方法将该列表转换为 Stream。然后，使用 map()将结果流映射为连续序列。最后，使用 Collectors.joining()方法将包含字符列表的序列流连接成一个字符串。它存储在“chString”变量中。

```java
// Java Program to demonstrate the working
// of the Collectors.joining() method

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.Arrays;
import java.util.List;

public class GFG {
    public static void main(String[] args)
    {
        // Create a character list
        List<Character> ch = Arrays.asList('G', 'e', 'e', 'k', 's',
                                           'f', 'o', 'r',
                                           'G', 'e', 'e', 'k', 's');

        // Convert the character list into String
        // using Collectors.joining() method
        String chString = ch.stream()
                              .map(String::valueOf)
                              .collect(Collectors.joining());

        // Print the concatenated String
        System.out.println(chString);
    }
}
```

**输出:**

```java
GeeksforGeeks
```

**程序 3:** 使用连接()和 n 个字符串列表:

在下面的程序中，在“字符串”中创建了一个字符串列表。然后使用 str.stream()方法将该列表转换为 Stream。然后，使用 map()将结果流映射为连续序列。最后，使用 Collectors.joining()方法将包含字符列表的序列流连接成一个字符串。它存储在“chString”变量中。

```java
// Java Program to demonstrate the working
// of the Collectors.joining() method

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.Arrays;
import java.util.List;

public class GFG {
    public static void main(String[] args)
    {
        // Create a character list
        List<String> str = Arrays.asList("Geeks", "for", "Geeks");

        // Convert the character list into String
        // using Collectors.joining() method
        String chString = str.stream()
                              .map(String::valueOf)
                              .collect(Collectors.joining());

        // Print the concatenated String
        System.out.println(chString);
    }
}
```

**输出:**

```java
GeeksforGeeks
```

### 连接(分隔符)

**Java . util . stream . collectors . join(CharSequence delimiter)**是 join()方法的重载，该方法以分隔符为参数，类型为 CharSequence。分隔符是一种符号或字符序列，用于分隔单词。例如，在每个句子中，空格“”被默认用作其中单词的分隔符。它返回一个 Collector，该 Collector 按照出现的顺序将输入元素连接或串连成 String，并用分隔符隔开。

**语法:**

```java
public static Collector<CharSequence, ?, String> joining(CharSequence delimiter)
```

下面是如何使用联接(分隔符)方法的图示:

**程序 1:** 使用带有字符列表的连接(分隔符):

在下面的程序中，在“ch”中创建了一个字符列表。然后使用 ch.stream()方法将该列表转换为 Stream。然后，使用 map()将结果流映射为连续序列。最后，使用 Collectors.joining()方法将包含字符列表的顺序流连接成一个字符串，并以“”作为分隔符传递。它存储在“chString”变量中。

```java
// Java Program to demonstrate the working
// of the Collectors.joining() method

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.Arrays;
import java.util.List;

public class GFG {
    public static void main(String[] args)
    {
        // Create a character list
        List<Character> ch = Arrays.asList('G', 'e', 'e', 'k', 's',
                                           'f', 'o', 'r',
                                           'G', 'e', 'e', 'k', 's');

        // Convert the character list into String
        // using Collectors.joining() method
        // with, as the delimiter
        String chString = ch.stream()
                              .map(String::valueOf)
                              .collect(Collectors.joining(", "));

        // Print the concatenated String
        System.out.println(chString);
    }
}
```

**输出:**

```java
G, e, e, k, s, f, o, r, G, e, e, k, s
```

**程序 2:** 使用字符串列表的连接(分隔符):

在下面的程序中，在“字符串”中创建了一个字符串列表。然后使用 str.stream()方法将该列表转换为 Stream。然后，使用 map()将结果流映射为连续序列。最后，使用 Collectors.joining()方法将包含字符列表的顺序流连接成一个字符串，并以“”作为分隔符传递。它存储在“chString”变量中。

```java
// Java Program to demonstrate the working
// of the Collectors.joining() method

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.Arrays;
import java.util.List;

public class GFG {
    public static void main(String[] args)
    {
        // Create a character list
        List<String> str = Arrays.asList("Geeks", "for", "Geeks");

        // Convert the character list into String
        // using Collectors.joining() method
        String chString = str.stream()
                              .map(String::valueOf)
                              .collect(Collectors.joining(", "));

        // Print the concatenated String
        System.out.println(chString);
    }
}
```

**输出:**

```java
Geeks, for, Geeks
```

### 连接(分隔符、前缀、后缀)

**Java . util . stream . collectors . join(CharSequence 分隔符、CharSequence 前缀、CharSequence 后缀)**是 char sequence 类型的 join()方法的重载，该方法以分隔符、前缀和后缀为参数。

分隔符是一种符号或字符序列，用于分隔单词。前缀是连接在字符串第一个元素开始处的符号或字符序列。那么后缀也是一个 CharSequence 参数，但是它被连接在字符串的最后一个元素之后。即在最后。

例如，在每个{Geeks，For，Geeks}中，空格“”被用作其中单词的默认分隔符。“{ 0 }”是前缀，“}”是后缀。它返回一个 Collector，该 Collector 按照出现的顺序将输入元素连接或串连成 String，并用分隔符隔开。

**语法:**

```java
public static Collector<CharSequence, ?, String> joining(CharSequence delimiter. 
                                                       CharSequence prefix,
                                                       CharSequence suffix))
```

下面是如何使用连接(分隔符、前缀、后缀)方法的图示:

**程序 1:** 使用带有字符列表的联接():

在下面的程序中，在“ch”中创建了一个字符列表。然后使用 ch.stream()方法将该列表转换为 Stream。然后，使用 map()将结果流映射为连续序列。最后，使用 Collectors.joining()方法将包含字符列表的序列流连接成一个字符串，以“，”作为分隔符，以“[”作为前缀，以“]”作为后缀。它存储在“chString”变量中。

```java
// Java Program to demonstrate the working
// of the Collectors.joining() method

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.Arrays;
import java.util.List;

public class GFG {
    public static void main(String[] args)
    {
        // Create a character list
        List<Character> ch = Arrays.asList('G', 'e', 'e', 'k', 's',
                                           'f', 'o', 'r',
                                           'G', 'e', 'e', 'k', 's');

        // Convert the character list into String
        // using Collectors.joining() method
        // with, as the delimiter
        String chString = ch.stream()
                              .map(String::valueOf)
                              .collect(Collectors.joining(", ", "[", "]"));

        // Print the concatenated String
        System.out.println(chString);
    }
}
```

**输出:**

```java
[G, e, e, k, s, f, o, r, G, e, e, k, s]
```

**程序 2:** 使用连接()和字符串列表:

在下面的程序中，在“字符串”中创建了一个字符串列表。然后使用 str.stream()方法将该列表转换为 Stream。然后，使用 map()将结果流映射为连续序列。最后，使用 Collectors.joining()方法将包含字符列表的序列流连接成一个字符串，以“，”作为分隔符，以“{”作为前缀，以“}”作为后缀。它存储在“chString”变量中。

```java
// Java Program to demonstrate the working
// of the Collectors.joining() method

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.Arrays;
import java.util.List;

public class GFG {
    public static void main(String[] args)
    {
        // Create a character list
        List<String> str = Arrays.asList("Geeks", "for", "Geeks");

        // Convert the character list into String
        // using Collectors.joining() method
        String chString = str.stream()
                              .map(String::valueOf)
                              .collect(Collectors.joining(", ", "{", "}"));

        // Print the concatenated String
        System.out.println(chString);
    }
}
```

**输出:**

```java
{Geeks, for, Geeks}
```