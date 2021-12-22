# 将字符数组转换为 IntStream 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-转换-字符-数组-intstream/](https://www.geeksforgeeks.org/java-program-to-convert-character-array-to-intstream/)

给定一个字符数组，任务是将这个数组转换成包含字符元素 ASCII 值的 IntStream。

**示例:**

```
Input: char[] = { 'G', 'e', 'e', 'k', 's' }
Output: 71, 101, 101, 107, 115

Input: char[] = { 'G', 'e', 'e', 'k', 's', 'F', 'o', 'r', 'G', 'e', 'e', 'k', 's' }
Output: 71, 101, 101, 107, 115, 70, 111, 114, 71, 101, 101, 107, 115

```

**算法:**

1.  获取要转换的字符数组。
2.  使用 Stream.of()方法将其转换为流。
3.  使用 flatMapToInt()方法将形成的流转换为输入流。
4.  打印形成的数据流。

下面是上述方法的实现:

```
// Java program to convert
// Character Array to IntStream

import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {

        // Get the Character Array to be converted
        Character charArray[] = { 'G', 'e', 'e', 'k', 's' };

        // Convert charArray to IntStream
        IntStream
            intStream
            = Stream

                  // Convert charArray into Stream of characters
                  .of(charArray)

                  // Convert the Stream of characters into IntStream
                  .flatMapToInt(IntStream::of);

        // Print the elements of the IntStream
        System.out.println("IntStream:");
        intStream.forEach(System.out::println);
    }
}
```

**输出:**

```
IntStream:
71
101
101
107
115

```