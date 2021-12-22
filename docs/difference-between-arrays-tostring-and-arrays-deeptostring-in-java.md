# Java 中 Arrays.toString()和 Arrays.deepToString()的区别

> 原文:[https://www . geeksforgeeks . org/arrays-to string-and-arrays-deep tostring-in-Java/](https://www.geeksforgeeks.org/difference-between-arrays-tostring-and-arrays-deeptostring-in-java/)

Arrays 类的 [**deepToString()**](https://www.geeksforgeeks.org/arrays-deeptostring-in-java-with-example/) 方法返回指定对象数组深层内容的字符串表示形式。不像[T5 数组。 **toString()**](https://www.geeksforgeeks.org/arrays-tostring-in-java-with-examples/) ，如果数组包含其他数组作为元素，则字符串表示包括它们的内容，以此类推。

[**arrays . ToString()**](https://www.geeksforgeeks.org/arrays-tostring-in-java-with-examples/)**:返回指定数组内容的字符串表示形式。字符串表示形式由包含在方括号(“[]”)中的数组元素列表组成。相邻的元素由字符“，”(逗号后跟空格)分隔。如果为空，则返回“null”。**

在对象数组的情况下，如果数组包含其他数组作为元素，它们将通过从对象继承的 Object.toString()方法转换为字符串，该方法描述它们的标识而不是内容。

*   **参数:**要返回其字符串表示形式的数组。
*   **返回:**数组的字符串表示。

[**arrays . deeptostring()**](https://www.geeksforgeeks.org/arrays-deeptostring-in-java-with-example/)T4:[Java . util . arrays . deeptostring(Object[])](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html#deepToString(java.lang.Object[]))方法是一个 [java.util.Arrays 类](https://www.geeksforgeeks.org/array-class-in-java/)方法。返回指定数组的“深层内容”的字符串表示形式。如果数组包含其他数组作为元素，则字符串表示包含它们的内容，依此类推。此方法设计用于将多维数组转换为字符串。简单的 toString()方法适用于简单数组，但不适用于多维数组。此方法设计用于将多维数组转换为字符串。

**语法:**

> 公共静态字符串深度字符串(对象[] arr)
> 
> arr–需要字符串表示的数组
> 
> 此函数返回 arr[]的字符串表示形式。如果指定的数组为空，则返回“null”。

### **Java 中 Arrays.toString()和 Arrays.toDeepString()的区别**

<figure class="table">

| 

**Arrays.toString()**

 | 

**Arrays.deepToString()**

 |
| --- | --- |
| 我们在 java 中使用 Arrays.toString()来获取对象的字符串表示 | 我们使用 Arrays.deepToString()方法来获取特定数组深层内容的字符串表示。 |
| 我们广泛使用 Arrays.toString()来返回一维数组的 String()表示。 | 我们可以使用 Arrays.deepToString()方法返回一维和多维数组的字符串表示形式。 |
| 如果数组包含其他数组作为元素，则字符串表示不包含其内容，依此类推。 | 如果数组包含其他数组作为元素，则字符串表示包含它们的内容，依此类推。 |
| 我们不使用 Arrays.toString()方法返回多维数组的字符串表示形式。 | 我们可以使用 Arrays.deepToString()方法返回多维数组的字符串表示形式。 |
| Arrays.toString()处理基元数组。 | Arrays.deepToString()不适用于基元。 |

</figure>

下面是 Arrays.toString()和 Arrays.deepToString()的图示**:**

**1。**一维**整数数组。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the usage of
// Arrays.toString() and Arrays.deepToString()

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        Integer[] a = { 1, 2, 3, 4, 5 };
        System.out.println("Using Arrays.toString(): "
                           + Arrays.toString(a));

        System.out.println("Using Arrays.deepToString(): "
                           + Arrays.deepToString(a));
    }
}
```

**Output**

```java
Using Arrays.toString(): [1, 2, 3, 4, 5]
Using Arrays.deepToString(): [1, 2, 3, 4, 5]

```

**2。**一维**基元数组**，其中只有 Arrays.toString()起作用。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the usage of
// Arrays.toString() and Arrays.deepToString()

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        int[] a = { 1, 2, 3, 4, 5 };
        System.out.println("Using Arrays.toString(): "
                           + Arrays.toString(a));
    }
}
```

**Output**

```java
Using Arrays.toString(): [1, 2, 3, 4, 5]

```

**3。** **多维阵列:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the usage of 
// Arrays.toString() and Arrays.deepToString()

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        Integer[] a1 = { 1, 2, 3, 4, 5 };
        Integer[] a2 = { 6, 7, 8, 9, 10 };
        Integer[][] multi = { a1, a2 };

        System.out.println("Using Arrays.toString(): "
                           + Arrays.toString(multi));

        System.out.println("Using Arrays.deepToString(): "
                           + Arrays.deepToString(multi));
    }
}
```

**Output**

```java
Using Arrays.toString(): [[Ljava.lang.Integer;@3d075dc0, [Ljava.lang.Integer;@214c265e]
Using Arrays.deepToString(): [[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]]

```