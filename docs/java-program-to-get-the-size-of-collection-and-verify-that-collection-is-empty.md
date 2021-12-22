# 获取集合大小并验证集合为空的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-size-collection-and-verify-collection-empty/](https://www.geeksforgeeks.org/java-program-to-get-the-size-of-collection-and-verify-that-collection-is-empty/)

java.util.Collection 接口的**[**size()**](https://www.geeksforgeeks.org/list-size-method-in-java-with-examples/)**和 [**isEmpty()**](https://www.geeksforgeeks.org/collection-isempty-method-in-java-with-examples/) 用于检查集合的大小以及集合是否为空。 **isEmpty()** 方法不取任何参数，也不返回值。****

******示例:******

```java
**Input:[99, 54, 112, 184, 2]
Output:size = 5 and Collection is not empty

Input:[]
Output: size = 0 and Collection is empty**
```

#### ******大小()方法:******

******语法:******

```java
**public int size()**
```

******参数**:该方法不取任何参数。****

******返回值:**这个方法返回这个列表中的元素个数。****

#### ******isEmpty()方法:******

******语法:******

```java
**Collection.isEmpty()**
```

******参数:**此方法不接受任何参数****

******返回值:**此方法不返回值。****

******示例 1:使用链接列表类******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**//Java Program to Get the Size of Collection 
// and Verify that Collection is Empty
// using LinkedList class

import java.io.*;
import java.util.*; 

class GFG {
    public static void main (String[] args) {

        Collection<Integer> list = new  LinkedList<Integer>();  

        //add integer values in this list  
        list.add(99);  
        list.add(54);  
        list.add(112);
          list.add(184);
          list.add(2);

        // Output the present list 
        System.out.print("The elements in Collection : ");  
        System.out.println(list);  

        //returns the size of the list
        System.out.println("Size of the collection "+list.size()); 

        // Check if list is empty using isEmpty() method 
        System.out.println("Is the LinkedList empty: "
                           + list.isEmpty()); 
        // Clearing the LinkedList 
        list.clear(); 

        // printing the new list 
        System.out.println("The new List is: " + list); 

        // Check if list is empty 
        // using isEmpty() method 
        System.out.println("Is the LinkedList empty: "
                           + list.isEmpty()); 
    }
}**
```

******Output**

```java
The elements in Collection : [99, 54, 112, 184, 2]
Size of the collection 5
Is the LinkedList empty: false
The new List is: []
Is the LinkedList empty: true

```**** 

******示例 2:** **使用数组列表类******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**//Java Program to Get the Size of Collection and 
// Verify that Collection is Empty 
// using ArrayList class

import java.io.*;
import java.util.*; 

class GFG {
    public static void main (String[] args) {

        Collection<String> arraylist = new ArrayList<String>();  

           arraylist.add("Geeks");  
        arraylist.add("for");  
        arraylist.add("geeks");

        // returns the size of the arraylist
        System.out.println("Size of the collection "+arraylist.size()); 

        // Check if list is empty using isEmpty() method 
        System.out.println("Is the ArrayList empty: "
                           + arraylist.isEmpty()); 
    }
}**
```

******Output**

```java
Size of the collection 3
Is the ArrayList empty: false

```****