# Java 中循环的泛型

> 原文:[https://www.geeksforgeeks.org/generic-for-loop-in-java/](https://www.geeksforgeeks.org/generic-for-loop-in-java/)

当我们知道我们必须**迭代整个集合或列表**时，那么我们可以使用通用 For 循环。Java 的 Generic 有一个名为**的**新**循环，用于每个**循环。也叫**增强为循环**。这个 for-each 循环使得**更容易迭代**数组**或**泛型集合类。****

在**正常换循环**中，我们写了三个语句:

```java
for( *statement1*; *statement 2*; *statement3* )
{
     //code to be executed 
}

```

**语句 1** 在代码执行之前执行，**语句 2** 陈述执行代码需要满足的条件，**语句 3** 在代码块执行之后执行。

但是如果我们查看每个循环的通用循环或 T2 循环，

回路的通用**由**三个参数组成:****

*   **迭代器函数**:需要下一个值时调用。它接收不变状态和控制变量作为参数。返回零信号终止。
*   **不变状态:**这在迭代过程中不会改变。它基本上是迭代的主题，如字符串、表或用户数据。
*   **控制变量:**表示迭代的初始值。

**语法**

```java
for( ObjectType variable : iterable/array/collections ){

     // code using name variable
}

```

**相当于**

```java
for( int i=0 ; i< list.size() ; i++) {

   ObjectType variable = list.get(i);

   // statements using variable
}

```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate Generic for loop

import java.io.*;

class GenericsForLoopExample {

    public static void main(String[] args)
    {
        // create an array
        int arr[] = { 120, 100, 34, 50, 75 };

        // get the sum of array elements
        int s = sum(arr);

        // print the sum
        System.out.println(s);
    }

    // returs the sum of array elements
    public static int sum(int arr[])
    {

        // initialize the sum variable
        int sum = 0;

        // generic for loop where var stores the integer
        // value stored at every index of array
        for (int var : arr) {
            sum += var;
        }

        return sum;
    }
}
```

**Output**

```java
379
```

**示例:**显示

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that Generic
// for loop can be used in iterating 
// Collections like HashMap

import java.io.*;
import java.util.*;

class EnhancedForLoopExample {

    public static void main(String[] args)
    {
        // create a empty hashmap
        HashMap<String, String> map = new HashMap<>();

        // enter name/url pair
        map.put("GFG", "geeksforgeeks.org");
        map.put("Github", "www.github.com");
        map.put("Practice", "practice.geeksforgeeks.org");
        map.put("Quiz", "quiz.geeksforgeeks.org");

        // using keySet() for storing 
         // all the keys in a Set
        Set<String> key = map.keySet();

        // Generic for loop for iterating all over the
        // keySet
        for (String k : key) {
            System.out.println("key :" + k);
        }

        // Generic for loop for iterating all over the
        // values
        for (String url : map.values()) {
            System.out.println("value :" + url);
        }
    }
}
```

**Output**

```java
key :Quiz
key :Github
key :Practice
key :GFG
value :quiz.geeksforgeeks.org
value :www.github.com
value :practice.geeksforgeeks.org
value :geeksforgeeks.org
```

### 通用 For 循环或 For 每个循环的限制:

**1。不合适**当我们想要修改列表的时候。

```java
for( Integer var : arr)
{
     // only changes the var value and not the value of the data stored inside the arr
     var = var + 100; 
} 

```

**2。**我们**无法跟踪指数。**

```java
for( Integer var : arr){

     if(var == target)
     {   
         // don't know the index of var to be compared with variable target         
         return **; 
     }           
} 

```

**4。仅向前迭代一步**。

```java
// This cannot be converted to Generic for loop
for( int i = n-1 ; i >= 0 ; i-- ) {

     // code

}                  

```

**4。**无法同时处理**两个**决策**报表**。

```java
// This loop cannot be converted to Generic for loop
for( int i = 0; i < arr.length; i++ ) {

     if( arr[i]==num )
         return **;
}                            

```