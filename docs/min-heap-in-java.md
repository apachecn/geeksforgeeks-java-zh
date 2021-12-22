# Java 中的最小堆

> 原文:[https://www.geeksforgeeks.org/min-heap-in-java/](https://www.geeksforgeeks.org/min-heap-in-java/)

最小堆是一个完整的二叉树，其中每个内部节点中的值小于或等于该节点的子节点中的值。将堆的元素映射到数组中并不重要:如果一个节点存储在索引 **k** 中，那么它的左子节点存储在索引 **2k + 1** 中，它的右子节点存储在索引 **2k + 2** 中。

插图:

```java
            5                      13
         /      \               /       \  
       10        15           16         31 
      /                      /  \        /  \
    30                     41    51    100   41
```

让我们来看一下闵堆的表示。所以基本上 Min Heap 是一个完整的二叉树。最小堆通常表示为一个数组。根元素将位于**Arr【0】**。对于任何具有节点的**，即**Arr【I】****

*   **Arr[(i -1) / 2]** 返回其父节点。
*   **Arr[(2 * i) + 1]** 返回其左子节点。
*   **Arr[(2 * i) + 2]** 返回其右子节点。

现在让我们讨论最小堆上的操作，如下所示:

*   **getMin():** 返回 Min 堆的根元素。该操作的时间复杂度为 **O(1)** 。
*   **extractMin():** 从 MinHeap 中移除最小元素。这个操作的时间复杂度是 **O(Log n)** ，因为这个操作需要在移除根之后维护堆属性(通过调用 heapify())。
*   **插入():**插入新钥匙需要 **O(Log n)** 时间。我们在树的末端添加一个新的键。如果一个新的键比它的父键大，那么我们不需要做任何事情。否则，我们需要遍历以修复违反的堆属性。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement Heaps
// by Illustrating Min Heap

// Main class (MinHeap)
class GFG {

    // Member variables of this class
    private int[] Heap;
    private int size;
    private int maxsize;

    // Initializaing front as static with unity
    private static final int FRONT = 1;

    // Constructor of this class
    public MinHeap(int maxsize)
    {

        // This keyword refers to current object itself
        this.maxsize = maxsize;
        this.size = 0;

        Heap = new int[this.maxsize + 1];
        Heap[0] = Integer.MIN_VALUE;
    }

    // Method 1
    // Returning the position of
    // the parent for the node currently
    // at pos
    private int parent(int pos) { return pos / 2; }

    // Method 2
    // Returning the position of the
    // left child for the node currently at pos
    private int leftChild(int pos) { return (2 * pos); }

    // Method 3
    // Returning the position of
    // the right child for the node currently
    // at pos
    private int rightChild(int pos)
    {
        return (2 * pos) + 1;
    }

    // Method 4
    // Returning true if the passed
    // node is a leaf node
    private boolean isLeaf(int pos)
    {

        if (pos > (size / 2) && pos <= size) {
            return true;
        }

        return false;
    }

    // Method 5
    // To swap two nodes of the heap
    private void swap(int fpos, int spos)
    {

        int tmp;
        tmp = Heap[fpos];

        Heap[fpos] = Heap[spos];
        Heap[spos] = tmp;
    }

    // Method 6
    // To heapify the node at pos
    private void minHeapify(int pos)
    {

        // If the node is a non-leaf node and greater
        // than any of its child
        if (!isLeaf(pos)) {
            if (Heap[pos] > Heap[leftChild(pos)]
                || Heap[pos] > Heap[rightChild(pos)]) {

                // Swap with the left child and heapify
                // the left child
                if (Heap[leftChild(pos)]
                    < Heap[rightChild(pos)]) {
                    swap(pos, leftChild(pos));
                    minHeapify(leftChild(pos));
                }

                // Swap with the right child and heapify
                // the right child
                else {
                    swap(pos, rightChild(pos));
                    minHeapify(rightChild(pos));
                }
            }
        }
    }

    // Method 7
    // To insert a node into the heap
    public void insert(int element)
    {

        if (size >= maxsize) {
            return;
        }

        Heap[++size] = element;
        int current = size;

        while (Heap[current] < Heap[parent(current)]) {
            swap(current, parent(current));
            current = parent(current);
        }
    }

    // Method 8
    // To print the contents of the heap
    public void print()
    {
        for (int i = 1; i <= size / 2; i++) {

            // Printing the parent and both childrens
            System.out.print(
                " PARENT : " + Heap[i]
                + " LEFT CHILD : " + Heap[2 * i]
                + " RIGHT CHILD :" + Heap[2 * i + 1]);

            // By here new line is required
            System.out.println();
        }
    }

    // Method 9
    // To remove and return the minimum
    // element from the heap
    public int remove()
    {

        int popped = Heap[FRONT];
        Heap[FRONT] = Heap[size--];
        minHeapify(FRONT);

        return popped;
    }

    // Method 10
    // Main driver method
    public static void main(String[] arg)
    {

        // Display message
        System.out.println("The Min Heap is ");

        // Creating object opf class in main() methodn
        GFG minHeap = new GFG(15);

        // Inserting element to minHeap
        // using insert() method

        // Custom input entries
        minHeap.insert(5);
        minHeap.insert(3);
        minHeap.insert(17);
        minHeap.insert(10);
        minHeap.insert(84);
        minHeap.insert(19);
        minHeap.insert(6);
        minHeap.insert(22);
        minHeap.insert(9);

        // Print all elements of the heap
        minHeap.print();

        // Removing minimum value from above heap
        // and printing it
        System.out.println("The Min val is "
                           + minHeap.remove());
    }
}
```

**Output**

```java
The Min Heap is 
 PARENT : 3 LEFT CHILD : 5 RIGHT CHILD :6
 PARENT : 5 LEFT CHILD : 9 RIGHT CHILD :84
 PARENT : 6 LEFT CHILD : 19 RIGHT CHILD :17
 PARENT : 9 LEFT CHILD : 22 RIGHT CHILD :10
The Min val is 3
```

> 我们使用 [PriorityQueue](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/) 类在 Java 中实现堆。默认情况下，最小堆由这个类实现，如下例所示:

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Demonstrate working of PriorityQueue
// Using Library Functions

// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating empty priority queue
        PriorityQueue<Integer> pQueue
            = new PriorityQueue<Integer>();

        // Adding items to the priority queue
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

        // Iterating over objects using Iterator
        // so do creating an Iterator class
        Iterator itr = pQueue.iterator();

        // Iterating toill there is single element left in
        // object using next() method
        while (itr.hasNext())
            System.out.println(itr.next());

        // Removing the top priority element (or head) and
        // printing the modified pQueue using poll()
        pQueue.poll();
        System.out.println("After removing an element "
                           + "with poll function:");

        // Again creating iterator object
        Iterator<Integer> itr2 = pQueue.iterator();

        while (itr2.hasNext())
            System.out.println(itr2.next());

        // Removing 30 using remove()
        pQueue.remove(30);

        System.out.println("after removing 30 with"
                           + " remove function:");

        // Again creating iterator object
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

**Output:** 

```java
Head value using peek function:10
The queue elements:
10
30
20
400
After removing an element with poll function:
20
30
400
after removing 30 with remove function:
20
400
Priority queue contains 20 or not?: true
Value in array: 
Value: 20
Value: 400
```