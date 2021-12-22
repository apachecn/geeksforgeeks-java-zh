# Java 中数据隐藏和抽象的区别

> 原文:[https://www . geesforgeks . org/Java 中数据隐藏和抽象的区别/](https://www.geeksforgeeks.org/difference-between-data-hiding-and-abstraction-in-java/)

[***抽象化***](https://www.geeksforgeeks.org/abstraction-in-java-2/) 是隐藏内部实现而只是突出服务的集合。这是通过使用抽象类和接口并进一步实现它们来实现的。一个物体区别于所有其他物体的唯一必要特征。只有重要的细节被强调，其余的都被用户或读者压制。

**抽象的现实例子**

> 通过使用自动柜员机图形用户界面屏幕，银行人员可以突出银行提供的一系列服务，而无需突出内部实施。

**抽象类型:**基本上有三种抽象类型

1.  过程抽象
2.  数据抽象
3.  控制抽象

**1。过程抽象:**从这个词本身来看，有一系列以函数形式出现的过程，它们依次跟随一个又一个过程，通过类来实现抽象。

**2。数据抽象:**从这个词本身来看，抽象是从描述一个对象的一组数据中实现的。

**3。控制抽象:**抽象是在编写程序时以包含对象细节的方式实现的。

**抽象优势:**

*   用户或社区可以实现安全性，因为内部实现没有亮点。
*   增强将变得非常容易，因为在不影响最终用户的情况下，用户可以在内部系统中执行任何类型的更改
*   它为最终用户非常方便地使用系统提供了更大的灵活性
*   它提高了应用程序的丰富性

**抽象的实现**:作为一个类实现，只表示重要的特质，不包含背景细节。仅提供必要的细节并隐藏其所有内部实现。下面是抽象的 java 实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program showing the working of abstraction

// Importing generic libraries
import java.io.*;

// Creating an abstract class
// demonstrate abstraction
abstract class Creature {

    // Just providing that creatures has legs
    // Hiding the number of legs
    abstract void No_Of_legs();
}

// A new child class is extending
// the parent abstract class above
class Elephant extends Creature {

    // Implementation of the abstract method
    void No_Of_legs()
    {

        // Printing message of function in non abstract
        // child class
        System.out.println("It has four legs");
    }
}

// Again a new child class is extended from parent
//  Human class to override function created above
class Human extends Creature {

    // Same function over-riden
    public void No_Of_legs()
    {

        // Message printed if this function is called or
        // Implementation of the abstract method
        System.out.println("It has two legs");
    }
}

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating human object showing the implementation
        Human ob = new Human();

        ob.No_Of_legs();

        // Creating object of above class in  main
        Elephant ob1 = new Elephant();

        // Calling the function in main by
        // creating object of above non abstract class
        ob1.No_Of_legs();
        // Implementation of abstraction
    }
}
```

**Output**

```
It has two legs
It has four legs
```

现在，跳到第二个概念，尽管这两个概念都用于实现[封装](https://www.geeksforgeeks.org/encapsulation-in-java/)，但不知何故，它们之间有一个圆滑的区别，如下所示:

***数据隐藏*** 是对外部用户隐藏内部数据。内部数据不应直接进入，即外部人员/类不能直接访问内部数据。这是通过使用访问说明符-私有修饰符来实现的。

**注意:T** 他给数据成员推荐的修改器是私有的。数据隐藏的主要优势是安全性

**数据隐藏示例:**

> 类别帐户{
> 
> 私人双账户 _ 余额；
> 
> ……..
> 
> …….
> 
> }
> 
> 在这里，每个员工的账户余额对于在同一组织工作的其他员工来说是私有的。没有人知道任何人的账户余额。在 java 中，这是通过使用关键字' private '关键字来实现的，这个过程称为数据隐藏。

它被用作安全性，因此没有身份验证就无法访问内部数据。未经授权的最终用户将无法访问内部数据。通过编程，我们可以通过将数据元素声明为私有来实现数据隐藏。现在要访问这些数据或进行修改，我们有一个特殊的方法，分别称为 getter setter。

Getter 用于访问私有数据，setter 仅在身份验证后用于修改私有数据。简单来说，就是对外部用户隐藏内部数据。

它被用作安全性，因此没有身份验证就无法访问内部数据。未经授权的最终用户将无法访问内部数据。通过编程，我们可以通过将数据元素声明为私有来实现数据隐藏。

***现在要访问这个数据或者进行修改，我们有一个特殊的方法分别称为***getter。

**数据隐藏涉及的概念:**获取器和设置器

Getter 用于访问私有数据，setter 仅在身份验证后用于修改私有数据。简单来说，就是对外部用户隐藏内部数据。它被用作安全性，因此没有身份验证就无法访问内部数据。未经授权的最终用户将无法访问内部数据。通过编程，我们可以通过将数据元素声明为私有来实现数据隐藏。现在要访问这些数据或进行修改，我们有一个特殊的方法，分别称为 getter setter。

Getter 用于访问私有数据，setter 仅在身份验证后用于修改私有数据。简单来说，就是对外部用户隐藏内部数据。它被用作安全性，因此没有身份验证就无法访问内部数据。未经授权的最终用户将无法访问内部数据。通过编程，我们可以通过将数据元素声明为私有来实现数据隐藏。

现在要访问这些数据或进行修改，我们有一个特殊的方法，分别称为 getter setter。Getter 用于访问私有数据，setter 仅在身份验证后用于修改私有数据。

**数据隐藏的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program showing working of data hiding

// Importing generic libraries
import java.io.*;

// Class created named Bank
class Bank {

    // Private data (data hiding)
    private long CurBalance = 0;

    // Bank_id is checked for authentication
    long bank_id;
    String name;

    // Getter function to modify private data
    public long get_balance(long Id)
    {

        // Checking whether the user is
        // authorised or unauthorised

        // Comparing bank_id of user and the give Id
        // then only it will get access
        if (this.bank_id == Id) {

            // Return current balance
            return CurBalance;
        }

        // Unauthorised user
        return -1;
    }
    // Setter function
    public void set_balance(long balance, long Id)
    {
        // Comparing bank_id of user and the give Id
        // then only it will get access
        if (this.bank_id == Id) {
            // Update balance in current ID
            CurBalance = CurBalance + balance;
        }
    }
}

// Another class created- Employee
public class Emp {
    public static void main(String[] args)
    {
        // Creating employee object of bank type
        Bank _emp = new Bank();

        // Assigning employee object values
        _emp.bank_id = 12345;
        _emp.name = "Roshan";

        // _emp.get_balance(123456)
        _emp.set_balance(10000, 12345);
        // This will no get access as bank_id is given wrong
        // so
        // unauthorised user is not getting access that is
        // data hiding

        long emp_balance = _emp.get_balance(12345);
        // As this time it is valid user it will get access

        // Display commands
        System.out.println("User Name"
                           + "  " + _emp.name);
        System.out.println("Bank_ID"
                           + "  " + _emp.bank_id);
        System.out.println("Current Balance"
                           + "  " + emp_balance);
    }
}
```

**输出:**

```
User Name Roshan
Bank_ID 12345
Current Balance 10000
```