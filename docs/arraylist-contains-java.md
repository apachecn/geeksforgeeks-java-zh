# Java 中的 Arraylist.contains()

> 原文:[https://www.geeksforgeeks.org/arraylist-contains-java/](https://www.geeksforgeeks.org/arraylist-contains-java/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)在 [Java](https://www.geeksforgeeks.org/java/) 中包含()方法，用于检查给定列表中是否存在指定元素。

**语法:**

```java
public boolean contains(Object)
object-element to be searched for
```

**参数:**
待测试列表中的对象元素

**返回:**
如果在列表中找到指定的元素，则返回真，否则返回假。

**代码#1:** 演示包含整数()的方法的工作原理

```java
// Java code to demonstrate the working of
// contains() method in ArrayList

// for ArrayList functions
import java.util.ArrayList;

class GFG {
    public static void main(String[] args)
    {

        // creating an Empty Integer ArrayList
        ArrayList<Integer> arr = new ArrayList<Integer>(4);

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // use contains() to check if the element
        // 2 exits or not
        boolean ans = arr.contains(2);

        if (ans)
            System.out.println("The list contains 2");
        else
            System.out.println("The list does not contains 2");

        // use contains() to check if the element
        // 5 exits or not
        ans = arr.contains(5);

        if (ans)
            System.out.println("The list contains 5");
        else
            System.out.println("The list does not contains 5");
    }
}
```

**Output:**

```java
The list contains 2
The list does not contains 5

```

**代码#2:** 演示字符串形式的包含()的方法的工作原理

```java
// Java code to demonstrate the working of
// contains() method in ArrayList of string

// for ArrayList functions
import java.util.ArrayList;

class GFG {
    public static void main(String[] args)
    {

        // creating an Empty String ArrayList
        ArrayList<String> arr = new ArrayList<String>(4);

        // using add() to initialize values
        // ["geeks", "for", "geeks"]
        arr.add("geeks");
        arr.add("for");
        arr.add("geeks");

        // use contains() to check if the element
        // "geeks" exits or not
        boolean ans = arr.contains("geeks");

        if (ans)
            System.out.println("The list contains geeks");
        else
            System.out.println("The list does not contains geeks");

        // use contains() to check if the element
        // "coding" exits or not
        ans = arr.contains("coding");

        if (ans)
            System.out.println("The list contains coding");
        else
            System.out.println("The list does not contains coding");
    }
}
```

**Output:**

```java
The list contains geeks
The list does not contains coding

```

**实际应用:**
在搜索操作中，我们可以检查给定的元素是否存在于列表中。

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))