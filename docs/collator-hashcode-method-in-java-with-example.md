# Java 中的 Collator hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/collator-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-hashcode-method-in-java-with-example/)

**java.text.Collator** 类的 **hashCode()** 方法用于获取这个 Collator 对象的 hashCode。

**语法:**

```java
public abstract int hashCode()
```

**参数**:此方法不接受任何参数。
**返回值:**该方法以**整数格式**返回**哈希码**值。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing new simple rule
            String simple = "< a < b < c < d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting hashCode of this object
            // using hashCode() method
            int hash = col.hashCode();

            // display result
            System.out.println("hashCode is :- "
                               + hash);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : "
                               + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**Output:** 

```java
hashCode is :- 1882448026
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col
                = Collator.getInstance(Locale.UK);

            // getting hashCode of this object
            // using hashCode() method
            int hash = col.hashCode();

            // display result
            System.out.println("hashCode is :- " + hash);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
hashCode is :- 681002966
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/text/Collator.html#hashCode--)