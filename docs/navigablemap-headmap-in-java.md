# Java 中的 naviglamblemap heartap()

> 原文:[https://www.geeksforgeeks.org/navigablemap-headmap-in-java/](https://www.geeksforgeeks.org/navigablemap-headmap-in-java/)

Java 中[导航地图界面的头地图()方法用于返回该地图中键小于(或等于，如果包含为真)toKey 的部分的视图。](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

[*   The returned map is backed by this map, so the changes of the returned map will be reflected in this map and vice versa.*   The returned map supports all optional map operations supported by the map.*   The returned map will throw an IllegalArgumentException, trying to insert a key outside its scope.](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

**语法** :

```
NavigableMap<K, V> headMap(K toKey,
                          boolean inclusive)

```

其中，K 是由该映射维护的键的类型，V 是与该映射中的键相关联的值。

**参数**:该功能接受两个参数:

*   **toKey** :这个参数指的是按键。
*   **包含**:该参数决定是否将待删除的键与相等进行比较。

**返回值**:返回该地图中键小于(或等于，如果包含为真)toKey 的部分的视图。

**程序 1** :当键为整数，*第二个参数缺失*。

```
// Java code to demonstrate the working of
// headMap?() method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of Integer and String
        NavigableMap<Integer, String> nmmp = new TreeMap<>();

        // assigning the values in the NavigableMap
        // using put()
        nmmp.put(2, "two");
        nmmp.put(7, "seven");
        nmmp.put(3, "three");

        System.out.println("View of map with key less than"
                      + " or equal to 7 : " + nmmp.headMap(7));
    }
}
```

**输出:**

```
View of map with key less than or equal to 7 : {2=two, 3=three}

```

**程序 2** :带第二个参数。

```
// Java code to demonstrate the working of
// headMap?() method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of Integer and String
        NavigableMap<Integer, String> nmmp = new TreeMap<>();

        // assigning the values in the NavigableMap
        // using put()
        nmmp.put(2, "two");
        nmmp.put(7, "seven");
        nmmp.put(3, "three");
        nmmp.put(9, "nine");

        // headMap with second argument as true
        System.out.println("View of map with key less than"
                     + " or equal to 7 : " + nmmp.headMap(7, true));
    }
}
```

**输出:**

```
View of map with key less than or equal to 7 : {2=two, 3=three, 7=seven}

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/navigablemap . html #头标(K，boolean)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#headMap(K, boolean))