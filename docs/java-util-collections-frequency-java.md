# Java 中的 Java . util . collections . frequency()

> 原文:[https://www . geesforgeks . org/Java-util-collections-frequency-Java/](https://www.geeksforgeeks.org/java-util-collections-frequency-java/)

该方法是一个 java.util.Collections 类方法。它计算给定列表中指定元素的频率。它[覆盖 equals()](https://www.geeksforgeeks.org/overriding-equals-method-in-java/) 方法来执行比较，以检查指定的对象和列表中的对象是否相等。
**语法:**

```java
public static int frequency(Collection c, Object o) 
parameters:
c: Collection in which to determine the frequency of o.
o: Object whose frequency is to be determined.
It throws Null Pointer Exception if the Collection c is null.

```

```java
// Java program to demonstrate 
// working of Collections.frequency()
import java.util.*;

public class GFG
{
    public static void main(String[] args)
    {
        // Let us create a list with 4 items
        ArrayList<String> list =
                        new ArrayList<String>();
        list.add("code");
        list.add("code");
        list.add("quiz");
        list.add("code");

        // count the frequency of the word "code"
        System.out.println("The frequency of the word code is: "+ 
                                Collections.frequency(list, "code")); 
    }
}
```

输出:

```java
The frequency of the word code is: 3

```

**对自定义对象使用 Java . util . collections . frequency()**

上述方法适用于 java 中已经定义的对象，但是自定义对象呢？为了计算 java 中自定义对象的出现频率，我们必须简单地重写 equals()方法。让我们看看如何做到这一点。

```java
// Java program to demonstrate working of 
// Collections.frequency()
// for custom defined objects
import java.util.*;

public class GFG
{
    public static void main(String[] args)
    {
        // Let us create a list of Student type
        ArrayList<Student> list =
                        new ArrayList<Student>();
        list.add(new Student("Ram", 19));
        list.add(new Student("Ashok", 20));
        list.add(new Student("Ram", 19));
        list.add(new Student("Ashok", 19));

        // count the frequency of the word "code"
        System.out.println("The frequency of the Student Ram, 19 is: "+ 
                                Collections.frequency(list, new Student("Ram", 19))); 
    }
}
class Student
{
    private String name;
    private int age;

    Student(String name, int age)
    {
    this.name=name;
    this.age=age;
    }

    public String getName()
    {
        return name;
    }

    public void setName(String name)
    {
        this.name = name;
    }

    public int getAge() 
    {
        return age;
    }

    public void setAge(int age)
    {
        this.age = age;
    }

    @Override
    public boolean equals(Object o)
    {
        Student s;
        if(!(o instanceof Student))
        {
            return false;
        }

        else
        {
            s=(Student)o;
            if(this.name.equals(s.getName()) && this.age== s.getAge())
            {
                return true;
            }
        }
        return false;
    }
}
```

输出:

```java
The frequency of the Student Ram,19 is: 2

```

本文由**塔尼莎米塔尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。