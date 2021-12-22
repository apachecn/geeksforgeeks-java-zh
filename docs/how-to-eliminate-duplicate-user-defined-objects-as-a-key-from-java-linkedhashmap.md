# 如何从 Java LinkedHashMap 中消除重复的用户定义对象作为关键字？

> 原文:[https://www . geesforgeks . org/如何从 java-linkedhashmap/](https://www.geeksforgeeks.org/how-to-eliminate-duplicate-user-defined-objects-as-a-key-from-java-linkedhashmap/) 中消除重复的用户定义对象作为密钥

通过在用户定义对象上实现 [equals 和 hashcode](https://www.geeksforgeeks.org/equals-hashcode-methods-java/) 方法，可以从 Java [LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 中删除重复的用户定义对象作为关键字。

**例:**

```java
Input : LinkedHashMap = [{[Apple, 40], Kashmir}, {[Grapes, 80], Nashik}]
    Duplicate key = {[Grapes, 80], Delhi}
Output: LinkedHashMap = [{[Apple, 40], Kashmir}, {[Grapes, 80], Delhi}]
```

**语法:**

**等于()方法:**

```java
public boolean equals  (Object obj)

// This method checks if some other Object
// passed to it as an argument is equal to 
// the Object on which it is invoked.
```

**hashCode()方法:**T0】

下面是问题陈述的实现:

T3】JavaT5

```java
// Java Program to eliminate duplicate user defined
// objects as a key from Java LinkedHashMap
import java.util.*;
class Employee {
    private String name;
    private int id;
    // Constructor
    public Employee(String name, int id)
    {
        this.name = name;
        this.id = id;
    }

    // HashCode Method
    public int hashCode()
    {
        System.out.println("In hashcode method");
        int hashcode = 0;
        return hashcode;
    }

    // Equals Method
    public boolean equals(Object obj)
    {
        System.out.println("In equals method");
        if (obj instanceof Employee) {
            Employee emp = (Employee)obj;
            return (emp.name.equals(this.name)
                    && emp.id == this.id);
        }
        else {
            return false;
        }
    }

    // Getters and Setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public int getId() { return id; }
    public void setId(int id) { this.id = id; }
    public String toString()
    {
        return "Employee Id: " + id + "  Name: " + name;
    }
}

// Driver code
public class Duplicate_Value {
    public static void main(String a[])
    {

        // LinkedHashMap initialization
        LinkedHashMap<Employee, Integer> lhm
            = new LinkedHashMap<Employee, Integer>();

        // Adding entries in LinkedHashMap
        lhm.put(new Employee("John", 1020), 1);
        lhm.put(new Employee("Ravi", 1040), 2);
        lhm.put(new Employee("Jaya", 1030), 3);

        // Print LinkedHashMap
        for (Map.Entry<Employee, Integer> entry :
             lhm.entrySet()) {
            System.out.println(entry.getKey() + "=>"
                               + entry.getValue());
        }

        // Create duplicate entry
        Employee duplicate = new Employee("John", 1020);
        System.out.println("Inserting duplicate record...");
        // Add duplicate entry
        lhm.put(duplicate, 4);

        System.out.println("After insertion:");
        for (Map.Entry<Employee, Integer> entry :
             lhm.entrySet()) {
            System.out.println(entry.getKey() + "=>"
                               + entry.getValue());
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(1)