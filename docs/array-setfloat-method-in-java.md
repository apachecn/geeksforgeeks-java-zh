# Java 中的数组 setFloat()方法

> 原文:[https://www . geesforgeks . org/array-set float-method-in-Java/](https://www.geeksforgeeks.org/array-setfloat-method-in-java/)

**java . lang . reflect . array . setFloat()**是 Java 中的一个内置方法，用于将指定的 float 值更改为给定对象数组的指定索引。

**语法:**

```
Array.setFloat(Object []array, int index, float value)
```

**参数:**该方法取三个参数:

*   **数组:**这是一个将要更新的 Object 类型的数组。
*   **索引:**这是要更新的数组的索引。
*   **值:**这是要在给定的*数组*的给定*索引*处设置的浮点值。

**返回值:**由于这个方法有一个 void 返回类型，因此它不返回任何值。更新反映了作为参数传递的对象数组。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **ArrayIndexOutOfBoundsException**– if the given index is not in the range of the size of the array.

    下面是 Array.setFloat()方法的实现:

    **程序 1:**

    ```
    // Java code to demonstrate
    // setFloat() method of Array class

    import java.lang.reflect.Array;
    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining float array
            float f[] = { 1.0f, 2.0f, 3.0f };

            System.out.print("Before Set : ");

            // printing the array
            for (float x : f) {
                System.out.print(x + " ");
            }

            float value = 4.0f;

            // setFloat method of class Array
            Array.setFloat(f, 1, value);

            System.out.print("\nAfter Set : ");

            // printing array
            for (float x : f) {
                System.out.print(x + " ");
            }
        }
    }
    ```

    **Output:**

    ```
    Before Set : 1.0 2.0 3.0 
    After Set : 1.0 4.0 3.0

    ```

    **程序 2:** 演示 java.lang.NullPointerException

    ```
    // Java code to demonstrate
    // setFloat() method of Array class

    import java.lang.reflect.Array;
    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining float array to null
            float b[] = null;

            try {
                float c = 1.0f;
                // Passing null array as parameter
                Array.setFloat(b, 5, c);
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
    // Java code to demonstrate setFloat()
    // method of Array class

    import java.lang.reflect.Array;
    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining float array
            float b[] = { 1.0f, 2.0f, 3.0f };

            try {
                float c = 1.0f;

                // Passing index as 5 in parameter
                // when the size of array is 3
                Array.setFloat(b, 5, c);
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
    // Java code to demonstrate setFloat()
    // method of Array class

    import java.lang.reflect.Array;
    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining float variable
            float b = 2.0f;

            try {
                float c = 1.0f;

                // Passing variable as parameter
                // where an array is expected.
                Array.setFloat(b, 5, c);
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