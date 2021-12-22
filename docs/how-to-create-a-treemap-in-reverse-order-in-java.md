# 如何在 Java 中反向创建树形图

> 原文:[https://www . geeksforgeeks . org/如何在 java 中以逆序创建树形图/](https://www.geeksforgeeks.org/how-to-create-a-treemap-in-reverse-order-in-java/)

默认情况下，Java 中的[树形图](https://www.geeksforgeeks.org/treemap-in-java/)元素按照键的升序排序。但是，我们可以使用 Java 中的 [Collections.reverseOrder()方法以相反的顺序创建树形图，并按键的降序显示元素。](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/)

Java 中的**collections . reverseorders()**方法返回一个比较器，该比较器对传递的比较器对象施加相反的顺序。我们可以使用这个方法按照用户定义的比较器的相反顺序对任何列表或任何其他集合进行排序。

**示例**:

```java
// Insert elements to the TreeMap

Input : treemap.put("1", "Welcome");
             treemap.put("2", "to");
             treemap.put("3", "the");
             treemap.put("4", "Geeks");
             treemap.put("5", "Community");

// Elements should be printed in reverse order
// of their insertion
Output : 5: Community
               4: Geeks
               3: the
               2: to
               1: Welcome

```

下面的程序展示了如何以相反的顺序遍历树形图:

```java
// Java program to traverse a TreeMap
// in reverse order
import java.util.*;

class GFG {
    public static void main(String args[])
    {
        // Map to store the elements
        Map<String, String> treemap = 
               new TreeMap<String, String>(Collections.reverseOrder());

        // Put elements to the map
        treemap.put("1", "Welcome");
        treemap.put("2", "to");
        treemap.put("3", "the");
        treemap.put("4", "Geeks");
        treemap.put("5", "Community");

        Set set = treemap.entrySet();
        Iterator i = set.iterator();

        // Traverse map and print elements
        while (i.hasNext()) {
            Map.Entry me = (Map.Entry)i.next();
            System.out.print(me.getKey() + ": ");
            System.out.println(me.getValue());
        }
    }
}
```

**Output:**

```java
5: Community
4: Geeks
3: the
2: to
1: Welcome

```