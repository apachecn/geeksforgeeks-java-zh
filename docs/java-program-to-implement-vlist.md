# 实现 VList 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-vlist/](https://www.geeksforgeeks.org/java-program-to-implement-vlist/)

VList 是一种数据结构，它结合了数组的快速索引和单链表的简单扩展。VList 一般支持以下功能。

*   插入元素
*   获取索引 k 处的元素
*   清除表
*   显示列表
*   等等。

> VList 将行连接为单链表，其中第 n 行包含最大 2^N 元素。

**示例:**

```java
VList:

[2]
↓
[1, 3]
↓
[5, 1, 5, 8]
↓
[10, 12, 5, 9, 1, 0, 8, 7]
↓
[3, 5, 7]
```

> VList 首先从左到右填充*，然后从上到下填充*。**

***实施:***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java Program to Implement VList

import java.io.*;
import java.util.*;

// This will act as each row of VList
class VListNode {
    VListNode next;
    List<Integer> list;

    public VListNode()
    {
        next = null;
        list = new ArrayList<Integer>();
    }
}

class VList {

    private VListNode start;
    private VListNode end;
    private int nodeNumber;
    private int size;

    // Constructor of VList
    public VList()
    {
        start = null;
        end = null;
        nodeNumber = 0;
        size = 0;
    }

    // Check if VList is Empty or Not
    public boolean isEmpty() { return start == null; }

    // Get Number of Elements in VList
    public void getSize()
    {
        System.out.println("VList size : " + size);
        System.out.println();
    }

    // Make VList Empty
    public void clearVList()
    {
        start = null;
        end = null;
        nodeNumber = 0;
        size = 0;

        System.out.println("VList is Cleared");
        System.out.println();
    }

    // Insert a new Element in VList
    public void insert(int x)
    {
        size++;
        int n = (int)Math.pow(2, nodeNumber);

        if (start == null) {
            start = new VListNode();
            start.list.add(x);
            end = start;
            return;
        }

        if (end.list.size() + 1 <= n) {
            end.list.add(x);
        }
        else {
            nodeNumber++;

            VListNode tempNode = new VListNode();
            tempNode.list.add(x);

            end.next = tempNode;
            end = tempNode;
        }
    }

    // Get value of Element at index k in VList
    public void searchElementWithPosition(int k)
    {
        System.out.print("Element at postition " + k
                         + " is = ");

        if (k < 1 || k > size) {
            System.out.println("Does not Exist");
            System.out.println();
            return;
        }

        k--;
        VListNode startTemp = start;

        while (k >= startTemp.list.size()) {
            k -= startTemp.list.size();
            startTemp = startTemp.next;
        }

        System.out.println(startTemp.list.get(k));
        System.out.println();
    }

    // Print full VList
    public void displayVList()
    {
        System.out.print("VList : ");
        if (size == 0) {
            System.out.print("empty\n");
            return;
        }

        System.out.println();

        VListNode startTemp = start;
        int num = 0;

        while (startTemp != null) {
            for (int i = 0; i < startTemp.list.size();
                 i++) {
                System.out.print(startTemp.list.get(i)
                                 + " ");
            }

            System.out.println();

            startTemp = startTemp.next;
            num++;
        }

        System.out.println();
    }
}

class GFG {
    public static void main(String[] args)
    {
        // Driver Code

        // Initialize Vlist
        VList vlist = new VList();

        int[] arr
            = new int[] { 9, 1, 5, 4, 3, 5, 2, 1, 0, 8 };

        // Insert Elements in VList
        for (int val : arr) {
            vlist.insert(val);
        }

        // Display VList
        vlist.displayVList();

        // Search 1st Element
        vlist.searchElementWithPosition(1);

        // Search 5th Element
        vlist.searchElementWithPosition(5);

        // Search 8th Element
        vlist.searchElementWithPosition(8);

        vlist.getSize();

        // Make List Empty
        vlist.clearVList();

        System.out.println("Vlist IsEmpty = "
                           + vlist.isEmpty());
    }
}*
```

***Output**

```java
VList : 
9 
1 5 
4 3 5 2 
1 0 8 

Element at postition 1 is = 9

Element at postition 5 is = 3

Element at postition 8 is = 1

VList size : 10

VList is Cleared

Vlist IsEmpty = true
```* 

***时间复杂度:***

*   ***插入操作:**O(1)**T3】***
*   ***搜索操作:** O(log(n))*
*   ***显示:** O(n)*
*   ***获取大小&检查空:** O(1)*