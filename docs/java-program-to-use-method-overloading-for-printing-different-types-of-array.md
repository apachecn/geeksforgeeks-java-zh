# Java 程序使用方法重载打印不同类型的数组

> 原文:[https://www . geesforgeks . org/Java-程序到使用方法-重载打印-不同类型的数组/](https://www.geeksforgeeks.org/java-program-to-use-method-overloading-for-printing-different-types-of-array/)

在[中，Java 方法重载](https://www.geeksforgeeks.org/overloading-in-java/)可以定义为包含多个同名方法的类，但参数列表或参数类型或方法的参数顺序不应相同。我们可以使用 java 中的方法重载打印不同类型的数组，方法是确保该方法包含具有相同方法名的不同参数。

让我们用三次重载的 printArray()方法实现一个程序，以打印不同类型的数组。而且每次函数都有不同的参数。在主方法中，为每个数组提供所需的输入，然后通过调用它们各自的方法将数组打印在屏幕上。

实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Use Method Overloading
// for Printing Different Types of Array
class methodOverloadingDemo {

    // creating a method for printing integer
    // array with integer parameter
    public static void printArray(Integer[] arr)
    {
        System.out.println("\nThe Integer array is: ");

        // for loop for printing the elements of array
        for (Integer i : arr)
            System.out.print(i + " ");
        System.out.println();
    }

    // overloading the above created method with different
    // parameter method contains a character parameter
    public static void printArray(Character[] arr)
    {
        System.out.println("\nThe Character array is: ");

        // for loop for printing the elements of array
        for (Character i : arr)
            System.out.print(i + " ");
        System.out.println();
    }

    // now the parameter for the overloaded method is String
    public static void printArray(String[] arr)
    {
        System.out.println("\nThe String array is: ");

        // for loop for printing the elements of array
        for (String i : arr)
            System.out.print(i + " ");
        System.out.println();
    }

    // now the parameter for the overloaded method is double
    public static void printArray(Double[] arr)
    {
        System.out.println("\nThe Double array is: ");

        // for loop for printing the elements of array
        for (Double i : arr)
            System.out.print(i + " ");
    }

    // main function
    public static void main(String args[])
    {

        // calling the parameters of all the
        // methods and taking the inputs
        Integer[] iarr = { 2, 4, 6, 6, 8 };
        Character[] carr = { 'H', 'E', 'L', 'L', 'O' };
        String[] sarr
            = { "Ram", "Nidhi", "John", "Raju", "Sara" };
        Double[] darr
            = { 10.0123, 89.123, 65.132, 78.321, 1.798 };

        // calling the methods and printing the arrays
        printArray(iarr);
        printArray(carr);
        printArray(sarr);
        printArray(darr);
    }
}
```

**Output**

```
The Integer array is: 
2 4 6 6 8 

The Character array is: 
H E L L O 

The String array is: 
Ram Nidhi John Raju Sara 

The Double array is: 
10.0123 89.123 65.132 78.321 1.798 
```

**时间复杂度:** O(N)，其中 N 是数组的大小。