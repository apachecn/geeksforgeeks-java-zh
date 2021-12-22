# 如何在 Java 中从 LinkedHashSet 中消除重复的用户定义对象？

> 原文:[https://www . geesforgeks . org/如何消除重复的用户定义对象-从-linkedhashset-in-java/](https://www.geeksforgeeks.org/how-to-eliminate-duplicate-user-defined-objects-from-linkedhashset-in-java/)

在创建自己类的 [**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/https://www.geeksforgeeks.org/hashset-in-java/) 时，始终确保 **HashSet** 的键的 **HashCode()** 方法不变。Java 对象 **hashCode()** 是一个原生方法，返回对象的整数 hash 码值。如果根据 equals()方法，两个对象相等，那么它们的哈希代码必须相同。如果根据 equals()方法，两个对象不相等，则不要求它们的哈希代码不同。

**语法:**

[**等于()方法:**](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)

```java
public boolean equals  (Object obj)

// This method checks if some other Object
// passed to it as an argument is equal to 
// the Object on which it is invoked.
```

[**HashCode()方法:**](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)

```java
public int hashCode()

// This method returns the hash code value 
// for the object on which this method is invoked.
```

只要在执行一个 Java 应用程序的过程中，在同一个对象上多次调用 **(hashcode)** ，那么 **hashCode** 方法必须一致地返回同一个整数，前提是在对象上的等号比较中使用的信息没有被修改。

如果两个对象根据 **equals(Object)** 方法是相等的，那么在两个对象的每一个上调用 **hashCode()** 方法必须产生相同的整数结果。

以下是上述问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program  to eliminate duplicate user 
// defined Objects from LinkedHashSet
import java.util.*;
// Java program to illustrate
// overriding of equals and
// hashcode methods
class student {
    int marks;
    String name;
    // Constructor
    public student(String name, int marks)
    {
        this.marks = marks;
        this.name = name;
    }
    // Getters and Setters
    public int getMarks() { return marks; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public void setMarks(int marks) { this.marks = marks; }
    @Override public int hashCode()
    {
        final int prime = 31;
        int result = 1;
        result = prime * result + marks;
        result = prime * result
                 + ((name == null) ? 0 : name.hashCode());
        return result;
    }
    @Override
    // if both the object references are
    // referring to the same object.
    public boolean equals(Object obj)
    {
        if (this == obj)
            return true;
        if (obj == null)
            return false;
        if (getClass() != obj.getClass())
            return false;

        // type casting of the argument.
        student other = (student)obj;

        // comparing the state of argument with
        // the state of 'this' Object
        if (marks != other.marks)
            return false;
        if (name == null) {
            if (other.name != null)
                return false;
        }
        else if (!name.equals(other.name))
            return false;
        return true;
    }
}

public class GFG {

    public static void main(String[] args)
    {
        // HashSet initialization
        HashSet<student> set = new HashSet<>();

        // Add entries in HashSet
        set.add(new student("sam", 452));
        set.add(new student("cam", 451));
        set.add(new student("sam", 452));
        set.add(new student("cam", 451));
        for (student std : set) {
            System.out.println(std.name + " " + std.marks);
        }
    }
}
```

**Output**

```java
cam 451
sam 452
```