# 用示例

链接 Java 中的锁请求到数组()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingreque-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedblockingdeque-toarray-method-in-java-with-example/)

*   ### toarray()

    **Java . util . concurrent . linkedblockingrequest . to array()**方法返回一个数组，该数组包含了按正确顺序(即从第一个到最后一个)排列的所有元素。创建新数组时，返回的数组将是安全的(因此会分配新内存)。因此调用者可以自由修改数组。它充当了基于数组和基于集合的 API 之间的桥梁。

    **语法**

    ```
    public Object[] toArray()
    ```

    **参数:**不取任何参数。

    **返回值:**返回一个包含所有元素的数组。

    以下示例说明了 LinkedBlockingDeque.toArray()方法:

    **例 1:**

    ```
    // Java Program Demonstrate toArray()
    // method of LinkedBlockingDeque

    import java.util.concurrent.*;
    import java.util.*;

    public class GFG {
        public static void main(String[] args)
            throws IllegalStateException
        {

            // create object of LinkedBlockingDeque
            LinkedBlockingDeque<Integer> LBD
                = new LinkedBlockingDeque<Integer>();

            // Add numbers to end of LinkedBlockingDeque
            LBD.add(7855642);
            LBD.add(35658786);
            LBD.add(5278367);
            LBD.add(74381793);

            System.out.println("LinkedBlockingDeque: "
                               + LBD);

            Object[] a = LBD.toArray();
            System.out.println("Returned Array: "
                               + Arrays.toString(a));
        }
    }
    ```

    **Output:**

    ```
    LinkedBlockingDeque: [7855642, 35658786, 5278367, 74381793]
    Returned Array: [7855642, 35658786, 5278367, 74381793]

    ```

*   ### toaarray(t[])

    Java 中**linkedblockingrequest 类**的 **toArray(arr[])** 方法方法用于形成与 linkedblockingrequest 相同元素的数组。它返回一个数组，该数组包含了这个 LinkedBlockingDeque 中所有元素的正确顺序**；**返回数组的运行时类型是指定数组的运行时类型。如果 LinkedBlockingDeque 适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此 linkedblockingrequest 的大小分配一个新数组。
    如果 linkedblockingrequest 适合有空余空间的指定数组(即数组中的元素比 linkedblockingrequest 多)，则紧接在 linkedblockingrequest 末尾的数组中的元素被设置为空。(只有当调用方知道 linkedblockingrequest 不包含任何空元素时，这在确定 linkedblockingrequest 的长度时才有用。)

    **语法:**

    ```
    public <T> T[] toArray(T[] a)
    ```

    **参数:**该方法接受一个参数 **arr[]** ，如果足够大的话，这个参数就是 LinkedBlockingDeque 的元素要存储到的数组；否则，将为此目的分配一个相同运行时类型的新数组。

    **返回值:**该方法返回一个数组，该数组包含类似于 linkedblockingrequest 的元素。

    **异常:**该方法可能会引发两种类型的异常:

    *   **arraystorexception**:当提到的数组属于不同类型，无法与 linkedblockingrequest 中提到的元素进行比较时。
    *   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

    下面的程序说明了 linkedblockingrequest . to array(arr[])方法的工作原理。

    **程序 1:** 当数组的大小为 LinkedBlockingDeque 时

    ```
    // Java code to illustrate toArray(arr[])

    import java.util.concurrent.*;
    import java.util.*;

    public class LinkedBlockingDequeDemo {
        public static void main(String args[])
        {
            // Creating an empty LinkedBlockingDeque
            LinkedBlockingDeque<String> LBD
                = new LinkedBlockingDeque<String>();

            // Use add() method to add
            // elements into the LinkedBlockingDeque
            LBD.add("Welcome");
            LBD.add("To");
            LBD.add("Geeks");
            LBD.add("For");
            LBD.add("Geeks");

            // Displaying the LinkedBlockingDeque
            System.out.println("The LinkedBlockingDeque: "
                               + LBD);

            // Creating the array and using toArray()
            String[] arr = new String[5];
            arr = LBD.toArray(arr);

            // Displaying arr
            System.out.println("Returned Array: "
                               + Arrays.toString(arr));
        }
    }
    ```

    **Output:**

    ```
    The LinkedBlockingDeque: [Welcome, To, Geeks, For, Geeks]
    Returned Array: [Welcome, To, Geeks, For, Geeks]

    ```