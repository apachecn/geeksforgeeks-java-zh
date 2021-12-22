# 检查一个元素是否出现在列表中的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-check-一个元素是否出现在列表中/](https://www.geeksforgeeks.org/java-program-to-check-whether-an-element-occurs-in-a-list/)

Java 中的[列表界面](https://www.geeksforgeeks.org/list-interface-java-examples/)代表一个有序的集合或序列。这个接口帮助我们控制插入元素的位置，并通过整数索引访问元素。这个接口是 Java 集合框架和 java.util 包的成员。实现列表接口的类包括[数组列表、](https://www.geeksforgeeks.org/arraylist-in-java/)T4】链表、[栈](https://www.geeksforgeeks.org/stack-data-structure/)和[向量。](https://www.geeksforgeeks.org/java-util-vector-class-java/)Vector 类从 Java 5 开始就被弃用了。

类、数组列表、链接列表和堆栈都使用 [**contains()方法**](https://www.geeksforgeeks.org/list-contains-method-in-java-with-examples/) 来检查列表中是否有元素。

Java 中 List 接口的 **contains()** 方法用于检查给定列表中是否存在指定元素。

**语法:**

```
public boolean contains(Object obj)

object-element to be searched for
```

**参数:**该方法接受单个参数*对象*，其在该列表中的存在将被测试。

**返回值:**如果在列表中找到指定的元素，则返回真，否则返回假。

**步骤:**

1.  导入必要的包。在这种情况下，我们需要导入 java.util 包。
2.  借助列表界面创建一个数组列表。
3.  使用 Add()方法将元素添加到数组列表中。
4.  借助 contains()方法检查所需的元素是否出现在数组列表中。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check whether an element
// is present in an ArrayList

// importing package
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // Creating an ArrayList of String type
        List<String> GFG = new ArrayList<String>();

        // Adding elements to the ArrayList
        GFG.add("Welcome");
        GFG.add("To");
        GFG.add("Geeks");
        GFG.add("For");
        GFG.add("Geeks");

        //  Using contains() method to check whether the
        //  particular
        // element is present in the List or not
        System.out.println(GFG.contains("Welcome")); 
        System.out.println(GFG.contains("Java")); 
    }
}
```

**Output**

```
true
false
```