# 如何增加数组列表的容量(大小)？

> 原文:[https://www . geeksforgeeks . org/如何增加数组列表的容量大小/](https://www.geeksforgeeks.org/how-to-increase-the-capacity-size-of-arraylist/)

ArrayList 类是一个可调整大小的数组，存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中。Java 中的[数组](https://www.geeksforgeeks.org/arrays-in-java/)和[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)之间的区别在于，数组的大小不能修改(即，如果您想在数组中添加/删除元素，您必须创建一个新的数组。但是，可以在数组列表中添加/添加或删除元素，而不需要创建新的数组。

每当创建一个 Java 中的数组列表实例时，默认情况下数组列表的容量是 10。由于数组列表是一个可增长的数组，每当数组列表中的元素数量增长超过阈值时，它就会自动调整自身的大小。但是，java.util.ArrayList 类的 [ensureCapacity()](https://www.geeksforgeeks.org/arraylist-ensurecapacity-method-in-java-with-examples/) 方法可以用来增加 ArrayList 实例的容量，如果需要的话，可以确保它至少可以容纳最小容量参数指定的元素数量。

**语法:**

> 公共空间保证容量(int minCapacity)

**参数:**该方法以期望的最小容量为参数。

**返回类型:**此方法不返回值。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// ensureCapacity() method for String values

import java.util.ArrayList;

public class GFG {
    public static void main(String[] arg) throws Exception
    {
        try {

            // Creating object of ArrayList of String of
            // size = 3
            ArrayList<String> numbers
                = new ArrayList<String>(3);

            // adding element to Arrlist numbers
            numbers.add("10");
            numbers.add("20");
            numbers.add("30");

            // Print the ArrayList
            System.out.println("ArrayList: " + numbers);

            // using ensureCapacity() method to
            // increase the capacity of ArrayList
            // numbersto hold 500 elements.
            System.out.println(
                "Increasing the capacity of ArrayList numbers to store upto 500 elements.");

            numbers.ensureCapacity(500);

            System.out.println(
                "ArrayList numbers can now store upto 500 elements.");
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output**

```
ArrayList: [10, 20, 30]
Increasing the capacity of ArrayList numbers to store upto 500 elements.
ArrayList numbers can now store upto 500 elements.
```