# Java 中的 LinkedBlockingQueue remove()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-remove-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-remove-method-in-java/)

LinkedBlockingQueue 的 **remove(Object obj)** 方法只从该 LinkedBlockingQueue 中移除给定对象的一个实例(作为参数传递)，如果它存在的话。如果这个队列包含一个或多个元素 e 的实例，这个方法返回真，如果这个队列包含现在从 LinkedBlockingQueue 中删除的元素。

**语法:**

```java
public boolean remove(Object o)
```

**参数:**该方法接受一个强制参数**对象**，它是要从 LinkedBlockingQueue 中删除的元素。

**返回值:**如果该队列包含现在从 LinkedBlockingQueue 中移除的元素，则该方法返回 *true* 。如果链接锁定队列不包含元素*对象*，则该方法返回*假*。

下面的程序说明了 LinkedBlockingQueue 类的移除(对象对象)方法:

**程序 1:** 尝试使用 remove(Object obj)从 LinkedBlockingQueue 中移除一些元素并打印结果。

```java
// Java Program Demonstrate  remove(Object obj)
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element using put() method
        linkedQueue.put("Karan");
        linkedQueue.put("Suraj");
        linkedQueue.put("Harsh");
        linkedQueue.put("Rahul");

        // print elements of queue
        System.out.println("Items in Queue are " + linkedQueue);

        // try to remove Karan from Queue using remove()
        boolean try1 = linkedQueue.remove("Karan");
        // Print result of remove()
        System.out.println("String name Karan is removed :"
                           + try1);

        // try to remove Sunny from Queue using remove()
        boolean try2 = linkedQueue.remove("Sunny");
        // Print result of remove()
        System.out.println("String name Sunny is removed :"
                           + try2);

        // try to remove Sunny from Queue using remove()
        boolean try3 = linkedQueue.remove("Harsh");
        // Print result of remove()
        System.out.println("String name Harsh is removed :"
                           + try2);

        // print queue
        System.out.println("After Removing Some Elements:");
        System.out.println("Items in Queue are " + linkedQueue);
    }
}
```

**输出:**

```java
Items in Queue are [Karan, Suraj, Harsh, Rahul]
String name Karan is removed :true
String name Sunny is removed :false
String name Harsh is removed :false
After Removing Some Elements:
Items in Queue are [Suraj, Rahul]

```

**程序 1:** 使用 LinkedBlockingQueue

```java
// Java Program Demonstrate remove(object obj)
// method of LinkedBlockingQueue

import java.util.Iterator;
import java.util.concurrent.LinkedBlockingQueue;
public class GFG {

    public void removeDemo() throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 5;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Ranjeet", "Tester", "29000", 27);
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000", 34);
        Employee emp3 = new Employee("Karan", "Analyst", "44000", 30);

        // Add Employee Objects to linkedQueue Using put(E e)
        linkedQueue.put(emp1);
        linkedQueue.put(emp2);
        linkedQueue.put(emp3);

        // print details of linkedQueue
        System.out.println("Before removing Elements");
        Iterator itr = linkedQueue.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());

        // remove employee2 name Sanjeet from linkedQueue
        // Using remove(Object obj) method
        linkedQueue.remove(emp2);

        // Also remove Ranjeet employee1 from linkedQueue
        // Using remove(Object obj) method
        linkedQueue.remove(emp1);

        // print details of linkedQueue
        System.out.println("After removing Some Elements");
        itr = linkedQueue.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());
    }

    // create an Employee Object with name,
    // position, salary and age as attributes
    public class Employee {

        public String name;
        public String position;
        public String salary;
        public int Age;
        Employee(String name, String position,
                 String salary, int age)
        {
            this.name = name;
            this.position = position;
            this.salary = salary;
            this.Age = age;
        }

        @Override
        public String toString()
        {
            return "Employee [name=" + name + ", position="
                + position + ", salary=" + salary + ", Age=" + Age + "]";
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        try {
            gfg.removeDemo();
        }
        catch (InterruptedException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
}
```

**中的 remove(Object obj)方法移除 Employee 对象输出:**

```java
Before removing Elements
Employee [name=Ranjeet, position=Tester, salary=29000, Age=27]
Employee [name=Sanjeet, position=Manager, salary=98000, Age=34]
Employee [name=Karan, position=Analyst, salary=44000, Age=30]
After removing Some Elements
Employee [name=Karan, position=Analyst, salary=44000, Age=30]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # remove-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#remove-java.lang.Object-)