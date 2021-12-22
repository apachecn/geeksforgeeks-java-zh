# Java 中的 ChoiceFormat 等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/choice format-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-equals-method-in-java-with-examples/)

[**Java . text . ChoiceFormat**](https://www.geeksforgeeks.org/tag/java-choiceformat/)类的 **equals()** 方法用于比较两个 choice format 对象，并给出关于比较的布尔值。
**语法:**

```java
public boolean equals(Object obj)
```

**参数**:该方法以**对象**为参数，作为另一个选择的变形对象进行比较。
**返回值:**如果两个选择格式对象相等，则该方法返回 **true** ，否则返回 false。
以下是举例说明**等于()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate equals() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing ChoiceFormat
        ChoiceFormat cf1
            = new ChoiceFormat(
                "4#wed| 5#thu | 6#fri | 7#sat");

        // creating and initializing ChoiceFormat
        ChoiceFormat cf2
            = new ChoiceFormat(
                "4#wed| 5#thu | 6#fri | 7#sat");

        // compare cf1 and cf2
        // using equals() method
        boolean status = cf1.equals(cf2);

        // display the result
        if (status)
            System.out.println("Both ChoiceFormat"
                               + " objects are equal");
        else
            System.out.println("Both ChoiceFormat "
                               + "objects are not equal");
    }
}
```

**Output:** 

```java
Both ChoiceFormat objects are equal
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate equals() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing ChoiceFormat
        ChoiceFormat cf1
            = new ChoiceFormat(
                "1#sun| 2#mon | 3#tues | 4#wed");

        // creating and initializing ChoiceFormat
        ChoiceFormat cf2
            = new ChoiceFormat(
                "4#wed| 5#thu | 6#fri | 7#sat");

        // compare cf1 and cf2
        // using equals() method
        boolean status = cf1.equals(cf2);

        // display the result
        if (status)
            System.out.println("Both ChoiceFormat"
                               + " objects are equal");
        else
            System.out.println("Both ChoiceFormat "
                               + "objects are not equal");
    }
}
```

**Output:** 

```java
Both ChoiceFormat objects are not equal
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # apply pattern-Java . lang . string-T4】