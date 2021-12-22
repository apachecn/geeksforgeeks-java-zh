# Java 中 LinkedBlockingQueue toString()方法示例

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedblockingqueue-tostring-method-in-java-with-examples/)

**LinkedBlockingQueue** 的 **toString()** 方法返回 LinkedBlockingQueue 元素的字符串表示。LinkedBlockingQueue 的字符串包含从第一个(头)到最后一个(尾)的元素，以适当的顺序放在方括号(“[]”)中。元素由字符“，”分隔(逗号和空格)。所以基本上 toString()方法用于将 LinkedBlockingQueue 的所有元素转换成字符串表示形式。

此方法覆盖类**抽象集合<E>T1 中的 toString()**

**语法:**

```
public String toString()
```

**返回值:**这个方法返回一个 String，它是 LinkedBlockingQueue 元素从第一个(头)到最后一个(尾)的表示，以适当的顺序用方括号(“[]”)括起来，用“，”(逗号和空格)分隔。

下面的程序说明了 LinkedBlockingQueue 类的 toString()方法:

**程序 1:**

```
// Java Program Demonstrate toString()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 50;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer> linkedQueue
            = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        linkedQueue.add(2300);
        linkedQueue.add(1322);
        linkedQueue.add(8945);
        linkedQueue.add(6512);

        // toString() on linkedQueue
        String queueRepresentation = linkedQueue.toString();

        // print results
        System.out.println("Queue Representation:");
        System.out.println(queueRepresentation);
    }
}
```

**输出:**

```
Queue Representation:
[2300, 1322, 8945, 6512]

```

```
// Java Program Demonstrate toString()
// method of LinkedBlockingQueue.

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    // create an Employee Object with 
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
        gfg.stringRepresentation();
    }

    public void stringRepresentation()
    {

        // define capacity of LinkedBlockingQueue
        int capacity = 50;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacity);

        Employee emp1 = new Employee("Aman", "Analyst", "24000");
        Employee emp2 = new Employee("Sachin", "Developer", "39000");

        // Add Employee Objects to linkedQueue
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);

        // toString() on linkedQueue
        String queueRepresentation = linkedQueue.toString();

        // print results
        System.out.println("Queue Representation:");
        System.out.println(queueRepresentation);
    }
}
```

**输出:**

```
Queue Representation:
[Employee [name=Aman, position=Analyst, salary=24000], Employee [name=Sachin, position=Developer, salary=39000]]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#toString--)