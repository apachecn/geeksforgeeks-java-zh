# Java 中的 ArrayDeque forEach()方法

> 原文:[https://www . geeksforgeeks . org/arraydeque-foreach-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-foreach-method-in-java/)

**ArrayDeque** 的 **forEach()** 方法继承自**T5【Java . lang . iterable】T6**接口。如果方法指定了迭代顺序，则按照迭代顺序执行操作。方法遍历 ArrayDeque 的 Iterable 的每个元素，直到该方法处理完所有元素或者发生异常。操作引发的异常被传递给调用方。

**语法:**

```
public void forEach(Consumer<? super E> action)
```

**参数:**该方法取一个参数名**动作**，代表每个元素要执行的动作。

**返回:**此方法不返回任何内容。

**异常:**如果指定的动作为空，该方法抛出**空指针异常**。

下面的程序说明了数组的 forEach()方法:

**示例 1:** 演示 ArrayDeque 上的 forEach()方法，该方法包含一个字符串值队列。

```
// Java Program Demonstrate forEach()
// method of ArrayDeque

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayDeque
        // which contains string values
        ArrayDeque<String> cities = new ArrayDeque<String>();

        // Add Strings to list
        cities.add("Kolkata");
        cities.add("Delhi");
        cities.add("Bombay");
        cities.add("Pune");

        // forEach method of ArrayDeque and
        // print city names
        cities.forEach((n) -> System.out.println(n));
    }
}
```

**Output:**

```
Kolkata
Delhi
Bombay
Pune

```

**示例 2:** 演示包含对象队列的 ArrayDeque 上的 forEach()方法。

```
// Java Program Demonstrate forEach()
// method of ArrayDeque

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayDeque which going to
        // contains a list of Objects
        ArrayDeque<batch> list = new ArrayDeque<batch>();

        // Add Objects to list
        list.add(new batch("CSE", 67));
        list.add(new batch("ECE", 57));
        list.add(new batch("IT", 90));
        list.add(new batch("ME", 78));

        // print result
        System.out.println("list of Objects:");

        // forEach method of ArrayDeque and
        // print student names
        list.forEach((n) -> print(n));
    }

    // printing details of object
    public static void print(batch n)
    {
        System.out.println("*******************************");
        System.out.println("Batch Name is " + n.name);
        System.out.println("No of Students are " + n.noOfStudents);
    }
}

// create a class
class batch {

    String name;
    int noOfStudents;

    batch(String name, int noOfStudents)
    {
        this.name = name;
        this.noOfStudents = noOfStudents;
    }
}
```

**Output:**

```
list of Objects:
*******************************
Batch Name is CSE
No of Students are 67
*******************************
Batch Name is ECE
No of Students are 57
*******************************
Batch Name is IT
No of Students are 90
*******************************
Batch Name is ME
No of Students are 78

```

**示例 3:** 演示 ArrayDeque 上 forEach()方法的 NullPointerException。

```
// Java Program Demonstrate forEach()
// method of ArrayDeque

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayDeque
        // which contains string values
        ArrayDeque<String> cities = new ArrayDeque<String>();

        // Add Strings to list
        cities.add("Kolkata");
        cities.add("Delhi");
        cities.add("Bombay");
        cities.add("Pune");

        try {
            // forEach method of ArrayDeque and
            // print city names
            cities.forEach(null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.NullPointerException

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/arraydeque . html # forEach(Java . util . function . consumer)](https://docs.oracle.com/javase/10/docs/api/java/util/ArrayDeque.html#forEach(java.util.function.Consumer))