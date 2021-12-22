# Java 中的数组列表 lastIndexOf()，示例

> 原文:[https://www . geesforgeks . org/ArrayList-last indexof-Java-example/](https://www.geeksforgeeks.org/arraylist-lastindexof-java-example/)

Java 中 [**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 的 **lastIndexOf()** 方法用于获取数组列表对象中元素最后一次出现的索引。

**语法:**

```
lastIndexOf(element)
```

**参数:**要返回最后一个索引的元素。

**返回:**
返回参数中传递的元素的最后一次出现。如果找不到元素，则返回-1。

演示 lastIndexOf()工作原理的程序:

```
// Java code to demonstrate the working of
// lastIndexOf() method in ArrayList

// for ArrayList functions
import java.util.ArrayList;

public class GFG {
    public static void main(String[] args)
    {

        // creating an Empty Integer ArrayList
        ArrayList<Integer> arr = new ArrayList<Integer>(7);

        // using add() to initialize values
        arr.add(10);
        arr.add(20);
        arr.add(30);
        arr.add(40);
        arr.add(30);
        arr.add(30);
        arr.add(40);

        System.out.println("The list initially " + arr);

        // last index of 30

        int element = arr.lastIndexOf(30);
        if (element != -1)
            System.out.println("the lastIndexof of" + 
                             " 30 is " + element);
        else
            System.out.println("30 is not present in" + 
                                        " the list");

        // last index of 100
        element = arr.lastIndexOf(100);
        if (element != -1)
            System.out.println("the lastIndexof of 100" + 
                                      " is " + element);
        else
            System.out.println("100 is not present in" + 
                                           " the list");
    }
}
```

**输出:**

```
The list initially [10, 20, 30, 40, 30, 30, 40]
the lastIndexof of 30 is 5
100 is not present in the list

```