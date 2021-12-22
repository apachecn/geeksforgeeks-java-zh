# Java 中的枚举

> 原文:[https://www.geeksforgeeks.org/enum-in-java/](https://www.geeksforgeeks.org/enum-in-java/)

枚举用于在编程语言中表示一组命名常数。例如，一副扑克牌中的 4 套花色可能是 4 个名为 Club、Diamond、Heart 和 Spade 的枚举数，属于名为花色的枚举类型。其他例子包括自然列举的类型(如行星、星期几、颜色、方向等。).
当我们在**编译时**知道所有可能的值时，使用枚举，例如菜单上的选择、舍入模式、命令行标志等。枚举类型中的常量集不必一直保持**固定不变**。

在 Java 中(从 1.5 开始)，枚举使用**枚举**数据类型来表示。Java 枚举比 [C/C++枚举](https://www.geeksforgeeks.org/enumeration-enum-c/)更强大。在 Java 中，我们还可以向其中添加变量、方法和构造函数。枚举的主要目的是定义我们自己的数据类型(枚举数据类型)。

**用 java 声明枚举:**

*   枚举声明可以在类外部或类内部完成，但不能在方法内部完成。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A simple enum example where enum is declared
// outside any class (Note enum keyword instead of
// class keyword)
enum Color
{
    RED, GREEN, BLUE;
}

public class Test
{
    // Driver method
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
    }
}
```

输出:

```
RED
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// enum declaration inside a class.
public class Test
{
    enum Color
    {
        RED, GREEN, BLUE;
    }

    // Driver method
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
    }
}
```

输出:

```
RED
```

*   枚举中的第一行应该是常量列表，然后是方法、变量和构造函数。
*   根据 [Java 命名约定](http://www.oracle.com/technetwork/java/codeconventions-135099.html)，建议我们用所有大写字母命名常量

**枚举的重要点:**

*   每个枚举都是通过使用类在内部实现的。

```
/* internally above enum Color is converted to
class Color
{
     public static final Color RED = new Color();
     public static final Color BLUE = new Color();
     public static final Color GREEN = new Color();
}*/
```

*   每个枚举常数代表一个枚举类型的**对象**。
*   枚举类型可以作为参数传递给 **switch** 语句。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program to demonstrate working on enum
// in switch case (Filename Test. Java)
import java.util.Scanner;

// An Enum class
enum Day
{
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY,
    THURSDAY, FRIDAY, SATURDAY;
}

// Driver class that contains an object of "day" and
// main().
public class Test
{
    Day day;

    // Constructor
    public Test(Day day)
    {
        this.day = day;
    }

    // Prints a line about Day using switch
    public void dayIsLike()
    {
        switch (day)
        {
        case MONDAY:
            System.out.println("Mondays are bad.");
            break;
        case FRIDAY:
            System.out.println("Fridays are better.");
            break;
        case SATURDAY:
        case SUNDAY:
            System.out.println("Weekends are best.");
            break;
        default:
            System.out.println("Midweek days are so-so.");
            break;
        }
    }

    // Driver method
    public static void main(String[] args)
    {
        String str = "MONDAY";
        Test t1 = new Test(Day.valueOf(str));
        t1.dayIsLike();
    }
}
```

输出:

```
Mondays are bad.
```

*   每个枚举常量总是隐式**公共静态最终**。由于它是**静态的**，我们可以使用枚举名称来访问它。既然是**决赛**，我们就不能创建子枚举。
*   我们可以在枚举内部声明 **main()方法**。因此，我们可以直接从命令提示符调用枚举。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program to demonstrate that we can have
// main() inside enum class.
enum Color
{
    RED, GREEN, BLUE;

    // Driver method
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
    }
}
```

输出:

```
RED
```

**枚举和继承:**

*   所有枚举都隐式扩展了 **java.lang.Enum 类**。因为一个类只能扩展 Java 中的一个父类**，所以枚举不能扩展其他任何东西。**
*   **toString()方法**在 **java.lang.Enum 类**中被覆盖，返回枚举常量名称。
*   enum 可以实现许多接口。

**值()，序数()和 valueOf()方法:**

*   这些方法存在于 **java.lang.Enum** 中。
*   **values()方法**可用于返回枚举中存在的所有值。
*   秩序在枚举中很重要。通过使用**序数()方法**，可以找到每个枚举常量索引，就像数组索引一样。
*   **valueOf()方法**返回指定字符串值的枚举常量(如果存在)。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of values(),
// ordinal() and valueOf()
enum Color
{
    RED, GREEN, BLUE;
}

public class Test
{
    public static void main(String[] args)
    {
        // Calling values()
        Color arr[] = Color.values();

        // enum with loop
        for (Color col : arr)
        {
            // Calling ordinal() to find index
            // of color.
            System.out.println(col + " at index "
                             + col.ordinal());
        }

        // Using valueOf(). Returns an object of
        // Color with given constant.
        // Uncommenting second line causes exception
        // IllegalArgumentException
        System.out.println(Color.valueOf("RED"));
        // System.out.println(Color.valueOf("WHITE"));
    }
}
```

输出:

```
RED at index 0
GREEN at index 1
BLUE at index 2
RED
```

**枚举和构造函数:**

*   enum 可以包含一个构造函数，并且在加载 enum 类时为每个 enum 常量单独执行。
*   我们不能显式创建枚举对象，因此不能直接调用枚举构造函数。

**枚举和方法:**

*   枚举可以包含**具体**方法和**抽象**方法。如果枚举类有一个抽象方法，那么枚举类的每个实例都必须实现它

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate that enums can have constructor
// and concrete methods.

// An enum (Note enum keyword inplace of class keyword)
enum Color
{
    RED, GREEN, BLUE;

    // enum constructor called separately for each
    // constant
    private Color()
    {
        System.out.println("Constructor called for : " +
        this.toString());
    }

    public void colorInfo()
    {
        System.out.println("Universal Color");
    }
}

public class Test
{   
    // Driver method
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
        c1.colorInfo();
    }
}
```

输出:

```
Constructor called for : RED
Constructor called for : GREEN
Constructor called for : BLUE
RED
Universal Color
```

**枚举的下一篇文章:**
[Java 中具有自定义值的枚举](https://www.geeksforgeeks.org/enum-customized-value-java/)

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。