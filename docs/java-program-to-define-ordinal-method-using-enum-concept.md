# 使用枚举概念定义序数()方法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-定义-序数-方法-使用-枚举-概念/](https://www.geeksforgeeks.org/java-program-to-define-ordinal-method-using-enum-concept/)

Java **枚举，**也称为 **Java 枚举**类型，是一种其字段由一组固定常数组成的类型。

**java.lang.Enum .序数()**讲述了**序数**(它是其**枚举**声明中的位置，其中初始常数被赋予零的序数)用于特定的枚举。

**序数()方法**是一个非静态的方法，它意味着它只能用类对象访问，如果我们试图访问另一个类的对象，它会给出错误。它是最终方法，不能被重写。

**语法:**

```
public final int ordinal();
```

**返回值:**

```
This method returns the ordinal of this enumeration constant.
```

> **枚举的默认值为 0** 并递增到枚举中存在的索引。
> 
> 比如我们在枚举类中声明了三个索引，那么枚举索引的序数()值是 0，1，2

**枚举默认顺序位置代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show the usage of
// ordinal() method of java enumeration

import java.lang.*;
 import java.util.*;

// enum showing Student details
enum Student {
   Rohit, Geeks,Author;
}

public class GFG {

   public static void main(String args[]) {

      System.out.println("Student Name:");

      for(Student m : Student.values()) {

         System.out.print(m+" : "+m.ordinal()+" ");
      }                   
   }
}
```

**Output**

```
Student Name:
Rohit : 0 Geeks : 1 Author : 2
```

我们还可以将该值存储到枚举中的索引中，但序号值将保持不变。它不会被改变。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show that the ordinal
// value remainw same whether we mention 
// index to the enum or not

import java.lang.*;
import java.util.*;

// enum showing Mobile prices
enum Student_id {

    james(3413),
    peter(34),
    sam(4235);
    int id;
    Student_id(int Id) { id = Id; }
    public int show() { return id; }
}

public class GFG {

    public static void main(String args[])
    {

        // printing all the default ordinary number for the
        // enum index
        System.out.println("Student Id List: ");

        for (Student_id m : Student_id.values()) {
            System.out.print(m + " : " + m.ordinal() + " ");
        }

        System.out.println();

        System.out.println("---------------------------");

        for (Student_id id : Student_id.values()) {

            // printing all the value stored in the enum
            // index
            System.out.print("student Name : " + id + ": "
                             + id.show());
            System.out.println();
        }
    }
}
```

**Output**

```
Student Id List: 
james : 0 peter : 1 sam : 2 
---------------------------
student Name : james: 3413
student Name : peter: 34
student Name : sam: 4235
```