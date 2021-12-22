# Java 中抽象集合 toArray()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract collection-to array-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-toarray-method-in-java-with-examples/)

### 1 . toarray()

**[Java 抽象集合](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)** 的 **toArray()** 方法用于形成与抽象集合相同元素的数组。基本上，它将抽象集合中的所有元素复制到一个新数组中。

**语法:**

```java
Object[] arr = AbstractCollection.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含与抽象集合相似元素的数组。

下面的程序说明了 AbstractCollection.toArray()方法:

**程序 1:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractCollection
        AbstractCollection<String>
            abs_col = new PriorityQueue<String>();

        // Use add() method to add
        // elements into the AbstractCollection
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractCollection
        System.out.println("The AbstractCollection: "
                           + abs_col);

        // Creating the array and using toArray()
        Object[] arr = abs_col.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The AbstractCollection: [For, Geeks, To, Welcome, Geeks]
The array is:
For
Geeks
To
Welcome
Geeks

```

**程序 2:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractCollection
        AbstractCollection<Integer>
            abs_col = new PriorityQueue<Integer>();

        // Use add() method to add
        // elements into the AbstractCollection
        abs_col.add(10);
        abs_col.add(15);
        abs_col.add(30);
        abs_col.add(20);
        abs_col.add(5);
        abs_col.add(25);

        // Displaying the AbstractCollection
        System.out.println("The AbstractCollection: "
                           + abs_col);

        // Creating the array and using toArray()
        Object[] arr = abs_col.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The AbstractCollection: [5, 10, 25, 20, 15, 30]
The array is:
5
10
25
20
15
30

```

### 2 . toaarray(arr[])

Java 中**抽象集合类**的 **toArray(arr[])** 方法方法用于形成一个与抽象集合相同元素的数组。它以正确的顺序返回包含这个抽象集合中所有元素的数组**；**返回数组的运行时类型是指定数组的运行时类型。如果抽象集合适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此抽象集合的大小分配一个新数组。
如果 AbstractCollection 适合有空余空间的指定数组(即数组中的元素比 AbstractCollection 多)，数组中紧跟在 AbstractCollection 末尾的元素将被设置为 null。(只有当调用方知道抽象集合不包含任何空元素时，这才有助于确定抽象集合的长度。)

**语法:**

```java
Object[] arr1 = AbstractCollection.toArray(arr[])
```

**参数:**该方法接受一个参数 **arr[]** ，如果抽象集合的元素足够大，则该参数是要存储到其中的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该方法返回一个包含与抽象集合相似元素的数组。

**异常:**该方法可能会引发两种类型的异常:

*   **arraystorexception**:当提到的数组属于不同类型，无法与 AbstractCollection 中提到的元素进行比较时。
*   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

下面的程序说明了 abstract collection . to array(arr[])方法的工作原理。

**程序 1:** 当数组具有抽象集合的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractCollection
        AbstractCollection<String>
            abs_col = new PriorityQueue<String>();

        // Use add() method to add
        // elements into the AbstractCollection
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractCollection
        System.out.println("The AbstractCollection: "
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

```java
The AbstractCollection: [For, Geeks, To, Welcome, Geeks]
The arr[] is:
For
Geeks
To
Welcome
Geeks

```

**程序 2:** 当数组小于抽象集合的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractCollection
        AbstractCollection<String>
            abs_col = new PriorityQueue<String>();

        // Use add() method to add
        // elements into the AbstractCollection
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractCollection
        System.out.println("The AbstractCollection: "
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

```java
The AbstractCollection: [For, Geeks, To, Welcome, Geeks]
The arr[] is:
For
Geeks
To
Welcome
Geeks

```

**程序 3:** 当数组大于抽象集合的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractCollection
        AbstractCollection<String>
            abs_col = new PriorityQueue<String>();

        // Use add() method to add
        // elements into the AbstractCollection
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractCollection
        System.out.println("The AbstractCollection: "
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

```java
The AbstractCollection: [For, Geeks, To, Welcome, Geeks]
The arr[] is:
For
Geeks
To
Welcome
Geeks
null
null
null
null
null

```

**程序 4:** 演示空指针异常

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class AbstractCollectionDemo {
    public static void main(String args[])
    {
        // Creating an empty AbstractCollection
        AbstractCollection<String>
            abs_col = new PriorityQueue<String>();

        // Use add() method to add
        // elements into the AbstractCollection
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the AbstractCollection
        System.out.println("The AbstractCollection: "
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

```java
The AbstractCollection: [For, Geeks, To, Welcome, Geeks]
Exception: java.lang.NullPointerException

```