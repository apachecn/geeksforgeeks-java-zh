# 将链接列表转换为 Java 中的字符串

> 原文:[https://www . geesforgeks . org/convert-linked list-to-string-in-Java/](https://www.geeksforgeeks.org/convert-linkedlist-to-string-in-java/)

一个[链接列表](https://www.geeksforgeeks.org/data-structures/linked-list/)是一个线性数据结构，其中元素不存储在连续的存储位置。

为了将链表转换成字符串，我们需要遍历链表，然后，我们需要将链表的元素附加到字符串变量中。

我们可以使用 String 类、 **StringBuilder** 或 **StringBuffer** 将链接列表转换为字符串。

对于追加字符串，我们可以对字符串类使用“+”运算符，对字符串缓冲区和字符串构建器使用追加方法。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Convert LinkedList to String in Java

import java.util.Iterator;
import java.util.LinkedList;
import java.util.ListIterator;

class GFG {
    public static void main(String[] args)
    {

        // creating a linkedlist
        LinkedList<Integer> list = new LinkedList<>();

        // adding elements to linkedlist
        list.add(100);
        list.add(200);
        list.add(300);
        list.add(400);

        // By using String Class
        String s = "";

        // using iterator for traversing a linkedllist
        Iterator<Integer> iterator = list.iterator();

        while (iterator.hasNext()) {
            // appending using "+" operator
            s = s + iterator.next() + " ";
        }

        // Displaying output
        System.out.println(s);

        // By using String Buffer
        StringBuffer stringBuffer = new StringBuffer();

        // using enhanced for loop for traversing a
        // linkedlist
        for (Integer integer : list) {

            // using append method for appending string
            stringBuffer.append(integer).append(" ");
        }

        // displaying output
        System.out.println(stringBuffer);

        // By using String Builder
        StringBuilder stringBuilder = new StringBuilder();

        // using ListIterator for traversing a linked list
        ListIterator<Integer> listIterator
            = list.listIterator();

        while (listIterator.hasNext()) {

            // using append method for appending string
            stringBuilder.append(listIterator.next())
                .append(" ");
        }

        // displaying output
        System.out.println(stringBuilder);
    }
}
```

**Output**

```java
100 200 300 400 
100 200 300 400 
100 200 300 400 
```

**例 2:**

在本例中，我们将使用用户定义的类

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Convert LinkedList to String in Java

import java.util.Iterator;
import java.util.LinkedList;
import java.util.ListIterator;

class friendsDetail {

    // class field
    private String name;
    private String nickName;
    private int id;

    // parameterised constructor
    public friendsDetail(String name, String nickName,
                         int id)
    {
        this.name = name;
        this.nickName = nickName;
        this.id = id;
    }

    // getter for name
    public String getName() { return name; }

    // setter for name
    public void setName(String name) { this.name = name; }

    // getter for marks
    public int getID() { return id; }

    // setter for marks
    public void setID(int id) { this.id = id; }

    // getter for nickname
    public String getNickName() { return nickName; }

    // setter for nickname
    public void setNickName(String nickName)
    {
        this.nickName = nickName;
    }

    //@Override toString method
    public String toString()
    {
        return "name='" + name + '\'' + ", nickName='"
            + nickName + '\'' + ", ID=" + id;
    }
}

class Main {
    public static void main(String[] args)
    {

        LinkedList<friendsDetail> list = new LinkedList<>();

        // adding elements to linked list
        list.add(
            new friendsDetail("Ridhi", "Goda", 202199));
        list.add(
            new friendsDetail("Ananya", "Natki", 202195));
        list.add(new friendsDetail("Ankit", "Chota Don",
                                   202192));
        list.add(
            new friendsDetail("Suraj", "Bhindi", 202147));
        list.add(
            new friendsDetail("Sarthak", "Nagin", 202178));
        list.add(new friendsDetail("Sonika", "Chipkali",
                                   202167));
        list.add(new friendsDetail("Shishya", "Gorilla",
                                   202157));

        System.out.println("Using String Class\n");

        // using string class
        String s = "";

        // using iterator for traversing a linked list
        Iterator<friendsDetail> itr = list.iterator();

        while (itr.hasNext()) {
            // appending atring using "+" operator
            s = s + itr.next() + "\n";
        }

        // Displaying output
        System.out.println(s);

        System.out.println("\nUsing String Buffer\n");

        // using string buffer
        StringBuffer stringBuffer = new StringBuffer();

        // using enhanced for loop for linked list traversal
        for (friendsDetail friendmarks : list) {
            // using append method for appending
            stringBuffer.append(friendmarks).append("\n");
        }

        // displaying output
        System.out.println(stringBuffer);

        // using string builder
        System.out.println("\nUsing String Builder\n");

        // using list iterator for traversing a linked list
        ListIterator<friendsDetail> itr2
            = list.listIterator();

        StringBuilder stringBuilder = new StringBuilder();

        while (itr2.hasNext()) {
            // using append method for appending
            stringBuilder.append(itr2.next()).append("\n");
        }

        // displaying output
        System.out.println(stringBuilder);
    }
}
```

**Output**

```java
Using String Class

name='Ridhi', nickName='Goda', ID=202199
name='Ananya', nickName='Natki', ID=202195
name='Ankit', nickName='Chota Don', ID=202192
name='Suraj', nickName='Bhindi', ID=202147
name='Sarthak', nickName='Nagin', ID=202178
name='Sonika', nickName='Chipkali', ID=202167
name='Shishya', nickName='Gorilla', ID=202157

Using String Buffer

name='Ridhi', nickName='Goda', ID=202199
name='Ananya', nickName='Natki', ID=202195
name='Ankit', nickName='Chota Don', ID=202192
name='Suraj', nickName='Bhindi', ID=202147
name='Sarthak', nickName='Nagin', ID=202178
name='Sonika', nickName='Chipkali', ID=202167
name='Shishya', nickName='Gorilla', ID=202157

Using String Builder

name='Ridhi', nickName='Goda', ID=202199
name='Ananya', nickName='Natki', ID=202195
name='Ankit', nickName='Chota Don', ID=202192
name='Suraj', nickName='Bhindi', ID=202147
name='Sarthak', nickName='Nagin', ID=202178
name='Sonika', nickName='Chipkali', ID=202167
name='Shishya', nickName='Gorilla', ID=202157
```