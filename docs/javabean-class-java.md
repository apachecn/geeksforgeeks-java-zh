# Java 中的 JavaBean 类

> 原文:[https://www.geeksforgeeks.org/javabean-class-java/](https://www.geeksforgeeks.org/javabean-class-java/)

JavaBeans 是[类](https://www.geeksforgeeks.org/classes-objects-java/)[将多个对象封装成一个对象(bean)。它是一个 java 类，应该遵循以下约定:](https://www.geeksforgeeks.org/encapsulation-in-java/)

[](https://www.geeksforgeeks.org/encapsulation-in-java/)
2.  [必须实现](https://www.geeksforgeeks.org/encapsulation-in-java/)[可序列化](https://www.geeksforgeeks.org/serialization-in-java/)。
3.  It should have a public no-arg constructor.
4.  All properties in Java must be private and have public getter and setter methods.

```
// Java program to illustrate the
// structure of JavaBean class
public class TestBean {
private String name;
public void setName(String name)
    {
        this.name = name;
    }
public String getName()
    {
        return name;
    }
}
```

**setter 方法的语法:**

1.  It should be public in nature.
2.  The return type should be empty.
3.  Setter method should be prefixed with set.
4.  There should be some arguments, that is, it should not be a parameterless method.

**getter 方法的语法:**

1.  It should be public in nature.
2.  The return type should not be invalid, that is, according to our requirements, we must give the return type.
3.  Getter methods should be prefixed with get.
4.  There should be no argument.

对于布尔属性，getter 方法名可以以“get”或“is”作为前缀。但建议用“是”。

```
// Java program to illustrate the
// getName() method on boolean type attribute
public class Test {
private boolean empty;
public boolean getName()
    {
        return empty;
    }
public boolean isempty()
    {
        return empty;
    }
}
```

**实施**

```
// Java Program of JavaBean class
package geeks;
public class Student implements java.io.Serializable
{
private int id;
private String name;
public Student()
    {
    }
public void setId(int id)
    {
        this.id = id;
    }
public int getId()
    {
        return id;
    }
public void setName(String name)
    {
        this.name = name;
    }
public String getName()
    {
        return name;
    }
}
```

```
// Java program to access JavaBean class
package geeks;
public class Test {
public static void main(String args[])
    {
        Student s = new Student(); // object is created
        s.setName("GFG"); // setting value to the object
        System.out.println(s.getName());
    }
}
```

输出:

```
GFG

```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。