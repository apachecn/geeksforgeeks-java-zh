# Java 中的 ArrayList removeIf()方法

> 原文:[https://www . geesforgeks . org/ArrayList-removeif-method-in-Java/](https://www.geeksforgeeks.org/arraylist-removeif-method-in-java/)

[**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 的 **removeIf()** 方法用于移除该数组列表中满足给定谓词过滤器的所有元素，该谓词过滤器作为参数传递给该方法。

错误或运行时异常在迭代过程中抛出，或者由谓词传递给调用方。如果我们能够移除一些元素，这个方法返回*真*。

Java 8 有一个重要的内置功能接口，那就是谓词。谓词或条件检查函数检查给定条件的给定输入，并返回相同的布尔结果，指示条件是否满足。

[Java 8 谓词附例。](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)

**语法:**

```java
public boolean removeIf(Predicate filter)
```

**参数:**该方法采用参数**过滤器**，该过滤器代表一个谓词，该谓词为要移除的元素返回 true。

**返回:**如果谓词返回真，并且我们能够移除元素，则该方法返回*真*。

**异常:**如果指定的过滤器为空，该方法抛出*空指针异常*。

下面的程序说明了数组列表的 removeIf()方法:

**程序 1:** 在数组列表上演示 removeIf()方法的程序，该列表包含一组数字，只有可被 3 整除的数字才会被删除。

```java
// Java Program Demonstrate removeIf()
// method of ArrayList

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {

        // create an ArrayList which going to
        // contains a list of Numbers
        ArrayList<Integer> Numbers = new ArrayList<Integer>();

        // Add Number to list
        Numbers.add(23);
        Numbers.add(32);
        Numbers.add(45);
        Numbers.add(63);

        // apply removeIf() method
        // we are going to remove numbers divisible by 3
        Numbers.removeIf(n -> (n % 3 == 0));

        // print list
        for (int i : Numbers) {
            System.out.println(i);
        }
    }
}
```

**输出:**

```java
23
32

```

**程序 2:** 演示 ArrayList 上 removeIf()方法的程序，该方法包含一组学生姓名和以“S”开头的姓名，将被删除。

```java
// Java Program Demonstrate removeIf()
// method of ArrayList

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // create an ArrayList which going to
        // contains a list of Student names which is actually
        // string values
        ArrayList<String> students = new ArrayList<String>();

        // Add Strings to list
        // each string represents student name
        students.add("Ram");
        students.add("Mohan");
        students.add("Sohan");
        students.add("Rabi");
        students.add("Shabbir");

        // apply removeIf() method
        // we are going to remove names
        // start with S
        students.removeIf(n -> (n.charAt(0) == 'S'));

        System.out.println("Students name Does not start with S");
        // print list
        for (String str : students) {
            System.out.println(str);
        }
    }
}
```

**输出:**

```java
Students name Does not start with S
Ram
Mohan
Rabi

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/ArrayList . html # removeIf(Java . util . function . predicate)](https://docs.oracle.com/javase/10/docs/api/java/util/ArrayList.html#removeIf(java.util.function.Predicate))