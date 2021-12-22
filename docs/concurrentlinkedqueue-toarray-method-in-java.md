# Java 中的 ConcurrentLinkedQueue toArray()方法

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedqueue-to array-method-in-Java/](https://www.geeksforgeeks.org/concurrentlinkedqueue-toarray-method-in-java/)

1.  **toArray() :** The **toArray()** method of **ConcurrentLinkedQueue** is used to returns an array of the same elements as that of the ConcurrentLinkedQueue in proper sequence. Basically, it copies all the element from a ConcurrentLinkedQueue to a new array. This method behaves as a bridge between array and ConcurrentLinkedQueue.

    **语法:**

    ```
    public Object[] toArray()
    ```

    **返回:**该方法返回**一个数组**，该数组包含类似于 ConcurrentLinkedQueue 的元素。

    下面的程序说明了 Java . util . concurrentlinkedqueue . to array()方法。

    **例 1:**

    ```
    // Java Program Demonstrate toArray()
    // method of ConcurrentLinkedQueue

    import java.util.concurrent.ConcurrentLinkedQueue;

    public class GFG {

        public static void main(String[] args)
        {
            // create object of ConcurrentLinkedQueue
            ConcurrentLinkedQueue<Integer> queue
                = new ConcurrentLinkedQueue<Integer>();

            // Add element to ConcurrentLinkedQueue
            queue.add(2300);
            queue.add(1322);
            queue.add(8945);
            queue.add(6512);

            // print queue details
            System.out.println("Queue Contains " + queue);

            // apply toArray() method on queue
            Object[] array = queue.toArray();

            // Print elements of array
            System.out.println("The array contains:");
            for (Object i : array) {
                System.out.print(i + "\t");
            }
        }
    }
    ```

    **Output:**

    ```
    Queue Contains [2300, 1322, 8945, 6512]
    The array contains:
    2300    1322    8945    6512

    ```

    **例 2:**

    ```
    // Java Program Demonstrate toArray()
    // method of ConcurrentLinkedQueue

    import java.util.concurrent.ConcurrentLinkedQueue;

    public class GFG {
        public static void main(String args[])
        {
            // Creating a ConcurrentLinkedQueue
            ConcurrentLinkedQueue<String>
                queue = new ConcurrentLinkedQueue<String>();

            // elements into the Queue
            queue.add("Welcome");
            queue.add("To");
            queue.add("Jungle");

            // Displaying the ConcurrentLinkedQueue
            System.out.println("The ConcurrentLinkedQueue: "
                               + queue);

            // Creating the array and using toArray()
            Object[] arr = queue.toArray();

            System.out.println("The array is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);
        }
    }
    ```

    **Output:**

    ```
    The ConcurrentLinkedQueue: [Welcome, To, Jungle]
    The array is:
    Welcome
    To
    Jungle

    ```

2.  **toArray(T[] a) :** The **toArray(T[] a)** method of **ConcurrentLinkedQueue** is used to an array containing the same elements as that of this ConcurrentLinkedQueue in proper sequence. This method differs from toArray() in only one condition. The type of the returned array is the same as the passed array in the parameter, if the ConcurrentLinkedQueue size is less than or equal to the passed array. Otherwise, a new array is allocated with the type same as the specified array and size of the array is equal to the size of this queue. This method behaves as a bridge between array and collections.

    **语法:**

    ```
    public <T> T[] toArray(T[] a)
    ```

    **参数:**该方法以**数组**为参数，如果队列足够大，队列的所有元素都要复制到该参数中。否则，会为此分配一个相同运行时类型的新数组。

    **返回:**这个方法返回包含类似于 ConcurrentLinkedQueue 元素的**数组**。

    **异常:**该方法抛出以下异常:

    *   **arraystorexception**:当传递的数组与 ConcurrentLinkedQueue 的元素类型不同时。
    *   **空指针异常**:如果传递的数组为空。

    下面的程序说明了 Java . util . concurrentlinkedqueue . to array(T[]a)方法。

    **例 1:**

    ```
    // Java Program Demonstrate toArray()
    // method of ConcurrentLinkedQueue

    import java.util.concurrent.ConcurrentLinkedQueue;

    public class GFG {

        public static void main(String[] args)
        {
            // create object of ConcurrentLinkedQueue
            ConcurrentLinkedQueue<String> queue
                = new ConcurrentLinkedQueue<String>();

            // elements into the Queue
            queue.add("Welcome");
            queue.add("To");
            queue.add("Jungle");

            // print queue details
            System.out.println("Queue Contains " + queue);

            // the array to pass in toArray()
            // array has size equal to size of ConcurrentLinkedQueue
            String[] passArray = new String[queue.size()];

            // Calling toArray(T[] a) method
            Object[] array = queue.toArray(passArray);

            // Print elements of passed array
            System.out.println("\nThe array passed :");
            for (String i : passArray) {
                System.out.print(i + " ");
            }

            System.out.println();

            // Print elements of returned array
            System.out.println("\nThe array returned :");
            for (Object i : array) {
                System.out.print(i + " ");
            }
        }
    }
    ```

    **Output:**

    ```
    Queue Contains [Welcome, To, Jungle]

    The array passed :
    Welcome To Jungle 

    The array returned :
    Welcome To Jungle

    ```

    **例 2:** 显示**数组异常**

    ```
    // Java Program Demonstrate toArray()
    // method of ConcurrentLinkedQueue

    import java.util.concurrent.ConcurrentLinkedQueue;

    public class GFG {

        public static void main(String[] args)
        {
            // create object of ConcurrentLinkedQueue
            ConcurrentLinkedQueue<Integer> queue
                = new ConcurrentLinkedQueue<Integer>();

            // Add element to ConcurrentLinkedQueue
            queue.add(2323);
            queue.add(2472);
            queue.add(4235);
            queue.add(1242);

            // the array to pass in toArray()
            // array has size equal to size of ConcurrentLinkedQueue
            String[] passArray = new String[queue.size()];

            // Calling toArray(T[] a) method
            try {
                Object[] array = queue.toArray(passArray);
            }
            catch (ArrayStoreException e) {
                System.out.println("Exception: " + e);
            }
        }
    }
    ```

    **Output:**

    ```
    Exception: java.lang.ArrayStoreException: java.lang.Integer

    ```

    **示例 2:** 显示**空指针异常**

    ```
    // Java Program Demonstrate toArray()
    // method of ConcurrentLinkedQueue

    import java.util.concurrent.ConcurrentLinkedQueue;

    public class GFG {

        public static void main(String[] args)
        {
            // create object of ConcurrentLinkedQueue
            ConcurrentLinkedQueue<Integer> queue
                = new ConcurrentLinkedQueue<Integer>();

            // Add element to ConcurrentLinkedQueue
            queue.add(2323);
            queue.add(2472);
            queue.add(4235);
            queue.add(1242);

            // the array to pass
            String[] passArray = null;

            // Calling toArray(T[] a) method
            try {
                Object[] array = queue.toArray(passArray);
            }
            catch (NullPointerException e) {
                System.out.println("Exception: " + e);
            }
        }
    }
    ```

    **Output:**

    ```
    Exception: java.lang.NullPointerException

    ```