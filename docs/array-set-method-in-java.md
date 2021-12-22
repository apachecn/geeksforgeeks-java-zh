# Java 中的数组集合()方法

> 原文:[https://www.geeksforgeeks.org/array-set-method-in-java/](https://www.geeksforgeeks.org/array-set-method-in-java/)

java.lang.reflect.Array.set()是 java 中的内置方法，用于将指定值设置为给定对象数组的指定索引。

**语法**

```
Array.set(Object []array, int index, Object value)

```

**参数:**

*   **数组:**这是一个将要更新的 Object 类型的数组。
*   **索引:**这是要更新的数组的索引。
*   **值:**这是在给定的**数组**的给定**索引**处设置的值

**返回类型:**这是一个不返回任何值的 void 类型方法。更新反映了作为参数传递的对象数组。

**异常:**该方法抛出以下异常。

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **ArrayIndexOutOfBoundsException** – if the given index is not in the range of the size of the array.

    下面的程序说明了 Array.set()方法:

    **程序 1 :**

    ```
    // Java code to demonstrate set() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {

            // Declaring and defining a String array
            String s[] = { "Geeks", "is", "Geeks" };

            System.out.print("Befor Set : ");
            // printing the array
            for (String x : s) {
                System.out.print(x);
            }

            // set method of class Array
            Array.set(s, 1, "for");

            System.out.print("\nAfter Set : ");
            // printing array
            for (String x : s) {
                System.out.print(x);
            }
        }
    }
    ```

    **Output:**

    ```
    Befor Set : GeeksisGeeks
    After Set : GeeksforGeeks

    ```

    **程序 2 :** 演示 java.lang.NullPointerException

    ```
    // Java code to demonstrate set() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {

            // Declaring and defining a String array
            String s[] = null;

            try {
                // set method of class Array
                Array.set(s, 1, "for");
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

    **程序 3 :** 演示 Java . lang . arrayindexoutofboundsexception

    ```
    // Java code to demonstrate set() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {

            // Declaring and defining a String array
            String s[] = { "Geeks", "for", "Geeks" };

            try {
                // set method of class Array
                Array.set(s, 4, "for");
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

    **程序 4 :** 演示 Java . lang . illegalargumentexception

    ```
    // Java code to demonstrate set() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {

            // Declaring and defining a String array
            String s = "GeeksforGeeks";

            try {
                // set method of class Array
                Array.set(s, 4, "for");
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