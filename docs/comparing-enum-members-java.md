# 比较 Java 中的枚举成员

> 原文:[https://www.geeksforgeeks.org/comparing-enum-members-java/](https://www.geeksforgeeks.org/comparing-enum-members-java/)

**先决条件:**Java 中的[枚举](https://www.geeksforgeeks.org/enum-in-java/)、 [== vs 等于](https://www.geeksforgeeks.org/difference-equals-method-java/)

在 Java 中，[枚举](https://www.geeksforgeeks.org/enum-in-java/)是一种特殊的 Java 类型，用于定义常量的集合。更准确地说，Java 枚举类型是一种特殊的 Java 类。枚举可以包含常数、方法等。enum 可以定义为一组命名常量。

**枚举成员的比较有两种方式:**

*   通过使用==运算符
*   通过使用 equals()方法

equals 方法在内部使用==运算符来检查两个枚举是否相等。这意味着，您可以使用==和等于方法来比较枚举。但问题是，如果我们有两种方法来比较 enum 的两个成员，那么哪一种更好呢？

**两者==运算符和。equals()方法仅用于比较。但区别不大:**

*   ==运算符从不引发 NullPointerException，而。equals()方法可以引发 NullPointerException。
*   ==负责编译时的类型兼容性检查，而。equals()方法永远不会担心这两个参数的类型。

**为了更好的理解，我们来看看节目:**

```
// Java program to illustrate enum members comparison
class EnumDemo {
    public enum Day { MON,
                      TUE,
                      WED,
                      THU,
                      FRI,
                      SAT,
                      SUN }
    public static void main(String[] args)
    {
        Day d = null;

        // Comparing an enum member with null
        // using == operator
        System.out.println(d == Day.MON);

        // Comparing an enum member with null
        // using .equals() method
        System.out.println(d.equals(Day.MON));
    }
}
```

输出:

```
false
Exception in thread "main" java.lang.NullPointerException

```

**解释:**在上面的程序中，我们正在比较一个枚举成员和一个 null。当我们使用==运算符进行比较时，我们不会得到任何异常，而当我们使用。equals()方法，那么我们得到的是 NullPointerException。
因此我们可以得出结论，当我们使用==运算符进行枚举成员比较时，它不会抛出任何异常，但是。equals()方法引发异常。

**另一个例子:**

```
// Java program to illustrate enum members comparison
class EnumDemo {
    public enum Day { MON,
                      TUE,
                      WED,
                      THU,
                      FRI,
                      SAT,
                      SUN }
    public enum Month { JAN,
                        FEB,
                        MAR,
                        APR,
                        MAY,
                        JUN,
                        JULY }
    public static void main(String[] args)
    {
        // Comparing two enum members which are from different enum type
        // using == operator
        System.out.println(Month.JAN == Day.MON);

        // Comparing two enum members which are from different enum type
        // using .equals() method
        System.out.println(Month.JAN.equals(Day.MON));
    }
}
```

输出:

```
error: incomparable types: Month and Day

```

**说明:**在上面的程序中，我们正在比较一个枚举成员和另一个枚举成员。当我们使用。equals()方法进行比较，那么我们不会得到任何编译失败(CF)，而当我们使用==运算符时，我们会得到编译失败(CF)，表示“无与伦比的类型”。因此，我们可以得出结论，当我们使用==运算符进行枚举成员比较时，它会在编译时执行类型兼容性检查。equals()方法永远不会担心这两个参数的类型(对于不可比较的类型，它只会给出“false”)。