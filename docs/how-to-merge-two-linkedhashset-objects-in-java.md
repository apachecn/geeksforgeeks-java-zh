# 如何在 Java 中合并两个链接的 HashSet 对象？

> 原文:[https://www . geesforgeks . org/how-two-link edhashset-objects-in-Java/](https://www.geeksforgeeks.org/how-to-merge-two-linkedhashset-objects-in-java/)

使用 addAll()方法合并两个 LinkedHashSet 对象或将一个 LinkedHashSet 对象的元素追加到另一个 LinkedHashSet 对象。与集合相比，addAll()方法被用作 Union。 [addAll](https://www.geeksforgeeks.org/java-util-arraylist-addall-method-java/) 方法将指定集合的所有元素添加到该集合对象中。

**示例:**

```
Input : List1 = [1,2,3], List2 = [3, 4, 5]
Output: [1, 2, 3, 4, 5]

Input : List1 = ['a', 'b', 'c'], List2 = ['d']
Output: ['a', 'b', 'c', 'd']
```

**语法:**

```
boolean addAll(Collection<? extends E> collection)
```

**参数:**这是包含要添加到此列表的元素的集合。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// How to merge two LinkedHashSet objects in Java?
import java.util.LinkedHashSet;
public class MergedLinkedHashSet {

    public static void main(String[] args)
    {

        LinkedHashSet<String> lhSetColors1
            = new LinkedHashSet<String>();

        lhSetColors1.add("yellow");
        lhSetColors1.add("white");
        lhSetColors1.add("black");

        LinkedHashSet<String> lhSetColors2
            = new LinkedHashSet<String>();

        lhSetColors2.add("yellow");
        lhSetColors2.add("red");
        lhSetColors2.add("green");

        /*
         * To merge two LinkedHashSet objects or
         * append LinkedHashSet object to another, use the
         * addAll method
         */
        lhSetColors1.addAll(lhSetColors2);

        System.out.println("Merged LinkedHashSet: "
                           + lhSetColors1);
    }
}
```

**Output**

```
Merged LinkedHashSet: [yellow, white, black, red, green]
```