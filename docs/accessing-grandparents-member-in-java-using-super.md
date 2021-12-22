# 使用超级

在 Java 中访问祖父母的成员

> 原文:[https://www . geeksforgeeks . org/access-祖辈-成员-in-Java-use-super/](https://www.geeksforgeeks.org/accessing-grandparents-member-in-java-using-super/)

**在 Java 中直接访问祖父母的成员:**

预测以下 Java 程序的输出。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// filename Main.java
class Grandparent {
    public void Print()
    {
        System.out.println("Grandparent's Print()");
    }
}

class Parent extends Grandparent {
    public void Print()
    {
        System.out.println("Parent's Print()");
    }
}

class Child extends Parent {
    public void Print()
    {
        // Trying to access Grandparent's Print()
        super.super.Print();
        System.out.println("Child's Print()");
    }
}

public class Main {
    public static void main(String[] args)
    {
        Child c = new Child();
        c.Print();
    }
}
```

**输出:**

```
prog.java:20: error: <identifier> expected
        super.super.Print();
              ^
prog.java:20: error: not a statement
        super.super.Print(); 
```

“super.super.print()”行有错误。在 Java 中，类不能直接访问祖父母的成员。不过在 C++中是允许的。在 C++中，我们可以使用范围解析运算符(::)来访问继承层次结构中任何祖先的成员。 ***在 Java 中，我们只能通过父类访问祖父母的成员。***

例如，下面的程序编译并运行良好。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// filename Main.java
class Grandparent {
    public void Print()
    {
        System.out.println("Grandparent's Print()");
    }
}

class Parent extends Grandparent {
    public void Print()
    {
        super.Print();
        System.out.println("Parent's Print()");
    }
}

class Child extends Parent {
    public void Print()
    {
        super.Print();
        System.out.println("Child's Print()");
    }
}

public class Main {
    public static void main(String[] args)
    {
        Child c = new Child();
        c.Print();
    }
}
```

**Output**

```
Grandparent's Print()
Parent's Print()
Child's Print()

```

**为什么 java 不允许访问祖父母的方法？**

它违反了封装。您不应该能够绕过父类的行为。有时能够绕过您自己的类的行为(特别是从同一个方法中)而不是您的父类的行为是有意义的。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。