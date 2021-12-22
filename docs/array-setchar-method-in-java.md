# Java 中的 Array setChar()方法

> 原文:[https://www.geeksforgeeks.org/array-setchar-method-in-java/](https://www.geeksforgeeks.org/array-setchar-method-in-java/)

**java . lang . reflect . array . setChar()**是 Java 中的一个内置方法，用于将指定的 char 值更改为给定对象数组的指定索引。

**语法:**

```java
Array.setChar(Object []array, int index, char value)
```

**参数:**该方法取三个参数:

*   **数组:**这是一个将要更新的 Object 类型的数组。
*   **索引:**这是要更新的数组的索引。
*   **值:**这是要在给定的**数组的给定**索引**处设置的字符值。**

**返回值:**这个方法有一个 void 返回类型。因此这不会返回任何值。更新反映了作为参数传递的对象数组。

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **ArrayIndexOutOfBoundsException**– if the given index is not in the range of the size of the array.

    下面是 Array.setChar()方法的实现:

    **程序 1:**

    ```java
    // Java code to demonstrate setChar()
    // method of Array class

    import java.lang.reflect.Array;

    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining char array
            char ch[] = { 'a', 'b', 'c', 'd', 'e' };

            System.out.print("Before Set : ");

            // printing the array
            for (char x : ch) {
                System.out.print(x + " ");
            }

            char value = 'g';

            // setChar method of class Array
            Array.setChar(ch, 1, value);

            System.out.print("\nAfter Set : ");

            // printing array
            for (char x : ch) {
                System.out.print(x + " ");
            }
        }
    }
    ```

    **Output:**

    ```java
    Before Set : a b c d e 
    After Set : a g c d e

    ```

    **程序 2:** 演示 java.lang.NullPointerException

    ```java
    // Java code to demonstrate setChar()
    // method of Array class

    import java.lang.reflect.Array;

    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining char array to null
            char b[] = null;

            try {
                char c = 'a';

                // Passing null array in parameter
                Array.setChar(b, 5, c);
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
    // Java code to demonstrate
    // setChar() method of Array class

    import java.lang.reflect.Array;
    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining char array
            char b[] = { 'a', 'b', 'c', 'd' };

            try {
                char c = 'g';
                // Passing index 5 as parameter
                // when the size is 4 instead
                Array.setChar(b, 5, c);
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
    // Java code to demonstrate setChar()
    // method of Array class

    import java.lang.reflect.Array;
    public class GfG {

        // main method
        public static void main(String[] args)
        {
            // Declaring and defining char variable
            char b = 'b';

            try {
                char c = 'g';

                // Passing a variable as parameter
                // when an array is expected instead
                Array.setChar(b, 5, c);
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