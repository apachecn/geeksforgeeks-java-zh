# Java 中的最大堆

> 原文:[https://www.geeksforgeeks.org/max-heap-in-java/](https://www.geeksforgeeks.org/max-heap-in-java/)

一个[最大堆](https://www.geeksforgeeks.org/binary-heap/)是一个完整的二叉树，其中每个内部节点中的值大于或等于该节点的子节点中的值。将堆的元素映射到数组中并不重要:如果一个节点存储在索引 k 中，那么它的左子节点存储在索引 2k+1 中，它的右子节点存储在索引 2k+2 中。

插图:最大堆

![max-heap](img/3a68c0b7e894e84fb6348ab61291f532.png)

**Max Heap 是如何表现的？**

最大堆是一棵完整的二叉树。最大堆通常表示为一个数组。根元素将位于 Arr[0]。下表显示了第 I 个节点的其他节点的索引，即 Arr[i]:

```
Arr[(i-1)/2] Returns the parent node. 
Arr[(2*i)+1] Returns the left child node. 
Arr[(2*i)+2] Returns the right child node.
```

**对最大堆的操作如下:**

*   getMax():返回 Max 堆的根元素。该操作的时间复杂度为 0(1)。
*   extractMax():从 MaxHeap 中移除最大元素。此操作的时间复杂度为 O(Log n)，因为此操作需要在移除根后通过调用 [heapify()方法](https://www.geeksforgeeks.org/heap-sort/)来维护堆属性。
*   insert():插入新密钥需要 O(Log n)时间。我们在树的末端添加一个新的键。如果新密钥比它的父密钥小，那么我们不需要做任何事情。否则，我们需要遍历以修复违反的堆属性。

> **注意:**在下面的实现中，我们从索引 1 开始做索引，以简化实现。

**方法:**

有两种方法可以实现所列目标:

1.  创建 maxHeapify()方法的基本方法
2.  通过库函数使用[collections . reverseorder()](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/)方法

**方法 1:** 创建 maxHeapify()方法的基本方法

我们将创建一个方法，假设左右子树已经被堆化，我们只需要修复根。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement Max Heap

// Main class
public class MaxHeap {
    private int[] Heap;
    private int size;
    private int maxsize;

    // Constructor to initialize an
    // empty max heap with given maximum
    // capacity
    public MaxHeap(int maxsize)
    {
        // This keyword refers to current instance itself
        this.maxsize = maxsize;
        this.size = 0;
        Heap = new int[this.maxsize];
    }

    // Method 1
    // Returning position of parent
    private int parent(int pos) { return (pos - 1) / 2; }

    // Method 2
    // Returning left children
    private int leftChild(int pos) { return (2 * pos); }

    // Method 3
    // Returning left children
    private int rightChild(int pos)
    {
        return (2 * pos) + 1;
    }

    // Method 4
    // Returning true of given node is leaf
    private boolean isLeaf(int pos)
    {
        if (pos > (size / 2) && pos <= size) {
            return true;
        }
        return false;
    }

    // Method 5
    // Swapping nodes
    private void swap(int fpos, int spos)
    {
        int tmp;
        tmp = Heap[fpos];
        Heap[fpos] = Heap[spos];
        Heap[spos] = tmp;
    }

    // Method 6
    // Recursive function to max heapify given subtree
    private void maxHeapify(int pos)
    {
        if (isLeaf(pos))
            return;

        if (Heap[pos] < Heap[leftChild(pos)]
            || Heap[pos] < Heap[rightChild(pos)]) {

            if (Heap[leftChild(pos)]
                > Heap[rightChild(pos)]) {
                swap(pos, leftChild(pos));
                maxHeapify(leftChild(pos));
            }
            else {
                swap(pos, rightChild(pos));
                maxHeapify(rightChild(pos));
            }
        }
    }

    // Method 7
    // Inserts a new element to max heap
    public void insert(int element)
    {
        Heap[size] = element;

        // Traverse up and fix violated property
        int current = size;
        while (Heap[current] > Heap[parent(current)]) {
            swap(current, parent(current));
            current = parent(current);
        }
        size++;
    }

    // Method 8
    // To display heap
    public void print()
    {

      for(int i=0;i<size/2;i++){

            System.out.print("Parent Node : " + Heap[i] );

            if(leftChild(i)<size) //if the child is out of the bound of the array
               System.out.print( " Left Child Node: " + Heap[leftChild(i)]);

            if(rightChild(i)<size) //if the right child index must not be out of the index of the array
                System.out.print(" Right Child Node: "+ Heap[rightChild(i)]);

                System.out.println(); //for new line

        }

    }

    // Method 9
    // Remove an element from max heap
    public int extractMax()
    {
        int popped = Heap[1];
        Heap[1] = Heap[size--];
        maxHeapify(1);
        return popped;
    }

    // Method 10
    // main dri er method
    public static void main(String[] arg)
    {
        // Display message for better readability
        System.out.println("The Max Heap is ");

        MaxHeap maxHeap = new MaxHeap(15);

        // Inserting nodes
        // Custom inputs
        maxHeap.insert(5);
        maxHeap.insert(3);
        maxHeap.insert(17);
        maxHeap.insert(10);
        maxHeap.insert(84);
        maxHeap.insert(19);
        maxHeap.insert(6);
        maxHeap.insert(22);
        maxHeap.insert(9);

        // Calling maxHeap() as defined above
        maxHeap.print();

        // Print and display the maximum value in heap
        System.out.println("The max val is "
                           + maxHeap.extractMax());
    }
}
```

**Output**

```
The Max Heap is 
Parent Node : 84 Left Child Node: 84 Right Child Node: 22
Parent Node : 22 Left Child Node: 19 Right Child Node: 17
Parent Node : 19 Left Child Node: 10 Right Child Node: 5
Parent Node : 17 Left Child Node: 6 Right Child Node: 3
The max val is 22

```

**方法 2:** 通过库函数使用[collections . reverse order()](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/)方法

我们使用 [PriorityQueue 类](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/)在 Java 中实现堆。默认情况下，最小堆由这个类实现。为了实现最大堆，我们使用[collections . reverse order()](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/)方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working
// of PriorityQueue as a Max Heap
// Using Collections.reverseOrder() method

// Importing all utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating empty priority queue
        PriorityQueue<Integer> pQueue
            = new PriorityQueue<Integer>(
                Collections.reverseOrder());

        // Adding items to our priority queue
        // using add() method
        pQueue.add(10);
        pQueue.add(30);
        pQueue.add(20);
        pQueue.add(400);

        // Printing the most priority element
        System.out.println("Head value using peek function:"
                           + pQueue.peek());

        // Printing all elements
        System.out.println("The queue elements:");
        Iterator itr = pQueue.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());

        // Removing the top priority element (or head) and
        // printing the modified pQueue using poll()
        pQueue.poll();
        System.out.println("After removing an element "
                           + "with poll function:");
        Iterator<Integer> itr2 = pQueue.iterator();
        while (itr2.hasNext())
            System.out.println(itr2.next());

        // Removing 30 using remove() method
        pQueue.remove(30);
        System.out.println("after removing 30 with"
                           + " remove function:");

        Iterator<Integer> itr3 = pQueue.iterator();
        while (itr3.hasNext())
            System.out.println(itr3.next());

        // Check if an element is present using contains()
        boolean b = pQueue.contains(20);
        System.out.println("Priority queue contains 20 "
                           + "or not?: " + b);

        // Getting objects from the queue using toArray()
        // in an array and print the array
        Object[] arr = pQueue.toArray();
        System.out.println("Value in array: ");

        for (int i = 0; i < arr.length; i++)
            System.out.println("Value: "
                               + arr[i].toString());
    }
}
```

**Output**

```
Head value using peek function:400
The queue elements:
400
30
20
10
After removing an element with poll function:
30
10
20
after removing 30 with remove function:
20
10
Priority queue contains 20 or not?: true
Value in array: 
Value: 20
Value: 10

```