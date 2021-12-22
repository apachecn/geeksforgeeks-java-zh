# 将集合更改为数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-更改-集合-数组/](https://www.geeksforgeeks.org/java-program-to-change-a-collection-to-an-array/)

数组是包含元素的线性数据结构，元素的大小是在创建时定义的，并且可以保存对象和原始同类数据。集合是一个预定义的类，只包含异构对象类型，但包含原语。方法可用于将一个集合更改为 java 中的数组。以下方法可用于将集合转换为数组:

1.  使用 [*列表()方法*](https://www.geeksforgeeks.org/list-add-method-in-java-with-examples/)
2.  [*使用*](https://www.geeksforgeeks.org/list-array-java/) 方法

**方法 1:** 使用 list.add()方法
使用 list.add() 在列表中的指定位置插入指定元素 E。

**语法:**

```
public void add(int index, E element);
```

**参数:**

*   **索引**:要插入元素的索引。
*   **元素**:要插入的元素。

**返回值**:这个方法不返回任何东西。
T3】例外:

*   [*指数超出范围时的边界异常*](https://www.geeksforgeeks.org/understanding-array-indexoutofbounds-exception-in-java/) *:* 。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to change Collection to an array

import java.util.Arrays;
import java.util.ArrayList;
import java.util.Arrays;

// Or simply add all generic lava libraries
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating arrayList list dynamically
        List<String> list = new ArrayList<String>();
        // List is created

        // Adding elements to the list
        list.add("Geeks ");
        list.add("for ");
        list.add("Geeks ");
        list.add("is ");
        list.add("the ");
        list.add("Best.");

        // Converting list to an array
        String[] str = list.toArray(new String[0]);

        // Iterating over elements of array
        for (int i = 0; i < str.length; i++) {
            String data = str[i];

            // Printing elements of an array
            System.out.print(data);
        }
    }
}
```

**输出:**

```
Geeks for Geeks is the Best
```

**方法 2:** 使用 list.toArray()方法

是 [*列表界面*](https://www.geeksforgeeks.org/list-interface-java-examples/) 中存在的一种方法，将列表中的所有元素按顺序作为数组返回。

**语法:**

```
 public Object[] toArray() ;
```

**参数:**

*   它由接口集合和接口列表中的' toArray '指定
*   它覆盖了类抽象集合中' toArray '
*   它返回一个数组，该数组以正确的顺序包含列表中的所有元素。

**返回类型:**值

```
An array of sequential elements of the list
```

**实现:**下面是一个清晰理解方法及其用法的例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert Collections into Array

// Importing generic Java libraries
import java.util.*;
import java.io.*;

public class GFG {

    // Main driver code
    public static void main(String[] args)
    {
        // Reading input from the user
        // via BufferedReader class
        BufferedReader in = new BufferedReader(
            new InputStreamReader(System.in));
        // 'in' is object created of this class

        // Creating object of Scanner class
        Scanner sc = new Scanner(System.in);

        // Creating ArrayList to store user input
        List<String> list = new ArrayList<String>();

        // Taking input from user
        // adding elements to the list
        while (sc.hasNext()) {
            String i = sc.nextLine();
            list.add(i);
        }

        // Converting list to an array
        String[] str = list.toArray(new String[0]);

        // Iteration over array
        for (int i = 0; i < str.length; i++) {
            String data = str[i];

            // Printing the elements
            System.out.print(data);
        }
    }
}
```

**输出:**

```
User Input : Geeks for Geeks
Output     : Geeks for Geeks
```