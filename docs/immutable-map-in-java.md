# Java 中的不可变映射

> 原文:[https://www.geeksforgeeks.org/immutable-map-in-java/](https://www.geeksforgeeks.org/immutable-map-in-java/)

*   顾名思义，不可变地图是一种不可变的地图。表示声明后地图的内容是固定的或不变的，即**为只读**。
*   如果试图添加、删除和更新地图中的元素，将引发**取消支持操作异常**。
*   不变映射也不允许空元素。
*   如果试图创建一个包含空元素的不变映射，将抛出**空指针异常**。如果试图在地图中添加空元素，将引发**不支持操作异常**。

**不变地图的优势**

*   它们是线程安全的。
*   它们的记忆效率很高。
*   由于它们是不可变的，因此它们可以毫无问题地被**传递给第三方库**。

**注意**是不可变集合，不是不可变对象的集合，所以里面的对象是可以修改的。

**类申报:**

```java
@GwtCompatible(serializable=true,
               emulated=true)
public abstract class ImmutableMap
extends Object
implements Map, Serializable

```

**等级等级:**

```java
java.lang.Object
  ↳ com.google.common.collect.ImmutableMap 

```

**创建不变地图**
不变地图可以通过多种方法创建。其中包括:

1.  **From existing Map using copyOf() function of Guava**

    ```java
    // Below is the Java program to create ImmutableMap

    import com.google.common.collect.ImmutableMap;
    import java.util.HashMap;
    import java.util.Map;

    class MapUtil {

        // Function to create ImmutableMap from Map
        public static <K, T> void iMap(Map<K, T> map)
        {
            // Create ImmutableMap from Map using copyOf()
            ImmutableMap<K, T> immutableMap = ImmutableMap.copyOf(map);

            // Print the ImmutableMap
            System.out.println(immutableMap);
        }

        public static void main(String[] args)
        {
            Map<Integer, String> map = new HashMap<Integer, String>();
            map.put(1, "Geeks");
            map.put(2, "For");
            map.put(3, "Geeks");
            iMap(map);
        }
    }
    ```

    输出:

    ```java
    {1=Geeks, 2=For, 3=Geeks}

    ```

2.  **New ImmutableMap using of() function from Guava**

    ```java
    // Below is the Java program to create ImmutableMap
    import com.google.common.collect.ImmutableMap;
    import java.util.HashMap;
    import java.util.Map;

    class MapUtil {

        // Function to create ImmutableMap
        public static void createImmutableMap()
        {
            // Create ImmutableMap using of()
            ImmutableMap<Integer, String> immutableMap = ImmutableMap.of(
                1, "Geeks",
                2, "For",
                3, "Geeks");

            // Print the ImmutableMap
            System.out.println(immutableMap);
        }

        public static void main(String[] args)
        {
            createImmutableMap();
        }
    }
    ```

    输出:

    ```java
    {1=Geeks, 2=For, 3=Geeks}

    ```

3.  **Using Java 9 Factory Of() method**

    在 Java 中，使用带集合、映射或列表的()来创建不可变映射。

    **请注意:下面的程序都是 Java 9 的。因此，您需要一个 Java 9 编译器来运行它们。**

    ```java
    // Java code illustrating of() method to
    // create a ImmutableSet
    import java.util.*;
    import com.google.common.collect.ImmutableMap;

    class GfG {
        public static void main(String args[])
        {
            // non-empty immutable set
            Map<Integer, String> map = Map.of(
                1, "Geeks",
                2, "For",
                3, "Geeks");

            // Let's print the set
            System.out.println(map);
        }
    }
    ```

    输出:

    ```java
    {1=Geeks, 2=For, 3=Geeks}

    ```

4.  **Using [Builder()](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/collect/ImmutableMap.Builder.html) from ImmutableMap**

    在番石榴中，ImmnutableMap 类提供了一个函数 Builder()。通过该功能，可以创建一个新的不变地图，或者
    可以从现有地图创建一个不变地图，或者两者都创建。

    *   **Creating a new ImmutableMap**

        ```java
        // Java code illustrating of() method to
        // create a ImmutableSet
        import java.util.*;
        import com.google.common.collect.ImmutableMap;

        class GfG {
            public static void main(String args[])
            {
                // non-empty immutable set
                ImmutableMap<Integer, String> imap = 
                                 ImmutableMap.<Integer, String>builder()
                                                         .put(1, "Geeks")
                                                         .put(2, "For")
                                                         .put(3, "Geeks")
                                                         .build();

                // Let's print the set
                System.out.println(imap);
            }
        }
        ```

        输出:

        ```java
        {1=Geeks, 2=For, 3=Geeks}

        ```

    *   **Creating an ImmutableMap from existing Map**

        ```java
        // Java code illustrating of() method to
        // create a ImmutableSet
        import java.util.*;
        import com.google.common.collect.ImmutableMap;

        class GfG {
            public static void main(String args[])
            {
                // non-empty immutable set
                Map<Integer, String> map = Map.of(1, "Geeks",
                                                  2, "For",
                                                  3, "Geeks");
                ImmutableMap<Integer, String> imap = 
                               ImmutableMap.<Integer, String>builder()
                                                         .putAll(map)
                                                         .build();

                // Let's print the set
                System.out.println(imap);
            }
        }
        ```

        输出:

        ```java
        {1=Geeks, 2=For, 3=Geeks}

        ```

    *   **Creating a new ImmutableMap including the existing Map**

        ```java
        // Java code illustrating of() method to
        // create a ImmutableSet
        import java.util.*;
        import com.google.common.collect.ImmutableMap;

        class GfG {
            public static void main(String args[])
            {
                // non-empty immutable set
                Map<Integer, String> map = Map.of(1, "Geeks",
                                                  2, "For",
                                                  3, "Geeks");
                ImmutableMap<Integer, String> imap = 
                             ImmutableMap.<Integer, String>builder()
                                                       .putAll(map)
                                                 .put(4, "Computer")
                                                   .put(5, "Portal")
                                                           .build();

                // Let's print the set
                System.out.println(imap);
            }
        }
        ```

        输出:

        ```java
        {1=Geeks, 2=For, 3=Geeks, 4=Computer, 5=Portal}

        ```

**尝试改变不变的地图**

如前所述，下面的程序将抛出**不支持操作异常**。

```java
// Java code to show that UnsupportedOperationException
// will be thrown when ImmutableMap is modified.
import java.util.*;

class GfG {
    public static void main(String args[])
    {
        // empty immutable map
        Map<Integer, String> map = Map.of();

        // Lets try adding element in these set
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");
    }
}
```

输出:

```java
Exception in thread "main" java.lang.UnsupportedOperationException
    at com.google.common.collect.ImmutableCollection.add(ImmutableCollection.java:218)
    at ImmutableListDemo.main(Main.java:16)

```

**与 Collections.unmodifiableMap()有何不同？**

Collections.unmodifiableMap 在相同的现有地图周围创建一个包装，这样包装就不能用于修改它。然而，我们仍然可以改变原始地图。

```java
// Java program to demonstrate that a Map created using
// Collections.unmodifiableMap() can be modified indirectly.
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        Map<Integer, String> map = new HashMap<Integer, String>();
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");

        // Create ImmutableMap from Map using copyOf()
        Map<Integer, String> imap = Collections.unmodifiableMap(map);

        // We change map and the changes reflect in imap.
        map.put(4, "Computer");
        map.put(5, "Portal");

        System.out.println(imap);
    }
}
```

**输出:**

```java
{1=Geeks, 2=For, 3=Geeks, 4=Computer, 5=Portal}

```

如果我们从现有地图创建不变地图并更改现有地图，则不变地图不会因为创建了副本而更改。

```java
// Below is a Java program for
// Creating an immutable Map using copyOf()
// and modifying original Map.
import java.io.*;
import java.util.*;
import com.google.common.collect.ImmutableMap;

class GFG {
    public static void main(String[] args)
    {
        Map<Integer, String> map = new HashMap<Integer, String>();
        map.put(1, "Geeks");
        map.put(2, "For");
        map.put(3, "Geeks");

        // Create ImmutableMap from Map using copyOf()
        ImmutableMap<Integer, String> imap = ImmutableMap.copyOf(map);

        // We change map and the changes wont reflect in imap.
        map.put(4, "Computer");
        map.put(5, "Portal");

        System.out.println(imap);
    }
}
```

输出:

```java
{1=Geeks, 2=For, 3=Geeks}

```