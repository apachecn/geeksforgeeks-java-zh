# Java 8 | ArrayDeque removeIf()方法在 Java 中用示例

> 原文:[https://www . geesforgeks . org/Java-8-arraydeque-removeif-method-in-Java-with-examples/](https://www.geeksforgeeks.org/java-8-arraydeque-removeif-method-in-java-with-examples/)

**ArrayDeque** 的 **removeIf()** 方法用于从 ArrayDeque 中移除满足给定谓词过滤器条件的所有元素，该条件作为参数传递给该方法。如果从向量中移除了某些元素，此方法将返回 true。

Java 8 有一个重要的内置功能接口，就是[谓词](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)。谓词或条件检查函数，它检查给定条件的给定输入，并返回相同的布尔结果，指示条件是否满足。

**语法:**

```java
public boolean removeIf(Predicate<? super E> filter)
```

**参数:**该方法采用参数**过滤器**，该过滤器代表一个谓词，该谓词为要移除的元素返回 true。

**返回:**如果谓词返回真且某些元素被移除，则此方法返回**真**。

**异常:**如果指定的过滤器为空，该方法抛出**空指针异常**。

下面的程序说明了 ArrayDeque 的 removeIf()方法:

**示例 1:** 演示 ArrayDeque 上的 removeIf()方法，该方法包含一组 String，remove strings 以 a 开头。

```java
// Java Program Demonstrate removeIf()
// method of ArrayDeque

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayDeque
        // containing a list of string values
        ArrayDeque<String> students = new ArrayDeque<String>();

        // Add Strings to list
        // each string represents student name
        students.add("Aman");
        students.add("Sanjeet");
        students.add("Amar");
        students.add("Rabi");
        students.add("Shabbir");

        // apply removeIf() method
        // to remove names which start with A
        students.removeIf(n -> (n.charAt(0) == 'A'));

        System.out.println("Students name do not starts with A");

        // print list
        for (String str : students) {
            System.out.println(str);
        }
    }
}
```

**输出:**

```java
Students name do not starts with A
Sanjeet
Rabi
Shabbir

```

**示例 2:** 演示 ArrayDeque 上的 removeIf()方法，该方法包含一组学生对象，用于移除所有分数低于 40 分的学生。

```java
// Java Program Demonstrate removeIf()
// method of ArrayDeque

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayDeque
        // containing a list of Student objects
        ArrayDeque<student> students = new ArrayDeque<student>();

        // Add student object to list
        students.add(new student("Aman", 78));
        students.add(new student("Amar", 79));
        students.add(new student("Suraj", 38));
        students.add(new student("Raju", 22));
        students.add(new student("Ankit", 76));
        students.add(new student("Sanju", 62));

        // apply removeIf() method
        // to remove students who scores below 40
        students.removeIf(n -> (n.marks <= 40));

        System.out.println("Students list who score above 40");

        // print list
        for (student str : students) {
            System.out.println(str.name + ", " + str.marks);
        }
    }
}

// create student class
class student {

    public String name;
    public int marks;

    student(String name, int marks)
    {
        this.name = name;
        this.marks = marks;
    }
}
```

**输出:**

```java
Students list who score above 40
Aman, 78
Amar, 79
Ankit, 76
Sanju, 62

```

**示例 3:** 演示 removeIf()方法中的 NullpointerException。

```java
// Java Program Demonstrate removeIf()
// method of ArrayDeque

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayDeque
        // containing a list of string values
        ArrayDeque<String> students = new ArrayDeque<String>();

        // Add Strings to list
        // each string represents student name
        students.add("Aman");
        students.add("Sanjeet");
        students.add("Amar");
        students.add("Rabi");
        students.add("Shabbir");

        try {
            // apply removeIf() method with null filter
            students.removeIf(null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/arraydeque . html # removeIf(Java . util . function . predicate)](https://docs.oracle.com/javase/10/docs/api/java/util/ArrayDeque.html#removeIf(java.util.function.Predicate))