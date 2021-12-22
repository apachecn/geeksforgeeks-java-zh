# Java 中 ArrayBlockingQueue take()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-take-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-take-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它会有一个固定的大小，你**可以不**存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

take()方法用于检索和删除该队列的头。如果队列是空的，那么它将等待直到一个元素变得可用。

**语法:**

```
public E take()throws InterruptedException
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回该队列头部的值。

**异常:**如果在等待时被中断，该方法将抛出*中断异常*。

下面的程序说明了 ArrayBlockingQueue 的 take()方法:
**程序 1** :

```
// Program to demonstrate take() method of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

public static void main(String[] args) 
                  throws InterruptedException{
    // Define capacity of ArrayBlockingQueue
    int capacity = 5;

    // Create object of ArrayBlockingQueue
    ArrayBlockingQueue<Integer> queue = 
        new ArrayBlockingQueue<Integer>(capacity);

    // Add elements to ArrayBlockingQueue
    queue.add(23);
    queue.add(32);
    queue.add(45);
    queue.add(12);

    // Print queue after adding numbers
    System.out.print("After addding numbers Queue: "
                                                +queue);

        // Apply take() method
    int head=queue.take();

    // Print head of queue using take() method
    System.out.println("Head of queue removed is "
                                                +head);
    System.out.print("After removing head. Queue: ");
    System.out.println(queue);

    // Apply take() method
    head = queue.take();

    // Print head of queue using take() method
    System.out.println("Head of queue removed is " 
                                               + head);
    System.out.print("After removing head. Queue: ");
    System.out.println(queue);

} 
}
```

**Output:**

```
After addding numbers Queue: [23, 32, 45, 12]Head of queue removed is 23
After removing head. Queue: [32, 45, 12]
Head of queue removed is 32
After removing head. Queue: [45, 12]

```

**程序 2:**

```
// Program to demonstrate take() method of ArrayBlockingQueue

import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    // Create a User Object with name 
    // and age as the attribute
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
                        throws InterruptedException
    {
        GFG gfg = new GFG();
        gfg.takeMethodExample();
    }

    // Method to give example of take function
    public void takeMethodExample() 
                        throws InterruptedException
    {

        // define capacity of ArrayBlockingQueue
        int capacity = 5;

        // create object of ArrayBlockingQueue
        ArrayBlockingQueue<User> queue = 
               new ArrayBlockingQueue<User>(capacity);

        // create user objects
        User user1 = new User("Aman", "24");
        User user2 = new User("Amar", "23");
        User user3 = new User("Sanjeet", "25");
        User user4 = new User("Suvo", "26");
        User user5 = new User("Ravi", "22");

        // Add Objects to ArrayBlockingQueue
        queue.offer(user1);
        queue.offer(user2);
        queue.offer(user3);
        queue.offer(user4);
        queue.offer(user5);

        // find take() of queue
        User head = queue.take();

        // print head
        System.out.println("Details of User Removed"
                    +" After Applying take() Method");
        System.out.println("User Name : " + head.name);
        System.out.println("User Age : " + head.age);

        // find take() of queue
        head = queue.take();

        // print head
        System.out.println("Details of User Removed"+
                      " After Applying take() Method");
        System.out.println("User Name : " + head.name);
        System.out.println("User Age : " + head.age);
    }
}
```

**Output:**

```
Details of User Removed After Applying take() Method
User Name : Aman
User Age : 24
Details of User Removed After Applying take() Method
User Name : Amar
User Age : 23

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # take()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ArrayBlockingQueue.html#take())