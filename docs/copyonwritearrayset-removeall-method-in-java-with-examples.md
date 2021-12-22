# Java 中的 CopyOnWriteArraySet removeAll()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarrayset-removeall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearrayset-removeall-method-in-java-with-examples/)

[copy onwriterarrayset](https://www.geeksforgeeks.org/copyonwritearrayset-in-java/)方法的 **removeAll()** 方法删除指定集合中存在的该 copy onwriterarrayset 的所有元素。这意味着这两个集合中常见的元素都将从这个 CopyOnWriteArraySet 中删除。

**语法:**

```
public boolean removeAll(Collection<E> c)
```

**参数:**该方法接受参数 **c** ，该参数是包含要从该集合中移除的元素的集合。

**返回值:**这个方法返回一个**布尔值**，比如 true，如果 CopyOnWriteArraySet 被改变的话。否则此方法返回 false。

**异常:**该方法抛出以下异常:

*   **ClassCastException** :如果这个集合的某个元素的类与指定的集合不兼容
*   **NullPointRexception**:如果该集合包含空元素，并且指定的集合不允许空元素，或者如果指定的集合为空。

下面的程序说明了 CopyOnWriteArrayList 类的 removeAll()函数:

**程序 1:**

```
// Java Program to illustrate the CopyOnWriteArraySet
// removeall() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet.add(10);
        ArrSet.add(20);
        ArrSet.add(30);
        ArrSet.add(50);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        // create object of ArrayList
        ArrayList<Integer> Arrlist
            = new ArrayList<Integer>();
        // add elements
        Arrlist.add(10);
        Arrlist.add(30);
        Arrlist.add(40);

        // print ArrayList
        System.out.println("ArrayList: " + Arrlist);

        // removing the common elements from
        // the CopyOnWriteArraySet using removeAll()
        System.out.println("Elements removed "
                           + "from CopyOnWriteArraySet: "
                           + ArrSet.removeAll(Arrlist));

        // print updated CopyOnWriteArraySet
        System.out.println("Updated CopyOnWriteArraySet: "
                           + ArrSet);
    }
}
```

**Output:**

```
CopyOnWriteArraySet: [10, 20, 30, 50]
ArrayList: [10, 30, 40]
Elements removed from CopyOnWriteArraySet: true
Updated CopyOnWriteArraySet: [20, 50]

```

**程序 2:** 显示空指针异常

```
// Java Program to illustrate the CopyOnWriteArraySet
// removeall() method in Java

import java.util.concurrent.CopyOnWriteArraySet;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create object of CopyOnWriteArraySet
        CopyOnWriteArraySet<Integer> ArrSet
            = new CopyOnWriteArraySet<Integer>();

        // Add elements
        ArrSet.add(10);
        ArrSet.add(20);
        ArrSet.add(30);
        ArrSet.add(50);

        // print CopyOnWriteArraySet
        System.out.println("CopyOnWriteArraySet: "
                           + ArrSet);

        try {

            // removing the null from
            // the CopyOnWriteArraySet using removeAll()
            // This will throw NullPointerException

            System.out.println("Elements removed "
                               + "from CopyOnWriteArraySet: "
                               + ArrSet.removeAll(null));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
CopyOnWriteArraySet: [10, 20, 30, 50]
java.lang.NullPointerException

```