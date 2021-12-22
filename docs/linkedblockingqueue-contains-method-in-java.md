# Java 中 LinkedBlockingQueue 包含()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-contains-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-contains-method-in-java/)

如果队列包含作为参数传递的对象对象，则 LinkedBlockingQueue 的 **contains(对象对象)**方法返回 true。它返回真，当且仅当，这个队列包含至少一个元素 e，它等于作为参数传递的对象 o，即 e.equals(o)。这个方法对于检查队列是否有元素非常有帮助。

**语法:**

```
public boolean contains(Object o)
```

**参数:**该方法取一个强制参数 **o** ，即队列中要检查的对象。

**返回值:**如果该队列包含作为参数传递的对象，则该方法返回*真*。否则返回*假*。

下面的程序说明了包含()方法的 LinkedBlockingQueue 类:

**程序 1:** 检查一个数字队列是否包含数字 n。数字 n 作为输入传递给 LinkedBlockingQueue 的 contains()。

```
// Java Program Demonstrate contains(Object o)
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

        // print LinkedQueue
        System.out.println("linkedQueue: " + linkedQueue);

        // check whether LinkedBlockingQueue contains 6512
        boolean response1 = linkedQueue.contains(6512);

        // print result
        System.out.println("LinkedBlockingQueue contains "
                           + "number 6512 : "
                           + response1);

        // check whether LinkedBlockingQueue contains 5324
        boolean response2 = linkedQueue.contains(5324);

        // print result
        System.out.println("LinkedBlockingQueue contains"
                           + " number 5324 : "
                           + response2);
    }
}
```

**Output:**

```
linkedQueue: [2300, 1322, 8945, 6512]

LinkedBlockingQueue contains number 6512 : true
LinkedBlockingQueue contains number 5324 : false

```

**程序 2:** 检查一个员工队列是否包含某个员工 e。员工 e 的详细信息作为输入传递给 LinkedBlockingQueue 的 contains()。

```
// Java Program Demonstrate contains(Object o)
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
        gfg.containsMethodExample();
    }

    public void containsMethodExample()
    {

        // define capacity of LinkedBlockingQueue
        int capacity = 50;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Employee> linkedQueue
            = new LinkedBlockingQueue<Employee>(capacity);

        Employee emp1 = new Employee("Aman",
                                     "Analyst",
                                     "24000");
        Employee emp2 = new Employee("Sachin",
                                     "Developer",
                                     "39000");

        // Add Employee Objects to linkedQueue
        linkedQueue.add(emp1);
        linkedQueue.add(emp2);

        // print LinkedQueue
        System.out.println("linkedQueue: " + linkedQueue);

        // Employee to be checked
        Employee checkEmp1 = new Employee("Sanjeev",
                                          "Tester",
                                          "26000");

        // check whether linkedQueue contains emp1
        boolean response1 = linkedQueue.contains(emp1);

        // print results
        System.out.println("linkedQueue contains "
                           + emp1.toString() + " : "
                           + response1);

        // check whether linkedQueue contains checkEmp1
        boolean response2 = linkedQueue.contains(checkEmp1);

        // print results
        System.out.println("linkedQueue contains "
                           + checkEmp1.toString() + " : "
                           + response2);
    }
}
```

**Output:**

```
linkedQueue: 
[Employee [name=Aman, position=Analyst, salary=24000], 
Employee [name=Sachin, position=Developer, salary=39000]]

linkedQueue contains Employee [name=Aman, position=Analyst, salary=24000] : true
linkedQueue contains Employee [name=Sanjeev, position=Tester, salary=26000] : false

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue . html # contains-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#contains-java.lang.Object-)