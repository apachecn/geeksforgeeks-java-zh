# 在循环链表中搜索元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-search-一个循环链表中的元素/](https://www.geeksforgeeks.org/java-program-to-search-an-element-in-a-circular-linked-list/)

链表是一种线性数据结构，其中每个节点都有一个数据部分和指向下一个节点的地址部分。循环链表是一种链表，其中最后一个节点指向第一个节点，形成一个节点圈。**例:**

```
Input : CList = 6->5->4->3->2, find = 3
Output: Element is present

Input : CList = 6->5->4->3->2, find = 1
Output: Element is not present
```

**在循环链表中搜索元素**

例如，如果要搜索的关键字是 30，链表是 5->4->3->2，那么函数应该返回 false。如果要搜索的关键字是 4，那么函数应该返回 true。

**进场:**

1.  初始化节点指针，temp = head
2.  初始化计数器 f=0(检查元素是否存在于链表中)
3.  如果标题为空，则打印列表为空
4.  否则开始遍历链表，如果在链表中找到元素，则在 f 中递增
5.  如果计数器为零，则找不到打印元素

下面是上述方法的实现:

T3】JavaT5

```
// Java program to Search an Element
// in a Circular Linked List
public class search {
    class Node {

        int data;
        Node next;
        public Node(int data) { this.data = data; }
    }
    // declaring head pointer as null
    public Node head = null;
    public Node tempo = null;

    // function adds new nodes at the end of list
    public void addNode(int data)
    {
        Node new1 = new Node(data);

        // If linked list is empty
        if (head == null) {
            head = new1;
        }
        else {
            tempo.next = new1;
        }

        tempo = new1;

        // last node points to first node
        tempo.next = head;
    }
    public void find(int key)
    {
        // temp will traverse the circular
        // linked list for searching element
        Node temp = head;

        // counter used to check if
        // element is found or not
        int f = 0;
        if (head == null) {
            System.out.println("List is empty");
        }
        else {
            do {
                if (temp.data == key) {
                    System.out.println(
                        "element is present");
                    f = 1;
                    break;
                }
                temp = temp.next;
            } while (temp != head);
            if (f == 0) {
                System.out.println(
                    "element is not present");
            }
        }
    }
    public static void main(String[] args)
    {
        search s = new search();

        // Adds data to the list
        s.addNode(5);
        s.addNode(4);
        s.addNode(3);
        s.addNode(2);

        // Search for node 2 in the list
        s.find(2);

        // Search for node 6 in the list
        s.find(6);
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N)，其中 N 为循环链表的长度。