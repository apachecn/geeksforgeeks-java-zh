# 使用字符文字存储转义序列的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到存储-转义序列-使用字符文字/](https://www.geeksforgeeks.org/java-program-to-store-escape-sequence-using-character-literals/)

一个[转义序列](https://www.geeksforgeeks.org/escape-sequences-in-java/)是一个字符或一个字符序列，其目的是实现那些他们不从字面上表示的字符，否则这些字符可能无法表示。这类字符的一些例子包括**退格、** **换行符**、**水平或垂直制表符**，等等。在 java 中，这些序列由反斜杠“\”前面的**表示，属于**字符数据类型。**Java 中共有 **8 个转义序列**。它们如下所示:**

```
**Tab : '\t'**
**Newline : '\n'**
**Backspace : '\b'**
**Form feed : '\f'**
**Carriage return : '\r'**
**Backslash : '\\'**
**Single quote : '\''**
**Double quote : '\"'** 
```

**1。类型铸造:** [类型铸造](https://www.geeksforgeeks.org/type-conversion-java-examples/)是将一个**原始数据类型**转换为**另一个**的概念。类型铸造有两种类型:

*   **Widening or automatic type casting** : In this process, a primitive data type with lower priority will be automatically converted to another primitive data type with higher priority. For example, the conversion from **int** to **double** .
*   **Reduction or explicit type conversion** : This is the process of converting the original data type with higher priority into the original data type with lower priority. For example, the conversion from **int** to **char** .

我们将在这里使用显式类型转换。更具体地说，从 **int** 到 **char** 的类型转换。

**2。ASCII 码:** ASCII 码用于用数字表示字符。这是一个统一的系统，允许计算机解释所有的字符。ASCII 代表**美国信息交换标准代码**。例如，字符的 ASCII 码为 **97** 。

有 **2 种方法**我们可以在 Java 中用字符文字存储转义序列。它们如下所示:

1.  **By using explicit type conversion**

将转义序列的 ASCII 码转换为字符文字，在单引号内使用正常转义序列

**方法 1:**

在这种方法中，我们使用最简单的方法，即直接将转义序列存储为字符文字。

**CODE:**

## Java

```
// Java code to store escape sequences
// as character literals

class StoreCharacterLiterals {

    // the method to print the escape
    // sequences
    static void escapeSequences()
    {
        // declaration of Character
        // literals
        char tab = '\t', backspace = '\b', newline = '\n',
             formFeed = '\f', carriageReturn = '\r',
             singleQuote = '\'', doubleQuote = '\"',
             backSlash = '\\';

        // printing the horizontal tab
        System.out.println("This" + tab + " is an "
                           + "implementation of tab");

        // implementing the backspace
        System.out.println("This" + backspace + " is an "
                           + "implementation "
                           + "of backspace");

        // implementing the newline
        System.out.println("This" + newline + " is an "
                           + "implementation of newline");

        // implementing the formfeed
        System.out.println("This" + formFeed + " is an"
                           + " implementation of "
                           + "formfeed");

        // implementing the carriage return
        System.out.println("This" + carriageReturn
                           + " is an implementation "
                           + "of Carriage Return");

        // printing the single quote
        System.out.println("This" + singleQuote
                           + " is an implementation"
                           + " of single quote");

        // printing the double quote
        System.out.println("This" + doubleQuote
                           + " is an implementation "
                           + "of double quote");

        // printing the backslash
        System.out.println("This" + backSlash
                           + " is an implementation "
                           + " of backslash");
    }

    // Driver Code
    public static void main(String[] args)
    {
        // creating an object of the class
        StoreCharacterLiterals ob = new StoreCharacterLiterals();

        // calling the escapeSequences() method
        ob.escapeSequences();
    }
}
```

**输出**

```
This     is an implementation of tab
Thi is an implementation of backspace
This
 is an implementation of newline
This
     is an implementation of formfeed
 is an implementation of Carriage Return
This' is an implementation of single quote
This" is an implementation of double quote
This\ is an implementation  of backslash

```

**方法 2:**

按照这种方法，我们使用**显式类型转换**从 **int** 到 **char** 来存储字符文本中的转义序列。

## Java

```
// Java code to store escape sequences
// as character literals

class StoreCharacterLiterals {

    // the method to print the escape
    // sequences
    static void escapeSequences()
    {

        // declaration of Character
        // literals using their ASCII codes
        // ASCII code for tab : 9
        // ASCII code for backspace : 8
        // ASCII code for newline : 10
        // ASCII code for formfeed : 12
        // ASCII code for carriage return : 13
        // ASCII code for single quote : 39
        // ASCII code for double quote : 34
        // ASCII code for backslash : 92
        char tab = 9, backspace = 8, newline = 10,
             formFeed = 12, carriageReturn = 13,
             singleQuote = 39, doubleQuote = 34,
             backSlash = 92;

        // printing the horizontal tab
        System.out.println("This" + tab + " is an "
                           + "implementation of tab");

        // implementing the backspace
        System.out.println("This" + backspace + " is an "
                           + "implementation "
                           + "of backspace");

        // implementing the newline
        System.out.println("This" + newline + " is an "
                           + "implementation of newline");

        // implementing the formfeed
        System.out.println("This" + formFeed + " is an"
                           + " implementation of "
                           + "formfeed");

        // implementing the carriage return
        System.out.println("This" + carriageReturn
                           + " is an implementation "
                           + "of Carriage Return");

        // printing the single quote
        System.out.println("This" + singleQuote
                           + " is an implementation"
                           + " of single quote");

        // printing the double quote
        System.out.println("This" + doubleQuote
                           + " is an implementation "
                           + "of double quote");

        // printing the backslash
        System.out.println("This" + backSlash
                           + " is an implementation "
                           + " of backslash");
    }

    // Driver Code
    public static void main(String[] args)
    {
        // creating an object of the class
        StoreCharacterLiterals ob = new StoreCharacterLiterals();

        // calling the escapeSequences() method
        ob.escapeSequences();
    }
}
```

**输出**

```
This     is an implementation of tab
Thi is an implementation of backspace
This
 is an implementation of newline
This
     is an implementation of formfeed
 is an implementation of Carriage Return
This' is an implementation of single quote
This" is an implementation of double quote
This\ is an implementation  of backslash
```

**注意:**在控制台(Windows)或终端(Ubuntu)运行代码。他在控制台上为 **\b** 编码输出。更多信息，请阅读:[https://stackoverflow . com/questions/3328824/Java-退格-转义](https://stackoverflow.com/questions/3328824/java-backspace-escape)