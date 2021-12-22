# 用示例复制 Java 中的 Collections()方法

> 原文:[https://www . geesforgeks . org/collections-copy-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-copy-method-in-java-with-examples/)

**java.util.Collections** 类的 **copy()** 方法用于将一个列表中的所有元素复制到另一个列表中。

操作完成后，目标列表中每个复制元素的索引将与其在源列表中的索引相同。目标列表必须至少与源列表一样长。如果较长，目标列表中的其余元素不受影响。

该方法在线性时间内运行。

**语法:**

```
public static void copy(List dest, List src)
```

**参数:**该方法采用以下参数作为参数

*   **目的地–**目的地列表。
*   **src–**来源列表。

**异常:**如果目标列表太小，无法包含整个源列表，此方法将抛出**indexout of boundsexception**。

以下是说明*检查数据集()*方法的示例

**例 1:**

```
// Java program to demonstrate
// copy() method

import java.util.*;

public class GFG1 {
    public static void main(String[] args)
        throws Exception
    {
        try {

            // creating object of Source list and destination List
            List<String> srclst = new ArrayList<String>(3);
            List<String> destlst = new ArrayList<String>(3);

            // Adding element to srclst
            srclst.add("Ram");
            srclst.add("Gopal");
            srclst.add("Verma");

            // Adding element to destlst
            destlst.add("1");
            destlst.add("2");
            destlst.add("3");

            // printing the srclst
            System.out.println("Value of source list: " + srclst);

            // printing the destlst
            System.out.println("Value of destination list: " + destlst);

            System.out.println("\nAfter copying:\n");

            // copy element into destlst
            Collections.copy(destlst, srclst);

            // printing the srclst
            System.out.println("Value of source list: " + srclst);

            // printing the destlst
            System.out.println("Value of destination list: " + destlst);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Value of source list: [Ram, Gopal, Verma]
Value of destination list: [1, 2, 3]

After copying:

Value of source list: [Ram, Gopal, Verma]
Value of destination list: [Ram, Gopal, Verma]

```

**示例 2:** 适用于*指数出界异常*

```
// Java program to demonstrate
// copy() method

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of Source list and destination List
            List<String> srclst = new ArrayList<String>(3);
            List<String> destlst = new ArrayList<String>(2);

            // Adding element to srclst
            srclst.add("Ram");
            srclst.add("Gopal");
            srclst.add("Verma");

            // Adding element to destlst
            destlst.add("1");
            destlst.add("2");

            // printing the srclst
            System.out.println("Value of source list: " + srclst);

            // printing the destlst
            System.out.println("Value of destination list: " + destlst);

            System.out.println("\nAfter copying:\n");

            // copy element into destlst
            Collections.copy(destlst, srclst);

            // printing the srclst
            System.out.println("Value of source list: " + srclst);

            // printing the destlst
            System.out.println("Value of destination list: " + destlst);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Value of source list: [Ram, Gopal, Verma]
Value of destination list: [1, 2]

After copying:

Exception thrown : 
java.lang.IndexOutOfBoundsException:
 Source does not fit in dest

```