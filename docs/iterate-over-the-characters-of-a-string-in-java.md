# 在 Java 中迭代字符串的字符

> 原文:[https://www . geesforgeks . org/iterate-over-of-characters-in-a-string-Java/](https://www.geeksforgeeks.org/iterate-over-the-characters-of-a-string-in-java/)

给定长度为 **N** 的[字符串](https://www.geeksforgeeks.org/strings-in-java/) **字符串**，任务是遍历字符串并打印给定字符串的所有字符。

插图:

```java
Input  : “GeeksforGeeks”
Output : G e e k s f o r G e e k s
```

```java
Input. : “Coder”
Output : C o d e r
```

**方法:**

1.  使用天真的方法
2.  使用 [String.toCharArray()](https://www.geeksforgeeks.org/java-string-tochararray-example/) 方法
3.  使用特性分析器
4.  使用字符串生成器
5.  使用 String.split()方法
6.  使用番石榴图书馆
7.  使用 String.chars()方法
8.  使用代码点

**方法 1:** 天真方法

解决这个问题最简单的方法是在范围**【0，N–1】**内迭代一个循环，其中 **N** 表示字符串的长度，使用变量 **i** 并打印 **str[i]** 的值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate Over the Characters of a String
// Using Naive Approach

// Importing classes from respective packages
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Method 1
    // Function to traverse the string and
    // print the characters of the string
    static void traverseString(String str)
    {
        // Traverse the string
        for (int i = 0; i < str.length(); i++) {

            // Print current character
            System.out.print(str.charAt(i) + " ");
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "GeeksforGeeks";

        // Calling the Method 1
        traverseString(str);
    }
}
```

**Output**

```java
G e e k s f o r G e e k s 
```

> *时间复杂度:O(N)*
> *辅助空间:O(1)*

**方法二:**使用[弦.托哈拉里()](https://www.geeksforgeeks.org/java-string-tochararray-example/)方法

在这种方法中，我们使用 **String.toCharArray()** 方法将字符串转换为字符数组。然后使用 for 循环或 for-each 循环迭代字符数组。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate Over the Characters of a String
// Using String.toCharArray() method

// Importing classes from respective packages
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Method 1
    // To traverse the string and
    // print the characters of the string
    static void traverseString(String str)
    {
        char[] ch = str.toCharArray();

        // Traverse the character array
        for (int i = 0; i < ch.length; i++) {

            // Print current character
            System.out.print(ch[i] + " ");
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "GeeksforGeeks";

        // Calling the Method 1
        traverseString(str);
    }
}
```

**Output**

```java
G e e k s f o r G e e k s 
```

> *时间复杂度:O(N)*
> *辅助空间:O(N)*

**方法 3:** 使用特征化器

在这种方法中，我们使用特性描述器方法 [current()](https://www.geeksforgeeks.org/characteriterator-current-method-in-java-with-examples/) 来获取当前角色，并使用 [next()](https://www.geeksforgeeks.org/characteriterator-next-method-in-java-with-examples/) 向前移动一个位置。StringCharacterIterator 提供了特性描述符的实现。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate Over the Characters of a String
// Using CharacterIterator

// Importing required libraries
import java.io.*;
import java.text.*;

// Main class
class GFG {

    // Method 1
    // To traverse the string and
    // print the characters of the string
    static void traverseString(String str)
    {
        CharacterIterator it
            = new StringCharacterIterator(str);

        // Iterate and print current character
        while (it.current() != CharacterIterator.DONE) {
            System.out.print(it.current() + " ");

            // Moving onto next element in the object
            // using next() method
            it.next();
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "GeeksforGeeks";

        // Calling the Method 1
        traverseString(str);
    }
}
```

**Output**

```java
G e e k s f o r G e e k s 
```

> *时间复杂度:O(N)*
> *辅助空间:O(1)*

**方法 4:** 使用 StringTokenizer

在这种方法中，我们在 Java 中使用 [StringTokenizer](https://www.geeksforgeeks.org/stringtokenizer-class-java-example-set-1-constructors/) 类。它根据分隔符将字符串分解成标记。不鼓励使用它。

```java
StringTokenizer(String str, String delim, boolean flag):
The first two parameters have same meaning.  The flag 
serves following purpose.

If the flag is false, delimiter characters serve to 
separate tokens. For example, if string is "hello geeks"
and delimiter is " ", then tokens are "hello" and "geeks".

If the flag is true, delimiter characters are 
considered to be tokens. For example, if string is "hello
 geeks" and delimiter is " ", then tokens are "hello", " " 
and "geeks".
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate Over the Characters of a String
// Using StringTokenizer

// Importing required librares
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Method 1
    // To traverse the string and
    // print the characters of the string
    static void traverseString(String str)
    {
        // If returnDelims is true, use the string itself as
        // a delimiter
        StringTokenizer st
            = new StringTokenizer(str, str, true);

        while (st.hasMoreTokens()) {
            System.out.print(st.nextToken() + " ");
        }

        System.out.println();

        // If returnDelims is false, use an empty string as
        // a delimiter
        st = new StringTokenizer(str, "", false);

        while (st.hasMoreTokens()) {
            System.out.print(st.nextToken() + " ");
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "GeeksforGeeks";

        /// Calling the above Method1
        traverseString(str);
    }
}
```

**Output**

```java
G e e k s f o r G e e k s 
GeeksforGeeks 
```

> *时间复杂度:O(N)*
> *辅助空间:O(N)*

**方法 5:** 使用 String.split()方法

在这种方法中，我们使用 String 类的 [split()](https://www.geeksforgeeks.org/split-string-java-examples/) 方法。它根据提供的正则表达式将字符串拆分为子字符串。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate Over the Characters of a String
// Using String.split() method

// Importing required classes from respective packages
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Method 1
    // To traverse the string and
    // print the characters of the string
    static void traverseString(String str)
    {
        // Split str around matches of empty string ""
        String[] substrings = str.split("");

      for (String ch : substrings) {
            System.out.print(ch + " ");
        }
    }

    // Method 2
    // main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "GeeksforGeeks";

        // Calling the Method1 to
        // print the characters of the string
        traverseString(str);
    }
}
```

**Output**

```java
G e e k s f o r G e e k s 
```

> *时间复杂度:O(N)*
> *辅助空间:O(N)*

**方法 6:** 利用番石榴文库

在这种方法中，我们使用**list . characters of(str)**方法，该方法返回一个不可变字符列表的视图。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate Over the Characters of a String
// Using Guava Library

// Importing required classes from respective packages
import com.google.common.collect.Lists;
import java.io.*;

// Main class
class GFG {

    // Method 1
    // To traverse the string and
    // print the characters of the string
    static void traverseString(String str)
    {
        // Using enhanced for loop
        for (Character ch : Lists.charactersOf(str)) {
            System.out.print(ch + " ");
        }

        // A new line is required
        System.out.println();

        // Using listIterator on the List
        // List<Characters>
        // iterator()
        // lambda
        Lists.charactersOf(str)
            .listIterator()
            .forEachRemaining(
                ch -> System.out.print(ch + " "));

        // A new line is required
        System.out.println();

        // Using method reference with listIterator
        // List<Characters>
        // iterator()
        Lists.charactersOf(str)
            .listIterator()
            .forEachRemaining(System.out::print);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "GeeksforGeeks";

        // Calling the Method1 to
        // print the characters of the string
        traverseString(str);
    }
}
```

**Output**

```java
G e e k s f o r G e e k s 
G e e k s f o r G e e k s 
GeeksforGeeks
```

> *时间复杂度:O(N)*
> *辅助空间:O(N)*

**方法 7:** 使用 String.chars()方法

在这种方法中，我们使用字符串类的**字符()**方法。由于性能原因，此方法不返回流<字符>对象。它返回一个**整数流**(整数流)对象，该对象可以转换为流<字符>(字符流)。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate Over the Characters of a String
// Using String.chars() method

// Importing classes from required packages
import com.google.common.collect.Lists;
import java.io.*;

// main class
class GFG {

    // Method 1
    // to traverse the string and
    // print the characters of the string
    static void traverseString(String str)
    {
        // Display message for better readability
        System.out.println(
            "Auto boxing into Stream<Character>");

        // Using method reference
        str.chars()
            .mapToObj(Character::toChars)
            .forEach(System.out::print);

        str.chars().forEach(System.out::print);

        // A new line is required
        System.out.println();

        // Using lambda expressions by casting int to char
        str.chars()
            .mapToObj(i -> Character.valueOf((char)i))
            .forEach(System.out::print);

        // A new line is required
        System.out.println();

        str.chars()
            .mapToObj(i -> (char)i)
            .forEach(System.out::print);

        // A new line is required
        System.out.println();
        str.chars()
            .mapToObj(
                i -> new StringBuilder().appendCodePoint(i))
            .forEach(System.out::print);

        // A new line is required
        System.out.println();

        // Display message for better readability
        System.out.println(
            "Without boxing into Stream<Character>");

        str.chars().forEach(
            i -> System.out.print(Character.toChars(i)));

        // A new line is required
        System.out.println();

        str.chars().forEach(i -> System.out.print((char)i));

        // A new line is required for
        // readability in output clearly
        System.out.println();

        str.chars().forEach(
            i
            -> System.out.print(
                new StringBuilder().appendCodePoint(i)));
    }

    // Method 2
    // main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "GeeksforGeeks";

        // Calling the Method 1 to
        // print the characters of the string
        traverseString(str);
    }
}
```

**Output**

```java
Auto boxing into Stream<Character>
GeeksforGeeks7110110110711510211111471101101107115
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
Without boxing into Stream<Character>
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
```

> *时间复杂度:O(N)*
> *辅助空间:O(N)*

**方法 8:** 使用代码点

在这种方法中，我们使用 [String.codePoints()](https://www.geeksforgeeks.org/intstream-codepoints-method-in-java-with-examples/) 方法返回一个 Unicode 值流。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate Over the Characters of a String
// Using Code Points

// importing classes from respective packages
import com.google.common.collect.Lists;
import java.io.*;

// main class
class GFG {

    // Method 1
    // To traverse the string and
    // print the characters of the string
    static void traverseString(String str)
    {
        // Display message for better readability
        System.out.println(
            "Auto boxing into Stream<Character>");

        // Using method reference
        str.codePoints()
            .mapToObj(Character::toChars)
            .forEach(System.out::print);
        str.codePoints().forEach(System.out::print);

        // New line is required
        System.out.println();

        // Using lambda expressions by casting int to char
        str.codePoints()
            .mapToObj(i -> Character.valueOf((char)i))
            .forEach(System.out::print);

        // New line is required
        System.out.println();

        // now using the codepoints() over the string
        str.codePoints()
            .mapToObj(i -> (char)i)
            .forEach(System.out::print);

        // New line is required
        System.out.println();

        str.codePoints()
            .mapToObj(
                i -> new StringBuilder().appendCodePoint(i))
            .forEach(System.out::print);

        System.out.println();

      // Display message for readability in output
      System.out.println(
            "Without boxing into Stream<Character>");
        str.codePoints().forEach(
            i -> System.out.print(Character.toChars(i)));

        System.out.println();

      str.codePoints().forEach(
            i -> System.out.print((char)i));

        System.out.println();

      str.codePoints().forEach(
            i
            -> System.out.print(
                new StringBuilder().appendCodePoint(i)));
    }

    // Method 2
    // main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "GeeksforGeeks";

       // Calling the Method1 to 
       // print the characters of the string
        traverseString(str);
    }
}
```

**Output**

```java
Auto boxing into Stream<Character>
GeeksforGeeks7110110110711510211111471101101107115
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
Without boxing into Stream<Character>
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
```

> *时间复杂度:O(N)*
> *辅助空间:O(N)*