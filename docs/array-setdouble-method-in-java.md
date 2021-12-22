# Java 中的数组 setDouble()方法

> 原文:[https://www . geesforgeks . org/array-set double-method-in-Java/](https://www.geeksforgeeks.org/array-setdouble-method-in-java/)

**java . lang . reflect . array . setDouble()**是 Java 中的一个内置方法，用于将指定的 double 值设置为给定对象数组的指定索引。

**语法:**

```
Array.setDouble(Object []array, int index, double value)
```

**参数:**该方法取三个参数:

*   **数组:**这是一个将要更新的 Object 类型的数组。
*   **索引:**这是要更新的数组的索引。
*   **值:**这是在给定的*数组*的给定*索引*处设置的双倍值。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **ArrayIndexOutOfBoundsException**– if the given index is not in the range of the size of the array.

    下面是 Array.setDouble()方法的实现:

    **程序 1:**

    ```
    // Java code to demonstrate setDouble()
    // method of Array class

    import java.lang.reflect.Array;

    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining double array
            double f[] = { 1.0, 2.0, 3.0 };

            // printing the array
            System.out.print("Before Set : ");
            for (double x : f) {
                System.out.print(x + " ");
            }

            double value = 400.0;

            // setDouble method of class Array
            Array.setDouble(f, 1, value);

            // printing array
            System.out.print("\nAfter Set : ");
            for (double x : f) {
                System.out.print(x + " ");
            }
        }
    }
    ```

    **Output:**

    ```
    Before Set : 1.0 2.0 3.0 
    After Set : 1.0 400.0 3.0

    ```

    **程序 2:** 演示 java.lang.NullPointerException

    ```
    // Java code to demonstrate setDouble()
    // method of Array class

    import java.lang.reflect.Array;

    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining double array to null
            double b[] = null;

            try {
                double c = 1.0;

                // setDouble method of class Array
                // passing null array in parameters
                Array.setDouble(b, 5, c);
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
    // Java code to demonstrate setDouble()
    // method of Array class

    import java.lang.reflect.Array;

    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining double array
            double b[] = { 1.0, 2.0, 3.0 };

            try {
                double c = 1.0;

                // setDouble method of class Array
                // passing index 5 when size is 3
                Array.setDouble(b, 5, c);
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
    // Java code to demonstrate setDouble()
    // method of Array class

    import java.lang.reflect.Array;

    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining double variable
            double b = 2.0;
            try {
                double c = 1.0;
                // setDouble method of class Array
                // passing a variable as parameter
                // when an array is required instead
                Array.setDouble(b, 5, c);
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