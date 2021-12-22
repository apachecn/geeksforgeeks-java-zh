# Java 中的 HashSet removeAll()方法，示例

> 原文:[https://www . geesforgeks . org/hashset-remove all-method-in-Java-with-example/](https://www.geeksforgeeks.org/hashset-removeall-method-in-java-with-example/)

**java.util.HashSet** 类的 **removeAll()** 方法用于从此集合中移除指定集合中包含的所有元素。
**语法:**

```
public boolean removeAll(Collection c)
```

**参数:**该方法将**集合 c** 作为包含要从该集合中移除的元素的参数。
**返回值:**如果该设置因调用而改变，则该方法返回 **true** 。
**异常:**如果此集合包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则此方法抛出**NullPointRexception**。
下面举例说明 *removeAll()* 方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of HashSet<Integer>
            HashSet<Integer>
                arrset1 = new HashSet<Integer>();

            // Populating arrset1
            arrset1.add(1);
            arrset1.add(2);
            arrset1.add(3);
            arrset1.add(4);
            arrset1.add(5);

            // print arrset1
            System.out.println("HashSet before "
                               + "removeAll() operation : "
                               + arrset1);

            // Creating another object of  HashSet<Integer>
            HashSet<Integer>
                arrset2 = new HashSet<Integer>();
            arrset2.add(1);
            arrset2.add(2);
            arrset2.add(3);

            // print arrset2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + arrset2);

            // Removing elements from arrset
            // specified in arrset2
            // using removeAll() method
            arrset1.removeAll(arrset2);

            // print arrset1
            System.out.println("HashSet after "
                               + "removeAll() operation : "
                               + arrset1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
HashSet before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : [1, 2, 3]
HashSet after removeAll() operation : [4, 5]
```

**示例 2:** 适用于*空指针异常*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of HashSet<Integer>
            HashSet<Integer>
                arrset1 = new HashSet<Integer>();

            // Populating arrset1
            arrset1.add(1);
            arrset1.add(2);
            arrset1.add(3);
            arrset1.add(4);
            arrset1.add(5);

            // print arrset1
            System.out.println("HashSet before "
                               + "removeAll() operation : "
                               + arrset1);

            // Creating another object of  HashSet<Integer>
            HashSet<Integer>
                arrset2 = null;

            // print arrset2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + arrset2);

            System.out.println("\nTrying to pass "
                               + "null as a specified element\n");

            // Removing elements from arrset
            // specified in arrset2
            // using removeAll() method
            arrset1.removeAll(arrset2);

            // print arrset1
            System.out.println("HashSet after "
                               + "removeAll() operation : "
                               + arrset1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
HashSet before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : null

Trying to pass null as a specified element

Exception thrown : java.lang.NullPointerException
```