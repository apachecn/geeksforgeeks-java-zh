# 使用 Lambda 表达式将数组列表转换为 Java 8 中的 HashMap

> 原文:[https://www . geesforgeks . org/converting-ArrayList-to-hashmap-in-Java-8-using-a-lambda-expression/](https://www.geeksforgeeks.org/converting-arraylist-to-hashmap-in-java-8-using-a-lambda-expression/)

lambda 表达式是一行或多行代码，其工作方式类似于函数或方法。它接受一个参数并返回值。Lambda 表达式可用于将数组列表转换为 HashMap。

**语法:**

```java
(parms1, parms2) -> expression
```

**例:**

```java
Input : List : [1="1", 2="2", 3="3"]
Output: Map  : {1=1, 2=2, 3=3, 4=4, 5=5}

Input : List : [1="I", 2="love", 3="Geeks" , 4="for" , 5="Geeks"]
Output: Map  : {1=I, 2=Love, 3=Geeks, 4=For, 5=Geeks}
```

**进场:**

1.  获取要转换为地图的列表
2.  创建一个空地图
3.  使用 Lambda 表达式将列表值放到映射中
4.  返回形成的地图

下面是上述方法的实现。

## 爪哇

```java
// Converting ArrayList to HashMap
// in Java 8 using a Lambda Expression
import java.util.*;
import java.util.ArrayList;
import java.util.Scanner;

// here we are making a class , and we will make
class ListItems {

    // key will act as an id of the value
    private Integer key;

    // value will be the value of the above key
    private String value;

    // create constructor for reference
    public ListItems(Integer id, String name)
    {

        // assigning the value of key and value
        this.key = id;
        this.value = name;
    }

    // return private variable key
    public Integer getkey() { return key; }

    // return private variable name
    public String getvalue() { return value; }
}
class Main {
    public static void main(String[] args)
    {
        // Write your code here

        // Creating a List of type ListItems using ArrayList
        List<ListItems> list = new ArrayList<ListItems>();

        // add the member of list
        list.add(new ListItems(1, "I"));
        list.add(new ListItems(2, "Love"));
        list.add(new ListItems(3, "Geeks"));
        list.add(new ListItems(4, "For"));
        list.add(new ListItems(5, "Geeks"));

        // Map which will store the list items
        Map<Integer, String> map = new HashMap<>();

        // for (ListItems n : list) { map.put(n.getkey(),
        // n.getvalue()); }
        // the below lambda  performs the same task as the
        // above given for loop will do
        // put the list items in the Map
        list.forEach(
            (n) -> { map.put(n.getkey(), n.getvalue()); });

        // Printing the given map
        System.out.println("Map : " + map);
    }
}
```

**输出**

```java
Map : {1=I, 2=Love, 3=Geeks, 4=For, 5=Geeks}
```

**时间复杂度:** O(N)，其中 N 是数组列表的长度。