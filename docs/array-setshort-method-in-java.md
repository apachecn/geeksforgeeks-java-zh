# Java 中的数组 setShort()方法

> 原文:[https://www . geesforgeks . org/array-set short-method-in-Java/](https://www.geeksforgeeks.org/array-setshort-method-in-java/)

**java . lang . reflect . array . setshort()**是 Java 中的一个内置方法，用于将指定的短值设置为给定对象数组的指定索引。

**语法**:

```
Array.setShort(Object []array,int index, short value)

```

**参数:**该方法取 3 个参数:

*   **数组:**这是一个将要更新的 Object 类型的数组。
*   **索引:**这是要更新的数组的索引。
*   **值:**这是在给定的**数组的给定**索引**处设置的短值。**

**异常:**该方法抛出以下异常:

*   **空指针异常**–当数组为空时。
*   **IllegalArgumentException**–当给定的对象数组不是数组时。
*   **ArrayIndexOutOfBoundsException** – if the given index is not in the range of the size of the array.

    下面是 Array.setShort()方法的实现:

    **程序 1 :**

    ```
    // Java code to demonstrate 
    // setShort() method of Array class

    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args) {

            // Declaring and defining Short array
            short b[] = {1,2,3,4};
            System.out.print("Befor Set : ");
            // printing the array
            for(short x : b){
                System.out.print(x + " ");
            }
            short value = 10;
            // set method of class Array
            Array.setShort(b, 1, value);

            System.out.print("\nAfter Set : ");
            // printing array
            for(short x : b){
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

    **程序 2 :** 演示 java.lang.NullPointerException

    ```
    // Java code to demonstrate 
    // setShort() method of Array class

    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args) {

            // Declaring and defining Short array to null
            short b[] = null;
            try{
                short s = 10;
                Array.setShort(b,5,s);
            }
            catch(Exception e){
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
    // setShort() method of Array class

    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args) {

            // Declaring and defining Short array
            short b[] = {1,2,3,4};
            try{
                short s = 10;
                Array.setShort(b,5,s);
            }
            catch(Exception e){
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
    // setShort() method of Array class
    import java.lang.reflect.Array;
    public class GfG {
        // main method
        public static void main(String[] args) {

            // Declaring and defining Short variable
            short b = 1;
            try{
                short s = 10;
                Array.setShort(b,5,s);
            }
            catch(Exception e){
                System.out.println("Exception : " + e);
            }

        }
    }
    ```

    **Output:**

    ```
    Exception : java.lang.IllegalArgumentException: Argument is not an array

    ```