# Java 中数组和字符串的区别

> 原文:[https://www . geesforgeks . org/Java 中数组和字符串的区别/](https://www.geeksforgeeks.org/difference-between-array-and-string-in-java/)

[数组](https://www.geeksforgeeks.org/arrays-in-java/)是存储在连续存储单元中的相似类型元素的集合。数组可以包含基元(int、char 等)以及类的对象(非基元)引用，这取决于数组的定义。在原始数据类型的情况下，实际值存储在连续的内存位置，而在类对象的情况下，[实际对象存储在堆段](https://www.geeksforgeeks.org/g-fact-46/)中。在 Java 中，所有数组都是动态分配的。数组的大小必须由 int 值指定，不能是长的或短的。数组索引从 0 开始，一直到 n-1，其中 n 是数组的长度。

**数组声明语法:**

```
type var-name[]'
OR
type[] var-name;
```

数组声明有两个组成部分:类型和变量名称。*类型*声明数组的元素类型。元素类型决定了组成数组的每个元素的数据类型。*变量名称*声明数组变量的名称。像 int 类型的数组一样，我们也可以创建其他原始数据类型的数组，如 char、float、double…等。

**示例:**

```
// both are valid declarations
int intArray[]
or int[] intArray

byte byteArray[]
short shortArray[]
boolean booleanArray[]
float floatArray[]
double doubleArray[]
char charArray[]

// An array of references to object of
// the class MyClass (a class created by 
// user)
MyClass myClassArray[];

// Array of object
Object[] arrayObject,

// Array of collection of unknown type
Collection[] collectionObject
```

**在 Java 中实例化数组**

当一个数组被声明时，只创建一个引用。为了实际创建一个数组或为其提供内存，我们可以创建一个如下所示的数组:

```
var-name = new type[size];
```

这里， *type* 指定正在分配的数据类型， *siz* e 指定数组中的元素个数， *var-name* 是数组变量的名称。

**示例:**

```
// Declaring an array
int intArray[]

// Allocating memory to array
int Array = new int[10];
```

运筹学

```
// Combining both statements in one
int[] intArray = new int[10];
```

**使用 for 循环访问 Java 数组元素**

数组中的每个元素都是通过其索引来访问的。索引以 0 开始，以(数组大小)–1 结束。一个数组的所有元素都可以使用 Java [进行循环](https://www.geeksforgeeks.org/loops-in-java/)来访问。

```
// Accessing the elements of the specified array
for(int i = 0; i < arr.length; i++)
   System.out.println("Element at index" + i + ": " + arr[i]);
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate creating an array
// of integers, put some values in the array,
// and prints each value to standard output
class GFG {
    public static void main(String args[])
    {
        // Declaring an Array of integers
        int[] arr;

        // Allocating memory for 5 integers
        arr = new int[5];

        // Initialize the first element of the array
        arr[0] = 10;
        // Initialize the second element of the array
        arr[1] = 20;

        // So on...
        arr[2] = 30;
        arr[3] = 40;
        arr[4] = 50;

        // Accessing the elements of the specified array
        for (int i = 0; i < arr.length; i++)
            System.out.println("Element at index " + i
                               + " : " + arr[i]);
    }
}
```

**Output**

```
Element at index 0 : 10
Element at index 1 : 20
Element at index 2 : 30
Element at index 3 : 40
Element at index 4 : 50

```

[**弦**](https://www.geeksforgeeks.org/strings-in-java/) **:**

在 Java 中，字符串基本上被视为一个代表一系列字符的对象，但它不是一个基本类型。在 Java 中，字符串类用于创建和操作字符串。在字符串类中，提供了许多方法来对字符串执行不同的操作。因为数组是可变的(可以增长)，所以字符串在 Java 中是不可变的。每当对字符串进行更改时，就会创建一个全新的字符串。

以下是在 **Java 编程语言**中创建字符串的基本语法。

**语法:**

```
<String_Type> <string_variable> = 
"<sequence_of_string>";
```

运筹学

```
<String_Type> <string_variable> = 
<new> <String_Type>("<sequence_of_string>");
```

每当创建字符串对象时，都会创建两个对象——一个在堆区域中，一个在字符串常量池中，字符串对象引用总是指向堆区域对象。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate String
class GFG {
    public static void main(String args[])
    {
        // Creating a String without using new operator
        String str = "GeeksForGeeks";

        // Prints the String
        System.out.println("String str = " + str);

        // Creating a String using new operator
        String str1 = new String("GeeksForGeeks");

        // Prints the String
        System.out.println("String str1 = " + str1);
    }
}
```

**Output**

```
String str = GeeksForGeeks
String str1 = GeeksForGeeks

```

**数组和字符串的区别:**

<figure class="table">

| **序列号** | **阵列** | **弦** |
| 01. | 数组是存储相同数据类型的元素集合的数据结构。 | 字符串基本上被视为表示一系列字符的对象。数组 |
| 02. | 数组可以保存任何数据类型。 | 但是，字符串只能保存字符数据类型。 |
| 03. | 数组的元素存储在一个连续的内存位置。 | 字符串类包含一个指针，指向堆内存中存储字符串实际内容的部分。 |
| 04. | Java 数组不以空字符结束，数组的结束元素是数组的最后一个元素。 | 但是默认情况下，字符串在 Java 中以空(“\0”)字符结尾。 |
| 05. | 数组是可变的。 | 字符串是不可变的。 |
| 06. | 数组的长度是固定的。 | 字符串的大小不是固定的。 |

</figure>