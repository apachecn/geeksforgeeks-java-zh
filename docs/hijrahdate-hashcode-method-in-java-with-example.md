# Java 中的 HijrahDate hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/hijrahdate-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-hashcode-method-in-java-with-example/)

类的 **hashCode()** 方法用于获取特定 hijrah 日期的哈希代码。

**语法:**

```java
public int hashCode()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回特定回历日期的哈希代码。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// hashCode() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting hash code of the date
            // by using hashCode() method
            long tempo = hidate.hashCode();

            // display the result
            System.out.println("hashcode : "
                               + tempo);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出:**

```java
hashcode : 2097279521

```

**例 2:**

```java
// Java program to demonstrate
// hashCode() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.of(1345, 06, 13);

            // getting hash code of the date
            // by using hashCode() method
            long tempo = hidate.hashCode();

            // display the result
            System.out.println("hashcode : "
                               + tempo);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出:**

```java
hashcode : 2097607230

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#hashCode--)