# Java 中的集合 min()方法，示例

> 原文:[https://www . geesforgeks . org/collections-min-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/)

### 最小值(集合 extends T> coll)

**java.util.Collections** 类的 **min()** 方法用于根据给定集合元素的自然顺序返回给定集合的最小元素。集合中的所有元素都必须实现 Comparable 接口。此外，集合中的所有元素必须是相互可比较的(也就是说，e1.compareTo(e2)不得为集合中的任何元素 e1 和 e2 引发 ClassCastException)。

此方法迭代整个集合，因此需要的时间与集合的大小成正比。

**语法:**

```
public static <T 
  extends Object & Comparable<? super T>> T 
    min(Collection<? extends T> coll)
```

**参数:**该方法将集合 **coll** 作为一个参数，其最小元素待定

**返回值:**该方法根据元素的自然排序返回给定集合的**最小元素**。

**异常:**如果集合为空，此方法抛出**nosucheelementexception**。

以下是说明 min()方法的示例

**例 1:**

```
// Java program to demonstrate
// min() method
// for <Integer> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create link list object
            List<Integer> list = new LinkedList<Integer>();

            // populate the list
            list.add(10);
            list.add(20);
            list.add(30);
            list.add(40);

            // printing the List
            System.out.println("List: " + list);

            // getting minimum value
            // using min() method
            int min = Collections.min(list);

            // printing the min value
            System.out.println("Minimum value is: " + min);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
List: [10, 20, 30, 40]
Minimum value is: 10

```

**例 2:** 演示*无故障元素异常*

```
// Java program to demonstrate
// min() method for NoSuchElementException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create link list object
            List<Integer> list = new LinkedList<Integer>();

            // printing the List
            System.out.println("List: " + list);

            // getting minimum value
            // using min() method
            System.out.println("Trying to get"
                               + " the minimum value "
                               + "with empty list");

            int min = Collections.min(list);

            // printing the min value
            System.out.println("Min value is: " + min);
        }

        catch (NoSuchElementException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
List: []
Trying to get the minimum value with empty list
Exception thrown : java.util.NoSuchElementException

```

### 最小值(集合 extends T> coll，比较器 super T> comp)

**java.util.Collections** 类的 **min(Collections，Comparator)** 方法用于根据指定的比较器引发的顺序返回给定集合的最小元素。集合中的所有元素必须可以通过指定的比较器相互比较。

此方法迭代整个集合，因此需要的时间与集合的大小成正比。

**参数:**该方法采用以下参数作为参数:

*   **coll-** 最小元素待定的集合。
*   **比较器-** 用来确定最小元素的比较器。空值表示应该使用元素的自然排序。

**返回值:**该方法根据指定的比较器返回给定集合的**最小元素**。

**异常:**如果集合为空，此方法抛出**nosucheelementexception**。

以下是举例说明 *min()* 方法的例子

**例 1:**

```
// Java program to demonstrate
// min() method
// for Integer

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // create link list object
            List<Integer> list = new LinkedList<Integer>();

            // populate the list
            list.add(10);
            list.add(20);
            list.add(30);
            list.add(40);

            // printing the List
            System.out.println("List: " + list);

            // getting minimum value
            // using min() method
            int min = Collections.min(list,
                                      Collections.reverseOrder());

            // printing the min value
            System.out.println("Min value by reverse order is: "
                               + min);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
List: [10, 20, 30, 40]
Min value by reverse order is: 40

```

**例 2:** 演示*无故障元素异常*

```
// Java program to demonstrate
// min() method for NoSuchElementException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create link list object
            List<Integer> list = new LinkedList<Integer>();

            // printing the List
            System.out.println("List: " + list);

            // getting minimum value
            // using min() method
            System.out.println("Trying to get"
                               + " the minimum value "
                               + "with empty list");

            int min = Collections.min(list,
                                      Collections.reverseOrder());

            // printing the min value
            System.out.println("Min value is: " + min);
        }

        catch (NoSuchElementException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
List: []
Trying to get the minimum value with empty list
Exception thrown : java.util.NoSuchElementException

```