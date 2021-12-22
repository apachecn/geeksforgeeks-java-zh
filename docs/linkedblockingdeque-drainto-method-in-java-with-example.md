# 用示例

链接 Java 中的 deblockingdequedrainto()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-drain to-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedblockingdeque-drainto-method-in-java-with-example/)

linkedblockingrequest 的 **drainTo(Collection col)** 方法从该 linkedblockingrequest 中移除所有可用元素，并将它们添加到作为参数传递的给定集合中。

### 排水(集合〔t0〕col)

LinkedBlockingDeque 的**drain to(Collection<E>col)**方法将从该查询中移除所有元素，并将它们添加到给定的集合 col 中。这是比重复轮询该查询更有效的方法。

在尝试从 deque 向集合 c 添加元素时也有可能遇到失败，并且由于该失败，当引发相关联的异常时，元素会分布在两个集合之间。如果一个 decue 试图将 drainTo()排到 decue 本身，那么将引发 IllegalArgumentException。如果在操作过程中修改了指定的集合，则此操作的行为是未定义的。因此，为了使用这样的方法，需要注意这种类型的情况来克服异常。

**语法:**

```java
public int drainTo(Collection<? super E> col)
```

**参数:**该方法接受一个参数**列**，该参数代表从 link edblockingrequest 转移元素的集合。

**返回值:**该方法返回从 deque 排入集合的元素数量。

**异常:**该方法抛出以下异常:

*   **取消支持操作异常**–如果集合无法添加元素。
*   **class castexception**–如果元素的类停止了向集合中添加元素的方法。
*   **空指针异常**–如果集合为空
*   **IllegalArgumentException**–如果方法的参数阻止它被添加到指定的集合中

下面的程序说明了 LinkedBlockingDeque 类的 drainTo()方法:

**程序 1:**

下面的程序有一个存储雇员对象的链接锁定请求。有一个数组列表，它将存储 linkedblockingrequest 中的所有员工对象。所以 drainTo()与 linkedblockingrequest 一起使用，将所有雇员从 deque 传递到 ArrayList。

```java
// Java Program Demonstrate drainTo(Collection c)
// method of LinkedBlockingDeque.

import java.util.ArrayList;
import java.util.concurrent.LinkedBlockingDeque;

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

        // define capacity of LinkedBlockingDeque
        int capacity = 50;

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Employee> linkedDeque
            = new LinkedBlockingDeque<Employee>(capacity);

        // create a ArrayList to pass as parameter to drainTo()
        ArrayList<Employee> collection
            = new ArrayList<Employee>();

        // add Employee object to deque
        Employee emp1 = new Employee("Aman", "Analyst", "24000");
        Employee emp2 = new Employee("Sachin", "Developer", "39000");
        linkedDeque.add(emp1);
        linkedDeque.add(emp2);

        // printing Arraylist and deque
        System.out.println("Before drainTo():");
        System.out.println("LinkedBlockingDeque : \n"
                           + linkedDeque.toString());
        System.out.println("ArrayList : \n"
                           + collection);

        // Apply drainTo method and pass collection as parameter
        int response = linkedDeque.drainTo(collection);

        // print no of element passed
        System.out.println("\nNo of element passed: "
                           + response);

        // printing Arraylist and deque
        // after applying drainTo() method
        System.out.println("\nAfter drainTo():");
        System.out.println("LinkedBlockingDeque : \n"
                           + linkedDeque.toString());
        System.out.println("ArrayList : \n"
                           + collection);
    }
}
```

**Output:**

```java
Before drainTo():
LinkedBlockingDeque : 
[Employee [name=Aman, position=Analyst, salary=24000], Employee [name=Sachin, position=Developer, salary=39000]]
ArrayList : 
[]

No of element passed: 2

After drainTo():
LinkedBlockingDeque : 
[]
ArrayList : 
[Employee [name=Aman, position=Analyst, salary=24000], Employee [name=Sachin, position=Developer, salary=39000]]

```

**程序 2:** 显示 drainTo()方法引发的异常的程序。

```java
// Java Program Demonstrate
// drainTo(Collection C)
// method of LinkedBlockingDeque.

import java.util.ArrayList;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingDeque
        int capacityOfDeque = 4;

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> linkedDeque
            = new LinkedBlockingDeque<Integer>(capacityOfDeque);

        // add elements to deque
        linkedDeque.put(85461);
        linkedDeque.put(44648);
        linkedDeque.put(45654);

        // create a collection with null
        ArrayList<Integer> add = null;

        // try to drain null deque to collection
        try {
            linkedDeque.drainTo(add);
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

**沥水(收藏<？super E > col，int maxElements)** 用于将在 drainTo()中作为整数传递的定数元传递给集合，集合也作为参数传递给方法。转移元素后，LinkedBlockingDeque 只有那些没有转移到集合的元素。该函数与上面的函数相同，只是在传递固定数量的元素时有一些限制。

**语法:**

```java
public int drainTo(Collection<E> col, int maxElements)
```

**参数:**该方法接受两个参数:

*   **列**–表示从 link edblockingrequest 转移元素的集合。
*   **maxElements**–这是整数类型，是指要传输到集合中的元素的最大数量。

**返回值:**该方法返回**元素的数量从**排到从德格收集。

**异常:**该方法抛出以下异常:

*   **取消支持操作异常**–如果集合无法添加元素。
*   **class castexception**-如果元素的类停止向集合中添加元素的方法。
*   **空指针异常**–如果集合为空
*   **IllegalArgumentException**–如果方法的参数阻止它被添加到指定的集合中

下面的程序说明了 LinkedBlockingDeque 类的 drainTo(Collection super E> col，int maxElements)方法

**程序 1:**

下面的程序有一个存储员工对象的链接锁定请求，还有一个存储链接锁定请求中所有员工对象的哈希集。所以 LinkedBlockingDeque 的 drainTo()用于将某个员工从 Deque 传递到 ArrayList。因此，没有要传输的元素作为参数在方法中传递。

```java
// Java program  to demonstrate drainTo()
// method of LinkedBlockingDeque.

import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {

    // create an Employee Object with
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
                + "position=" + position
                + ", salary=" + salary + "]";
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

        // define capacity of LinkedBlockingDeque
        int capacity = 10;

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Employee> linkedDeque
            = new LinkedBlockingDeque<Employee>(capacity);

        // create a HashSet to pass as parameter to drainTo()
        HashSet<Employee> collection
            = new HashSet<Employee>();

        // add Employee object to deque
        Employee emp1 = new Employee("Sachin",
                                     "Analyst",
                                     "40000");
        Employee emp2 = new Employee("Aman",
                                     "Developer",
                                     "69000");
        Employee emp3 = new Employee("Kajal",
                                     "Accountant",
                                     "39000");

        linkedDeque.add(emp1);
        linkedDeque.add(emp2);
        linkedDeque.add(emp3);

        // printing Arraylist and deque
        // before applying drainTo() method
        System.out.println("Before drainTo():");

        System.out.println("No of Elements in Deque is "
                           + linkedDeque.size());

        System.out.println("Elements in Deque is as follows");

        Iterator<Employee> listOfemp
            = linkedDeque.iterator();
        while (listOfemp.hasNext())
            System.out.println(listOfemp.next());

        System.out.println("No of Elements in HashSet is "
                           + collection.size());
        System.out.println("Elements in HashSet is as follows:");
        for (Employee emp : collection)
            System.out.println(emp);

        // Initialize no of element passed to collection
        // using drainTo() method
        int noOfElement = 2;

        // Apply drainTo method
        // and pass collection as parameter
        int response
            = linkedDeque.drainTo(collection, noOfElement);

        // print no of element passed
        System.out.println("\nNo of element passed: "
                           + response);

        // printing Arraylist and deque
        // after applying drainTo() method
        System.out.println("\nAfter drainTo():");
        System.out.println("No of Elements in Deque is "
                           + linkedDeque.size());
        System.out.println("Elements in Deque is as follows");
        listOfemp = linkedDeque.iterator();
        while (listOfemp.hasNext())
            System.out.println(listOfemp.next());

        System.out.println("No of Elements in HashSet is "
                           + collection.size());
        System.out.println("Elements in HashSet is as follows:");
        for (Employee emp : collection)
            System.out.println(emp);
    }
}
```

**Output:**

```java
Before drainTo():
No of Elements in Deque is 3
Elements in Deque is as follows
Employee [name=Sachin, position=Analyst, salary=40000]
Employee [name=Aman, position=Developer, salary=69000]
Employee [name=Kajal, position=Accountant, salary=39000]
No of Elements in HashSet is 0
Elements in HashSet is as follows:

No of element passed: 2

After drainTo():
No of Elements in Deque is 1
Elements in Deque is as follows
Employee [name=Kajal, position=Accountant, salary=39000]
No of Elements in HashSet is 2
Elements in HashSet is as follows:
Employee [name=Sachin, position=Analyst, salary=40000]
Employee [name=Aman, position=Developer, salary=69000]

```