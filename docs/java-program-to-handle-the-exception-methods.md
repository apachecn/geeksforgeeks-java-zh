# 处理异常方法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序处理异常的方法/](https://www.geeksforgeeks.org/java-program-to-handle-the-exception-methods/)

扰乱程序正常流程的不太可能发生的事件称为异常。Java 异常处理是一种面向对象的异常处理方式。当程序执行过程中出现错误时，会创建一个异常对象，该对象包含有关异常层次结构的信息以及调试所必需的其他信息。

**异常类型:**

*   选中的例外
*   未检查的异常

**处理异常:**

**例 1:**

我们被要求根据班级的平均表现向学校的每个班级分发巧克力。给我们两个等长的数组。一个数组包含每个盒子里巧克力的数量，第二个数组包含每个班级的学生数量。如果一个班级的平均成绩低于标准，他们没有资格获得任何巧克力，盒子里的巧克力数量将在所有其他盒子中平均分配。每个班级分别得到一盒巧克力。

所以要在一个班级的学生中分配巧克力的数量，我们必须将巧克力的数量除以班级的学生数量。假设一个班级的平均成绩低于标准，他们不会得到任何巧克力，该班级的学生人数将为零。在解决上述问题时，可以面对一个被零除的异常。为了克服它，我们可以使用 try-catch 块并要求用户更新给定的信息。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate Arithmetic Exception

class GFG {
    public static void main(String[] args)
    {
        // Number of chocolates in each box
        int chocolates[] = { 106, 145, 123, 127, 125 };

        // Number of students in class
        int students[] = { 35, 40, 0, 34, 60 };

        // Number of chocolates given to each student of a
        // particular class
        int numChoc[] = new int[5];
        try {
            for (int i = 0; i < 5; i++) {
                // Calculating the chocolates
                // to be distributed
                numChoc[i] = chocolates[i] / students[i];
            }
        }
        // Catching Divide by Zero Exception
        catch (ArithmeticException error) {
            System.out.println("Arithmetic Exception");
            System.out.println(error.getMessage()
                               + " error.");
        }
    }
}
```

**Output**

```
Arithmetic Exception
/ by zero error.

```

**例 2:**

Java 有一个强大的错误处理机制，允许我们使用不同的捕获块在一个尝试块中处理多个异常。java 中的 Catch 块类似于 if-else 语句，当异常发生时，这些语句将变为活动的。当异常发生时，程序将生成的异常对象与 catch 块中指定的异常进行比较。程序检查第一个 catch 块，然后继续执行其他操作，直到生成的异常匹配。如果没有匹配的 catch 块，程序将暂停，并在控制台引发异常。

在 try 块中生成异常后，控制立即转移到 catch 块，try 块将不再执行。通过更改数组的大小，或者将数组 2 中的某个元素更改为零，或者初始化应答数组，来修改下面的代码，以便更好地理解 Java 异常处理。

下面的代码说明了如何在单个 try 块中处理各种类型的错误。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Handle Various Exceptions

class GFG {
    public static void main(String[] args)
    {
        // Array1 Elements
        int[] array1 = { 2, 4, 6, 7, 8 };

        // Array2 Elements
        int[] array2 = { 1, 2, 3, 4, 5 };
        // Initialized to null value
        int[] ans = null;
        try {
            for (int i = 0; i < 5; i++) {
                ans[i] = array1[i] / array2[i];
                // Generates Number Format Exception
                Integer.parseInt("Geeks for Geeks");
            }
        }
        catch (ArithmeticException error) {
            System.out.println(
                "The catch block with Arithmetic Exception is executed");
        }
        catch (NullPointerException error) {
            System.out.println(
                "The catch block with Null Pointer Exception is executed");
        }
        catch (ArrayIndexOutOfBoundsException error) {
            System.out.println(
                "The catch block with Array Index Out Of Bounds Exception is executed");
        }
        catch (NumberFormatException error) {
            System.out.println(
                "The catch block with Number Format Exception is executed");
        }
        // Executes when an exception which
        // is not specified above occurs
        catch (Exception error) {
            System.out.println(
                "An unknown exception is found "
                + error.getMessage());
        }

        // Executes after the catch block
        System.out.println("End of program");
    }
}
```

**Output**

```
The catch block with Null Pointer Exception is executed
End of program

```