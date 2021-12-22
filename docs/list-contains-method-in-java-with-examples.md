# 列表包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/list-contains-in-Java-method-with-examples/](https://www.geeksforgeeks.org/list-contains-method-in-java-with-examples/)

Java 中 List 接口的 contains()方法用于检查指定的元素是否存在于给定的列表中。

**语法:**

```
public boolean contains(Object obj)

object-element to be searched for

```

**参数:**该方法接受单个参数*对象*，其在该列表中的存在将被测试。

**返回值:**如果在列表中找到指定的元素，则返回真，否则返回假。

下面的程序说明了列表中的 contains()方法:

**程序 1:** 演示整数列表中包含()的方法的工作。

```
// Java code to demonstrate the working of
// contains() method in List interface

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // creating an Empty Integer List
        List<Integer> arr = new ArrayList<Integer>(4);

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // use contains() to check if the element
        // 2 exits or not
        boolean ans = arr.contains(2);

        if (ans)
            System.out.println("The list contains 2");
        else
            System.out.println("The list does not contains 2");

        // use contains() to check if the element
        // 5 exits or not
        ans = arr.contains(5);

        if (ans)
            System.out.println("The list contains 5");
        else
            System.out.println("The list does not contains 5");
    }
}
```

**输出:**

```
The list contains 2
The list does not contains 5

```

**程序 2:** 演示字符串列表中包含()的方法的工作。

```
// Java code to demonstrate the working of
// contains() method in List of string

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // creating an Empty String List
        List<String> arr = new ArrayList<String>(4);

        // using add() to initialize values
        // ["geeks", "for", "geeks"]
        arr.add("geeks");
        arr.add("for");
        arr.add("geeks");

        // use contains() to check if the element
        // "geeks" exits or not
        boolean ans = arr.contains("geeks");

        if (ans)
            System.out.println("The list contains geeks");
        else
            System.out.println("The list does not contains geeks");

        // use contains() to check if the element
        // "coding" exits or not
        ans = arr.contains("coding");

        if (ans)
            System.out.println("The list contains coding");
        else
            System.out.println("The list does not contains coding");
    }
}
```

**输出:**

```
The list contains geeks
The list does not contains coding

```

**实际应用:**在搜索操作中，我们可以检查列表中是否存在给定的元素。

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/list . html # contains(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/List.html#contains(java.lang.Object))