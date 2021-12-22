# 关于 hashCode 和 equals 方法的有趣面试问题

> 原文:[https://www . geesforgeks . org/interest-interview-question-hashcode-equals-method/](https://www.geeksforgeeks.org/interesting-interview-question-hashcode-equals-method/)

**先决条件:**[Java 中的 equal 和 hashcode 方法](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)、[为什么要覆盖 Equal 和 Hashcode 方法](https://www.geeksforgeeks.org/override-equalsobject-hashcode-method/)

[hashCode 和 equals 方法](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)是 Java 面试中经常被问到的问题。一般来说，我们不会[覆盖这两种方法](https://www.geeksforgeeks.org/override-equalsobject-hashcode-method/)，但是当我们必须覆盖这两种方法时，会有一些场景/需求。当我们将用户定义的对象存储在使用哈希算法的集合类中时，就会出现这种情况。即 HashTable、HashSet 和 HashMap。

**面试问题:**创建一个包含每个员工地址的地图，并使用员工对象作为关键字。在此地图中存储一些员工的地址。现在创建一个方法，接受 Map 和 Employee 对象作为参数，并返回该雇员的地址。

**方法 1(不覆盖 hashCode 和 equals 方法)**

```java
// Java program to create a map of employee
// and address Without overriding
// hashCode and equals methods
import java.util.HashMap;
import java.util.Map;

class Employee {
private int empId;
private String name;

    public Employee(int empId, String name)
    {
        this.empId = empId;
        this.name = name;
    }

}

class Address {
private int houseNo;
private String streetName;
private String city;
private int pinCode;

    public Address(int houseNo, String streetName, 
                         String city, int pinCode)
    {
        this.houseNo = houseNo;
        this.streetName = streetName;
        this.city = city;
        this.pinCode = pinCode;
    }

    public String getAddress()
    {
        return houseNo + ", " + streetName +
                   ", " + city + ", " + pinCode;
    }
}

public class Test {
    public static String getAddress(Map map, Employee emp)
    {
        Address adrs = (Address)map.get(emp);
        return adrs.getAddress();
    }
    public static void main(String[] args)
    {

        Employee emp1 = new Employee(110, "Sajid Ali Khan");
        Address adrs1 = new Address(304, "Marol Mahrisi", 
                                         "Mumbai", 400069);

        Employee emp2 = new Employee(111, "Jaspreet Singh");
        Address adrs2 = new Address(203, "Seepz", "Mumbai", 
                                                 400093);

        Map<Employee, Address> map = new HashMap<>();
        map.put(emp1, adrs1);
        map.put(emp2, adrs2);

        System.out.println(Test.getAddress(map, new Employee(110, 
                                              "Sajid Ali Khan")));
    }
}
```

输出:

```java
Exception in thread "main" java.lang.NullPointerException
    at Test.getAddress(Test.java:44)
    at Test.main(Test.java:59)

```

我们期望输出是雇员的地址，但是我们得到了 NullPointerException，这是非常直接的。Map 中的新员工(110，“赛义德·阿里汗”)和争论中的新员工(110，“赛义德·阿里汗”)是两个不同的例子。因此我们得到了 NullPointRexception**，因为当我们进行 map.get(emp)时，它返回空值。**

**方法 2(覆盖 hashCode 和 equals 方法)**

```java
// Java program to create a map of employee
// and address using overriding
// hashCode and equals methods
import java.util.HashMap;
import java.util.Map;

class Employee {
private int empId;
private String name;

    public Employee(int empId, String name)
    {
        this.empId = empId;
        this.name = name;
    }

    @Override public int hashCode()
    {
        final int prime = 31;
        int result = 1;
        result = prime * result + empId;
        result = prime * result +
          ((name == null) ? 0 : name.hashCode());
        return result;
    }

    @Override public boolean equals(Object obj)
    {
        if (this == obj)
            return true;
        if (obj == null)
            return false;
        if (getClass() != obj.getClass())
            return false;
        Employee other = (Employee)obj;
        if (empId != other.empId)
            return false;
        if (name == null) {
            if (other.name != null)
                return false;
        } else if (!name.equals(other.name))
            return false;
        return true;
    }
}

class Address {
private int houseNo;
private String streetName;
private String city;
private int pinCode;

    public Address(int houseNo, String streetName, 
                        String city, int pinCode)
    {
        this.houseNo = houseNo;
        this.streetName = streetName;
        this.city = city;
        this.pinCode = pinCode;
    }

    public String getAddress()
    {
        return houseNo + ", " + streetName + ", " + 
                              city + ", " + pinCode;
    }

}

public class Test {
    public static String getAddress(Map map, Employee emp)
    {
        Address adrs = (Address)map.get(emp);
        return adrs.getAddress();
    }
    public static void main(String[] args)
    {
        Employee emp1 = new Employee(110, "Sajid Ali Khan");
        Address adrs1 = new Address(304, "Marol Mahrisi",
                                       "Mumbai", 400069);

        Employee emp2 = new Employee(111, "Jaspreet Singh");
        Address adrs2 = new Address(203, "Seepz", "Mumbai",
                                                  400093);

        Map<Employee, Address> map = new HashMap<>();
        map.put(emp1, adrs1);
        map.put(emp2, adrs2);

        System.out.println(Test.getAddress(map, new Employee(110, 
                                              "Sajid Ali Khan")));
    }
}
```

输出:

```java
304, Marol Mahrisi, Mumbai, 400069

```

我们得到了预期的输出，这是因为我们在代码中正确地覆盖了 hashCode 和 equals 方法。当我们执行 map.get(emp)时，它会在内部调用我们的重写 hashcode 方法，这将导致与在 map 中用作键的 employee 对象的 hashCode 相同的结果。

一旦找到右桶，将调用 equals 方法并匹配两个 Employee 对象的所有值。结果，我们得到了雇员对象的正确地址。

本文由**赛义德阿里汗**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。