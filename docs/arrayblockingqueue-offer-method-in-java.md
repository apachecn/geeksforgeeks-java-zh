# Java 中 ArrayBlockingQueue offer()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-offer-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-offer-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它将有一个固定的大小，你不能存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

根据传递给它的参数，有两种类型的 offer()方法:

1.  The **offer(E *element*)** method **inserts the element passed as parameter** to method at the tail of this queue(ArrayBlockingQueue), if queue is not full. It returns true when the operation of addition is successful and false if this queue is full. This method is preferred over add() method because add method throws error when queue is full but offer() method returns false in such situation.
    **Syntax:**

    ```
    public boolean offer(E e)
    ```

    **参数:**该方法取一个参数，*元素*。这是指要添加到队列中的元素。

    **返回值:**当加法运算成功时，该方法返回*真*，如果该队列已满，则返回假。

    **异常**如果指定的元素为空，该方法抛出*空指针异常*。

    下面的程序说明了数组锁定队列的提供(E 元素)方法:
    **程序 1:**

    ```
    // Demonstrating offer(E element) method of ArrayBlockingQueue

    import java.util.concurrent.ArrayBlockingQueue;

    public class GFG {

    public static void main(String[] args) {
        // Define capacity of ArrayBlockingQueue
        int capacity = 5;

        // Create object of ArrayBlockingQueue
        ArrayBlockingQueue<Integer> queue = 
              new ArrayBlockingQueue<Integer>(capacity);

        // Add 5 elements to ArrayBlockingQueue
        System.out.println("adding 423: "+queue.offer(423));
        System.out.println("adding 243: "+queue.offer(243));
        System.out.println("adding 237: "+queue.offer(237));
        System.out.println("adding 867: "+queue.offer(867));
        System.out.println("adding 23: "+queue.offer(23));

        // Check whether queue is full or not
        if(queue.remainingCapacity()==0) {
            System.out.println("queue is full");
            System.out.println("queue contains "+queue);
        }else {
            System.out.println("queue is not full");
            System.out.println("queue contains "+queue);
        }

        // Try to add more elements
        System.out.println("adding 123: "+queue.offer(123));
        System.out.println("adding 321: "+queue.offer(321));

    } 
    }
    ```

    **Output:**

    ```
    adding 423: true
    adding 243: true
    adding 237: true
    adding 867: true
    adding 23: true
    queue is full
    queue contains [423, 243, 237, 867, 23]
    adding 123: false
    adding 321: false

    ```

    **程序 2:**

    ```
    // Program Demonstrate offer(E e) method of ArrayBlockingQueue

    import java.util.concurrent.ArrayBlockingQueue;

    public class GFG {

        // create a User Object with name and age as an attribute
        public class User {

            public String name;
            public String age;
            User(String name, String age)
            {
                this.name = name;
                this.age = age;
            }
        }

        // Main Method
        public static void main(String[] args)
        {
            GFG gfg = new GFG();
            gfg.offerExample();
        }

        // Method to give example of contains function
        public void offerExample()
        {

            // Define the capacity of ArrayBlockingQueue
            int capacity = 5;

            // Create object of ArrayBlockingQueue
            ArrayBlockingQueue<User> queue = 
                    new ArrayBlockingQueue<User>(capacity);

            // Create user objects
            User user1 = new User("Aman", "24");
            User user2 = new User("Amar", "23");
            User user3 = new User("Sanjeet", "25");
            User user4 = new User("Suvo", "26");
            User user5 = new User("Ravi", "22");

            // Add Objects to ArrayBlockingQueue
            System.out.println("adding user having name = "
                    + user1.name + ": " + queue.offer(user1));
            System.out.println("adding user having name = "
                    + user2.name + ": " + queue.offer(user2));
            System.out.println("adding user having name = "
                    + user3.name + ": " + queue.offer(user3));
            System.out.println("adding user having name = "
                    + user4.name + ": " + queue.offer(user4));
            System.out.println("adding user having name = "
                    + user5.name + ": " + queue.offer(user5));

            // Check whether the queue is full or not
            if (queue.remainingCapacity() == 0) {
                System.out.println("queue is full");
            }
            else {
                System.out.println("queue is not full");
            }

            // Create more user objects
            User user6 = new User("Ram", "20");
            User user7 = new User("Mohan", "27");

            // Add users in queue
            System.out.println("adding user having name = "
                    + user6.name + ": " + queue.offer(user6));
            System.out.println("adding user having name = "
                    + user7.name + ": " + queue.offer(user7));
        }
    }
    ```

    **Output:**

    ```
    adding user having name = Aman: true
    adding user having name = Amar: true
    adding user having name = Sanjeet: true
    adding user having name = Suvo: true
    adding user having name = Ravi: true
    queue is full
    adding user having name = Ram: false
    adding user having name = Mohan: false

    ```

2.  The **offer(*E element, long timeout, TimeUnit unit*)** method **inserts the element passed as parameter** to method at the tail of this queue(ArrayBlockingQueue) if queue is not full. It will **wait till a specified time for space to become available if the queue is full**. It returns true when the operation of addition is successful and false if this queue is full and the specified waiting time elapses before space is available. This method is useful when we want to wait for the queue to remove its element and when the queue is not full the element will be added to the queue but we can wait for a specific time and this time can be defined by us.

    **语法:**

    ```
    public boolean offer(E e, long timeout, TimeUnit unit) throws InterruptedException
    ```

    **参数:**该方法取三个参数:

    *   *元素*(对象)-队列中要添加的元素。
    *   *超时*(长)-放弃前等待的时间，单位为单位。
    *   *单位*(时间单位)-决定如何解释超时参数的时间单位。

    **返回值:**当添加方法成功时，该方法返回 True，如果在空间可用之前经过了指定的等待时间，则返回 false。

    **异常:**该方法抛出两种类型的异常:

    *   *中断异常*–如果在等待时中断。
    *   *NullPointRexception*–如果指定的元素为空。

    下面的程序说明了数组锁定队列的提供(E 元素，长超时，时间单位单位)方法:

    ```
    // Program Demonstrate offer(E e, long timeout, TimeUnit unit)
    // method of ArrayBlockingQueue

    import java.util.concurrent.ArrayBlockingQueue;
    import java.util.concurrent.TimeUnit;

    public class GFG {

        public static void main(String[] args) 
                      throws InterruptedException
        {
            // Define capacity of ArrayBlockingQueue
            int capacity = 5;

            // Create object of ArrayBlockingQueue
            ArrayBlockingQueue<Integer> queue = 
                new ArrayBlockingQueue<Integer>(capacity);

            // Add 5 elements to ArrayBlockingQueue having
            // Timeout in seconds with value 10 secs
            System.out.println("adding 423: " + 
                  queue.offer(433, 10, TimeUnit.SECONDS));
            System.out.println("adding 456: " + 
                  queue.offer(456, 10, TimeUnit.SECONDS));
            System.out.println("adding 987: " + 
                  queue.offer(987, 10, TimeUnit.SECONDS));
            System.out.println("adding 578: " + 
                  queue.offer(578, 10, TimeUnit.SECONDS));
            System.out.println("adding 852: " + 
                  queue.offer(852, 10, TimeUnit.SECONDS));

            // Check whether queue is full or not
            if (queue.remainingCapacity() == 0) {
                System.out.println("queue is full");
                System.out.println("queue contains " + queue);
            }
            else {
                System.out.println("queue is not full");
                System.out.println("queue contains " + queue);
            }

            // Try to add more elements
            System.out.println("adding 546: " + 
                      queue.offer(546, 10, TimeUnit.SECONDS));
        }
    }
    ```

    **Output:**

    ```
    adding 423: true
    adding 456: true
    adding 987: true
    adding 578: true
    adding 852: true
    queue is full
    queue contains [433, 456, 987, 578, 852]
    adding 546: false

    ```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # offer(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#offer(E))