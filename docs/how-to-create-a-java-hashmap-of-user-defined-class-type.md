# 如何创建自定义类类型的 Java HashMap？

> 原文:[https://www . geesforgeks . org/如何创建用户定义类类型的 Java-hashmap/](https://www.geeksforgeeks.org/how-to-create-a-java-hashmap-of-user-defined-class-type/)

**先决条件:**[HashMap 的内部工作](https://www.geeksforgeeks.org/internal-working-of-hashmap-java/)、 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)
如果我们希望创建一个自己类的 HashMap，我们需要保证 HashMap 的键的 hashcode()不变就好像它发生了一样那么就不可能从 HashMap 得到键的对象值。

在运行时，JVM 处理每个对象的哈希代码，并赋予它兴趣。当我们改变一个对象的状态时，JVM 会再次计算它的哈希代码，这可能会导致内存泄漏。为了使事情正常工作，我们必须做的是确保键对象的状态更改不会更改对象的哈希代码，即**键必须正确地重写了 equals()和 hash code()方法，才能正常工作。**

这样做的方法之一是使关键对象**成为不可变的**。不变性允许您每次为一个键对象获取相同的 hashcode。这就是为什么像 String、Integer 或其他包装类这样的不可变类是一个不错的键对象申请者的主要动机。在这里了解更多信息- [如何使类不变？](https://www.geeksforgeeks.org/create-immutable-class-java/)

```
// Java example to create a Java HashMap
// of user-defined class type

import java.util.*;
import java.io.*;

// User defined class
public class CustomKeyObject {

    public static class Student {

        private int rollno;
        private String name;

        // Constructor
        public Student(int rollno, String name)
        {
            this.rollno = rollno;
            this.name = name;
        }

        public String getname()
        {
            return this.name;
        }

        public int getmarks()
        {
            return this.rollno;
        }

        public void setname(String name)
        {
            this.name = name;
        }

        public void setmarks(int rollno)
        {
            this.rollno = rollno;
        }

        // Overriding the hashcode() function
        @Override
        public int hashCode()
        {

            // uses roll no to verify the uniqueness
            // of the object of Student class

            final int temp = 14;
            int ans = 1;
            ans = temp * ans + rollno;
            return ans;
        }

        // Equal objects must produce the same
        // hash code as long as they are equal
        @Override
        public boolean equals(Object o)
        {
            if (this == o) {
                return true;
            }
            if (o == null) {
                return false;
            }
            if (this.getClass() != o.getClass()) {
                return false;
            }
            Student other = (Student)o;
            if (this.rollno != other.rollno) {
                return false;
            }
            return true;
        }
    }

    // main method
    public static void main(String[] args)
        throws NumberFormatException,
               IOException
    {
        HashMap<Student, String> map = new HashMap<>();

        Student one = new Student(1, "Geeks1"); // key1

        Student two = new Student(2, "Geeks2"); // key2

        // put keys in map
        map.put(one, one.getname());
        map.put(two, two.getname());

        // changing key state so that
        // hashcode() should be calculated again
        one.setname("Not Geeks1");
        two.setname("Not Geeks2");

        // still prints Geeks1
        System.out.println(map.get(one));

        // still prints Geeks1
        System.out.println(map.get(two));

        // try with newly created key with same Rollno
        Student three = new Student(1, "Geeks3");

        // we get Geeks1
        System.out.println(map.get(three));
    }

    // This code is contributed by Subhesh
}
```

**Output:**

```
Geeks1
Geeks2
Geeks1

```