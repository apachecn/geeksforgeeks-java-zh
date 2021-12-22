# 将字符串转换为字符串数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-string-to-string-array/](https://www.geeksforgeeks.org/java-program-to-convert-string-to-string-array/)

给定一个字符串，任务是将该字符串转换为 Java 中的字符串数组。如下图所示:

插图:

```java
Input:  String : "Geeks for Geeks"
Output: String[]: [Geeks for Geeks]
```

```java
Input: String    : "A computer science portal"
Output: String[] : [A computer science portal]
```

**方法:**

它们如下:

1.  使用 str.split()方法
2.  使用循环
3.  使用 Set.toArray()方法
4.  使用字符串标记器
5.  使用 pattern.split()方法

现在让我们深入讨论实现相同的每种方法，以便更好地理解相同的方法。它们如下:

**方法 1:** 使用 str.split()方法

**进场:**

*   创建字符串类型的数组。
*   使用 string_name.split()拆分给定的字符串。
*   将拆分的数组存储到字符串数组中。
*   打印上面的字符串数组。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert String to String Array
// Using str.split() method

// Importing input output classes
import java.io.*;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Input string to be convert to string array
        String str = "Geeks for Geeks";

        String strArray[] = str.split(" ");

        System.out.println("String : " + str);
        System.out.println("String array : [ ");

        // Iterating over the string
        for (int i = 0; i < strArray.length; i++) {
            // Printing the elements of String array
            System.out.print(strArray[i] + ", ");
        }

        System.out.print("]");
    }
}
```

**Output**

```java
String : Geeks for Geeks
String array : [ 
Geeks, for, Geeks, ]
```

**方法 2:** 使用循环

**进场:**

*   获取字符串集。
*   创建空字符串数组
*   使用高级 for 循环，将集合的每个元素复制到字符串数组中
*   打印字符串数组。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert String to String Array
// Using HashSet and Set classes

// Importing required classes from respective packages
import java.io.*;
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

// Main class
class GFG {
    // Method 1
    //  To convert Set<String> to String[]
    public static String[] method(Set<String> string)
    {
        // Create String[] of size of setOfString
        String[] string_array = new String[string.size()];

        // Copy elements from set to string array
        // using advanced for loop

        int index = 0;

        for (String str : string) {
            string_array[index++] = str;
        }

        // Return the formed String[]
        return string_array;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input string
        String str = "Geeks for Geeks";

        // Getting the Set of String
        Set<String> string_set
            = new HashSet<>(Arrays.asList(str));

        // Printing  the setOfString
        System.out.println("String: " + str);

        // Converting Set to String array
        String[] String_array = method(string_set);

        // Lastly printing the arrayOfString
        // using Arrays.toString() method
        System.out.println("Array of String: "
                           + Arrays.toString(String_array));
    }
}
```

**Output**

```java
String: Geeks for Geeks
Array of String: [Geeks for Geeks]
```

**方法 3:** 使用 Set.toArray()方法

**进场:**

*   将给定的字符串转换成一组字符串。
*   现在创建一个空字符串数组。
*   通过传递字符串类型的空数组，使用 set.toArray()将字符串集转换为字符串数组。
*   打印字符串数组。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert String to String Array
// Using Set.toArray() method

// Importing required classes from respective packages
import java.io.*;
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

// Main class
public class GFG {

    // Method 1
    // To convert Set<String> to string array
    public static String[] convert(Set<String> setOfString)
    {

        // Create String[] from setOfString
        String[] arrayOfString
            = setOfString.toArray(new String[0]);

        // return the formed String[]
        return arrayOfString;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Custom input string as input
        String str = "Geeks for Geeks";

        // Getting the Set of String
        Set<String> string
            = new HashSet<>(Arrays.asList(str));

        // Printing the setOfString
        System.out.println("String: " + str);

        // Converting Set to String array
        String[] string_array = convert(string);

        // Print the arrayOfString
        // using Arrays.toString() method
        System.out.println("String array : "
                           + Arrays.toString(string_array));
    }
}
```

**Output**

```java
String: Geeks for Geeks
String array : [Geeks for Geeks]
```

**方法 4:** [使用字符串标记器](https://www.geeksforgeeks.org/stringtokenizer-class-java-example-set-1-constructors/)

字符串标记器有助于将字符串对象分割成越来越小的部分。这些较小的部分被称为代币。

1.  标记给定的字符串
2.  创建一个具有标记计数大小的类型字符串数组。
3.  将这些标记存储到字符串数组中。
4.  打印字符串数组。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert String to String Array
// Using Set.toArray() method

// Importing required classes from respective packages
import java.io.*;
import java.util.StringTokenizer;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing integer variable
        // to zero
        int i = 0;

        // Custom input string as input
        String str = "Geeks for Geeks";

        // Tokenize a given string using the default
        // delimiter
        StringTokenizer str_tokenizer
            = new StringTokenizer(str);

        String[] string_array
            = new String[str_tokenizer.countTokens()];
        // Add tokens to our array

        while (str_tokenizer.hasMoreTokens()) {
            string_array[i] = str_tokenizer.nextToken();
            i++;
        }

        // Print and display the string
        System.out.print("String :" + str);

        // Display message
        System.out.print("\nString array : [ ");

        // Printing hte string array
        // using for each loop
        for (String string : string_array) {
            System.out.print(string + " ");
        }

        System.out.print("]");
    }
}
```

**Output**

```java
String :Geeks for Geeks
String array : [ Geeks for Geeks ]
```

**方法 5:** 使用 pattern.split()方法

这个 pattern.split()方法的目的是根据给定的模式将给定的字符串分解成一个数组。我们可以通过给出一些特定的模式来拆分我们的字符串。

**进场:**

1.  定义模式(REGEX)
2.  然后使用编译方法创建一个模式
3.  然后使用*模式分割字符串，用特定的模式分割()*并将其存储在数组中。
4.  打印字符串数组

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert String to String Array
// Using Set.toArray() method

// Importing required classes from respective packages
import java.io.*;
import java.util.regex.Pattern;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Custom string as input
        String str = "Geeks for Geeks";

        // Step 1: Define REGEX
        String my_pattern = "\\s";

        // Step 2: Create a pattern using compile method
        Pattern pattern = Pattern.compile(my_pattern);

        // Step 3: Create an array of strings using the
        // pattern we already defined
        String[] string_array = pattern.split(str);

        // Print and display string and
        // its corresponding string array
        System.out.print("String : " + str);
        System.out.print("\nString array : [ ");

        // Iterating over the string
        for (int i = 0; i < string_array.length; i++) {
            // Printing the string array
            System.out.print(string_array[i] + " ");
        }

        System.out.print("]");
    }
}
```

**Output**

```java
String : Geeks for Geeks
String array : [ Geeks for Geeks ]
```