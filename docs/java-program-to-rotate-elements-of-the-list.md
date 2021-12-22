# 旋转列表元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序转列表元素/](https://www.geeksforgeeks.org/java-program-to-rotate-elements-of-the-list/)

[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)是可以存储重复值的有序对象集合。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。在本文中，我们将看到如何旋转列表的元素。让我们考虑以下列表。

![initial list](img/206d3572c0cbbd514e0d21214b223aad.png)

旋转前的原始列表

列表中有两种类型的循环。它们是右旋转和左旋转。四次向右旋转后，列表如下所示:

![After four right rotations](img/35915826786e9571372db7ce3b70e586.png)

旋转四个位置后的列表

**方法 1:(不使用内置方法)**

**向右旋转工作**

*   首先将列表的最后一个元素存储在一个临时变量中。
*   将元素向右移动一个位置。
*   现在用 temp 变量中的值更改列表的第一个元素值。
*   将临时变量的值更新为新的最后一个元素。
*   重复上述步骤需要一定的旋转次数。

![](img/ab8b8b1dae6fc81d6769e76a72a9c9df.png)

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Rotate Elements of the List
import java.io.*;
import java.util.*;
class GFG {

    public static void main(String[] args)
    {
        // creating ArrayList
        List<Integer> my_list = new ArrayList<>();
        my_list.add(10);
        my_list.add(20);
        my_list.add(30);
        my_list.add(40);
        my_list.add(50);
        my_list.add(60);
        my_list.add(70);

        // Printing list before rotation
        System.out.println(
            "List Before Rotation : "
            + Arrays.toString(my_list.toArray()));

        // Loop according to the number of rotations
        for (int i = 0; i < 4; i++) {

            // storing the last element in the list
            int temp = my_list.get(6);

            // traverse the list and move elements to right
            for (int j = 6; j > 0; j--) {
                my_list.set(j, my_list.get(j - 1));
            }
            my_list.set(0, temp);
        }

        // Printing list after rotation
        System.out.println(
            "List After Rotation :  "
            + Arrays.toString(my_list.toArray()));
    }
}
```

**Output**

```
List Before Rotation : [10, 20, 30, 40, 50, 60, 70]
List After Rotation :  [40, 50, 60, 70, 10, 20, 30]
```

四次向左旋转后，列表如下所示:

![After four left rotations](img/60756c1ca910714dc448a04bd20dc204.png)

旋转四个位置后的列表

**向左旋转工作**

*   首先将列表的第一个元素存储在一个临时变量中。
*   将元素向左移动一个位置。
*   现在用 temp 变量中的值更改列表的最后一个元素值。
*   将临时变量的值更新为新的第一个元素。
*   重复上述步骤需要一定的旋转次数。

![](img/4c3a0adac344c023b2cfbc7d9e261a8f.png)

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Rotate Elements of the List

import java.io.*;
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // creating array list
        List<Integer> my_list = new ArrayList<>();
        my_list.add(10);
        my_list.add(20);
        my_list.add(30);
        my_list.add(40);
        my_list.add(50);
        my_list.add(60);
        my_list.add(70);

        // Printing list before rotation
        System.out.println(
            "List Before Rotation : "
            + Arrays.toString(my_list.toArray()));

        // Loop according to the number of rotations
        for (int i = 0; i < 4; i++) {
            // storing the first element in the list
            int temp = my_list.get(0);
            // traverse the list and move elements to left
            for (int j = 0; j < 6; j++) {
                my_list.set(j, my_list.get(j + 1));
            }
            my_list.set(6, temp);
        }

        // Printing list after rotation
        System.out.println(
            "List After Rotation :  "
            + Arrays.toString(my_list.toArray()));
    }
}
```

**Output**

```
List Before Rotation : [10, 20, 30, 40, 50, 60, 70]
List After Rotation :  [50, 60, 70, 10, 20, 30, 40]
```