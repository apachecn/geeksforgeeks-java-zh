# Java 中的 MinguoDate hashCode()方法，示例

> 原文:[https://www . geeksforgeeks . org/minuodate-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-hashcode-method-in-java-with-example/)

类的 **hashCode()** 方法用于获取特定民国日期的 hash 代码。

**语法:**

```
public int hashCode()

```

**参数**:该方法不接受任何参数作为参数。

**返回值**:该方法返回特定民国日期的哈希码。

以下是举例说明 **hashCode()** 方法:

T4】例 1:

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

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

**Output:**

```
hashcode : -1990230825

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.of(1345, 06, 13);

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

**Output:**

```
hashcode : -1996123070

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#hashCode--)