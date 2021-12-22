# 在 Java 中将数组合并成一个新的对象数组

> 原文:[https://www . geesforgeks . org/merge-arrays-in-a-new-object-array-in-Java/](https://www.geeksforgeeks.org/merge-arrays-into-a-new-object-array-in-java/)

给定两个相同类型的数组，它们需要合并成一个新的对象数组。任务是将相同类型的两个数组合并成一个对象数组，使得数组元素在新合并的数组中保持其原始顺序，并且在合并的对象数组中，第一个数组的元素在第二个数组的元素之前。

这种合并可以在 Java 中以多种方式完成，比如 Java8、System.arrraycopy()和 Java Collections。

1.  **Java 8**: In Java8 this can be done using the [Stream API](https://www.geeksforgeeks.org/java-8-stream/).
    *   **Using Stream.of(), flatMap() and toArray() methods**:

        **Class hierarchy of Stream :**

        ```java
        java.lang.Object
          ↳  java.util.stream

        ```

        **方法描述**

        | 修饰符和类型 | 方法 | 描述 |
        | --- | --- | --- |
        | 静态<t>流</t> | 的(T…值) | 返回元素为指定值的顺序有序流。 |
        | <r>流</r> | 平面图(功能 super T,? extends Stream extends R%gt;>映射器) | 在对每个元素应用映射函数后返回一个对象流，然后对结果进行平面化。 |
        | 对象[] | toarray() | 返回包含此流元素的数组。 |

        **示例:**

        ```java
        Input : a[] = {1, 2, 3}
                b[] = {4, 5, 6}
        Output : {1, 2, 3, 4, 5, 6}

        ```

        **解释:**
        (a，b)的流获取数组并将它们流水线化为一个流。然后 flatMap()方法在对 Stream.of()的每个元素应用映射函数后返回一个对象流，然后将结果展平。最后，toArray()将流元素转换为数组，并返回形成的数组。

        ```java
        // Java program to merge two arrays of 
        // same type into an Object array.

        import java.util.stream.Stream;
        import java.util.Arrays;
        import java.io.*;

        class GFG {

            public static <T> Object[] concatenate(T[] a, T[] b)
            {
                // Function to merge two arrays of 
                // same type
                return Stream.of(a, b)
                             .flatMap(Stream::of)
                             .toArray();

                // Arrays::stream can also be used in place
                // of Stream::of in the flatMap() above.
            }

            public static void main (String[] args) 
            {
                Integer[] a = new Integer[]{1,2,3};
                Integer[] b = new Integer[]{4,5,6};

                Object[] c = concatenate(a,b);

            System.out.println("Merged object array : "
                               + Arrays.toString(c));
            }
        }
        ```

        **输出:**

        ```java
        Merged object array : [1, 2, 3, 4, 5, 6]

        ```

    *   **Using Stream.concat(), Arrays.stream() and toArray() methods**:

        **方法描述**

        | 修饰符和类型 | 方法 | 描述 |
        | --- | --- | --- |
        | 静态<t>流</t> | 串联(流 extends T> a，流 extends T> b) | 创建一个延迟连接的流，其元素是第一个流的所有元素，后跟第二个流的所有元素。 |

        **示例:**

        ```java
        Input : a[] = {1, 2, 3}
                b[] = {4, 5, 6}
        Output : {1, 2, 3, 4, 5, 6}

        ```

        **解释:**
        stream . concat()创建一个合并的流，其中元素按照它们在参数中的顺序排列。在这里，Stream.concat()创建一个串联流，其元素是从数组“a”转换而来的流的所有元素，后跟从数组“b”转换而来的流的所有元素。然后，连接的流被转换为数组并返回。

        ```java
        // Java program to merge two arrays of 
        // same type into an Object array.

        import java.util.stream.Stream;
        import java.util.Arrays;
        import java.io.*;

        class GFG {

            public static <T> Object[] concatenate(T[] a, T[] b)
            {
                // Function to merge two arrays of 
                // same type
                return Stream.concat(Arrays.stream(a), 
                                     Arrays.stream(b))
                             .toArray();
            }

            public static void main (String[] args) 
            {
                Integer[] a = new Integer[]{1,2,3};
                Integer[] b = new Integer[]{4,5,6};

                Object[] c = concatenate(a,b);

            System.out.println("Merged object array : "
                               + Arrays.toString(c));
            }
        }
        ```

        **输出:**

        ```java
        Merged object array : [1, 2, 3, 4, 5, 6]

        ```

2.  [**System.arraycopy()**](https://www.geeksforgeeks.org/java-lang-system-arraycopy-method/): The java.lang.System.arraycopy() method copies a source array from a specific beginning position to the destination array from the mentioned position. No. of arguments to be copied are decided by len argument.

    源位置到源位置+长度–1 的组件从目标位置到目标位置+长度–1 被复制到目标阵列。

    **类别申报:**

    ```java
    public final class *System* extends *Object*

    ```

    **语法:**

    ```java
    public static void arraycopy(Object source_arr, int sourcePos,
                                Object dest_arr, int destPos, int len)

    Parameters : 
    source_arr : array to be copied from
    sourcePos : starting position in source array from where to copy
    dest_arr : array to be copied in
    destPos : starting position in destination array, where to copy in
    len : total no. of components to be copied.

    ```

    **示例:**

    ```java
    Input : a[] = {1, 2, 3}
            b[] = {4, 5, 6}
    Output : {1, 2, 3, 4, 5, 6}

    ```

    ```java
    // Java program to merge two arrays of 
    // same type into an Object array.

    import java.util.stream.Stream;
    import java.util.Arrays;
    import java.io.*;

    class GFG {

        // Function to merge two arrays of same type
        public static <T> Object[] concatenate(T[] a, T[] b)
        {
            // Create an empty Object array of the combined
            // size of the array a and array b
            Object[] n=new Object[a.length + b.length];

            // Copy the array a into n
            System.arraycopy(a, 0, n, 0, a.length);

            // Copy the array b into n
            System.arraycopy(b, 0, n, a.length, b.length);

            return n;
        }

        public static void main (String[] args) 
        {
            Integer[] a = new Integer[]{1,2,3};
            Integer[] b = new Integer[]{4,5,6};

            Object[] c = concatenate(a,b);

        System.out.println("Merged object array : "
                           + Arrays.toString(c));
        }
    }
    ```

    **输出:**

    ```java
    Merged object array : [1, 2, 3, 4, 5, 6]

    ```

3.  [**Java Collections**](https://www.geeksforgeeks.org/collections-in-java-2/):Collection 是表示为单个单元的一组单个对象。Java 提供了集合框架，该框架定义了几个类和接口，将一组对象表示为一个单元。
    *   **Using Java Collections for Java 8 Stream**:
        Examples:

        ```java
        Input : a[] = {1, 2, 3}
                b[] = {4, 5, 6}
        Output : {1, 2, 3, 4, 5, 6}

        ```

        ```java
        // Java program to merge two arrays of 
        // same type into an Object array.

        import java.util.stream.*;
        import java.util.Arrays;
        import java.io.*;

        class GFG {

            // Function to merge two arrays of same type
            public static <T> Object[] concatenate(T[] a, T[] b)
            {

                // Create an empty List of type Object
                List<Object> n = new ArrayList<>();

                // Add arrays to list
                Stream.of(a, b)
                     .flatMap(Stream::of)
                     .forEach(n::add);

                // Convert list to array and return
                return n.toArray();
            }

            public static void main (String[] args) 
            {
                Integer[] a = new Integer[]{1,2,3};
                Integer[] b = new Integer[]{4,5,6};

                Object[] c = concatenate(a,b);

            System.out.println("Merged object array : "
                               + Arrays.toString(c));
            }
        }
        ```

        **输出:**

        ```java
        Merged object array : [1, 2, 3, 4, 5, 6]

        ```

    *   **Using Java Collections for Java 7 using Collections.addAll()**:
        Examples:

        ```java
        Input : a[] = {1, 2, 3}
                b[] = {4, 5, 6}
        Output : {1, 2, 3, 4, 5, 6}

        ```

        ```java
        // Java program to merge two arrays of 
        // same type into an Object array.

        import java.util.*;
        import java.io.*;

        class GFG {

            // Function to merge two arrays of same type
            public static <T> List<Object> concatenate(T[] a, T[] b)
            {
                // Create an empty List of type Object
                List<Object> n = new ArrayList<>();

                // Add the array a into n
                Collections.addAll(n, a);

                // Add the array b into n
                Collections.addAll(n, b);

                return n;
            }

            public static void main (String[] args) 
            {
                Integer[] a = new Integer[]{1,2,3};
                Integer[] b = new Integer[]{4,5,6};

                List<Object> c = concatenate(a,b);

                System.out.println("Merged object array : "
                                   + c);
            }
        }
        ```

        **输出:**

        ```java
        Merged object array : [1, 2, 3, 4, 5, 6]

        ```