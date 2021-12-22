# Java 令牌

> 原文:[https://www.geeksforgeeks.org/java-tokens/](https://www.geeksforgeeks.org/java-tokens/)

一个**标记**是程序中对编译器有意义的最小元素。令牌可以分为以下几类:

1.  关键词
2.  标识符
3.  常数
4.  特殊符号
5.  经营者

1.  **[关键词](https://www.geeksforgeeks.org/list-of-all-java-keywords/) :** 关键词是编程语言中预先定义或保留的词。每个关键字都意味着在程序中执行特定的功能。因为关键字是编译器的参考名称，所以它们不能用作变量名，因为这样做，我们试图给关键字赋予一个不允许的新含义。 **Java** 语言支持以下关键词:

    ```
     abstract     assert      boolean      
    break        byte        case
    catch        char        class        
    const        continue    default
    do           double      else         
    enum         exports     extends
    final        finally     float        
    for          goto        if
    implements   import      instanceof   
    int          interface   long
    module       native      new          
    open         opens       package
    private      protected   provides     
    public       requires    return
    short        static      strictfp     
    super        switch      synchronized
    this         throw       throws       
    to           transient   transitive
    try          uses        void         
    volatile     while       with 
    ```

2.  **[Identifiers](https://www.geeksforgeeks.org/java-identifiers/): **Identifiers are used as the general terminology for naming of variables, functions and arrays. These are user-defined names consisting of an arbitrarily long sequence of letters and digits with either a letter or the underscore(_) as a first character. Identifier names must differ in spelling and case from any keywords. You cannot use keywords as identifiers; they are reserved for special use. Once declared, you can use the identifier in later program statements to refer to the associated value. A special kind of identifier, called a statement label, can be used in goto statements.

    **有效标识符示例:**

    ```
    MyVariable
    MYVARIABLE
    myvariable
    x
    i
    x1
    i1
    _myvariable
    $myvariable
    sum_of_array
    geeks123
    ```

    **无效标识符示例:**

    ```
    My Variable  // contains a space
    123geeks   // Begins with a digit
    a+c // plus sign is not an alphanumeric character
    variable-2 // hyphen is not an alphanumeric character
    sum_&_difference // ampersand is not an alphanumeric character

    ```

3.  **[Constants/Literals](https://www.geeksforgeeks.org/literals-in-java/): **Constants are also like normal variables. But, the only difference is, their values can not be modified by the program once they are defined. Constants refer to fixed values. They are also called as literals.

    常量可以属于任何数据类型。
    **语法:**

    ```
    final data_type variable_name;
    ```

4.  **特殊符号:**以下特殊符号在 Java 中使用，有一些特殊含义，因此不能用于其他目的。

    ```
    [] () {}, ; * =
    ```

    *   **括号[]:** 左右括号作为数组元素引用。这些表示单一和多维下标。
    *   **括号():**这些特殊符号用来表示函数调用和函数参数。
    *   **大括号{}:** 这些开始和结束的大括号标记了包含多个可执行语句的代码块的开始和结束。
    *   **逗号(，:**用于分隔多个语句，就像分隔函数调用中的参数一样。
    *   **分号:**它是一个运算符，本质上调用一个叫做初始化列表的东西。
    *   **星号(*):** 用于创建指针变量。
    *   **赋值运算符:**用于赋值。
5.  **[运算符](https://www.geeksforgeeks.org/operators-in-java/) :** Java 提供了多种类型的运算符，可以根据需要使用。它们根据提供的功能进行分类。有些类型是-
    1.  [算术运算符](#Arithmetic Operators)
    2.  [一元运算符](#Unary Operators)
    3.  [赋值运算符](#Assignment Operator)
    4.  [关系运算符](#Relational Operators)
    5.  [逻辑运算符](#Logical Operators)
    6.  [三元运算符](#Ternary Operator)
    7.  [按位运算符](#Bitwise Operators)
    8.  [轮班操作员](#Shift Operators)
    9.  [操作员实例](#instance of Operator)
    10.  [优先和结合](#Precedence and Associativity)