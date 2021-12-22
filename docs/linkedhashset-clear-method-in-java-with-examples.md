# 用示例链接 Java 中的 clear()方法

> 原文:[https://www . geeksforgeeks . org/link edhashset-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedhashset-clear-method-in-java-with-examples/)

**[Java . util . linkedhashset](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/)**类的 **clear()** 方法用于从该集合中移除所有元素。此调用返回后，集合将为空。

**语法:**

```
public void clear()
```

**返回值:**此方法**不返回**任何东西。

下面举例说明 *clear()* 方法。

**例 1:**

```
// Java program to demonstrate
// clear() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Create the object of LinkedHashSet<Integer>
            LinkedHashSet<Integer>
                linkset = new LinkedHashSet<Integer>();

            // populate hash set
            linkset.add(10);
            linkset.add(20);
            linkset.add(30);

            // print the LinkedHashSet
            System.out.println("LinkedHashSet: "
                               + linkset);

            // clear set values
            // using clear() method
            linkset.clear();

            // print the LinkedHashSet
            System.out.println("LinkedHashSet after "
                               + "use of clear() method: "
                               + linkset);
        }

        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
LinkedHashSet: [10, 20, 30]
LinkedHashSet after use of clear() method: []

```

**例 2:**

```
// Java program to demonstrate
// clear() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Create the object of LinkedHashSet<Integer>
            LinkedHashSet<String>
                linkset = new LinkedHashSet<String>();

            // populate hash set
            linkset.add("A");
            linkset.add("B");
            linkset.add("C");

            // print the LinkedHashSet
            System.out.println("LinkedHashSet: "
                               + linkset);

            // clear set values
            // using clear() method
            linkset.clear();

            // print the LinkedHashSet
            System.out.println("LinkedHashSet after "
                               + "use of clear() method: "
                               + linkset);
        }

        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
LinkedHashSet: [A, B, C]
LinkedHashSet after use of clear() method: []

```