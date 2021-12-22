# Java 中的 Bidi createLineBidi()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-createlinebidi-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-createlinebidi-method-in-java-with-examples/)

**java.text.Bidi** 类的 **createLineBidi()** 方法用于创建一个新的 Bidi 对象，该对象具有相同的基本方向，并表示范围内当前 Bidi 的每个属性。

**语法:**

```java
public Bidi createLineBidi(int lineStart,
                           int lineLimit)
```

**参数**:该方法以下列参数为参数

*   **Line starting point** : This is the new Bidi.
*   **Line terminal** : It is this new Bidi.

的终点

**返回值:**这个方法返回一个新的 **Bidi 对象**

以下是说明 **createLineBidi()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// createLineBidi() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        // text with base direction
        Bidi bidi
            = new Bidi(
                "Geeks For Geeks",
                Bidi.DIRECTION_RIGHT_TO_LEFT);

        // creating and new bidi Object using the old one
        // using createLineBidi() method
        Bidi newbidi = bidi.createLineBidi(1, 6);

        // display the new bidi status
        System.out.println("New Bidi "
                           + "\nLength : "
                           + newbidi.getLength()
                           + "\nnumber of levels : "
                           + newbidi.getRunCount()
                           + "\nBase Level : "
                           + newbidi.getBaseLevel());
    }
}
```

**输出:**

```java
New Bidi 
Length : 5
number of levels : 2
Base Level : 1

```

**例 2:**

```java
// Java program to demonstrate
// createLineBidi() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        // text with base direction
        Bidi bidi
            = new Bidi("Tajmahal",
                       Bidi.DIRECTION_RIGHT_TO_LEFT);

        // creating and new bidi Object using the old one
        // using createLineBidi() method
        Bidi newbidi = bidi.createLineBidi(3, 5);

        // display the new bidi status
        System.out.println("New Bidi "
                           + "\nLength : "
                           + newbidi.getLength()
                           + "\nnumber of levels : "
                           + newbidi.getRunCount()
                           + "\nBase Level : "
                           + newbidi.getBaseLevel());
    }
}
```

**输出:**

```java
New Bidi 
Length : 2
number of levels : 1
Base Level : 2

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # createLineBidi-int-int-](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#createLineBidi-int-int-)