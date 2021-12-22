# Java 中()方法的 DayOfWeek 示例

> 原文:[https://www . geeksforgeeks . org/dayofweek-of-in-Java-in-method-with-examples/](https://www.geeksforgeeks.org/dayofweek-of-method-in-java-with-examples/)

**java.time.DayOfWeek** 的()方法的**是 java 中的一个内置函数，它从一个 int 值返回 DayOfWeek 的一个实例。int 值的范围在 1(星期一)到 7(星期日)之间。**

**方法声明:**

```
public static DayOfWeek of(int dayOfWeek)

```

**语法:**

```
DayOfWeek dayOfWeekObject = DayOfWeek.of(int dayOfWeek)

```

**参数:**该方法以 dayOfWeek 为参数，其中:

*   *dayOfWeek*–是从 1(星期一)到 7(星期日)的 int 值。
*   *dayOfWeekObject*–是 dayOfWeekObject 的一个实例。

**返回值:**函数返回 DayOfWeek 对象的一个实例。

以下程序说明了上述方法:
**程序 1:**

```
// Java Program Demonstrate of()
// method of DayOfWeek
import java.time.DayOfWeek;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Getting an instance of DayOfWeek from int value
        DayOfWeek dayOfWeek = DayOfWeek.of(4);

        // Printing the day of the week
        // and its Int value
        System.out.println("Day of the Week - "
                           + dayOfWeek.name());
        System.out.println("Int Value of "
                           + dayOfWeek.name() + " - "
                           + dayOfWeek.getValue());
    }
}
```

**Output:**

```
Day of the Week - THURSDAY
Int Value of THURSDAY - 4

```

**程序 2:**

```
// Java Program Demonstrate of()
// method of DayOfWeek
import java.time.DayOfWeek;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Getting an instance of DayOfWeek from int value
        DayOfWeek dayOfWeek = DayOfWeek.of(7);

        // Printing the day of the week
        // and its Int value
        System.out.println("Day of the Week - "
                           + dayOfWeek.name());
        System.out.println("Int Value of "
                           + dayOfWeek.name() + " - "
                           + dayOfWeek.getValue());
    }
}
```

**Output:**

```
Day of the Week - SUNDAY
Int Value of SUNDAY - 7

```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # of-int-