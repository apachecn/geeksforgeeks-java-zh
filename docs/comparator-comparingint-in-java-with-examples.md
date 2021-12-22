# 比较器比较 Java 中的 Int()和示例

> 原文:[https://www . geesforgeks . org/comparator-comparingint-in-Java-with-examples/](https://www.geeksforgeeks.org/comparator-comparingint-in-java-with-examples/)

**comparingInt([Java . util . function . ToIntFunction](https://www.geeksforgeeks.org/tointfunction-interface-in-java-with-examples/))**方法接受一个函数作为参数，该函数从类型 T 中提取一个 int 排序关键字，并返回一个按该排序关键字进行比较的比较器。如果指定的函数也是可序列化的，则返回的比较器是可序列化的。

**语法:**

```java
static <T> Comparator<T> comparingInt(ToIntFunction <T> keyExtractor)

```

**参数:**该方法接受单个参数**键提取器**，该函数用于提取整数排序键。

**返回值:**该方法返回一个比较器，通过提取的键进行比较

**异常:**如果参数为空，此方法将引发 NullPointerException。

下面的程序说明了 comparingInt(Java . util . function . to intfunction)方法:
**程序 1:**

```java
// Java program to demonstrate
// Comparator.comparingInt(java.util.function.ToIntFunction)  method

import java.util.Arrays;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
public class GFG {
    public static void main(String[] args)
    {

        // create some user objects
        User u1 = new User("Aaman", 25);
        User u2 = new User("Joyita", 22);
        User u3 = new User("Suvam", 28);
        User u4 = new User("mahafuj", 25);

        // before sort
        List<User> list
            = Arrays.asList(u2, u1, u4, u3);
        System.out.println("Before Sort:");
        list.forEach(User
                     -> System.out.println("User age "
                                           + User.getAge()));

        Collections.sort(list,
                         Comparator.comparingInt(
                             User::getAge));
        System.out.println("\nAfterSort:");
        list.forEach(User
                     -> System.out.println("User age "
                                           + User.getAge()));
    }
}
class User implements Comparable<User> {
    public String name;
    public int age;

    public User(String name, int age)
    {
        this.name = name;
        this.age = age;
    }

    public int compareTo(User u1)
    {
        return name.compareTo(u1.name);
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
    public String toString()
    {
        return "User [name=" + name
            + ", age=" + age + "]";
    }
}
```

打印在集成开发环境控制台上的输出如下所示。
**输出:**
![](img/0bab8f2794b4adfec67e89193ff2e21e.png)

**程序 2:**

```java
// Java program to demonstrate
// Comparator.comparingInt(java.util.function.ToIntFunction)  method

import java.util.Arrays;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
public class GFG {
    public static void main(String[] args)
    {

        // before sort
        List<Order> list = Arrays.asList(
            new Order("A382y482y48", 320),
            new Order("Vvekhfbkje2", 242),
            new Order("efkhfbekjfbe", 1345),
            new Order("bhdhdfaddvad", 230),
            new Order("abkasbcjabjc", 100));
        System.out.println("Before Sort:");
        list.forEach(order -> System.out.println(order));

        Collections.sort(list,
                         Comparator.comparingInt(
                             Order::getValue));
        System.out.println("\nAfter Sort:");
        list.forEach(order -> System.out.println(order));
    }
}
class Order implements Comparable<Order> {
    public String orderNo;
    public int value;

    public int compareTo(Order o1)
    {
        return orderNo.compareTo(o1.orderNo);
    }

    public Order(String orderNo, int value)
    {
        super();
        this.orderNo = orderNo;
        this.value = value;
    }

    @Override
    public String toString()
    {
        return "Order [orderNo=" + orderNo
            + ", value=" + value + "]";
    }

    public String getOrderNo()
    {
        return orderNo;
    }

    public void setOrderNo(String orderNo)
    {
        this.orderNo = orderNo;
    }

    public int getValue()
    {
        return value;
    }

    public void setValue(int value)
    {
        this.value = value;
    }
}
```

控制台上打印的输出如下所示。
**输出:**
![](img/9ca9dc80228c5378649722985e576752.png)

**参考文献:**T2