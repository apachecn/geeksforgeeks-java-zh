# Java 中的 IntStream codePoints()方法，带示例

> 原文:[https://www . geesforgeks . org/int stream-code points-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intstream-codepoints-method-in-java-with-examples/)

**IntStream** 类的**代码点()**方法用于从给定序列中获取代码点值流。它返回作为参数传递的字符的 ASCII 值

**语法:**

```
public IntStream codePoints()
```

**返回值:**该方法返回**输入流代码值**

以下示例说明了 codePoints()方法的使用:

**例 1:**

```
// Java program to demonstrate
// codePoints() method of IntStream class

import java.util.stream.IntStream;

public class GFG {
    public static void main(String args[])
    {

        // String to be converted
        String str = "GeeksForGeeks";

        // Convert the string to code values
        // using codePoints() method
        IntStream stream = str.codePoints();

        System.out.println("ASCII Values are: ");

        // Print the code points
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```
ASCII Values are: 
71
101
101
107
115
70
111
114
71
101
101
107
115

```

**例 2:**

```
// Java program to demonstrate
// codePoints() method of IntStream class

import java.util.stream.IntStream;

public class GFG {
    public static void main(String args[])
    {

        // String to be converted
        String str = "A computer science"
                     + " portal for geeks";

        // Convert the string to code values
        // using codePoints() method
        IntStream stream = str.codePoints();

        System.out.println("ASCII Values are: ");

        // Print the code points
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```
ASCII Values are: 
65
32
99
111
109
112
117
116
101
114
32
115
99
105
101
110
99
101
32
112
111
114
116
97
108
32
102
111
114
32
103
101
101
107
115

```