# Java 中的 NavigableSet lower()方法

> 原文:[https://www . geesforgeks . org/navigableset-Java 中的下方法/](https://www.geeksforgeeks.org/navigableset-lower-method-in-java/)

Java 中[navigatableset 接口的 lower()方法用于返回该集合中严格小于给定元素的最大元素，如果集合中不存在这样的元素，则返回 null。](https://www.geeksforgeeks.org/navigableset-java-examples/)

**语法** :

```
E lower(E ele)

```

其中，E 是此 Set 容器维护的元素类型。

**参数**:该功能接受一个参数*元素*，该参数是指该 Set 容器维护的元素类型。

**返回值**:返回该集合中最大的元素，严格小于给定的元素，如果没有这样的元素，则返回 null。

下面的程序说明了 Java 中的 lower()方法:

**程序 1** :带整数元素的导航集。

```
// A Java program to demonstrate lower()
// method of NavigableSet
import java.util.NavigableSet;
import java.util.TreeSet;

public class GFG {
    public static void main(String[] args)
    {
        NavigableSet<Integer> ns = new TreeSet<>();
        ns.add(0);
        ns.add(1);
        ns.add(2);
        ns.add(3);
        ns.add(4);
        ns.add(5);
        ns.add(6);

        System.out.println("Greatest element strictly less than"
                           + " 4 is: " + ns.lower(4));
    }
}
```

**输出:**

```
Greatest element strictly less than 4 is: 3

```

**程序 2:** 带字符串元素的导航集。

```
// A Java program to lower()
// method of NavigableSet
import java.util.NavigableSet;
import java.util.TreeSet;

public class GFG {
    public static void main(String[] args)
    {
        NavigableSet<String> ns = new TreeSet<>();
        ns.add("A");
        ns.add("B");
        ns.add("C");
        ns.add("D");
        ns.add("E");
        ns.add("F");
        ns.add("G");

        System.out.println("Greatest element strictly less than"
                           + " D is: " + ns.lower("D"));
    }
}
```

**输出:**

```
Greatest element strictly less than D is: C

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/navigatableset . html # lower(E)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#ceiling(E))