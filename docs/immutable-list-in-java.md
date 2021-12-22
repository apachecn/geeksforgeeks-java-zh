# Java 中的不可变列表

> 原文:[https://www.geeksforgeeks.org/immutable-list-in-java/](https://www.geeksforgeeks.org/immutable-list-in-java/)

*   顾名思义，不可变列表是一种不可变的列表类型。表示列表的内容在声明后是固定的或不变的，即**为只读**。
*   如果试图添加、删除和更新列表中的元素，将引发**取消支持操作异常**。
*   不变列表也不允许空元素。
*   如果试图创建具有空元素的不可替换列表，将引发**空指针异常**。如果试图在列表中添加空元素，将引发**不支持操作异常**。

**不变列表的优势**

*   它们是线程安全的。
*   它们的记忆效率很高。
*   由于它们是不可变的，因此它们可以毫无问题地被**传递给第三方库**。

**注意**是不可变集合，不是不可变对象的集合，所以里面的对象是可以修改的。

**类别申报:**

```java
@GwtCompatible(serializable=true,
               emulated=true)
public abstract class ImmutableList
extends ImmutableCollection
implements List, RandomAccess

```

**等级等级:**

```java
java.lang.Object
  ↳ java.util.AbstractCollection
      ↳ com.google.common.collect.ImmutableCollection
          ↳ com.google.common.collect.ImmutableList 

```

**创建不变列表**
不变列表可以通过各种方法创建。其中包括:

1.  **From existing List using copyOf() function of Guava**

    ```java
    // Below is the Java program to create ImmutableList

    import com.google.common.collect.ImmutableList;
    import java.util.*;

    class GFG {

        // Function to create ImmutableList from List
        public static <T> void iList(List<T> list)
        {
            // Create ImmutableMap from Map using copyOf()
            ImmutableList<T> immutableList =
                              ImmutableList.copyOf(list);

            // Print the ImmutableMap
            System.out.println(immutableList);
        }

        public static void main(String[] args)
        {
            List<String> list = new ArrayList<>(
                Arrays.asList("Geeks", "For", "Geeks"));

            iList(list);
        }
    }
    ```

    输出:

    ```java
    [Geeks, For, Geeks]

    ```

2.  **New ImmutableList using of() function from Guava**

    ```java
    // Below is the Java program to create ImmutableList

    import com.google.common.collect.ImmutableList;
    import java.util.*;

    class GFG {

        // Function to create ImmutableList
        public static void iList()
        {
            // Create ImmutableList using of()
            ImmutableList<String> immutableList = 
                   ImmutableList.of("Geeks", "For", "Geeks");

            // Print the ImmutableMap
            System.out.println(immutableList);
        }

        public static void main(String[] args)
        {
            iList();
        }
    }
    ```

    输出:

    ```java
    [Geeks, For, Geeks]

    ```

3.  **Using Java 9 Factory Of() method**

    在 Java 中，使用()和集合、映射或列表来创建不可变列表。

    **请注意:下面的程序都是 Java 9 的。因此，您需要一个 Java 9 编译器来运行它们。**

    ```java
    // Java code illustrating of() method to
    // create a ImmutableSet
    import java.util.*;
    import com.google.common.collect.ImmutableList;

    class GfG {
        public static void main(String args[])
        {
            // non-empty immutable set
            List<String> list = List.of("Geeks", "For", "Geeks");

            // Let's print the list
            System.out.println(list);
        }
    }
    ```

    输出:

    ```java
    [Geeks, For, Geeks]

    ```

4.  **Using [Builder()](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/collect/ImmutableList.Builder.html) from ImmutableList**

    在番石榴中，ImmnutableList 类提供了一个函数 Builder()。通过该功能，可以创建一个新的不可替换列表，或者从现有列表中创建一个不可替换列表，或者两者都创建。

    *   **Creating a new ImmutableList**

        ```java
        // Java code illustrating of() method to
        // create a ImmutableList
        import java.util.*;
        import com.google.common.collect.ImmutableList;

        class GfG {
            public static void main(String args[])
            {
                // non-empty immutable set
                ImmutableList<String> iList = ImmutableList.<String>builder()
                                                  .add("Geeks", "For", "Geeks")
                                                  .build();

                // Let's print the List
                System.out.println(iList);
            }
        }
        ```

        输出:

        ```java
        [Geeks, For, Geeks]

        ```

    *   **Creating an ImmutableList from existing List**

        ```java
        // Java code illustrating of() method to
        // create a ImmutableList
        import java.util.*;
        import com.google.common.collect.ImmutableList;

        class GfG {
            public static void main(String args[])
            {
                // non-empty immutable set
                List<String> list = List.of("Geeks", "For", "Geeks");
                ImmutableList<String> iList = ImmutableList.<String>builder()
                                                  .addAll(list)
                                                  .build();

                // Let's print the List
                System.out.println(iList);
            }
        }
        ```

        输出:

        ```java
        [Geeks, For, Geeks]

        ```

    *   **Creating a new ImmutableList including the existing List**

        ```java
        // Java code illustrating of() method to
        // create a ImmutableList
        import java.util.*;
        import com.google.common.collect.ImmutableList;

        class GfG {
            public static void main(String args[])
            {
                // non-empty immutable set
                List<String> list = List.of("Geeks", "For", "Geeks");
                ImmutableList<String> iList = ImmutableList.<String>builder()
                                                  .addAll(list)
                                                  .add("Computer", "Portal", )
                                                  .build();

                // Let's print the set
                System.out.println(iList);
            }
        }
        ```

        输出:

        ```java
        [Geeks, For, Geeks, Computer, Portal]

        ```

**尝试改变不变的**

如前所述，下面的程序将抛出**不支持操作异常**。

```java
// Java code to show that UnsupportedOperationException
// will be thrown when ImmutableList is modified.
import java.util.*;

class GfG {
    public static void main(String args[])
    {
        // empty immutable map
        List<String> list = List.of();

        // Lets try adding element in  List
        List.add("Geeks");
    }
}
```

输出:

```java
Exception in thread "main" java.lang.UnsupportedOperationException
    at com.google.common.collect.ImmutableCollection.add(ImmutableCollection.java:218)
    at ImmutableListDemo.main(Main.java:16)

```

**与 Collections.unmodifiableList()有何不同？**

集合。未修改列表在相同的现有列表周围创建一个包装，这样包装就不能用于修改它。但是，我们仍然可以更改原始列表。

```java
// Java program to demonstrate that a List created using
// Collections.unmodifiableList() can be modified indirectly.
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        List<String> list = new ArrayList<>();
        list.add("Geeks");

        // Create ImmutableList from List using copyOf()
        List<String> iList = Collections.unmodifiableList(list);

        // We change List and the changes reflect in iList.
        list.add("For");
        list.add("Geeks");

        System.out.println(iList);
    }
}
```

**输出:**

```java
[Geeks, For, Geeks]

```

如果我们从现有列表中创建一个不变列表并更改现有列表，则不变列表不会因为创建了副本而更改。

```java
// Below is a Java program for
// Creating an immutable List using copyOf()
// and modifying original List.
import java.io.*;
import java.util.*;
import com.google.common.collect.ImmutableList;

class GFG {
    public static void main(String[] args)
    {
        List<String> list = new ArrayList<>();
        list.add("Geeks");

        // Create ImmutableList from List using copyOf()
        ImmutableList<String> iList = ImmutableList.copyOf(list);

        // We change List and the changes wont reflect in iList.
        list.add("For");
        list.add("Geeks");

        System.out.println(iList);
    }
}
```

输出:

```java
[Geeks]

```