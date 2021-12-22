# Java 中的 Arraylist removeRange()，示例

> 原文:[https://www . geesforgeks . org/ArrayList-remove range-Java-examples/](https://www.geeksforgeeks.org/arraylist-removerange-java-examples/)

Java 中 [**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 的 **removeRange()** 方法用于从数组列表对象中移除指定范围内的所有元素。它将任何后续元素向左移动。此调用通过(toIndex-fromIndex)元素来缩短列表，其中 toIndex 是结束索引，fromIndex 是开始索引，所有元素都将从该索引中删除。(如果 toIndex==fromIndex，此操作无效)
**语法:**

```
removeRange(int fromIndex, int toIndex)
```

**参数:**
有两个参数:
**1。fromIndex :** 要从中删除索引元素的起始索引。
**2。toIndex :** 在[from index-to index]范围内，所有元素都被删除。
参数为 **int** 数据类型。
**返回:**
此方法不返回任何值。它只移除指定范围内的所有元素。
**错误:**
***indexout of boundsexception***:如果 fromIndex 或 toIndex 超出范围(fromIndex = size()或 toIndex > size()或 to index<from index)
**示例 1** :演示 removeRange()方法的使用

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// working of removeRange() method
import java.util.*;

// extending the class to arraylist since removeRange()
// is a protected method
public class GFG extends ArrayList<Integer> {

    public static void main(String[] args)
    {

        // create an empty array list

        GFG arr = new GFG();

        // use add() method to add values in the list
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(12);
        arr.add(9);
        arr.add(13);

        // prints the list before removing
        System.out.println("The list before using removeRange:" + arr);

        // removing range of 1st 2 elements
        arr.removeRange(0, 2);
        System.out.println("The list after using removeRange:" + arr);
    }
}
```

**输出:**

```
The list before using removeRange:[1, 2, 3, 12, 9, 13]
The list after using removeRange:[3, 12, 9, 13]
```

**示例 2** :演示错误的程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the error in
// working of removeRange() method
import java.util.*;

// extending the class to arraylist since removeRange()
// is a protected method
public class GFG extends ArrayList<Integer> {

    public static void main(String[] args)
    {

        // create an empty array list

        GFG arr = new GFG();

        // use add() method to add values in the list
        arr.add(1);
        arr.add(2);
        arr.add(3);

        arr.removeRange(1, 4); // error as 4 is out of range

        System.out.println("The list after using removeRange:" + arr);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException
    at java.lang.System.arraycopy(Native Method)
    at java.util.ArrayList.removeRange(ArrayList.java:638)
    at GFG.main(GFG.java:25)
```

**注意** : removeRange(int fromIndex，int toIndex)方法是数组列表中**保护的方法**。受保护的方法可以在类、子类和包中访问，但不能是公共的。因此，我们将该类扩展到数组列表。