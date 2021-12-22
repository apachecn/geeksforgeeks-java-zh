# Java 中的排序器比较(对象，对象)方法与示例

> 原文:[https://www . geesforgeks . org/collator-compare object-object-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-compareobject-object-method-in-java-with-example/)

**java.text.Collator** 类的 **compare()** 方法用于比较两个对象的强度，它会根据结果返回 0，正值和负值作为输出。

**语法:**

```
public int compare(Object o1, Object o2)
```

**参数**:该方法取**两个对象**，两者之间进行比较。
**返回值:**如果第一个对象等于、大于或小于另一个对象，它将分别返回零、正值和负值。
**异常:**如果参数不能被转换为 Strings，这个方法抛出 *ClassCastException* 。
以下是举例说明**对比()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// compare() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col = Collator.getInstance();

            // Creating an initializing
            // object for comparison
            Object obj1 = "ab";

            // Creating an initializing
            // Object for comparison
            Object obj2 = "Ab";

            // compare both object
            // using compare() method
            int i
                = col.compare((String)obj1, (String)obj2);

            // display result
            if (i < 0)
                System.out.println("ab is less than Ab");
            else if (i > 0)
                System.out.println("ab is greater than Ab");
            else
                System.out.println("ab is equal to Ab");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
ab is less than Ab
```