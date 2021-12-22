# 如何用 Java 打印 LinkedHashSet 元素？

> 原文:[https://www . geesforgeks . org/how-print-link edhashset-elements-in-Java/](https://www.geeksforgeeks.org/how-to-print-linkedhashset-elements-in-java/)

[**linked HashSet**](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/)**是 HashSet 的子类，其中不允许重复，但插入顺序保持不变。元素按照插入的顺序打印。**

****有几种方法可以打印 LinkedHashSet 元素:****

***   By simply printing elements*   By using the enhanced for loop*   Use [iterator](https://www.geeksforgeeks.org/iterators-in-java/)*   使用[阵列。tostring()](https://www.geeksforgeeks.org/arrays-tostring-in-java-with-examples/)*   Use **to print the LinkedHashSet elements with custom class objects. **toString()** method of object class**T21】**

****方法一:简单打印元素到控制台****

***   Let's make an example of LinkedHashSet, add elements to it, and simply print it to the console.*   One method is to simply print the name of the Collection object, and then print the contents of the LinkedHashSet.**

## **Java**

```
// Java program to print the elements of LinkedHashSet

import java.util.*;
class GfG {
    public static void main(String args[])
    {

        // Creating an instance of LinkedHashSet
        LinkedHashSet<String> hs = new LinkedHashSet<>();

        // Adding elements to the LinkedHashSet
        hs.add("Hey");
        hs.add("How");
        hs.add("are");
        hs.add("You");

        // Printing
        System.out.println(hs);
    }
}
```

****输出****

```
[Hey, How, are, You]
```