# Java 中的数组流()方法

> 原文:[https://www.geeksforgeeks.org/arrays-stream-method-in-java/](https://www.geeksforgeeks.org/arrays-stream-method-in-java/)

### 流(T[]数组)

Java 中**数组类**的**流(T[]数组)**方法用于从作为参数传递的数组及其元素中获取一个顺序流。它返回一个顺序流，数组的元素作为参数传递，作为它的源。

**语法:**

```
public static <T> Stream<T> stream(T[] array)
```

**参数:**该方法接受一个强制参数**数组**，该数组的元素将被转换为一个顺序流。

**返回值:**该方法从作为参数传递的数组中返回一个**顺序流**。

下面是说明 Arrays.stream()方法的示例:

**程序 1:** Arrays.stream()将字符串数组转换为流。

```
// Java program to demonstrate Arrays.stream() method

import java.util.*;
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a String array
        String[] arr = { "Geeks", "for", "Geeks" };

        // Using Arrays.stream() to convert
        // array into Stream
        Stream<String> stream = Arrays.stream(arr);

        // Displaying elements in Stream
        stream.forEach(str -> System.out.print(str + " "));
    }
}
```

**Output:**

```
Geeks for Geeks

```

**程序 2:** Arrays.stream()将 int 数组转换为 stream。

```
// Java program to demonstrate Arrays.stream() method

import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String[] args)
    {
        // Creating an integer array
        int arr[] = { 1, 2, 3, 4, 5 };

        // Using Arrays.stream() to convert
        // array into Stream
        IntStream stream = Arrays.stream(arr);

        // Displaying elements in Stream
        stream.forEach(str -> System.out.print(str + " "));
    }
}
```

**Output:**

```
1 2 3 4 5

```

### 流(T[]数组，int startInclusive，int endExclusive)

Java 中**数组类**的**流(T[]数组，int startInclusive，int endExclusive)** 方法用于从作为参数传递的数组中获取一个顺序流，该数组只有一些特定的元素。这些特定元素取自作为参数传递给此方法的一系列索引。它返回一个以指定数组的指定范围为源的顺序流。

**语法:**

```
public static <T> Stream<T> 
    stream(T[] array, int startInclusive, int endExclusive)
```

**参数:**该方法接受三个强制参数:

*   **数组**是其元素将被转换为连续流的数组。
*   **startInclusive** 是第一个覆盖的指数，包含
*   **endExclusive** 是紧接着要覆盖的最后一个索引之后的索引

**返回值:**该方法返回一个**序列流**，该序列流由作为参数传递的数组元素范围形成。

下面是说明 Arrays.stream()方法的示例:

**程序 1:** Arrays.stream()将字符串数组转换为流。

```
// Java program to demonstrate Arrays.stream() method

import java.util.*;
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a String array
        String[] arr = { "Geeks", "for", "Geeks",
                         "A", "Computer", "Portal" };

        // Using Arrays.stream() to convert
        // array into Stream
        Stream<String> stream = Arrays.stream(arr, 3, 6);

        // Displaying elements in Stream
        stream.forEach(str -> System.out.print(str + " "));
    }
}
```

**Output:**

```
A Computer Portal

```

**程序 2:** Arrays.stream()将 int 数组转换为 stream。

```
// Java program to demonstrate Arrays.stream() method

import java.util.*;
import java.util.stream.*;

class GFG {

    public static void main(String[] args)
    {
        // Creating an integer array
        int arr[] = { 1, 2, 3, 4, 5 };

        // Using Arrays.stream() to convert
        // array into Stream
        IntStream stream = Arrays.stream(arr, 1, 3);

        // Displaying elements in Stream
        stream.forEach(str -> System.out.print(str + " "));
    }
}
```

**Output:**

```
2 3

```