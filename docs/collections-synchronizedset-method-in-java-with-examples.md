# Java 中的 Collections synchronizedSet()方法，示例

> 原文:[https://www . geesforgeks . org/collections-synchronized set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-synchronizedset-method-in-java-with-examples/)

**java.util.Collections** 类的 **synchronizedSet()** 方法用于返回由指定集合支持的同步(线程安全)集合。为了保证串行访问，通过返回的集合完成对后备集合的所有访问是至关重要的。

**语法:**

```
public static <T> Set<T>
  synchronizedSet(Set<T> s)
```

**参数:**该方法将**集**作为参数“包装”在同步集中。

**返回值:**该方法返回指定集合的**同步视图**。

以下是说明 *synchronizedSet()* 方法的示例

**例 1:**

```
// Java program to demonstrate
// synchronizedSet() method
// for String Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of Set<String>
            Set<String> set = new HashSet<String>();

            // populate the set
            set.add("1");
            set.add("2");
            set.add("3");

            // printing the Collection
            System.out.println("Set : " + set);

            // create a synchronized set
            Set<String>
                synset = Collections.synchronizedSet(set);

            // printing the set
            System.out.println("Synchronized set is : "
                               + synset);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Set : [1, 2, 3]
Synchronized set is : [1, 2, 3]

```

**例 2:**

```
// Java program to demonstrate
// synchronizedSet() method
// for Integer Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of Set<Integer>
            Set<Integer> set = new HashSet<Integer>();

            // populate the set
            set.add(100);
            set.add(200);
            set.add(300);

            // printing the Collection
            System.out.println("Set : " + set);

            // create a synchronized set
            Set<Integer>
                synset = Collections.synchronizedSet(set);

            // printing the set
            System.out.println("Synchronized set is : "
                               + synset);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Set : [100, 200, 300]
Synchronized set is : [100, 200, 300]

```