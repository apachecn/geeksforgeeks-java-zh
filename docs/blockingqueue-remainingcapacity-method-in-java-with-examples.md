# Java 中的 BlockingQueue remainingCapacity()方法，带示例

> 原文:[https://www . geeksforgeeks . org/blocking queue-remainingcapacity-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-remainingcapacity-method-in-java-with-examples/)

[**【封锁队列】**](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/) 的 **remainingCapacity()** 方法返回可以添加到封锁队列而不被封锁的更多元素的数量。

返回的容量出现在三种情况下:

*   If the remaining capacity is zero, no more elements can be added to the blocking queue.
*   If the remaining capacity of the blocked queue is equal to the size of the queue, you cannot delete any elements from the queue, because the queue is empty in this case.
*   In any other case, the capacity is always equal to the difference between the initial capacity of the blocking queue and the current size of the blocking queue.

**语法:**

```java
public int remainingCapacity()
```

**返回值:**该方法返回阻塞队列的**剩余容量**。

**注**:**封锁队列**的 **remainingCapacity()** 方法继承了 Java 中的**队列**类。

下面的程序说明了阻塞队列类的 remainingCapacity()方法:

**程序 1:**

```java
// Java Program Demonstrate remainingCapacity()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 7;

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>(
                capacityOfQueue);

        // Add element to BlockingQueue
        BQ.add("John");
        BQ.add("Tom");
        BQ.add("Clark");
        BQ.add("Kat");

        // find remaining Capacity  of BQ
        // using remainingCapacity() method
        int remainingCapacity
            = BQ.remainingCapacity();

        // print result
        System.out.println("Queue is " + BQ);

        // print head of the queue
        System.out.println("Remaining Capacity of Queue is "
                           + remainingCapacity);
    }
}
```

**输出:**

```java
Queue is [John, Tom, Clark, Kat]
Remaining Capacity of Queue is 3

```

**程序二:**

```java
// Java Program Demonstrate remainingCapacity()
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
public class GFG {

    public void findPeek()
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 7;

        // create object of BlockingQueue
        BlockingQueue<Employee> BQ
            = new LinkedBlockingQueue<Employee>(
                capacityOfQueue);

        // Add element to BlockingQueue
        Employee emp1
            = new Employee("Ravi", "Tester", "39000");
        Employee emp2
            = new Employee("Sanjeet", "Manager", "98000");

        // Add Employee Objects to BQ
        BQ.add(emp1);
        BQ.add(emp2);

        // add element and find remaining capacity
        // follow same process again
        // until the queue becomes full
        while (BQ.size() != 7) {

            // adding emp2 again and again to queue
            System.out.println(
                "Adding employee is success "
                + BQ.offer(emp2));

            // find remaining capacity of BQ
            // using remainingCapacity() method
            int remain = BQ.remainingCapacity();

            // print remaining capacity  value
            System.out.println(
                "Remaining Capacity of list :"
                + remain);
        }
    }

    // create an Employee Object with name,
    // position and salary as an attribute
    public class Employee {

        public String name;
        public String position;
        public String salary;
        Employee(String name,
                 String position,
                 String salary)
        {
            this.name = name;
            this.position = position;
            this.salary = salary;
        }
        @Override
        public String toString()
        {
            return "Employee [name=" + name
                + ", position="
                + position + ", salary="
                + salary + "]";
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.findPeek();
    }
}
```

**输出:**

```java
Adding employee is success true
Remaining Capacity of list :4
Adding employee is success true
Remaining Capacity of list :3
Adding employee is success true
Remaining Capacity of list :2
Adding employee is success true
Remaining Capacity of list :1
Adding employee is success true
Remaining Capacity of list :0

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingqueue . html # remainingCapacity()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#remainingCapacity())