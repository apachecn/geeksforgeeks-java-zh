# Java 中 link edtransferqueue remaingccapacity()方法示例

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-remainingcapacity-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-remainingcapacity-method-in-java-with-examples/)

**T1。remainingCapacity():** 方法总是返回整数。MAX_VALUE，因为这种队列不受容量限制。

**语法**

```
public int remainingCapacity()
```

**参数:**该方法不取任何参数。

**返回:**该方法只返回一个值，即**整数。最大值**。

以下示例说明了 linkedtransferqueue . remainingcapacity()方法:

**例 1:**

```
// Java program to illustrate
// LinkedTransferQueue.remainingCapacity() method

import java.util.concurrent.LinkedTransferQueue;

class GFG {
    public static void main(String args[])
    {

        // create object of LinkedTransferQueue
        // using LinkedTransferQueue() constructor
        LinkedTransferQueue<Integer> LTQ
            = new LinkedTransferQueue<Integer>();

        // Add numbers to end of LinkedTransferQueue
        LTQ.add(7855642);
        LTQ.add(35658786);
        LTQ.add(5278367);
        LTQ.add(74381793);

        // print Dequee
        System.out.println("Linked Transfer Queue1: "
                           + LTQ);

        // print the remaining capacity
        // using remainingCapacity() method
        System.out.println(LTQ.remainingCapacity());
    }
}
```

**Output:**

```
Linked Transfer Queue1: [7855642, 35658786, 5278367, 74381793]
2147483647

```

**例 2:**

```
// Java program to illustrate
// LinkedTransferQueue.remainingCapacity() method

import java.util.concurrent.LinkedTransferQueue;

class GFG {
    public static void main(String args[])
    {

        // create object of LinkedTransferQueue
        // using LinkedTransferQueue() constructor
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        // Add numbers to end of LinkedTransferQueue
        LTQ.add("Geeks");
        LTQ.add("For");
        LTQ.add("Geeks");
        LTQ.add("GeeksForGeeks");

        // print Dequee
        System.out.println("Linked Transfer Queue1: "
                           + LTQ);

        // print the remaining capacity
        // using remainingCapacity() method
        System.out.println(LTQ.remainingCapacity());
    }
}
```

**Output:**

```
Linked Transfer Queue1: [Geeks, For, Geeks, GeeksForGeeks]
2147483647

```