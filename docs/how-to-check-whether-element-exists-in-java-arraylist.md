# 如何检查 Java 数组列表中是否存在元素？

> 原文:[https://www . geesforgeks . org/how-to-check-element-exist-in-Java-ArrayList/](https://www.geeksforgeeks.org/how-to-check-whether-element-exists-in-java-arraylist/)

[Java ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 是一个可调整大小的数组，可以在 java.util 包中找到。与内置数组不同，我们可以随时从数组列表中添加或删除元素。

**我们可以通过两种方式检查 java 中的 ArrayList 中是否存在** **元素:**

1.  使用 contains()方法
2.  使用 indexOf()方法

**方法 1:使用 contains()方法**

java.util.ArrayList 类的[**包含()**](https://www.geeksforgeeks.org/arraylist-contains-java/) 方法，可以用来检查一个元素是否存在于 Java ArrayList 中。

**语法:**

```
public boolean contains(Object)
```

**参数:**

*   **对象**–列表中待测试的元素

**返回:**如果在列表中找到指定的元素，则返回真，否则返回假。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check
// whether element exists
// in Java ArrayList

import java.io.*;
import java.util.ArrayList;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<Integer> list = new ArrayList<>();

        // use add() method to add elements in the list
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);

        // passing 5 as as as
        // parameter to contains()
        // function
        if (list.contains(5))
            System.out.println("5 exists in the ArrayList");

        else
            System.out.println("5 does not exist in the ArrayList");

        if (list.contains(2))
            System.out.println("2 exists in the ArrayList");

        else
            System.out.println("2 does not exist in the ArrayList");

    }
}
```

**Output**

```
5 does not exist in the ArrayList
2 exists in the ArrayList
```

**方法二:使用 indexOf()方法**

*   Contains() 方法使用 indexOf() 方法来确定列表中是否存在指定的元素。
*   所以我们也可以直接使用 indexOf() 方法来检查是否存在任何提供的元素值。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check 
// whether element exists 
// in Java ArrayList

import java.io.*;
import java.util.ArrayList;

class GFG {
    public static void main (String[] args) {
        ArrayList<Integer> list = new ArrayList<>();

      // use add() method to add elements in the list
      list.add(2);
      list.add(5);
      list.add(1);
      list.add(6);

      // passing 5 as as as
      // parameter to contains()
      // function
      if(list.indexOf(5)>=0)
        System.out.println("5 exists in the ArrayList");

      else
        System.out.println("5 does not exist in the ArrayList");

      if(list.indexOf(8)>=0)
         System.out.println("8 exists in the ArrayList");

      else
        System.out.println("8 does not exist in the ArrayList");

    }
}
```

**Output**

```
5 exists in the ArrayList
8 does not exist in the ArrayList
```