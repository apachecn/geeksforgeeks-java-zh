# Java 中的 BlockingQueue remove()方法，示例

> 原文:[https://www . geesforgeks . org/blockingqueue-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingqueue-remove-method-in-java-with-examples/)

**阻塞队列**的**移除(对象对象)**方法仅从该阻塞队列中移除给定对象的一个实例(作为参数传递，如果它存在的话)。如果这个队列包含一个或多个元素 e 的实例，这个方法返回真，如果这个队列包含现在从阻塞队列中删除的元素。

**语法:**

```
public boolean remove(Object o)
```

**参数:**该方法接受一个强制参数**对象**，它是要从阻塞队列中删除的元素。

**返回值:**如果该队列包含现在从阻塞队列中删除的元素，则该方法返回*真*。如果阻塞队列不包含元素*对象*，则该方法返回*假*。

**注**:**blocking Queue**的 **remove()** 方法继承了 Java 中的 **Queue** 类。

下面的程序说明了阻塞队列类的移除方法:

**程序 1:**

```
// Java Program Demonstrate  remove(Object obj)
// method of BlockingQueue

import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 4;

        // create object of BlockingQueue
        BlockingQueue<String> BQ
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add element using put() method
        BQ.put("Karan");
        BQ.put("Suraj");
        BQ.put("Harsh");
        BQ.put("Rahul");

        // print elements of queue
        System.out.println("Items in Queue are " + BQ);

        // try to remove Karan from Queue using remove()
        boolean try1 = BQ.remove("Karan");
        // Print result of remove()
        System.out.println("String name Karan is removed :"
                           + try1);

        // try to remove Sunny from Queue using remove()
        boolean try2 = BQ.remove("Sunny");
        // Print result of remove()
        System.out.println("String name Sunny is removed :"
                           + try2);

        // try to remove Sunny from Queue using remove()
        boolean try3 = BQ.remove("Harsh");
        // Print result of remove()
        System.out.println("String name Harsh is removed :"
                           + try2);

        // print queue
        System.out.println("After Removing Some Elements:");
        System.out.println("Items in Queue are " + BQ);
    }
}
```

**输出:**

```
Items in Queue are [Karan, Suraj, Harsh, Rahul]
String name Karan is removed :true
String name Sunny is removed :false
String name Harsh is removed :false
After Removing Some Elements:
Items in Queue are [Suraj, Rahul]

```

**程序 1:**

```
// Java Program Demonstrate remove(object obj)
// method of BlockingQueue

import java.util.Iterator;
import java.util.concurrent.LinkedBlockingQueue;
import java.util.concurrent.BlockingQueue;
public class GFG {

    public void removeDemo() throws InterruptedException
    {
        // define capacity of BlockingQueue
        int capacityOfQueue = 5;

        // create object of BlockingQueue
        BlockingQueue<Employee> BQ
            = new LinkedBlockingQueue<Employee>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        Employee emp1 = new Employee("Ranjeet", "Tester", "29000", 27);
        Employee emp2 = new Employee("Sanjeet", "Manager", "98000", 34);
        Employee emp3 = new Employee("Karan", "Analyst", "44000", 30);

        // Add Employee Objects to BQ Using put(E e)
        BQ.put(emp1);
        BQ.put(emp2);
        BQ.put(emp3);

        // print details of BQ
        System.out.println("Before removing Elements");
        Iterator itr = BQ.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());

        // remove employee2 name Sanjeet from BQ
        // Using remove(Object obj) method
        BQ.remove(emp2);

        // Also remove Ranjeet employee1 from BQ
        // Using remove(Object obj) method
        BQ.remove(emp1);

        // print details of BQ
        System.out.println("After removing Some Elements");
        itr = BQ.iterator();
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

**输出:**

```
Before removing Elements
Employee [name=Ranjeet, position=Tester, salary=29000, Age=27]
Employee [name=Sanjeet, position=Manager, salary=98000, Age=34]
Employee [name=Karan, position=Analyst, salary=44000, Age=30]
After removing Some Elements
Employee [name=Karan, position=Analyst, salary=44000, Age=30]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/blockingqueue . html # remove(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html#remove(java.lang.Object))