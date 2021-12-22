# Java 中的 Collections max()方法，示例

> 原文:[https://www . geesforgeks . org/collections-max-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/)

### 最大值(集合 extends T> coll)

**java.util.Collections** 类的 **max()** 方法用于根据给定集合元素的自然顺序返回给定集合的最大元素。集合中的所有元素都必须实现 Comparable 接口。此外，集合中的所有元素必须是相互可比较的(也就是说，e1.compareTo(e2)不得为集合中的任何元素 e1 和 e2 引发 ClassCastException)。
该方法迭代整个集合，因此需要的时间与集合的大小成正比。

**语法:**

```
public static <T extends Object & Comparable> T
  max(Collection coll)
```

**参数:**该方法将集合 **coll** 作为待确定最大元素的参数。
**返回值:**该方法根据元素的自然排序，返回给定集合的**最大元素**。

**异常:**该方法抛出以下异常:

*   **class castexception–**如果集合包含不可相互比较的元素(例如字符串和整数)。
*   如果集合为空，则**no suchelementexception–**

以下是举例说明 *max()* 方法的例子

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// max() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of LinkedList
            List<Integer> list = new LinkedList<Integer>();

            // Adding element to Vector v
            list.add(-1);
            list.add(4);
            list.add(-5);
            list.add(1);

            // printing the max value
            // using max() method
            System.out.println("Max value is: "
                               + Collections.max(list));
        }

        catch (ClassCastException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Max value is: 4
```

**例 2:*级除外***

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// max() method for ClassCastException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of LinkedList
            List<String> list = new LinkedList<String>();

            // creating variable of object type
            Object i = Integer.valueOf(42);

            // Adding element to Vector v
            list.add("Hello");
            list.add((String)i);

            // printing the max value
            // using max() method
            System.out.println("Max value is: "
                               + Collections.max(list));
        }

        catch (ClassCastException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Exception thrown : java.lang.ClassCastException: java.lang.Integer cannot be cast to java.lang.String
```

**例 3:** 为*无素异常*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// max() method for NoSuchElementException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of LinkedList
            List<Integer> list = new LinkedList<Integer>();

            // printing the max value
            // using max() method
            System.out.println("Trying to get "
                               + "the max from empty list");
            System.out.println("Max value is: "
                               + Collections.max(list));
        }

        catch (ClassCastException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Trying to get the max from empty list
Exception thrown : java.util.NoSuchElementException
```

### 公共静态测试最大值(集合 extends T> coll，比较器 super T> comp)

**java.util.Collections** 类的 **max()** 方法用于根据指定比较器诱导的顺序返回给定集合的最大元素。集合中的所有元素必须通过指定的比较器进行相互比较(也就是说，comp.compare(e1，e2)不得为集合中的任何元素 e1 和 e2 引发 ClassCastException)。
该方法迭代整个集合，因此需要的时间与集合的大小成正比。

**参数:**该方法采用以下参数作为参数

*   **coll–**最大元素待定的集合。
*   **comp–**用于确定最大元素的比较器。空值表示应该使用元素的自然排序。

**返回值:**该方法根据指定的比较器返回给定集合的**最大元素**。

**异常:**该方法抛出以下异常:

*   **class castexception–**如果集合包含不可相互比较的元素(例如字符串和整数)。
*   如果集合为空，则**no suchelementexception–**

以下是举例说明 *max()* 方法的例子

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// max() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of LinkedList
            List<Integer> list = new LinkedList<Integer>();

            // Adding element to Vector v
            list.add(-1);
            list.add(4);
            list.add(-5);
            list.add(1);

            // printing the max value
            // using max() method
            System.out.println("Max val: "
                               + Collections.max(list,
                                                 Collections.reverseOrder()));
        }

        catch (ClassCastException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Max val: -5
```

**例 2:*级除外***

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// max() method for ClassCastException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of LinkedList
            List<String> list = new LinkedList<String>();

            // creating variable of object type
            Object i = Integer.valueOf(42);

            // Adding element to Vector v
            list.add("Hello");
            list.add((String)i);

            // printing the max value
            // using max() method
            System.out.println("Max val: "
                               + Collections
                                     .max(list,
                                          Collections
                                              .reverseOrder()));
        }

        catch (ClassCastException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Exception thrown : java.lang.ClassCastException: java.lang.Integer cannot be cast to java.lang.String
```

**例 3:** 为*无素异常*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// max() method for NoSuchElementException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of LinkedList
            List<Integer> list = new LinkedList<Integer>();

            // printing the max value
            // using max() method
            System.out.println("Trying to get "
                               + "the max from empty list");
            System.out.println("Max val: "
                               + Collections
                                     .max(list,
                                          Collections
                                              .reverseOrder()));
        }

        catch (ClassCastException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Trying to get the max from empty list
Exception thrown : java.util.NoSuchElementException
```