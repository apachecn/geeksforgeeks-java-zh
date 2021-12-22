# 从 Java 的数组列表中获取随机元素

> 原文:[https://www . geesforgeks . org/get-random-elements-from-ArrayList-in-Java/](https://www.geeksforgeeks.org/getting-random-elements-from-arraylist-in-java/)

[ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 是 [**集合框架**](https://www.geeksforgeeks.org/collections-in-java-2/) 的一部分，存在于 java.util 包中。它为我们提供了 Java 中的动态数组。

从列表中生成随机数有很好的实用价值

**从数组列表中获取随机元素有多种方法:**

1.  使用数学. random()
2.  使用数组列表洗牌
3.  使用随机类

**方法一:使用** [**奥数()**](https://www.geeksforgeeks.org/java-math-random-method-examples/)

**语法:**

```
public static double random()

```

**返回:**
此方法返回大于等于 0.0 且小于 1.0 的伪随机双精度值。

*   Math.random()生成一个介于 0 和 1 之间的随机值。
*   将该值乘以数组列表的大小，只取该值的整数部分。
*   现在，执行上述步骤后生成的数字可以作为数组列表的索引。
*   使用 get()方法，使用上面生成的索引从数组列表中返回一个随机元素。

**注意:**每次调用 Math.random()方法时，它都会生成一个新的随机值，但是数组列表中元素的原始顺序不会受到干扰。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for Getting Random Elements 
// from ArrayList using Math.random() function

import java.io.*;
import java.util.ArrayList;
class GFG {
    public static void main(String[] args)
    {
        // creating ArrayList
        ArrayList<Integer> my_list = new ArrayList<Integer>();

        // adding elements
        my_list.add(10);
        my_list.add(80);
        my_list.add(30);
        my_list.add(70);
        my_list.add(5);
        my_list.add(90);
        my_list.add(19);
        my_list.add(25);

        // loop to print elements at randonm
        for (int i = 0; i < my_list.size(); i++) 
        {
           // generating the index using Math.random()
            int index = (int)(Math.random() * my_list.size());

            System.out.println("Random Element is :"
                               + my_list.get(index));
        }
    }
}
```

**Output**

```
Random Element is :70
Random Element is :25
Random Element is :90
Random Element is :5
Random Element is :70
Random Element is :30
Random Element is :70
Random Element is :10
```

**方法二:使用** [**数组列表洗牌**](https://www.geeksforgeeks.org/shuffle-or-randomize-a-list-in-java/)

*   Java 的 Collections.shuffle()方法打乱了数组列表中元素的顺序。
*   现在，我们可以简单地迭代数组列表并返回元素，因为它们现在是随机的。

**注:**实际的数组列表本身被打乱，原始排序丢失。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for Getting Random Elements 
// from ArrayList using Collections.shuffle()

import java.io.*;
import java.util.*;
import java.util.ArrayList;
class GFG {
    public static void main(String[] args)
    {
        // creating ArrayList
        ArrayList<Integer> my_list = new ArrayList<Integer>();

        // adding elements
        my_list.add(10);
        my_list.add(80);
        my_list.add(30);
        my_list.add(70);
        my_list.add(5);
        my_list.add(90);
        my_list.add(19);
        my_list.add(25);

        // using collections.shuffle to shuffle elements of
        // ArrayList
        Collections.shuffle(my_list);

        // using for each loop to print values at random
        System.out.println("Random values :");

        for (Integer random_values : my_list)
        {
            System.out.print(random_values + " ");
        }
    }
}
```

**Output**

```
Random values :
19 5 25 90 10 30 80 70
```

**方法三:使用** [**随机类功能**](https://www.geeksforgeeks.org/java-util-random-nextint-java/)

*   **可以使用 Random 类的 nextInt()** 方法生成一个介于 0 和 ArrayList 大小之间的随机值。
*   现在使用这个数字作为数组列表的索引。
*   使用 get()方法从 ArrayList 返回一个随机元素，该随机元素使用从 nextInt()方法生成的数字。

**注意:**数组列表的原始顺序保持不变。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for Getting Random Elements 
// from ArrayList using nextInt() function

import java.io.*;
import java.util.ArrayList;
import java.util.Random;
class GFG {
    public static void main(String[] args)
    {
        // creating ArrayList
        ArrayList<Integer> my_list = new ArrayList<Integer>();

        // adding elements
        my_list.add(10);
        my_list.add(80);
        my_list.add(30);
        my_list.add(70);
        my_list.add(5);
        my_list.add(90);
        my_list.add(19);
        my_list.add(25);

        // initializing random class
        Random random_method = new Random();

        // loop for generation random number
        for (int i = 0; i < my_list.size(); i++) 
        {
            // generating random index with the help of
            // nextInt() method
            int index = random_method.nextInt(my_list.size());

            System.out.println("Random Element is :"
                               + my_list.get(index));
        }
    }
}
```

**Output**

```
Random Element is :5
Random Element is :10
Random Element is :19
Random Element is :5
Random Element is :30
Random Element is :70
Random Element is :25
Random Element is :90
```