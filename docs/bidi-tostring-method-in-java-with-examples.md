# Java 中的 Bidi toString()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-tostring-method-in-java-with-examples/)

**java.text.Bidi** 类的 **toString()** 方法用于在字符串表示中显示这个 Bidi 实例。

**语法:**

```
public String toString()
```

**参数**:这个方法不接受任何东西作为参数。

**返回值:**该方法以**字符串格式**显示比迪内部状态。

以下是说明 **toString()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// toString() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi
            = new Bidi("Geeks",
                       Bidi.DIRECTION_LEFT_TO_RIGHT);

        // getting the internal state of bidi
        // using toString() method
        String status = bidi.toString();

        // display the result
        System.out.println("status of bidi : "
                           + status);
    }
}
```

**输出:**

```
status of bidi :
 sun.text.bidi.BidiBase[
  dir: 0 
  baselevel: 0
  length: 5
  runs: [0 0 0 0 0]
  text: [0x47 0x65 0x65 0x6b 0x73]]

```

**例 2:**

```
// Java program to demonstrate
// toString() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi
            = new Bidi(
                "TE1",
                Bidi.DIRECTION_RIGHT_TO_LEFT);

        // getting the internal state of bidi
        // using toString() method
        String status = bidi.toString();

        // display the result
        System.out.println(
            "status of bidi : "
            + status);
    }
}
```

**输出:**

```
status of bidi :
 sun.text.bidi.BidiBase[
  dir: 2
  baselevel: 1
  length: 3
  runs: [2 2 2]
  text: [0x54 0x45 0x31]]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/Bidi . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#toString--)