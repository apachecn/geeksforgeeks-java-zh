# Java 中的类 getSigners()方法，示例

> 原文:[https://www . geesforgeks . org/class-getsigners-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getsigners-method-in-java-with-examples/)

[**Java . lang . class**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)的 **getSigners()** 方法用于获取该类的签名者。方法返回这个类的签名者。如果此对象表示基元类型或 void，则此方法返回 null。

**语法:**

```
public Object[] getSigners()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法返回该类的**签名者**。如果此对象表示基元类型或 void，则此方法返回 null。
下面的程序演示了 getSigners()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate getSigners() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the signers of myClass
        // using getSigners() method
        System.out.println(
            "Signers of myClass: "
            + Arrays.toString(
                  myClass.getSigners()));
    }
}
```

**Output:** 

```
Class represented by myClass: class Test
Signers of myClass: null
```