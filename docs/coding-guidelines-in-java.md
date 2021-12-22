# Java 中的编码指南

> 原文:[https://www.geeksforgeeks.org/coding-guidelines-in-java/](https://www.geeksforgeeks.org/coding-guidelines-in-java/)

[Java](https://www.geeksforgeeks.org/java-tutorials/) 是目前最流行、应用最广泛的编程语言和平台之一。平台是一种有助于开发和运行用任何编程语言编写的程序的环境。Java 快速、可靠、安全。从桌面到网络应用，从科学超级计算机到游戏机，从手机到互联网，Java 被应用到每一个角落。

[![](img/fc2fde84664eb1a3e0545bd19c84467c.png)](https://www.geeksforgeeks.org/java-tutorials/)

在本文中，让我们了解一些有助于提高程序可读性的编码准则。

**为什么是编码指南？**

编码准则很重要，因为大部分软件成本都用于维护。此外，软件并不总是由一个开发人员开发的。因此，保持编写软件的惯例增加了程序的可读性。

很少有指导方针是:

1.  **[命名约定](https://www.geeksforgeeks.org/java-naming-conventions/) :** 我们在 java 编程中一般遵循 camel case 约定。这意味着所有的类和接口都应该是名词，大小写混合，每个内部单词的第一个字母大写。所有的方法都应该是动词，第一个字母小写，每个内部单词的第一个字母大写。变量应该是有意义的，并且必须避免一个字符的变量名。在大写的情况下定义一个常量变量。
2.  **花括号:**花括号用于定义类、方法和循环的主体。花括号的使用有两种标准格式，使用其中任何一种。
    *   大括号应用于启动类、方法、循环等的行的末尾。，右大括号本身在一行上，与第一行的开始垂直对齐。例如:

        ```
        class Geeksforgeeks {
            ... Geeksforgeeks(){
             // Constructor
                ...
            }

            int Geek(int a, float b){

                ... for (int i = 0; i < Field; i++){
                    ....
                }
            }
        }
        ```

    *   每个大括号都被添加到一个新的行中，并且这一对是垂直对齐的。这种格式的前面代码片段如下:

        ```
        class Geeksforgeeks 
        {
            ... Geeksforgeeks()
            { // Constructor
                ...
            }
            int Geek(int a, float b)
            {
                ... for (int i = 0; i < Field; i++)
                {
                    ....
                }...;
            }
        }
        ```

    *   左大括号后或右大括号前不应有空行。
3.  **缩进:**缩进的单位应为 4 个空格。制表位应该每 8 个空格设置一次。所有缩进必须由空格字符实现，并且制表符不能存在于结果源文件中。提高每行可读性的公认标准是:
    *   对垂直列表中相似的项目应用缩进(如行尾注释和声明中的标识符)。
    *   用空格包围二元运算符(包括赋值)。
    *   分号或逗号后加一个空格。
    *   在关键字(“if”、“while”、“return”、“catch”、“switch”、“for”)和后面的括号之间添加一个空格。
    *   多余的括号也有助于突出表达式的结构(但要避免使用过多的嵌套括号)。
    *   插入空行来区分代码的重要部分。
    *   让我们用一个代码来实现上述所有准则:

        ```
        class Geeksforgeeks {
            private int s;
            private double d;

            Geeksforgeeks()
            { // Constructor
                s = 1;
                d = 3.14;
            }

            int Geek(int a, float b)
            {
                // Must initialize local variables
                int l = 0; 
                float le = 1; 
                int n = 10;
                l = n - 2;
                le = l + b * 3;

                for (int i = 0; i < n; i++) {
                    l = l * 2;
                    l = l - n;
                }
                return l + a;
            }
        }
        ```

4.  **空格:**空格在可读性方面也起着主要作用，如下所示:
    *   [运算符](https://www.geeksforgeeks.org/operators-in-java/)应该用空格字符包围。例如:

        > 操作应写成:
        > **a =(b+ c)* d；**
        > 
        > 而不是像:
        > **a =(b+ c)* d**

    *   [Java 的保留字](https://www.geeksforgeeks.org/list-of-all-java-keywords/)后面要有空格。例如:

        > 循环必须初始化为:
        > 而(真){…}
        > 
        > 而不是作为:
        > 而（真){…}

    *   逗号后面应该有一个空格。例如:

        > 函数必须初始化为:
        > 好玩(a、b、c、d)；
        > 
        > 而不作为:
        > 好玩(a、b、c、d)；

    *   冒号应该用空格包围。例如:

        > 案语句必须初始化为:
        > 情况 100:断线；
        > 
        > 而不作为:
        > 情况 100:破；

    *   [for 语句中的分号](https://www.geeksforgeeks.org/role-of-semicolon-in-various-programming-languages/)后面应该跟一个空格字符。例如:

        > 为循环必须初始化为:
        > 为(I = 0；一<n；i++)
        > 
        > 而不作为:
        > 为(I = 0；一<n；i++)

5.  **[Comments](https://www.geeksforgeeks.org/comments-in-java/):** Java programs can have two types of comments. They are Implementation and Documentation. Comments should contain only the information that is relevant for reading and understanding the program. For example, information about how the package is built or in what directory it resides should not be included in the program as a comment.

    **实施意见:**实施意见以 **//** 为界。Java 还允许使用/*…*/进行实现注释。实现注释用于特定实现的注释或临时删除代码。程序可以有四种类型的实现注释:块、单行、尾随和临时删除代码。

    *   **块注释**用于提供文件、方法、数据结构和算法的描述。块注释可以用在每个文件的开头，每个方法之前或方法中。方法中的块注释应该缩进到与它们描述的代码相同的级别。块注释在其开始之前应该有一个空行，除非它紧接在复合语句的开始之后。例如:

        > //第一行
        > 的块注释//第 2 行
        > 的块注释//第 3 行的块注释

    *   **单行注释**可以出现在缩进到后面代码级别的单行上。如果注释不能写在一行中，它应该遵循块注释格式。单行注释前面应该有一个空行，除非它紧接在复合语句的开始之后。例如:

        > a = 10
        > b = 20；
        > 
        > //一个单行注释
        > c = a * b；

    *   **尾随(非常短)注释**可以出现在它们描述的代码的同一行，但是应该与代码相隔很远的距离。如果一段相关代码中出现多个短注释，它们都应该缩进到相同的选项卡设置中。例如:

        ```
        if (a == 2) {
            b = true; // special case
        }
        else {
            c = isPrime(x); // works only for odd
        }
        ```

    *   **临时删除代码:**分隔符//可以注释掉一部分或一整行。它也可以在多行中用来注释掉整个代码段。需要注意的是，这只能在代码处于活动开发阶段时临时使用；未使用的代码最终应该被物理删除，因为这会使源代码更难维护。例如:

        ```
        if (a > 1) {
            b = a; // + 1;
            ...
        }
        else {
            // b = 2;
            ...
        }
        ```

    **文档注释:**文档注释描述了 [Java 类](https://www.geeksforgeeks.org/classes-objects-java/)、[接口](https://www.geeksforgeeks.org/interfaces-in-java/)、[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)、[方法](https://www.geeksforgeeks.org/methods-in-java/)和字段。它们由**/* *……*/**分隔。请注意开头的双星号(**)，每个类、接口或成员有一个注释。这个注释应该出现在声明的前面，注释和它引用的代码之间没有空格。可以使用 *javadoc* 工具将文档注释提取到 HTML 文件中。类成员的 Javadoc 可以在一行中指定，如下所示:

    > /**这是一个 java 文档注释*/
    > private int comments _；

    文档注释旨在从无实现的角度描述代码的规范，供可能手头没有源代码的开发人员阅读。Java 将文档注释与注释后的第一个声明相关联。因此，文档注释不应该出现在方法或构造函数定义块中。例如:

    ```
    /**
     * the Geeksforgeeks class provides...
     */
    public class Geeksforgeeks {
        /**
         * constructor documentation comment...
         */
        public Geek(){
            ...
        }

        ...
    } // Geeksforgeeks class closed
    ```

虽然我们可以说上述指导方针不是决定性的，它们是相对的，但是维护指导方针总是首选的，因为软件从来不是由一个人开发的，并且可能不是由开发软件的同一个团队维护的。为了解决软件中的任何错误，部署的代码必须易于阅读。遵循上面的指导方针不仅可以让开发人员阅读代码，也可以让第一次阅读代码的新手阅读代码。