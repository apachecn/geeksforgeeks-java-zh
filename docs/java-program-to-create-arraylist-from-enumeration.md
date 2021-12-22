# 从枚举创建数组列表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-create-ArrayList-from-enumeration/](https://www.geeksforgeeks.org/java-program-to-create-arraylist-from-enumeration/)

[枚举](https://www.geeksforgeeks.org/enum-in-java/)用于在编程语言中表示一组命名常数。当我们在编译时知道所有可能的值时，例如菜单上的选项、舍入模式、命令行标志等，就使用枚举。枚举类型中的常量集不必一直保持固定。

**从枚举创建数组列表的步骤:**

1.  创建一个向量并添加元素。
2.  使用 vector 的 element()方法获取 vector 元素的枚举。
3.  使用集合的列表(枚举 e)方法获取数组列表。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Create Java ArrayList From Enumeration

import java.util.ArrayList;
import java.util.Collections;
import java.util.Enumeration;
import java.util.Vector;

class GFG {

    public static void main(String[] arg)
    {

        // creating and adding elements to Vector
        Vector<String> v = new Vector<String>();
        v.add("Geeks");
        v.add("For");
        v.add("Geeks");
        v.add("2020");
        v.add("2021");

        // Displaying vector elements
        System.out.println("Elements in vector : " + v);

        // getting enumeration of the vector element
        Enumeration<String> elementsEnumeration = v.elements();

        //  list(Enumeration e) method returns an ArrayList
        //  containing the elements returned by the
        //  specified Enumeration
        ArrayList<String> arrayList
            = Collections.list(elementsEnumeration);

        // Displaying arraylist element
        System.out.println("Elements in arraylist : "
                           + arrayList);
    }
}
```

**输出:**

```java
Elements in vector : [Geeks, For, Geeks, 2020, 2021]
Elements in arraylist : [Geeks, For, Geeks, 2020, 2021]
```