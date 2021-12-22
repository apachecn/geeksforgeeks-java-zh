# Java 中的 DayOfWeek values()方法，带示例

> 原文:[https://www . geesforgeks . org/dayofweek-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dayofweek-values-method-in-java-with-examples/)

**java.time.DayOfWeek** 的 **values()** 方法是 java 中的一个内置函数，它按照声明的顺序返回一个包含一周中几天的数组，例如星期一、星期二等等。

**方法声明:**

```java
public static DayOfWeek[] values()

```

**语法:**

```java
DayOfWeek week[] =  DayOfWeek.values()

```

**参数:**该方法不接受任何参数。

**返回值:**该函数返回一个数组，该数组包含按声明顺序排列的星期几。

以下程序说明了上述方法:
**程序 1:**

```java
// Java Program Demonstrate values()
// method of DayOfWeek
import java.time.DayOfWeek;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Initializing an array containing
        // all the days of the Week
        DayOfWeek week[] = DayOfWeek.values();

        // Printing the days of the Week
        for (DayOfWeek c : week)
            System.out.println(c);
    }
}
```

**Output:**

```java
MONDAY
TUESDAY
WEDNESDAY
THURSDAY
FRIDAY
SATURDAY
SUNDAY

```

**程序 2:**

```java
// Java Program Demonstrate values()
// method of DayOfWeek
import java.time.DayOfWeek;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Initializing an array containing
        // all the days of the Week
        DayOfWeek week[] = DayOfWeek.values();

        // Printing the days of the Week
        for (int i = 0; i < week.length; i++)
            System.out.println(week[i]
                               + " has int value - "
                               + (i + 1));
    }
}
```

**Output:**

```java
MONDAY has int value - 1
TUESDAY has int value - 2
WEDNESDAY has int value - 3
THURSDAY has int value - 4
FRIDAY has int value - 5
SATURDAY has int value - 6
SUNDAY has int value - 7

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # values–](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#values--)