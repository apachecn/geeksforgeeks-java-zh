# 在 Java 中将数组转换为集合

> 原文:[https://www . geesforgeks . org/将数组转换为 java 集合/](https://www.geeksforgeeks.org/convert-an-array-into-collection-in-java/)

Java **集合**提供了一个存储和操作对象组的架构。数据的数据类型可以更改为常规数据类型，如数组到集合。要将基于数组的数据转换为  集合基于我们可以使用 **java。乌提尔。** **阵列** **类**。这个类提供一个静态方法 asList(T… a)，将数组转换为  集合。

#### **步骤:**

*   定义一个函数来编写逻辑
*   从用户那里获取数组输入
*   借助 [**asList()**](https://www.geeksforgeeks.org/arrays-aslist-method-in-java-with-examples/) 功能将数组输入转换为**集合**。

**使用的方法:**

**1。asList():** 这个方法的 [**java.util.Arrays**](https://www.geeksforgeeks.org/array-class-in-java/) 类用于返回一个固定大小的列表，该列表由指定的数组支持，并作为基于数组和基于集合的 API 之间的桥梁，与 Collection.toArray()结合使用。

这在 O(1)时间内运行。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Convert an Array into Collection in Java

// import java util library
import java.util.*;

// class for writing logic of the problem
public class ArrayToCollection {
    public static void main(String args[])
    {
        // array input
        String playersArray[]
            = { "Virat", "Sachin", "Rohit", "Bumrah" };

        // printing input elements for comparision
        System.out.println("Array input: "
                           + Arrays.toString(playersArray));

        // converting array into Collection
        // with asList() function
        List playersList = Arrays.asList(playersArray);

        // print converted elements
        System.out.println("Converted elements: "
                           + playersList);
    }
}
```

**输出:**

```
Array input: [Virat, Sachin, Rohit, Bumrah]
Converted elements: [Virat, Sachin, Rohit, Bumrah]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Convert an Array into Collection in Java

// import java util library
import java.util.*;

public class ArrayToCollection {

    public static void main(String args[])
    {
        String countryArray[]
            = { "India", "Pakistan", "Afganistan",
                "Srilanka" };

        System.out.println("Array input: "
                           + Arrays.toString(countryArray));

        List countryList = Arrays.asList(countryArray);
        System.out.println("Converted elements: "
                           + countryList);
    }
}
```

**输出:**

```
Array input: [India, Pakistan, Afganistan, Srilanka]
Converted elements: [India, Pakistan, Afganistan, Srilanka]

```