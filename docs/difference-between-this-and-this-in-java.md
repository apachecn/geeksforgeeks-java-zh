# Java 中这个和这个()的区别

> 原文:[https://www . geesforgeks . org/这个和这个在 java 中的区别/](https://www.geeksforgeeks.org/difference-between-this-and-this-in-java/)

在 Java 中，这个和这个()是完全不同的。

*   **这个**关键字是用来引用当前对象的，即通过它调用方法。
*   **this()** 用于从同一个类的另一个调用一个构造函数。

下表显示了**这个关键字**和**这个()之间的点对点差异。**

<figure class="table">

| **这个** | **本()** |
| --- | --- |
| 此关键字仅用于对象。 | this()仅用于构造函数。

 |
| 它指的是当前对象。 | 它指的是参数与传递给**的参数(即**参数)匹配的同一个类的构造函数。 |
| 点(。)运算符用于访问成员。
例如，this.variableName | 没有点(。)运算符。只传递匹配的参数。 |
| 它用于区分方法中的局部变量和实例变量。 | 它用于引用属于同一类的构造函数。 |

</figure>

参见下面的代码，描述了**这个关键字的使用。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

public class Student {

    private String name;
    private int age;

    // Note that in the Constructor below "this keyword" is
    // used to differentiate between the local variable and
    // the instance variable.

    public Student(String name, int age)
    {
        // Assigns the value of local name variable
        // to the name(instance variable).
        this.name = name;
        // Assigns the value of local Age variable
        // to the Age(instance variable).
        this.age = age;
    }

    public void show()
    {
        System.out.println("Name = " + this.name);
        System.out.println("Age = " + this.age);
    }

    public static void main(String[] args)
    {
        // Creating new instance of Student Class
        Student student = new Student("Geeks", 20);
        student.show();
    }
}
```

**Output**

```
Name = Geeks
Age = 20

```

现在来看看下面描述**这个()用法的代码。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

public class Student {

    private String name;
    private int age;

    // Constructor 1 with String as parameter.
    public Student(String name)
    {
        // This line of code calls the second constructor.
        this(20);
        System.out.println("Name of Student : " + name);
    }

    // Constructor 2 with int in parameter.
    public Student(int age)
    {
        System.out.println("Age of student = " + age);
    }

    // Constructor 3 with no parameters.
    public Student()
    {
        // This line calls the first constructor.
        this("Geeks");
    }

    public static void main(String[] args)
    {
        // This calls the third constructor.
        Student student = new Student();
    }
}
```

**Output**

```
Age of student = 20
Name of Student : Geeks

```

> 请注意 **this()** 应该始终是构造函数中的第一条可执行语句。否则，程序会给出编译时错误。