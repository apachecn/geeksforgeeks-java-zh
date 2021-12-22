# 将字符串转换为整数数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-string-to-integer-array/](https://www.geeksforgeeks.org/java-program-to-convert-string-to-integer-array/)

**字符串–**Java 中的字符串是由一个字符数组在内部支持的对象。由于数组是不可变的，而字符串也是一种保存字符的特殊数组，因此字符串也是不可变的。

**整数数组–**数组是同一类型变量的组合。同样，由一个通用名称引用的整数(int)的集合是一个整数数组。

**问题陈述–**给定一个字符串，任务是将那个**字符串**转换成**整数数组**。

让我们先看几个例子，让它更清楚。

**示例:**

```java
Input  : String : "1 23 456 7890"
Output : Integer array : [1 23 456 7890]
```

```java
Input  : String : "[1,2,356,678,3378]"
Output : Integer array : [1, 2, 356, 678, 3378]
```

有许多方法可以做到这一点；下面列出了其中的一些。

**方法:**

1.  使用 string.replaceAll()方法
2.  使用 string.split()方法

### **方法 1–**使用 string.replaceAll()方法

[string.replaceAll()](https://www.geeksforgeeks.org/java-lang-string-replace-method-java/) 方法接受两个参数，一个正则表达式和替换值。此方法将使用给定的替换值替换给定的正则表达式，然后使用 split()方法拆分字符串。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert String to Integer Array
// Using string.replaceAll() method

// Importing input output and utility classes
import java.io.*;
import java.util.Arrays;

public class GFG {
    public static void main(String[] args)
    {
        // declaring the string
        String str = "[1,2,356,678,3378]";

        // calling replaceAll() method and split() method on
        // string
        String[] string = str.replaceAll("\\[", "")
                              .replaceAll("]", "")
                              .split(",");

        // declaring an array with the size of string
        int[] arr = new int[string.length];

        // parsing the String argument as a signed decimal
        // integer object and storing that integer into the
        // array
        for (int i = 0; i < string.length; i++) {
            arr[i] = Integer.valueOf(string[i]);
        }

        // printing string
        System.out.print("String : " + str);

        // printing the Integer array
        System.out.print("\nInteger array : "
                         + Arrays.toString(arr));
    }
}
```

**Output**

```java
String : [1,2,356,678,3378]
Integer array : [1, 2, 356, 678, 3378]
```

### **方法 2–使用 string.split()方法**

[string.split()](https://www.geeksforgeeks.org/split-string-java-examples/) 方法用于将字符串拆分成各种子字符串。然后，使用 integer.parseInt()方法将这些子字符串转换为整数，并将该值整数值存储到 Integer 数组中。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert String to Integer Array
// Using string.split() method

// Importing input output and utility classes
import java.io.*;

public class GFG {
    // Function for conversion
    static int[] method(String str)
    {

        String[] splitArray = str.split(" ");
        int[] array = new int[splitArray.length];

        // parsing the String argument as a signed decimal
        // integer object and storing that integer into the
        // array
        for (int i = 0; i < splitArray.length; i++) {
            array[i] = Integer.parseInt(splitArray[i]);
        }
        return array;
    }

    // main method
    public static void main(String[] args)
    {
        // Bufferedreader declaration
        BufferedReader br = new BufferedReader(
            new InputStreamReader(System.in));

        // string declaration
        String str = "1 23 456 7890";
        int i;

        // declaring the variable & calling the method with
        // passing string as an argument
        int[] array = method(str);

        // printing the string
        System.out.print("\nString : " + str);

        // printing the Integer array
        System.out.print("\nInteger array : [");
        for (i = 0; i < array.length; i++) {
            System.out.print(array[i] + " ");
        }

        System.out.print("]");
    }
}
```

**Output**

```java
String : 1 23 456 7890
Integer array : [1 23 456 7890 ]
```