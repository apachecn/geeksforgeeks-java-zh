# 抽象顺序列表到 Java 中的 Array(T[])方法，示例

> 原文:[https://www . geesforgeks . org/abstractsequentialist-to arrayt-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-toarrayt-method-in-java-with-example/)

Java 中**抽象顺序列表类**的 **toArray(arr[])** 方法方法用于形成与抽象顺序列表相同元素的数组。它以正确的顺序返回一个包含这个抽象顺序列表中所有元素的数组**；**返回数组的运行时类型是指定数组的运行时类型。如果抽象序列列表适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此 AbstractSequentialList 的大小分配一个新数组。
如果抽象序列元素列表适合指定的有空间的数组(即数组的元素比抽象序列元素列表多)，数组中紧接在抽象序列元素列表末尾的元素被设置为空。(只有当调用方知道抽象顺序列表不包含任何空元素时，这在确定抽象顺序列表的长度时才有用。)

**语法:**

```
public <T> T[] toArray(T[] a)
```

**参数:**该方法接受一个参数 **arr[]** ，如果抽象顺序列表的元素足够大，则该参数是要存储到其中的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该方法返回一个包含类似于抽象序列列表元素的数组。

**异常:**该方法可能会引发两种类型的异常:

*   **arraystorexception**:当提到的数组属于不同类型，无法与 AbstractSequentialList 中提到的元素进行比较时。
*   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

下面的程序说明了 abstractsequentialilist . to array(arr[])方法的工作原理。

**程序 1:** 当数组大小为抽象序列列表时

```
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            abs_col = new LinkedList<String>();

        // Use add() method to add
        // elements into the AbstractSequentialList
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSequentialList
        System.out.println("The AbstractSequentialList: "
                           + abs_col);

        // Creating the array and using toArray()
        String[] arr = new String[5];
        arr = abs_col.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The AbstractSequentialList: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks

```

**程序 2:** 当数组小于抽象序列列表的大小时

```
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            abs_col = new LinkedList<String>();

        // Use add() method to add
        // elements into the AbstractSequentialList
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSequentialList
        System.out.println("The AbstractSequentialList: "
                           + abs_col);

        // Creating the array and using toArray()
        String[] arr = new String[1];
        arr = abs_col.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The AbstractSequentialList: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks

```

**程序 3:** 当数组大于抽象序列列表的大小时

```
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            abs_col = new LinkedList<String>();

        // Use add() method to add
        // elements into the AbstractSequentialList
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSequentialList
        System.out.println("The AbstractSequentialList: "
                           + abs_col);

        // Creating the array and using toArray()
        String[] arr = new String[10];
        arr = abs_col.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The AbstractSequentialList: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks
null
null
null
null
null

```

**程序 4:** 演示空指针异常

```
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractSequentialListDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractSequentialList
        AbstractSequentialList<String>
            abs_col = new LinkedList<String>();

        // Use add() method to add
        // elements into the AbstractSequentialList
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractSequentialList
        System.out.println("The AbstractSequentialList: "
                           + abs_col);

        try {
            // Creating the array
            String[] arr = null;
            // using toArray()
            // Since arr is null
            // Hence exception will be thrown
            arr = abs_col.toArray(arr);

            // Displaying arr
            System.out.println("The arr[] is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
The AbstractSequentialList: [Welcome, To, Geeks, For, Geeks]
Exception: java.lang.NullPointerException

```