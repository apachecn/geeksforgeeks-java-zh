# Java 中的 Array setInt()方法

> 原文:[https://www.geeksforgeeks.org/array-setint-method-in-java/](https://www.geeksforgeeks.org/array-setint-method-in-java/)

**java . lang . reflect . array . setInt()**是 Java 中的一个内置方法，用于将指定的 int 值设置为给定对象数组的指定索引。

**语法**:

```java
Array.setInt(Object []array, int index, int value)

```

**参数:**

*   **数组:**这是一个将要更新的 Object 类型的数组。
*   **索引:**这是要更新的数组的索引。
*   **值:**这是要在给定的**数组的给定**索引**处设置的 int 值。**

**返回值:**这是一个不返回值的 void 类型方法。更新反映了作为参数传递的对象数组。

**异常:**该方法抛出以下异常。

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **ArrayIndexOutOfBoundsException** – if the given index is not in the range of the size of the array.

    下面的程序说明了 Array.setInt()方法:

    **程序 1 :**

    ```java
    // Java code to demonstrate setInt() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {

            // Declaring and defining Integer array
            int b[] = { 1, 2, 3, 4 };
            System.out.print("Befor Set : ");
            // printing the array
            for (Integer x : b) {
                System.out.print(x + " ");
            }
            int value = 10;
            // set method of class Array
            Array.setInt(b, 1, value);

            System.out.print("\nAfter Set : ");
            // printing array
            for (Integer x : b) {
                System.out.print(x + " ");
            }
        }
    }
    ```

    **输出**

    ```java
    Befor Set : 1 2 3 4 
    After Set : 1 10 3 4 

    ```

    **程序 2 :** 演示 java.lang.NullPointerException。

    ```java
    // Java code to demonstrate setInt() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {

            // Declaring and defining Integer array to null
            Integer b[] = null;
            try {
                Array.setInt(b, 5, 10);
            }
            catch (Exception e) {
                System.out.println("Exception : " + e);
            }
        }
    }
    ```

    **输出**

    ```java
    Exception : java.lang.NullPointerException

    ```

    **程序 3 :** 演示 Java . lang . arrayindexoutofboundsexception。

    ```java
    // Java code to demonstrate setInt() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {

            // Declaring and defining Integer array
            Integer b[] = { 1, 2, 3, 4 };
            try {
                Array.setInt(b, 5, 10);
            }
            catch (Exception e) {
                System.out.println("Exception : " + e);
            }
        }
    }
    ```

    **输出**

    ```java
    Exception : java.lang.ArrayIndexOutOfBoundsException

    ```

    **程序 4 :** 演示 Java . lang . illegalargumentexception。

    ```java
    // Java code to demonstrate setInt() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {

            // Declaring and defining Integer variable
            Integer b = 1;
            try {
                Array.setInt(b, 5, 10);
            }
            catch (Exception e) {
                System.out.println("Exception : " + e);
            }
        }
    }
    ```

    **输出**

    ```java
    Exception : java.lang.IllegalArgumentException: Argument is not an array

    ```