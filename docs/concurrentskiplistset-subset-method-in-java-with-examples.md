# Java 中的 ConcurrentSkipListSet subSet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-subset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistset-subset-method-in-java-with-examples/)

[**java . util . concurrentskiplistset**](https://www.geeksforgeeks.org/concurrentskiplistset-in-java-with-examples/)的**Subject()**方法是 Java 中的内置函数，其中元素在该方法定义的范围内返回。
函数的语法给出了对指定元素的清晰理解，后面是示例。
**语法:**

```java
subSet(E fromElement, E toElement)
           or 
subSet(E fromElement, boolean fromInclusive, E toElement, boolean toInclusive)
```

**参数:**
这个方法的第一个变体采用了两个参数，定义了将要返回的元素的范围。返回的集中不包含 toElement。
第二个变体类似于第一个变体，但这里布尔参数特别包括或排除了 toElement 和 fromElement。
**返回:**
第一个方法变体返回该集合的一部分的视图，该集合的元素范围从 fromElement(包含)到 toElement(不包含)。
第二个方法变体返回该集合的一部分的视图，该集合的元素范围是从“从元素”到“到元素”，由布尔包含参数定义。
**异常:**
**空指针异常:**如果指定的元素为空。
下面是用 Java 说明 ConcurrentSkipListSet subSet()的示例程序:
**示例:1**
返回 30000 到 90000 的元素，但不包括 90000。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate ConcurrentSkipListSet subSet() method

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetExample {
    public static void main(String[] args)
    {

        // Initializing the set using ConcurrentSkipListSet()
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        set.add(65552);
        set.add(34324);
        set.add(93423);
        set.add(41523);
        set.add(90000);

        // Printing the ConcurrentSkipListSet
        System.out.println("ConcurrentSkipListSet: "
                           + set);

        // Printing the elements of ConcurrentSkipListSet that
        // are returned by subSet() method
        System.out.println("The returned elements are: "
                           + set.subSet(30000, 90000));
    }
}
```

**Output:** 

```java
ConcurrentSkipListSet: [34324, 41523, 65552, 90000, 93423]
The returned elements are: [34324, 41523, 65552]
```

**示例:2**
在本例中，因为布尔包含为真，所以也返回了元素 400。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate ConcurrentSkipListSet subSet() method

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetExample {
    public static void main(String[] args)
    {

        // Initializing the set using ConcurrentSkipListSet()
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        set.add(652);
        set.add(324);
        set.add(400);
        set.add(123);
        set.add(200);

        // Printing the ConcurrentSkipListSet
        System.out.println("ConcurrentSkipListSet: "
                           + set);

        // Printing the elements of ConcurrentSkipListSet that
        // are returned by subSet() method
        System.out.println("The returned elements are: "
                           + set.subSet(100, true, 400, true));
    }
}
```

**Output:** 

```java
ConcurrentSkipListSet: [123, 200, 324, 400, 652]
The returned elements are: [123, 200, 324, 400]
```