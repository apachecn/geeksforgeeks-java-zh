# Java 中 LinkedBlockingQueue remaingccapacity()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-remainingcapacity-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-remainingcapacity-method-in-java/)

LinkedBlockingQueue 的 **remainingCapacity()** 方法返回可以添加到 LinkedBlockingQueue 而不阻塞的更多元素的数量。
返还的容量出现三种情况:

*   如果剩余容量为零，则不能向链接锁定队列添加更多元素。
*   如果 LinkedBlockingQueue 的剩余容量等于队列的大小，则不能从队列中删除任何元素，因为在这种情况下，队列是空的。
*   在任何其他情况下，容量始终等于此链接锁定队列的初始容量和此链接锁定队列的当前大小之间的差值。

**语法:**

```
public int remainingCapacity()
```

**返回值:**该方法返回链路阻塞队列的**剩余容量**。

下面的程序说明了 LinkedBlockingQueue 类的 remainingCapacity()方法:

**程序 1:** 使用 remaining Capacity()方法返回 LinkedBlockingQueue 的剩余容量，其中 LinkedBlockingQueue 包含名称列表。

```
// Java Program Demonstrate remainingCapacity()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 7;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        linkedQueue.add("John");
        linkedQueue.add("Tom");
        linkedQueue.add("Clark");
        linkedQueue.add("Kat");

        // find remaining Capacity  of linkedQueue
        // using remainingCapacity() method
        int remainingCapacity = linkedQueue.remainingCapacity();

        // print result
        System.out.println("Queue is " + linkedQueue);

        // print head of queue
        System.out.println("Remaining Capacity of Queue is "
                           + remainingCapacity);
    }
}
```

**Output:**

```
Queue is [John, Tom, Clark, Kat]
Remaining Capacity of Queue is 3

```

**程序 2:** 查找包含员工列表的链接锁定队列的剩余容量。

```
// Java Program Demonstrate peek()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
public class GFG {

    public void findPeek()
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 7;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Ravi", "Tester", "39000");
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000");

        // Add Employee Objects to linkedQueue
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);

        // add element and find remaining capacity
        // follow same process again
        // until the queue becomes full

        while (linkedQueue.size() != 7) {

            // adding emp2 again and again to queue
            System.out.println("Adding employee is success "
                               + linkedQueue.offer(emp2));

            // find remaining capacity of linkedQueue
            // using remainingCapacity() method
            int remain = linkedQueue.remainingCapacity();

            // print remaining capacity  value
            System.out.println("Remaining Capacity of list :"
                               + remain);
        }
    }

    // create an Employee Object with name,
    // position and salary as an attribute
    public class Employee {

        public String name;
        public String position;
        public String salary;
        Employee(String name, String position, String salary)
        {
            this.name = name;
            this.position = position;
            this.salary = salary;
        }
        @Override
        public String toString()
        {
            return "Employee [name=" + name + ", position="
                + position + ", salary=" + salary + "]";
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

**Output:**

```
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

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # remainingCapacity–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#remainingCapacity--)