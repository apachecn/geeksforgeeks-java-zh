# 如何在 Java 中消除哈希表中的重复键？

> 原文:[https://www . geesforgeks . org/如何消除 java 哈希表中的重复键/](https://www.geeksforgeeks.org/how-to-eliminate-duplicate-keys-in-hashtable-in-java/)

[HashTable 类](https://www.geeksforgeeks.org/hashtable-in-java/)是 Java 中 Collection 框架的一部分，它与 HashMap 的唯一主要区别在于它是同步的。哈希表将键映射到值，即它在内部使用存储桶来存储键-值对，并且键-值对的对应存储桶由键的哈希代码确定。当使用哈希表时，我们指定任何用作键的对象和任何我们想要链接到该键的值。任何非空对象都可以用作键。

**概念:**T2【hashCode()方法

覆盖 [hashCode()](https://www.geeksforgeeks.org/equals-hashcode-methods-java/) 方法时，有一些事情需要保持警惕，如下所示:

1.  如果两个对象等于 equals()方法，那么当在这些对象上调用时，hashCode()应该为两者返回相同的值。
2.  虽然 hashCode()不必总是为根据 equals()方法不被认为相等的对象返回不同的值，但是应该记住冲突很少。
3.  每当在程序中的任何时刻对同一对象调用 hashCode()方法时，它都应该返回相同的值。

**方法:**为了使用任何用户定义的对象作为键，其对应的类应该实现 [hashCode()](https://www.geeksforgeeks.org/equals-hashcode-methods-java/) 方法和 [equals()](https://www.geeksforgeeks.org/overriding-equals-method-in-java/) 方法。因为哈希表使用这些方法来成功地存储和检索条目。

**实现:**让我们随机创建一个子类来演示名为*的教师类*。包含*教师身份证*和*教师姓名*。在这里，没有两个或两个以上的老师可以有相同的 id，但他们可能有相同的名字。这个逻辑我们将在教师课堂的 [*equals()*](https://www.geeksforgeeks.org/overriding-equals-method-in-java/) 方法中实现。此示例显示用户定义的对象可以用作哈希表中的键，并且可以避免任何重复的键。

**例 1:** 子类|教师类

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Sub-class
public class Teacher {

    // Member variables
    private int id;
    private String name;

    // Constructor
    public Teacher(int id, String name)
    {
        // This keyword to refer current object
        this.id = id;
        this.name = name;
    }

    // Remember : Can create own logic and implement
    // that in this method,but here

    // Supposed to use the already defined logic
    // which uses the "id" to generate a hash

    // Override hash code
    @Override public int hashCode()
    {
        final int prime = 31;
        int result = 1;
        result = prime * result + id;
        return result;
    }

    // Overriding the equals method
    // to compare the equality of two objects
    @Override public boolean equals(Object obj)
    {
        // Step 1: Checking whether its a same object
        if (this == obj)
            return true;

        // Step 2: Checking whether the object is null
        if (obj == null)
            return false;

        // Step 3: Checking the instance of the object
        // here we can also use the instance of operator
        if (getClass() != obj.getClass())
            return false;

        // Step 4:  If the two objects do not have the
        // same "id" then they are treated as unequal
        // objects
        Teacher other = (Teacher)obj;
        if (id != other.id)
            return false;
        return true;
    }

    // overriding toString()
    // to print the Teacher detail
    @Override public String toString()
    {
        return name + " (" + id + ")";
    }
}
```

**示例 2:** 创建驱动程序类

创建包含存储键值对的哈希表的驱动程序类。这里，如示例 1 所示，部门名称将作为该特定教师的值存储。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Driver class 

// Importing Hashtable and Set class from
// java.util package
import java.util.Hashtable;
import java.util.Set;

public class Gfg {

    // Main driver method
    public static void main(String args[])
    {

        // Creating a Hashtable object with key and value
        // key of type Teacher and
        // corresponding value of type string
        Hashtable<Teacher, String> table
            = new Hashtable<>();

        // Adding value to the hash table object
        // Custom inputs (4 inputs here)
        table.put(new Teacher(12, "Mrs. Shalini Singhal"),
                  "IT");
        table.put(new Teacher(58, "Mrs. Sunita Gupta"),
                  "IT");
        table.put(new Teacher(11, "Mr. Kailash Soni"),
                  "CS");
        // adding duplicate key
        table.put(new Teacher(12, "Mrs. Shalini Singhal"),
                  "IT");

        // Printing all the values
        // from the table creating a set of keys

        // Retrieving the keys from the keyset() method
        Set<Teacher> keys = table.keySet();

        // For-each loop to traverse and print
        // all the correspondong values
        for (Teacher t : keys) {

            // Printing all values from table from above
            // retrieved keys
            System.out.println(t + " ==> " + table.get(t));
        }
    }
}
```

**输出:**

```
Mrs. Shalini Singhal (12) ==> IT
Mr. Kailash Soni (11) ==>  CS
Mrs. Sunita Gupta (58) ==>  IT
```