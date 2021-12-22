# Java 中的 LinkedBlockingQueue drainTo()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-drain to-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-drainto-method-in-java/)

LinkedBlocking Queue 的 **drainTo(Collection col)** 方法从该 LinkedBlockingQueue 中移除所有可用元素，并将它们添加到作为参数传递的给定集合中。

### 排水(集合〔t0〕col)

**排水(收集<？LinkedBlockingQueue 的 super E > col)** 方法从这个队列中移除所有元素，并将它们添加到给定的集合 col 中，这是一种比重复轮询这个队列更有效的方法。
尝试从队列中向集合 c 添加元素时也可能遇到失败，并且由于该失败，当引发相关异常时，元素会在两个集合之间分布。如果一个队列试图将 drainTo()排入队列本身，那么将引发 IllegalArgumentException。如果在操作过程中修改了指定的集合，则此操作的行为未定义。因此，为了使用这样的方法，需要注意这种类型的情况来克服异常。
**语法:**

```java
public int drainTo(Collection<? super E> col)
```

**参数:**该方法接受一个参数**列**，该参数代表从 LinkedBlockingQueue 传输元素的集合。
**返回值:**该方法返回从队列中排入集合的元素数量。
**异常:**该方法抛出以下异常:

*   **取消支持操作异常**–如果集合无法添加元素。
*   **class castexception**–如果元素的类停止了向集合中添加元素的方法。
*   **空指针异常**–如果集合为空
*   **IllegalArgumentException**–如果方法的参数阻止它被添加到指定的集合中

下面的程序说明了 LinkedBlockingQueue 类的 drainTo()方法:
**程序 1:**
下面的程序有一个存储 Employee 对象的 LinkedBlockingQueue。有一个数组列表，它将存储 LinkedBlockingQueue 中的所有员工对象。因此 drainTo()与 LinkedBlockingQueue 一起使用，将所有员工从队列传递到数组列表。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate drainTo(Collection c)
// method of LinkedBlockingQueue.

import java.util.ArrayList;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    // create a Employee Object with
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
        gfg.containsMethodExample();
    }

    public void containsMethodExample()
    {

        // define capacity of LinkedBlockingQueue
        int capacity = 50;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacity);

        // create a ArrayList to pass as parameter to drainTo()
        ArrayList<Employee> collection = new ArrayList<Employee>();

        // add Employee object to queue
        Employee emp1 = new Employee("Aman", "Analyst", "24000");
        Employee emp2 = new Employee("Sachin", "Developer", "39000");
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);

        // printing Arraylist and queue
        System.out.println("Before drainTo():");
        System.out.println("LinkedBlockingQueue : \n"
                           + linkedQueue.toString());
        System.out.println("ArrayList : \n"
                           + collection);

        // Apply drainTo method and pass collection as parameter
        int response = linkedQueue.drainTo(collection);

        // print no of element passed
        System.out.println("\nNo of element passed: " + response);

        // printing Arraylist and queue after applying drainTo() method
        System.out.println("\nAfter drainTo():");
        System.out.println("LinkedBlockingQueue : \n"
                           + linkedQueue.toString());
        System.out.println("ArrayList : \n"
                           + collection);
    }
}
```

**Output:** 

```java
Before drainTo():
LinkedBlockingQueue : 
[Employee [name=Aman, position=Analyst, salary=24000],
 Employee [name=Sachin, position=Developer, salary=39000]]
ArrayList : 
[]

No of element passed: 2

After drainTo():
LinkedBlockingQueue : 
[]
ArrayList : 
[Employee [name=Aman, position=Analyst, salary=24000], Employee [name=Sachin, position=Developer, salary=39000]]
```

**程序 2:** 显示 drainTo()方法引发的异常的程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate
// drainTo(Collection C)
// method of LinkedBlockingQueue.

import java.util.ArrayList;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer>
            linkedQueue = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // add elements to queue
        linkedQueue.put(85461);
        linkedQueue.put(44648);
        linkedQueue.put(45654);

        // create a collection with null
        ArrayList<Integer> add = null;

        // try to drain null queue to collection
        try {
            linkedQueue.drainTo(add);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```java
Exception: java.lang.NullPointerException
```

### 排水(集合 super E> col，int maxElements)

**排水(收集<？super E > col，int maxElements)** 用于将在 drainTo()中作为整数传递的定数元传递给集合，集合也作为参数传递给方法。传输元素后，LinkedBlockingQueue 只有那些没有传输到集合的元素。该函数与上面的函数相同，只是在传递固定数量的元素时有一些限制。
**语法:**

```java
public int drainTo(Collection<? super E> col, int maxElements)
```

**参数:**该方法接受两个参数:

*   **列**–表示从 LinkedBlockingQueue 传输元素的集合。
*   **maxElements**–这是整数类型，是指要传输到集合中的元素的最大数量。

**返回值:**该方法从队列中返回要收集的**元素数量。
**异常:**此方法抛出以下异常:**

*   **取消支持操作异常**–如果集合无法添加元素。
*   **class castexception**-如果元素的类停止向集合中添加元素的方法。
*   **空指针异常**–如果集合为空
*   **IllegalArgumentException**–如果方法的参数阻止它被添加到指定的集合中

下面的程序说明了 LinkedBlockingQueue 类
**的 drainTo(Collection super E> col，int maxElements)方法程序 1:**
下面的程序有一个存储 employee 对象的 LinkedBlockingQueue，还有一个存储 LinkedBlockingQueue 中所有 Employee 对象的 HashSet。所以 LinkedBlockingQueue 的 drainTo()用于将某个员工从队列传递到数组列表。因此，没有要传输的元素作为参数在方法中传递。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program  to demonstrate drainTo()
// method of LinkedBlockingQueue.

import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    // create a Employee Object with
    // position and salary as attribute
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
            return "Employee [name=" + name + ", "
                + "position=" + position + ", salary=" + salary + "]";
        }
    }

    // Main Method
    public static void main(String[] args)
    {
        GFG gfg = new GFG();
        gfg.containsMethodExample();
    }

    public void containsMethodExample()
    {

        // define capacity of LinkedBlockingQueue
        int capacity = 10;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacity);

        // create a HashSet to pass as parameter to drainTo()
        HashSet<Employee> collection = new HashSet<Employee>();

        // add Employee object to queue
        Employee emp1 = new Employee("Sachin", "Analyst", "40000");
        Employee emp2 = new Employee("Aman", "Developer", "69000");
        Employee emp3 = new Employee("Kajal", "Accountant", "39000");
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);
        linkedQueue.add(emp3);

        // printing Arraylist and queue before applying drainTo() method
        System.out.println("Before drainTo():");
        System.out.println("No of Elements in Queue is " + linkedQueue.size());
        System.out.println("Elements in Queue is as follows");
        Iterator<Employee> listOfemp = linkedQueue.iterator();
        while (listOfemp.hasNext())
            System.out.println(listOfemp.next());

        System.out.println("No of Elements in HashSet is " + collection.size());
        System.out.println("Elements in HashSet is as follows:");
        for (Employee emp : collection)
            System.out.println(emp);

        // Initialize no of element passed to collection
        // using drainTo() method
        int noOfElement = 2;

        // Apply drainTo method and pass collection as parameter
        int response = linkedQueue.drainTo(collection, noOfElement);

        // print no of element passed
        System.out.println("\nNo of element passed: " + response);

        // printing Arraylist and queue after applying drainTo() method
        System.out.println("\nAfter drainTo():");
        System.out.println("No of Elements in Queue is " + linkedQueue.size());
        System.out.println("Elements in Queue is as follows");
        listOfemp = linkedQueue.iterator();
        while (listOfemp.hasNext())
            System.out.println(listOfemp.next());

        System.out.println("No of Elements in HashSet is " + collection.size());
        System.out.println("Elements in HashSet is as follows:");
        for (Employee emp : collection)
            System.out.println(emp);
    }
}
```

**Output:** 

```java
Before drainTo():
No of Elements in Queue is 3
Elements in Queue is as follows
Employee [name=Sachin, position=Analyst, salary=40000]
Employee [name=Aman, position=Developer, salary=69000]
Employee [name=Kajal, position=Accountant, salary=39000]
No of Elements in HashSet is 0
Elements in HashSet is as follows:

No of element passed: 2

After drainTo():
No of Elements in Queue is 1
Elements in Queue is as follows
Employee [name=Kajal, position=Accountant, salary=39000]
No of Elements in HashSet is 2
Elements in HashSet is as follows:
Employee [name=Sachin, position=Analyst, salary=40000]
Employee [name=Aman, position=Developer, salary=69000]
```

**参考:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # Drainto-Java . util . collection-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#drainTo-java.util.Collection-)
*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # Drainto-Java . util . collection-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#drainTo-java.util.Collection-int-)