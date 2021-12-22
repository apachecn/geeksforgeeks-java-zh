# Java 关系运算符示例

> 原文:[https://www . geesforgeks . org/Java-relational-operators-with-examples/](https://www.geeksforgeeks.org/java-relational-operators-with-examples/)

**运算符**构成了任何编程语言的基本构件。Java 也提供了许多类型的运算符，可以根据执行各种计算和函数的需要来使用，包括逻辑、算术、关系等。它们根据提供的功能进行分类。

**操作员类型:**

1.  [算术运算符](https://www.geeksforgeeks.org/java-arithmetic-operators-with-examples/)
2.  [一元运算符](https://www.geeksforgeeks.org/java-unary-operator-with-examples/)
3.  [赋值运算符](https://www.geeksforgeeks.org/java-assignment-operator-with-examples/)
4.  [关系运算符](https://www.geeksforgeeks.org/java-relational-operators-with-examples/)
5.  [逻辑运算符](https://www.geeksforgeeks.org/java-logical-operators-with-examples/)
6.  [三元运算符](https://www.geeksforgeeks.org/java-ternary-operator-with-examples/)
7.  [按位运算符](https://www.geeksforgeeks.org/bitwise-operators-in-java/)
8.  [轮班操作员](https://www.geeksforgeeks.org/bitwise-operators-in-java/)

**Java 关系运算符**是一堆二进制运算符，用于检查两个操作数之间的关系，包括相等、大于、小于等。它们在比较后返回一个布尔结果，广泛用于循环语句以及条件 if-else 语句等。表示关系运算符的一般格式是:

**语法:**

```
variable1 *relation_operator* variable2
```

让我们看看 Java 中的每一个关系运算符:

**运算符 1:‘等于’运算符(==)**

该运算符用于检查两个给定的操作数是否相等。如果左侧的操作数等于右侧的操作数，运算符返回 true，否则返回 false。

**语法:**

```
var1 == var2
```

插图:

```
var1 = "GeeksforGeeks"
var2 = 20
var1 == var2 results in false
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate equal to Operator

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initializing variables
        int var1 = 5, var2 = 10, var3 = 5;

        // Displaying var1, var2, var3
        System.out.println("Var1 = " + var1);
        System.out.println("Var2 = " + var2);
        System.out.println("Var3 = " + var3);

        // Comparing var1 and var2 and
        // printing corresponding boolean value
        System.out.println("var1 == var2: "
                           + (var1 == var2));

        // Comparing var1 and var3 and
        // printing corresponding boolean value
        System.out.println("var1 == var3: "
                           + (var1 == var3));
    }
}
```

**Output**

```
Var1 = 5
Var2 = 10
Var3 = 5
var1 == var2: false
var1 == var3: true
```

**运算符 2:‘不等于’运算符(！=)**

该运算符用于检查两个给定的操作数是否相等。它的功能与等于运算符相反。如果左侧的操作数不等于右侧的操作数，则返回 true，否则返回 false。

**语法:**

```
var1 != var2
```

插图:

```
var1 = "GeeksforGeeks"
var2 = 20

var1 != var2 results in true
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate No- equal-to Operator

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initializing variables
        int var1 = 5, var2 = 10, var3 = 5;

        // Displaying var1, var2, var3
        System.out.println("Var1 = " + var1);
        System.out.println("Var2 = " + var2);
        System.out.println("Var3 = " + var3);

        // Comparing var1 and var2 and
        // printing corresponding boolean value
        System.out.println("var1 == var2: "
                           + (var1 != var2));

        // Comparing var1 and var3 and
        // printing corresponding boolean value
        System.out.println("var1 == var3: "
                           + (var1 != var3));
    }
}
```

**Output**

```
Var1 = 5
Var2 = 10
Var3 = 5
var1 == var2: true
var1 == var3: false
```

**运算符 3:“大于”运算符(> )**

这将检查第一个操作数是否大于第二个操作数。当左侧的操作数大于右侧的操作数时，运算符返回 true。

**语法:**

```
var1 > var2
```

插图:

```
var1 = 30
var2 = 20

var1 > var2 results in true
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to Illustrate Greater than operator

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initializing variables
        int var1 = 30, var2 = 20, var3 = 5;

        // Displaying var1, var2, var3
        System.out.println("Var1 = " + var1);
        System.out.println("Var2 = " + var2);
        System.out.println("Var3 = " + var3);

        // Comparing var1 and var2 and
        // printing corresponding boolean value
        System.out.println("var1 > var2: " + (var1 > var2));

        // Comparing var1 and var3 and
        // printing corresponding boolean value
        System.out.println("var3 > var1: "
                           + (var3 >= var1));
    }
}
```

**Output**

```
Var1 = 30
Var2 = 20
Var3 = 5
var1 > var2: true
var3 > var1: false
```

**运算符 4:“小于”运算符(< )**

这将检查第一个操作数是否小于第二个操作数。当左侧的操作数小于右侧的操作数时，运算符返回 true。它的功能与大于运算符的功能相反。

**语法:**

```
var1 < var2
```

插图:

```
var1 = 10
var2 = 20

var1 < var2 results in true
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to Illustrate Less than Operator

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initializing variables
        int var1 = 10, var2 = 20, var3 = 5;

        // Displaying var1, var2, var3
        System.out.println("Var1 = " + var1);
        System.out.println("Var2 = " + var2);
        System.out.println("Var3 = " + var3);

        // Comparing var1 and var2 and
        // printing corresponding boolean value
        System.out.println("var1 < var2: " + (var1 < var2));

        // Comparing var2 and var3 and
        // printing corresponding boolean value
        System.out.println("var2 < var3: " + (var2 < var3));
    }
}
```

**Output**

```
Var1 = 10
Var2 = 20
Var3 = 5
var1 < var2: true
var2 < var3: false
```

**运算符 5:** **大于或等于(> =)**

这将检查第一个操作数是否大于或等于第二个操作数。当左侧的操作数大于或等于右侧时，运算符返回 true。

**语法:**

```
var1 >= var2
```

插图:

```
var1 = 20
var2 = 20
var3 = 10

var1 >= var2 results in true
var2 >= var3 results in true
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Greater than or equal to
// Operator

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initializing variables
        int var1 = 20, var2 = 20, var3 = 10;

        // Displaying var1, var2, var3
        System.out.println("Var1 = " + var1);
        System.out.println("Var2 = " + var2);
        System.out.println("Var3 = " + var3);

        // Comparing var1 and var2 and
        // printing corresponding boolean value
        System.out.println("var1 >= var2: "
                           + (var1 >= var2));

        // Comparing var2 and var3 and
        // printing corresponding boolean value
        System.out.println("var2 >= var3: "
                           + (var3 >= var1));
    }
}
```

**Output**

```
Var1 = 20
Var2 = 20
Var3 = 10
var1 >= var2: true
var2 >= var3: false
```

**运算符 6:** **小于或等于(< =)**

这将检查第一个操作数是否小于或等于第二个操作数。当左侧的操作数小于或等于右侧时，运算符返回 true。

**语法:**

```
var1 <= var2
```

插图:

```
var1 = 10
var2 = 10
var3 = 9

var1 <= var2 results in true
var2 <= var3 results in false
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Less
// than or equal to operator

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initializing variables
        int var1 = 10, var2 = 10, var3 = 9;

        // Displaying var1, var2, var3
        System.out.println("Var1 = " + var1);
        System.out.println("Var2 = " + var2);
        System.out.println("Var3 = " + var3);

        // Comparing var1 and var2 and
        // printing corresponding boolean value
        System.out.println("var1 <= var2: "
                           + (var1 <= var2));

        // Comparing var2 and var3 and
        // printing corresponding boolean value
        System.out.println("var2 <= var3: "
                           + (var2 <= var3));
    }
}
```

**Output**

```
Var1 = 10
Var2 = 10
Var3 = 9
var1 <= var2: true
var2 <= var3: false
```