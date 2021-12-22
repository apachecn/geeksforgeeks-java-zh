# Java 中带()方法的月日，示例

> 原文:[https://www . geesforgeks . org/monthday-with-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-with-method-in-java-with-examples/)

**使用 **MonthDay** 类的(月月)**方法，该方法使用作为参数传递的月来更改 MonthDay 对象的年中月，然后该方法返回更改后的 MonthDay 的副本。如果更改操作后指定月份的月日值无效，则该日期将被调整为最后一个有效的月日。

**语法:**

```
public MonthDay with(Month month)

```

**参数:**该方法接受**月**作为参数，该参数是返回的月日中要设置的月份。

**返回值:**此方法返回一个月日，该月日基于请求的月份

下面的程序说明了用()方法:
**程序 1:**

```
// Java program to demonstrate
// MonthDay.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a MonthDay object
        MonthDay monthday
            = MonthDay.of(8, 28);

        // print instance
        System.out.println("MonthDay before"
                           + " applying method: "
                           + monthday);

        // apply with method of MonthDay class
        MonthDay updatedlocal
            = monthday.with(Month.OCTOBER);

        // print instance
        System.out.println("MonthDay after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
MonthDay before applying method: --08-28
MonthDay after applying method: --10-28

```

**程序 2:**

```
// Java program to demonstrate
// MonthDay.with() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a MonthDay object
        MonthDay monthday
            = MonthDay.of(10, 31);

        // print instance
        System.out.println("MonthDay before"
                           + " applying method: "
                           + monthday);

        // apply with method of MonthDay class
        MonthDay updatedlocal
            = monthday.with(Month.FEBRUARY);

        // print instance
        System.out.println("MonthDay after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
MonthDay before applying method: --10-31
MonthDay after applying method: --02-29

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # with(Java . time . month)](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#with(java.time.Month))