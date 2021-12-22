# Java–用示例覆盖协变方法

> 原文:[https://www . geeksforgeeks . org/Java-协变-方法-用示例覆盖/](https://www.geeksforgeeks.org/java-covariant-method-overriding-with-examples/)

Java 5 中实现的协变方法重写方法通过使您能够返回被重写方法的实际返回类型的子类型，有助于删除客户端类型转换。

协变方法重写意味着当重写子类中的方法时，返回类型可能会有所不同。在 java 5 之前，如果子类中的返回类型改变了，就不允许重写任何函数。但是现在有可能只有返回类型是子类型类。

重写协变方法为您提供了一种返回被重写方法的实际返回类的子类型的方法。它有助于消除程序员的类型转换负担。当重写方法返回对象时，通常使用此方法。

让我们举个例子来理解它。函数 clone()返回类对象的对象。但是由于每个类都是对象类的子类，所以我们将返回自己类的对象。假设协变机制的首要概念还没有实现。那我们还是要投对象。如果不使用强制转换，则会出现“对象无法转换为学生”的错误。

**例 1:**

## Java

```
// Covariant Method Overriding of Java
import java.util.ArrayList;
// Student class
class Student implements Cloneable {
    int rollNo;
    String className;
    String name;

    // Getters and setters
    public int getRollNo() { return rollNo; }
    public void setRollNo(int rollNo)
    {
        this.rollNo = rollNo;
    }
    public String getClassName() { return className; }
    public void setClassName(String className)
    {
        this.className = className;
    }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    // Class constructor
    public Student(int rollNo, String className,
                   String name)
    {
        this.rollNo = rollNo;
        this.className = className;
        this.name = name;
    }

    // Print method
    public void printData()
    {
        System.out.println("Name : " + name
                           + ", RollNo: " + rollNo
                           + ", Class Name : " + className);
    }

    // Override the clone method
    @Override
    public Object clone() throws CloneNotSupportedException
    {
        return super.clone();
    }
}

// Driver code
public class GFG {
    public static void main(String arg[])
        throws CloneNotSupportedException
    {
        // new student object created
        Student student1 = new Student(1, "MCA", "Kapil");
        student1.printData();

        // Student object created using clone method
        // assuming type casting is required
        Student student2 = (Student)student1.clone();
        student2.setName("Sachin");
        student2.setRollNo(2);
        student2.printData();
    }
}
```

**输出**

```
Name : Kapil, RollNo: 1, Class Name : MCA
Name : Sachin, RollNo: 2, Class Name : MCA

```

在上面的例子中，当我们使用 clone()方法时，它返回 object 类的对象，然后我们将其类型转换为 Student 类。

```
Student student2 = (Student) student1.clone();
```

假设我们在程序中使用了 10 次 clone 方法，那么我们每次都需要输入它。我们应该超越协变方法来解决这些类型的问题。我们将使用协变的概念返回学生类的对象，而不是对象类。

让我们看看如何使用它。

**例 2:**

## Java

```
// Covariant Method Overriding of Java
import java.util.ArrayList;
// Student class
class Student implements Cloneable {
    int rollNo;
    String className;
    String name;

    // Getters and setters
    public int getRollNo() { return rollNo; }
    public void setRollNo(int rollNo)
    {
        this.rollNo = rollNo;
    }
    public String getClassName() { return className; }
    public void setClassName(String className)
    {
        this.className = className;
    }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    // Class constructor
    public Student(int rollNo, String className,
                   String name)
    {
        this.rollNo = rollNo;
        this.className = className;
        this.name = name;
    }

    // Print method
    public void printData()
    {
        System.out.println("Name : " + name
                           + ", RollNo: " + rollNo
                           + ", Class Name : " + className);
    }

    // Override the clone method
    @Override
    public Student clone() throws CloneNotSupportedException
    {
        return (Student) super.clone();
    }
}

// Driver code
public class GFG {
    public static void main(String arg[])
        throws CloneNotSupportedException
    {
        // new student object created
        Student student1 = new Student(1, "MCA", "Kapil");
        student1.printData();

        // Student object created using clone method
        Student student2 = student1.clone();
        student2.setName("Sachin");
        student2.setRollNo(2);
        student2.printData();
    }
}
```

**输出**

```
Name : Kapil, RollNo: 1, Class Name : MCA
Name : Sachin, RollNo: 2, Class Name : MCA

```

我们可以在上面看到，因为我们返回的是一个 Student 类对象，而不是 object 类，所以我们不需要将从 clone()方法返回的对象键入 Student。