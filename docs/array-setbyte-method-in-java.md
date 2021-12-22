# Java 中的数组 setByte()方法

> 原文:[https://www.geeksforgeeks.org/array-setbyte-method-in-java/](https://www.geeksforgeeks.org/array-setbyte-method-in-java/)

java . lang . reflect . array . setbyte()是 Java 中的内置方法，用于将指定的字节值设置为给定对象数组的指定索引。

**语法**:

```
Array.setByte(Object []array, int index, byte value)

```

**参数:**该方法取 3 个参数:

*   **数组:**这是一个将要更新的 Object 类型的数组。
*   **索引:**这是要更新的数组的索引。
*   **值:**这是要在给定的*数组*的给定*索引*处设置的字节值。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **arrayindexoofboundsexception**–如果给定的索引不在数组的大小范围内。

下面的程序说明了 Array.setByte()方法:

**程序 1:**

```
// Java code to demonstrate
// setByte() method of Array class

import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining Byte array
        byte b[] = { 1, 2, 3, 4 };

        System.out.print("Befor Set : ");

        // printing the array
        for (byte x : b) {
            System.out.print(x + " ");
        }
        byte value = 10;

        // set method of class Array
        Array.setByte(b, 1, value);

        System.out.print("\nAfter Set : ");

        // printing array
        for (byte x : b) {
            System.out.print(x + " ");
        }
    }
}
```

**Output:**

```
Befor Set : 1 2 3 4 
After Set : 1 10 3 4

```

**程序 2:** 演示 java.lang.NullPointerException

```
// Java code to demonstrate
// setByte() method of Array class

import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining Byte array to null
        byte b[] = null;

        try {
            byte s = 10;
            Array.setByte(b, 5, s);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```
Exception : java.lang.NullPointerException

```

**程序 3:** 演示 Java . lang . arrayindexoutofboundsexception

```
// Java code to demonstrate
// setByte() method of Array class

import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining Byte array
        byte b[] = { 1, 2, 3, 4 };

        try {
            byte s = 10;
            Array.setByte(b, 5, s);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```
Exception : java.lang.ArrayIndexOutOfBoundsException

```

**程序 4:** 演示 Java . lang . illegalargumentexception

```
// Java code to demonstrate
// setByte() method of Array class

import java.lang.reflect.Array;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // Declaring and defining Byte variable
        byte b = 1;

        try {
            byte s = 10;
            Array.setByte(b, 5, s);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```
Exception : java.lang.IllegalArgumentException: Argument is not an array

```