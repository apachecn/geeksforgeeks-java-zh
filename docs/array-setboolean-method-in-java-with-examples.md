# Java 中的数组集合布尔()方法，示例

> 原文:[https://www . geesforgeks . org/array-set boolean-method-in-Java-with-examples/](https://www.geeksforgeeks.org/array-setboolean-method-in-java-with-examples/)

**Java . lang . reflect . array . setboolean()**方法是一种内置方法，用于将指定的布尔值设置为给定对象数组的指定索引。

**语法:**

```java
Array.setBoolean(Object []array, int index, boolean value)
```

**参数:**该方法取三个参数:

*   **数组:**待更新对象类型的数组。
*   **索引:**要更新的数组的索引。
*   **值:**在给定的*数组*的给定*索引*处设置的布尔值。

**返回类型:**这是一个 void 类型的方法，不返回任何值。更新反映了作为参数传递的对象数组。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **ArrayIndexOutOfBoundsException**– if the given index is not in the range of the size of the array.

    下面是 Array.setBoolean()方法的实现:

    **程序 1:**

    ```java
    // Java code to demonstrate setBoolean()
    // method of Array class

    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {
            // Declaring and defining boolean array
            boolean b[] = { true, false, true };

            // array before using setBoolean()
            System.out.print("Before Set : ");

            // printing the array
            for (boolean x : b) {
                System.out.print(x + " ");
            }

            // boolean value to be set
            boolean value = true;

            // setBoolean method of class Array
            Array.setBoolean(b, 1, value);

            // array after using setBoolean()
            System.out.print("\nAfter Set : ");

            // printing array
            for (boolean x : b) {
                System.out.print(x + " ");
            }
        }
    }
    ```

    **Output:**

    ```java
    Before Set : true false true 
    After Set : true true true

    ```

    **程序 2:** 演示 java.lang.NullPointerException

    ```java
    // Java code to demonstrate setBoolean()
    // method of Array class

    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {
            // Declaring and defining boolean array to null
            boolean b[] = null;

            try {
                // boolean value to be set
                boolean c = false;

                // passing a null array as parameter
                Array.setBoolean(b, 5, c);
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

    **程序 3:** 演示 Java . lang . arrayindexoutofboundsexception

    ```java
    // Java code to demonstrate setBoolean()
    // method of Array class

    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {
            // Declaring and defining boolean array
            boolean b[] = { true, false, true };

            try {
                // value to be set
                boolean c = false;

                // passing index as 5 when size is 3
                Array.setBoolean(b, 5, c);
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

    **程序 4:** 演示 Java . lang . illegalargumentexception

    ```java
    // Java code to demonstrate setBoolean()
    // method of Array class

    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args)
        {
            // Declaring and defining boolean variable
            boolean b = true;

            try {
                // value to be set
                boolean c = false;

                // passing variable in the place of an array
                Array.setBoolean(b, 5, c);
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