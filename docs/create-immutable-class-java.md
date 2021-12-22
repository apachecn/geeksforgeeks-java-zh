# 如何在 Java 中创建不可变类？

> 原文:[https://www.geeksforgeeks.org/create-immutable-class-java/](https://www.geeksforgeeks.org/create-immutable-class-java/)

java 中的不可变类意味着一旦一个对象被创建，我们就不能改变它的内容。在 Java 中，所有的[包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)(像整数、布尔、字节、短)和字符串类都是不可变的。我们也可以创建自己的不可变类。在继续之前，请仔细检查不变性的特征，以便在实现时有一个好的理解。以下是要求:

*   该类必须声明为 final，这样就不能创建子类。
*   类中的数据成员必须声明为私有，以便不允许直接访问。
*   类中的数据成员必须声明为 final，这样我们就不能在对象创建后更改它的值。
*   参数化构造函数应该初始化执行深度复制的所有字段，以便不能用对象引用修改数据成员。
*   应该在 getter 方法中执行对象的深度复制，以返回副本，而不是返回实际的对象引用)

> **注意:**不应该有设置器，或者更简单的说，不应该有改变实例变量值的选项。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Create An Immutable Class

// Importing required classes
import java.util.HashMap;
import java.util.Map;

// Class 1
// An immutable class
final class Student {

    // Member attributes of final class
    private final String name;
    private final int regNo;
    private final Map<String, String> metadata;

    // Constructor of immutable class
    // Parameterized constructor
    public Student(String name, int regNo,
                   Map<String, String> metadata)
    {

        // This keyword refers to current instance itself
        this.name = name;
        this.regNo = regNo;

        // Creating Map object with reference to HashMap
        // Declaring object of string type
        Map<String, String> tempMap = new HashMap<>();

        // Iterating using for-each loop
        for (Map.Entry<String, String> entry :
             metadata.entrySet()) {
            tempMap.put(entry.getKey(), entry.getValue());
        }

        this.metadata = tempMap;
    }

    // Method 1
    public String getName() { return name; }

    // Method 2
    public int getRegNo() { return regNo; }

    // Note that there should not be any setters

    // Method 3
    // User -defined type
    // To get meta data
    public Map<String, String> getMetadata()
    {

        // Creating Map with HashMap reference
        Map<String, String> tempMap = new HashMap<>();

        for (Map.Entry<String, String> entry :
             this.metadata.entrySet()) {
            tempMap.put(entry.getKey(), entry.getValue());
        }
        return tempMap;
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating Map object with reference to HashMap
        Map<String, String> map = new HashMap<>();

        // Adding elements to Map object
        // using put() method
        map.put("1", "first");
        map.put("2", "second");

        Student s = new Student("ABC", 101, map);

        // Calling the above methods 1,2,3 of class1
        // inside main() method in class2 and
        // executing the print statement over them
        System.out.println(s.getName());
        System.out.println(s.getRegNo());
        System.out.println(s.getMetadata());

        // Uncommenting below line causes error
        // s.regNo = 102;

        map.put("3", "third");
        // Remains unchanged due to deep copy in constructor
        System.out.println(s.getMetadata());
        s.getMetadata().put("4", "fourth");
        // Remains unchanged due to deep copy in getter
        System.out.println(s.getMetadata());
    }
}
```

**Output**

```
ABC
101
{1=first, 2=second}
{1=first, 2=second}
{1=first, 2=second}
```

在这个例子中，我们已经创建了一个名为 Student 的最终类。它有三个最终数据成员、一个参数化构造函数和 getter 方法。请注意，这里没有 setter 方法。另外，请注意，我们不需要对包装类型的数据成员执行深度复制或克隆，因为它们已经是不可变的了。
本文由 **Abhishree Shetty** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。