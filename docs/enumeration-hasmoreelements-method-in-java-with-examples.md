# Java 中枚举 hasMoreElements()方法，带示例

> 原文:[https://www . geesforgeks . org/enumeration-hasmorelements-method-in-Java-with-examples/](https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/)

实现**枚举接口**的对象生成一系列元素，一次一个。**hasmorelements()**枚举**的**方法，用于测试该枚举是否包含更多元素。如果枚举包含更多元素，那么它将返回 true 否则返回 false。

**语法:**

```
boolean hasMoreElements()

```

**参数:**此方法不接受任何内容。

**返回值:**当且仅当此枚举对象至少包含一个要提供的元素时，此方法返回 true 否则为假。

下面的程序说明了 hasMoreElements()方法:
**程序 1:**

```
// Java program to demonstrate
// Enumeration.hasMoreElements() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        Enumeration Days;
        Vector week = new Vector();

        week.add("Sunday");
        week.add("Monday");
        week.add("Tuesday");
        week.add("Wednesday");
        week.add("Thursday");
        week.add("Friday");
        week.add("Saturday");
        Days = week.elements();

        while (Days.hasMoreElements()) {
            System.out.println("Day = "
                               + Days.nextElement());
        }
    }
}
```

**Output:**

```
Day = Sunday
Day = Monday
Day = Tuesday
Day = Wednesday
Day = Thursday
Day = Friday
Day = Saturday

```

**程序 2:**

```
// Java program to demonstrate
// Enumeration.hasMoreElements() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        Enumeration<Integer> classNine;
        Vector<Integer> rollno = new Vector<Integer>();

        rollno.add(1);
        rollno.add(2);
        rollno.add(3);
        rollno.add(4);
        rollno.add(5);
        rollno.add(6);
        rollno.add(7);
        rollno.add(8);
        classNine = rollno.elements();

        while (classNine.hasMoreElements()) {
            System.out.println("Roll No = "
                               + classNine.nextElement());
        }
    }
}
```

**Output:**

```
Roll No = 1
Roll No = 2
Roll No = 3
Roll No = 4
Roll No = 5
Roll No = 6
Roll No = 7
Roll No = 8

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/enumeration . html # hasmorelements()](https://docs.oracle.com/javase/10/docs/api/java/util/Enumeration.html#hasMoreElements())