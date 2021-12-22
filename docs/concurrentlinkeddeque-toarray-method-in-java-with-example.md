# Java 中的 ConcurrentLinkedDeque toArray()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/concurrentlinkeddeque-toarray-method-in-java-with-example/)

*   ### toarray()

    **Java . util . concurrentlinkedrequest . to array()**方法返回一个数组，该数组包含了以适当的顺序(即从第一个到最后一个)排列的所有元素。创建新数组时，返回的数组将是安全的(因此会分配新内存)。因此调用者可以自由修改数组。它充当了基于数组和基于集合的 API 之间的桥梁。

    **语法**

    ```
    public Object[] toArray()
    ```

    **参数:**不取任何参数。

    **返回值:**返回一个包含所有元素的数组。

    以下示例说明了 concurrentlinkedrequest . to array()方法:

    **例 1:**

    ```
    // Java Program Demonstrate toArray()
    // method of ConcurrentLinkedDeque

    import java.util.concurrent.*;
    import java.util.*;

    public class GFG {
        public static void main(String[] args)
            throws IllegalStateException
        {

            // create object of ConcurrentLinkedDeque
            ConcurrentLinkedDeque<Integer> deque
                = new ConcurrentLinkedDeque<Integer>();

            // Add numbers to end of ConcurrentLinkedDeque
            deque.add(7855642);
            deque.add(35658786);
            deque.add(5278367);
            deque.add(74381793);

            System.out.println("ConcurrentLinkedDeque: "
                               + deque);

            Object[] a = deque.toArray();
            System.out.println("Returned Array: "
                               + Arrays.toString(a));
        }
    }
    ```

    **Output:**

    ```
    ConcurrentLinkedDeque: [7855642, 35658786, 5278367, 74381793]
    Returned Array: [7855642, 35658786, 5278367, 74381793]

    ```

*   ### toaarray(t[])

    Java 中**concurrentlinkedeque 类**的 **toArray(arr[])** 方法方法用于形成一个与 concurrentlinkedeque 相同元素的数组。它以正确的顺序返回一个包含这个 ConcurrentLinkedDeque 中所有元素的数组**；**返回数组的运行时类型是指定数组的运行时类型。如果 ConcurrentLinkedDeque 适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此 concurrentlinkedrequest 的大小分配一个新数组。
    如果 concurrentlinkedeque 适合指定的有空余空间的数组(即数组中的元素比 concurrentlinkedeque 多)，则紧接在 concurrentlinkedeque 末尾的数组中的元素被取消为空。(只有当调用方知道 concurrentlinkedeque 不包含任何空元素时，这才有助于确定 concurrentlinkedeque 的长度。)

    **语法:**

    ```
    public <T> T[] toArray(T[] a)
    ```

    **参数:**该方法接受一个参数 **arr[]** ，如果 ConcurrentLinkedDeque 的元素足够大，则该参数是要存储该元素的数组；否则，将为此目的分配一个相同运行时类型的新数组。

    **返回值:**该方法返回一个数组，该数组包含类似于 ConcurrentLinkedDeque 的元素。

    **异常:**该方法可能会引发两种类型的异常:

    *   **arraystorexception**:当提到的数组是不同类型的，无法与 concurrentlinkedrequest 中提到的元素进行比较时。
    *   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

    下面的程序说明了 concurrentlinkedrequest . to array(arr[])方法的工作原理。

    **程序 1:** 当数组的大小为 ConcurrentLinkedDeque 时

    ```
    // Java code to illustrate toArray(arr[])

    import java.util.concurrent.*;
    import java.util.*;

    public class ConcurrentLinkedDequeDemo {
        public static void main(String args[])
        {
            // Creating an empty ConcurrentLinkedDeque
            ConcurrentLinkedDeque<String> deque
                = new ConcurrentLinkedDeque<String>();

            // Use add() method to add
            // elements into the ConcurrentLinkedDeque
            deque.add("Welcome");
            deque.add("To");
            deque.add("Geeks");
            deque.add("For");
            deque.add("Geeks");

            // Displaying the ConcurrentLinkedDeque
            System.out.println("The ConcurrentLinkedDeque: "
                               + deque);

            // Creating the array and using toArray()
            String[] arr = new String[5];
            arr = deque.toArray(arr);

            // Displaying arr
            System.out.println("Returned Array: "
                               + Arrays.toString(arr));
        }
    }
    ```

    **Output:**

    ```
    The ConcurrentLinkedDeque: [Welcome, To, Geeks, For, Geeks]
    Returned Array: [Welcome, To, Geeks, For, Geeks]

    ```