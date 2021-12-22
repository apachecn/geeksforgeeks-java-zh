# Java 中数组到数组列表的转换

> 原文:[https://www . geesforgeks . org/array-to-ArrayList-conversion-in-Java/](https://www.geeksforgeeks.org/array-to-arraylist-conversion-in-java/)

**数组**是元素的集合，可以是原始数据类型，也可以是对象。Java 中的数组本质上是静态的。**数组列表，**则只能将元素存储为对象。与数组不同，Java 中的数组列表本质上是动态的。数组列表是存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中的集合类，它实现了 [java.util.List](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口。

可以使用以下方法将数组转换为数组列表:

1.  **Using ArrayList.add() method to manually add the array elements in the ArrayList**: This method involves creating a new ArrayList and adding all of the elements of the given array to the newly created ArrayList using add() method.

    ```java
    Syntax: public void add(int index, E element)

    ```

    **参数:**该功能接受 2 个强制参数:

    *   **索引**–要插入指定元素的索引。
    *   **元素**–要插入的元素。

    **返回:**该方法不返回任何值

    **异常:**如果指数超出范围，该方法将抛出 **[指数。](https://www.geeksforgeeks.org/understanding-array-indexoutofbounds- exception-in-java/)**

    示例:

    ```java
    // Java program to illustrate conversion 
    // of an array to an ArrayList

    import java.util.Arrays;
    import java.util.ArrayList;

    class ArrayToArrayList {
        public static void func1(int arr[])
        {
            ArrayList<Integer> array_list = 
                    new ArrayList<Integer>();

            // Using add() method to add elements in array_list
            for (int i = 0; i < arr.length; i++)
                array_list.add(new Integer(arr[i]));
            System.out.print(array_list);
        }

        public static void main(String[] args)
        {

            int array[] = { 1, 2, 3, 4, 5 };
            func1(array);
        }
    }
    ```

    **Output:**

    ```java
    [1, 2, 3, 4, 5]

    ```

2.  **Using Arrays.asList() method of java.utils.Arrays class:** This method converts the array into list and then passes the list as the parameter to initialise a new ArrayList with the list values.

    ```java
    Syntax: public static List asList(T[] a)

    ```

    **参数:**该方法接受一个命令参数 T[] a，其中 a 是支持列表的数组，T 是数组的类型。

    **返回:**方法返回指定数组的列表视图。

    示例:

    ```java
    // Java program to illustrate conversion
    // of an array to an ArrayList

    import java.util.Arrays;
    import java.util.ArrayList;

    class ArrayToArrayList {
        public static void func2(Integer arr[])
        {
            // Using Arrays.asList() method
            ArrayList<Integer> array_list = 
                new ArrayList<Integer>(Arrays.asList(arr));
            System.out.print(array_list);
        }

        public static void main(String[] args)
        {

            // Integer objects are used instead
            // of primitives for conversion to list
            Integer array[] = { new Integer(1),
                                new Integer(2),
                                new Integer(3),
                                new Integer(4),
                                new Integer(5) };
            func2(array);
        }
    }
    ```

    **Output:**

    ```java
    [1, 2, 3, 4, 5]

    ```

3.  **Using Collections.addAll() method of java.utils.Collections class:** This method takes the ArrayList in which the array values are to be inserted as the first parameter; and the Array whose values are to be used as the second parameter. Then it copies the values of the Array into the ArrayList.

    ```java
    Syntax: public static boolean addAll(Collection c, T.. a)

    ```

    **参数:**该方法接受 2 个强制参数:

    *   **c**–这是要插入元素的集合。
    *   **a**–要插入 c 的 T 型阵列

    **返回:**如果集合因调用而改变，则方法返回“真”，否则返回“假”。

    **异常:**方法抛出

    *   **不支持的掺杂异常**。
    *   如果指定的集合为空，则**NullPointRexception**。
    *   **IllegalArgumentException** 如果数组中某个值的某个方面阻止它被添加到 c。

    示例:

    ```java
    // Java program to illustrate conversion 
    // of an array to an ArrayList

    import java.util.Collections;
    import java.util.ArrayList;

    class ArrayToArrayList {
        public static void func3(String arr[])
        {
            ArrayList<String> array_list = new ArrayList<String>();

            // Using Collections.addAll() method
            Collections.addAll(array_list, arr);
            System.out.print(array_list);
        }

        public static void main(String[] args)
        {

            String array[] = { "ABC", "DEF", "GHI", "JKL" };
            func3(array);
        }
    }
    ```

    **Output:**

    ```java
    [ABC, DEF, GHI, JKL]

    ```

4.  **Using Arrays.stream() method of java.utils.Arrays class:** This method creates a sequential stream of the values of the array. Then with the help of collect() method and the stream, the values are copied into the ArrayList.

    ```java
    Syntax: public static IntStream stream(T[] a)

    ```

    **参数:**该方法接受一个强制参数‘a’，该参数是要转换成类型为 T 的流的数组
    **返回:**该方法返回指定类型的数组流(这里是 Int)。

    **解说:**T2**阵.流()。collect()** 方法使用**Java . util . stream . collectors**类，借助 **toList()** 方法将流转换为列表。

    **注意:**此方法需要 **Java 8** 或更高版本。

    示例:

    ```java
    // Java program to illustrate conversion 
    // of an array to an ArrayList

    import java.util.Arrays;
    import java.util.ArrayList;
    import java.util.stream.Collectors;

    class ArrayToArrayList {
        public static void func4(String arr[])
        {
            // Using Arrays.stream.collect() method.
            ArrayList<String> array_list = (ArrayList<String>)
                        Arrays.stream(arr)
                              .collect(Collectors.toList());
            System.out.print(array_list);
        }

        public static void main(String[] args)
        {

            String array[] = { "ABC", "DEF", "GHI", "JKL" };
            func4(array);
        }
    }
    ```

    **Output:**

    ```java
    [ABC, DEF, GHI, JKL]

    ```

5.  **Using List.of(Elements) method of java.utils.List Interface:** This method takes the array as the parameter and then creates an immutable list of the values of the array. This immutable list is then passed as the parameter to create a new ArrayList,

    ```java
    Syntax: static {T} List{T} of(a)

    ```

    **参数:**该方法接受一个强制参数‘a’，它是要转换的数组，T 表示列表的元素类型(可以省略)。
    **返回:**方法返回包含指定元素的列表。
    **异常:**如果数组为空，该方法抛出**空指针异常**。

    **注意:**此方法需要 **Java 9** 或更高版本。

    示例:

    ```java
    // Java program to illustrate conversion 
    // of an array to an ArrayList

    import java.util.List;
    import java.util.Arrays;
    import java.util.ArrayList;
    import java.util.stream.Collectors;

    class ArrayToArrayList {
        public static void func5(String arr[])
        {
            // Using List.of() method.
            ArrayList<String> array_list = 
            new ArrayList<String>(List.of(arr));
            System.out.print(array_list);
        }

        public static void main(String[] args)
        {
            String array[] = { "ABC", "DEF", "GHI", "JKL" };
            func5(array);
        }
    }
    ```

    **Output:**

    ```java
    [ABC, DEF, GHI, JKL]

    ```

**参考文献:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/stream/package-summary . html](https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html)
*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/stream/collectors . html](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Collectors.html)
*   [https://docs . Oracle . com/javae/9/docs/API/Java/util/list . html](https://docs.oracle.com/javase/9/docs/api/java/util/List.html)