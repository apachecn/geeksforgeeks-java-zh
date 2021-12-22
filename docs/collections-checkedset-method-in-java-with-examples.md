# Java 中的 Collections checkedSet()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-checked set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-checkedset-method-in-java-with-examples/)

**java.util.Collections** 类的 **checkedSet()** 方法用于返回指定集合的动态类型安全视图。
如果指定的集合是可序列化的，则返回的集合是可序列化的。
因为 null 被认为是任何引用类型的值，所以只要支持集允许插入 null 元素，返回集就允许插入 null 元素。
**语法:**

```
public static  Set checkedSet(Set s, Class type)
```

**参数:**该方法将以下参数作为参数

*   **s:** 为其返回动态类型安全视图的集合
*   **类型:**允许持有的元素类型

**返回值:**该方法动态返回指定集合的**类型安全视图**。
以下举例说明 checkedSet()方法
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// checkedSet() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // creating object of Set<String>
            Set<String> hset = new TreeSet<String>();

            // Adding element to hmap
            hset.add("Ram");
            hset.add("Gopal");
            hset.add("Verma");

            // print the set
            System.out.println("Set: " + hset);

            // create typesafe view of the specified set
            Set<String>
                tsset = Collections
                            .checkedSet(hset, String.class);

            // printing the typesafe view of specified list
            System.out.println("Typesafe view of Set: "
                               + tsset);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Set: [Gopal, Ram, Verma]
Typesafe view of Set: [Gopal, Ram, Verma]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// checkedSet() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of Set<Integer>
            Set<Integer> hset = new TreeSet<Integer>();

            // Adding element to hset
            hset.add(20);
            hset.add(30);
            hset.add(40);

            // print the set
            System.out.println("Set: " + hset);

            // create typesafe view of the specified set
            Set<Integer>
                tsset = Collections
                            .checkedSet(hset, Integer.class);

            // printing the typesafe view of specified list
            System.out.println("Typesafe view of Set: " + tsset);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Set: [20, 30, 40]
Typesafe view of Set: [20, 30, 40]
```