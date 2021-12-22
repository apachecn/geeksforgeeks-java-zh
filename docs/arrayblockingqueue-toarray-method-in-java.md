# Java 中 ArrayBlockingQueue toArray()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-to array-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-toarray-method-in-java/)

1.  **The toArray() method of [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/) class:**
    The toArray() method of ArrayBlockingQueue class is used to create an array containing the same elements as that of this ArrayBlockingQueue, in proper sequence. Basically, it copies all the element from the ArrayBlockingQueue to a new array. This method behaves as a bridge between array and collections.

    **语法:**

    ```java
    public Object[] toArray()
    ```

    **返回值:**该方法返回一个包含该队列中所有元素的数组。

    下面的程序举例说明 ArrayBlockingQueue 类的 toArray()方法:
    **程序 1:**

    ```java
    // Program Demonstrate how to apply toArray() method
    // of ArrayBlockingQueue Class.

    import java.util.concurrent.ArrayBlockingQueue;

    public class GFG {

        public static void main(String[] args)
        {
            // Define capacity of ArrayBlockingQueue
            int capacity = 5;

            // Create object of ArrayBlockingQueue
            ArrayBlockingQueue<Integer> queue = new 
                         ArrayBlockingQueue<Integer>(capacity);

            // Add 5 elements to ArrayBlockingQueue
            queue.offer(423);
            queue.offer(422);
            queue.offer(421);
            queue.offer(420);
            queue.offer(424);

            // Create a array by calling toArray() method
            Object[] array = queue.toArray();

            // Print queue
            System.out.println("Queue is " + queue);

            // Print elements of array
            System.out.println("The array created by toArray() is:");
            for (Object i : array) {
                System.out.println(i);
            }
        }
    }
    ```

    **Output:**

    ```java
    Queue is [423, 422, 421, 420, 424]
    The array created by toArray() is:
    423
    422
    421
    420
    424

    ```

    **程序 2:**

    ```java
    // Program Demonstrate how to apply toArray() method
    // of ArrayBlockingQueue Class.

    import java.util.concurrent.ArrayBlockingQueue;

    public class GFG {

        public static void main(String[] args)
        {
            // Define capacity of ArrayBlockingQueue
            int capacity = 5;

            // Create object of ArrayBlockingQueue
            ArrayBlockingQueue<String> queue = new 
                          ArrayBlockingQueue<String>(capacity);

            // Add 5 elements to ArrayBlockingQueue
            queue.offer("User");
            queue.offer("Employee");
            queue.offer("Manager");
            queue.offer("Analyst");
            queue.offer("HR");

            // Create a array by calling toArray() method
            Object[] array = queue.toArray();

            // Print queue
            System.out.println("Queue is " + queue);

            // Print elements of array
            System.out.println("The array created by toArray() is:");
            for (Object i : array) {
                System.out.println(i);
            }
        }
    }
    ```

    **Output:**

    ```java
    Queue is [User, Employee, Manager, Analyst, HR]
    The array created by toArray() is:
    User
    Employee
    Manager
    Analyst
    HR

    ```

2.  **The toArray(*T[] arr*) method of [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/) class**:
    The toArray(*T[] a*) method of ArrayBlockingQueue class is used to create an array containing the same elements as that of this ArrayBlockingQueue, in proper sequence. It has an additional condition. The type of the returned array is the same as the specified array in the parameter if the queue size is less than or equal to the specified array. Otherwise, a new array is allocated with the type same as the specified array and size of the array is equal to the size of this queue. This method behaves as a bridge between array and collections.
    Suppose a queue is an ArrayBlockingQueue and it contains only strings. Then

    ```java
    String[] new_arr = queue.toArray(new String[0]);
    ```

    注意*到数组(新对象[0])* 与到数组()方法相同。

    **语法:**

    ```java
    public  T[] toArray(T[] a)
    ```

    **参数:**该方法取一个参数 *arr* ，如果队列足够大，那么它是一个数组，队列的所有元素都将被复制到这个数组中；否则，会为此分配一个相同运行时类型的新数组。

    **返回值:**该方法返回一个包含该队列中所有元素的数组。

    **异常:**方法可以抛出以下异常之一:

    *   *arraystorexception*:传递的数组类型不同，无法与队列的元素进行比较时。
    *   *空指针异常*:如果数组为空。

    下面的程序说明了 ArrayBlockingQueue 类的 Array(T[] a)方法:
    **程序 1:**

    ```java
    // Program Demonstrate how to apply toArray(T[] a) method
    // of ArrayBlockingQueue Class.

    import java.util.concurrent.ArrayBlockingQueue;

    public class GFG {

        public static void main(String[] args)
        {
            // Define capacity of ArrayBlockingQueue
            int capacity = 5;

            // Create object of ArrayBlockingQueue
            ArrayBlockingQueue<String> queue = new 
                     ArrayBlockingQueue<String>(capacity);

            // Add 5 elements to ArrayBlockingQueue
            queue.offer("User");
            queue.offer("Employee");
            queue.offer("Manager");
            queue.offer("Analyst");
            queue.offer("HR");

            // Creating the array
            String[] array = new String[5];

            // Calling toArray(T[] a) method
            Object[] ReturnArray = queue.toArray(array);

            // Print queue
            System.out.println("Queue is " + queue);

            // Print elements of array passed as parameter
            System.out.println();
            System.out.println("The array passed to toArray() is:");
            for (Object i : array) {
                System.out.println(i);
            }

            // Print elements of array retuned by method toArray()
            System.out.println();
            System.out.println("The array retuned by toArray() is:");
            for (Object i : ReturnArray) {
                System.out.println(i);
            }
        }
    }
    ```

    **Output:**

    ```java
    Queue is [User, Employee, Manager, Analyst, HR]

    The array passed to toArray() is:
    User
    Employee
    Manager
    Analyst
    HR

    The array retuned by toArray() is:
    User
    Employee
    Manager
    Analyst
    HR

    ```

**参考:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/arrayblockingqueue . html # to array](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#toArray--)
*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/arrayblockingqueue . html # to array-T:A](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ArrayBlockingQueue.html#toArray-T:A-)