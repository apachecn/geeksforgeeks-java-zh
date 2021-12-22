# Character.isISOControl()方法，用 Java 举例

> 原文:[https://www . geeksforgeeks . org/character-isisocontrol-method-with-examples-in-Java/](https://www.geeksforgeeks.org/character-isisocontrol-method-with-examples-in-java/)

**java . lang . character . isisocontrol()**是 Java 中的一个内置方法，用于确定指定的字符是否是 ISO 控制字符。如果一个字符的代码在“\u0000”到“\u001F”的范围内或在“\u007F”到“\u009F”的范围内，则该字符被认为是 ISO 控制字符。此方法无法处理补充字符。为了支持所有的 Unicode 字符，包括补充字符，在上述方法中，参数可以是 int 数据类型。

**语法:**

```java
public static boolean isISOControl(data_type ch)

```

**参数:**该函数接受单个参数 ***ch*** ，该参数是强制的。它指定要测试的字符。参数可以是 char 或 int 数据类型。

**返回值:**函数返回一个布尔值。如果字符是国际标准化组织控制字符，布尔值为真，否则为假。

下面的程序说明了上述方法:

**程序 1:**

```java
// java program to demonstrate
// Character.isISOControl() method
// when the parameter is a character

import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2 and assign values
        char c1 = '-', c2 = '\u0017';

        // assign isISOControl results of c1
        // to boolean primitives  bool1
        boolean bool1 = Character.isISOControl(c1);

        if (bool1)
            System.out.println(c1 + " is an ISO control character");
        else
            System.out.println(c1 + " is not an ISO control character");

        // assign isISOControl results of c2
        // to boolean primitives  bool2
        boolean bool2 = Character.isISOControl(c2);

        if (bool2)
            System.out.println(c2 + " is an ISO control character");
        else
            System.out.println(c2 + " is not an ISO control character");
    }
}
```

**Output:**

```java
- is not an ISO control character
 is an ISO control character

```

**程序 2:**

```java
// java program to demonstrate
// Character.isISOControl(char ch) method
// when the parameter is an integer
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2 and assign values
        int c1 = 0x008f;
        int c2 = 0x0123;

        // assign isISOControl results of c1
        // to boolean primitives  bool1
        boolean bool1 = Character.isISOControl(c1);
        if (bool1)
            System.out.println(c1 + " is an ISO control character");
        else
            System.out.println(c1 + " is not an ISO control character");

        // assign isISOControl results of c2
        // to boolean primitives  bool2
        boolean bool2 = Character.isISOControl(c2);
        if (bool2)
            System.out.println(c2 + " is an ISO control character");
        else
            System.out.println(c2 + " is not an ISO control character");
    }
}
```

**Output:**

```java
143 is an ISO control character
291 is not an ISO control character

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # isISOControl(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isISOControl(char))