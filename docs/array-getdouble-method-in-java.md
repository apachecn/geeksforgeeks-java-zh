# Java 中的数组 getDouble()方法

> 原文:[https://www . geesforgeks . org/array-getdouble-method-in-Java/](https://www.geeksforgeeks.org/array-getdouble-method-in-java/)

**java . lang . reflect . Array . getdouble()**是 Java 中 Array 类的一个内置方法，用于将指定数组中给定索引处的元素作为 Double 返回。

**语法**:

```java
Array.getDouble(Object []array, int index)

```

**参数:**该方法接受两个强制参数:

*   **数组:**要返回其索引的对象数组。
*   **索引:**给定数组的特定索引。返回给定数组中“index”处的元素。

**返回值:**这个方法以字节的形式返回数组的元素。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **arrayindexoofboundsexception**–如果给定的索引不在数组的大小范围内。

**注意:**类型转换不是必需的，因为返回类型是双精度的。

下面的程序说明了数组类的 getDouble()方法。

**程序 1** :

```java
// Java code to demonstrate getDouble() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a double array
        double a[] = { 1.0, 2.0, 3.0 };

        // Traversing the array
        for (int i = 0; i < 3; i++) {

            // Array.getDouble() method

            double x = Array.getDouble(a, i);
            // Printing the values
            System.out.print(x + " ");
        }
    }
}
```

**Output:**

```java
1.0 2.0 3.0

```

**程序 2** :

```java
// Java code to demonstrate getDouble() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a double array
        double a[] = { 1.0, 2.0, 3.0 };

        try {
            double x = Array.getDouble(a, 4);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.ArrayIndexOutOfBoundsException

```

**程序 3** :

```java
// Java code to demonstrate getDouble() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a double array as null
        double a[] = null;

        try {
            double x = Array.getDouble(a, 4);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.NullPointerException

```

**程序 4** :

```java
// Java code to demonstrate getDouble() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a double variable
        double a = 1.0f;

        try {
            double x = Array.getDouble(a, 4);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array

```

**程序 5** :

```java
// Java code to demonstrate getDouble() method of Array class
import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining a String array
        String s[] = { "Geeks", "for", "Geeks" };

        try {
            double x = Array.getDouble(s, 4);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.IllegalArgumentException: Argument is not an array

```