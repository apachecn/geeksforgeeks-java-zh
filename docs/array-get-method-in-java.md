# Java 中的数组 get()方法

> 原文:[https://www.geeksforgeeks.org/array-get-method-in-java/](https://www.geeksforgeeks.org/array-get-method-in-java/)

**java . lang . reflect . Array . get()**是 Java 中的一个内置方法，用于返回指定数组中给定索引处的元素。

**语法**

```java
Array.get(Object []array, int index)

```

**参数:**该方法接受两个强制参数:

*   **数组:**要返回其索引的对象数组。
*   **索引:**给定数组的特定索引。返回给定数组中“index”处的元素。

**返回值:**这个方法返回数组的元素作为 Object 类的类型。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **arrayindexoofboundsexception**–如果给定的索引不在数组的大小范围内。

下面的程序说明了数组类的 get()方法:

**程序 1:**

```java
import java.lang.reflect.Array;

public class GfG {
    // main method
    public static void main(String[] args)
    {
        // Declaring and defining an int array
        int a[] = { 1, 2, 3, 4, 5 };

        // Traversing the array
        for (int i = 0; i < 5; i++) {

            // Array.get method
            // Note : typecasting is essential
            // as the return type in Object.
            int x = (int)Array.get(a, i);

            // Printing the values
            System.out.print(x + " ");
        }
    }
}
```

**Output:**

```java
1 2 3 4 5

```

**程序 2:** 演示 ArrayIndexOutOfBoundsException。

```java
import java.lang.reflect.Array;

public class GfG {
    // main method
    public static void main(String[] args)
    {
        // Declaring and defining an int array
        int a[] = { 1, 2, 3, 4, 5 };

        try {
            // invalid index
            int x = (int)Array.get(a, 6);
            System.out.println(x);
        }
        catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.ArrayIndexOutOfBoundsException

```

**程序 3:** 演示 NullPointerException。

```java
import java.lang.reflect.Array;

public class GfG {
    // main method
    public static void main(String[] args)
    {
        // Declaring an int array
        int a[];

        // array to null
        a = null;

        try {
            // null Object array
            int x = (int)Array.get(a, 6);
            System.out.println(x);
        }
        catch (Exception e) {
            // throws Exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.NullPointerException

```

**程序 4:** 演示 IllegalArgumentException。

```java
import java.lang.reflect.Array;

public class GfG {
    // main method
    public static void main(String[] args)
    {
        // int (Not an array)
        int y = 0;

        try {
            // illegalArgument
            int x = (int)Array.get(y, 6);

            System.out.println(x);
        }
        catch (Exception e) {
            // Throws exception
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array

```