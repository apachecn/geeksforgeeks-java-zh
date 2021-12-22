# Java 中的数组 getFloat()方法

> 原文:[https://www . geesforgeks . org/array-getfloat-method-in-Java/](https://www.geeksforgeeks.org/array-getfloat-method-in-java/)

**java . lang . reflect . Array . getfloat()**是 Java 中 Array 类的一个内置方法，用于将指定数组中给定索引处的元素作为 Float 返回。

**语法**:

```java
Array.getFloat(Object []array, int index)

```

**参数:**该方法接受两个强制参数:

*   **数组:**要返回其索引的对象数组。
*   **索引:**给定数组的特定索引。返回给定数组中“index”处的元素。

**返回值:**这个方法以字节的形式返回数组的元素。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **arrayindexoofboundsexception**–如果给定的索引不在数组的大小范围内。

**注意:**类型转换不是必需的，因为返回类型是浮动的。

下面的程序说明了数组类的 getFloat()方法。

**程序 1** :

```java
// Java code to demonstrate getFloat() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a float array
        float a[] = { 1.0f, 2.0f, 3.0f };

        // Traversing the array
        for (int i = 0; i < 3; i++) {

            // Array.getBoolean() method

            float x = Array.getFloat(a, i);
            // Printing the values
            System.out.print(x + " ");
        }
    }
}
```

**输出**:

```java
1.0 2.0 3.0 

```

**程序 2** :

```java
// Java code to demonstrate getFloat() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a float array
        float a[] = { 1.0f, 2.0f, 3.0f };

        try {
            float x = Array.getFloat(a, 4);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出**:

```java
Exception : java.lang.ArrayIndexOutOfBoundsException

```

**程序 3** :

```java
// Java code to demonstrate getFloat() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a float array as null
        float a[] = null;

        try {
            float x = Array.getFloat(a, 4);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出**:

```java
Exception : java.lang.NullPointerException

```

**程序 4** :

```java
// Java code to demonstrate getFloat() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a float variable
        float a = 1.0f;

        try {
            float x = Array.getFloat(a, 4);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出**:

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array

```

**程序 5** :

```java
// Java code to demonstrate getFloat() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a String array
        String s[] = { "Geeks", "for", "Geeks" };

        try {
            float x = Array.getFloat(s, 4);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**输出**:

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array

```