# Java 中的 Collections synchronized collection()方法，示例

> 原文:[https://www . geeksforgeeks . org/collections-synchronized collection-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-synchronizedcollection-method-in-java-with-examples/)

**java.util.Collections** 类的 **synchronizedCollection()** 方法用于返回由指定集合支持的同步(线程安全)集合。为了保证串行访问，通过返回的集合完成对后备集合的所有访问是非常重要的。
**语法:**

```
public static <T> Collection<T>
  synchronizedCollection(Collection<T> c)
```

**参数:**该方法将**集合 c** 作为参数“包装”在同步集合中。
**返回值:**该方法返回指定集合的**同步视图**。
以下是举例说明*synchronized collection()*方法
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate synchronizedCollection()
// method for String Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of List<String>
            List<String> vector = new ArrayList<String>();

            // populate the vector
            vector.add("A");
            vector.add("B");
            vector.add("C");
            vector.add("D");
            vector.add("E");

            // printing the Collection
            System.out.println("Collection : " + vector);

            // getting the synchronized view of Collection
            Collection<String> c = Collections
                                       .synchronizedCollection(vector);

            // printing the Collection
            System.out.println("Synchronized view"
                               + " of collection : " + c);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output**

```
Collection : [A, B, C, D, E]
Synchronized view of collection : [A, B, C, D, E]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate synchronizedCollection()
// method for Integer Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of List<String>
            List<Integer> vector = new ArrayList<Integer>();

            // populate the vector
            vector.add(20);
            vector.add(30);
            vector.add(40);
            vector.add(50);
            vector.add(60);

            // printing the Collection
            System.out.println("Collection : " + vector);

            // getting the synchronized view of Collection
            Collection<Integer> c = Collections
                                        .synchronizedCollection(vector);

            // printing the Collection
            System.out.println("Synchronized view is : " + c);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Collection : [20, 30, 40, 50, 60]
Synchronized view is : [20, 30, 40, 50, 60]
```