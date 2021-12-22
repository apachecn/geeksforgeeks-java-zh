# Java 中的命名约定

> 原文:[https://www.geeksforgeeks.org/java-naming-conventions/](https://www.geeksforgeeks.org/java-naming-conventions/)

一个程序员总是被说写干净的代码，其中命名必须是适当的，这样对于任何其他程序员来说，它都是一个读取代码的简单方法。从更小的层面来看，这似乎毫无意义，但想想工业层面，为了节省时间，有必要编写干净的代码，为此制定了一些规则，其中一个因素是命名[关键字](https://www.geeksforgeeks.org/list-of-all-java-keywords/) right，这在 Java 中被称为命名约定。

例如，当你使用一个描述位移的变量名时，那么它应该被命名为“位移”或类似的不太可能是 x，d，随着代码变宽和可读性变小，这变得复杂。考虑下面的插图，以获得更好的理解，稍后我们将详细讨论。

**插图:**

*   **Class:** If you name any class, it should be a noun, so it should be named according to the goal to be achieved in the program, such as Add2Numbers, ReverseString and so on, which are unlikely to be A1, Programming and so on. It should clearly point out what's inside, instead of looking at the main body of the class.
*   **Interface:** If you name an interface, it should look like an adjective, such as considering the existing ones: Runnable, Serializable, etc. Try to use "able" at the end, yes, it is said to be an attempt, because there is no hard and fast restriction rule, as if we did consider a built-in interface, such as "Remote", which has no ble at the end. Consider that if you should create an interface for reading, it is recommended to name a similar "readable" interface according to the naming convention in java.
*   **Method:** Now, if we look carefully, a method should do what it really contains in its body. From now on, it should be a verb.
*   Constant: As the name implies, it should look like what we see when reading. It looks fixed, such as PI, MAX_INT, MIN_INT, etc., as shown below.

### Java 中的命名约定

在 java 中，很好的做法是将类、变量和方法命名为它们实际应该做的事情，而不是随机命名它们。下面是 java 编程语言的一些命名约定。为了良好的维护和代码可读性，在用 java 开发软件时必须遵循这些原则。Java 使用 CamelCase 作为编写方法、变量、类、包和常量名称的实践。

**Java 编程中的 Camel 案例**由复合词或短语组成，这样每个单词或缩写都以大写字母开头，或者第一个单词以小写字母开头，其余都以大写字母结尾。这里用更简单的术语来说，它意味着如果有两个

> **注意:**一定要注意这些异常情况，java 中的 camel case 如下:
> 
> *   In package, even if we combine two or more words in java, everything is very small.
> *   In constants, we do capitalize everything, and even if we combine two or more words in java, we only use the "_" character.

**类型 1:类和接口**

*   The class name should be **noun** . In the mixed case, the first letter of each internal word is capitalized. Interface names should also be capitalized like class names.
*   When using whole words, acronyms and abbreviations must be avoided.

```java
Classes: class Student { }
         class S=Integer {}
         class Scanner {}
```

```java
Interfaces : Runnable
             Remote
             Seriazable 
```

**第二式:Methods**

*   Methods should be **verb** , a mixed case with the initial letter of **lowercase** , and the initial letter of each internal word is capitalized.

```java
public static void main(String [] args)  {}
```

顾名思义，这个方法应该是一个主要的方法，实际上它也是一个主要的方法，因为 java 中的 main()方法是程序开始执行的地方。

**类型 3:变量**

变量名应该简短但有意义。

```java
Variables can also start with either underscore('_') or dollar sign '{content}apos; characters.
```

*   It should be a mnemonic, that is, it is designed to indicate its intention to use to casual observers.
*   **Except for temporary variables, the single-character variable name** should be avoided.
*   Common names of temporary variables are I, J, K, M, and the integer is n; C, d and e of the characters.

```java
int[] marks;
double double answer,
```

顾名思义，一个代表分数，另一个代表答案，不管是哪一个，我都不介意。

**类型 4:常量变量**

*   **should be capitalized** , and words should be separated by underscores ("_").
*   There are various constants in predefined classes, such as Float, Long, String, etc.

```java
num = PI;
```

**类型 5: Packages**

*   The unique package name prefix is always written in **all lowercase ASCII letters** , which should be one of the top-level domain names, such as com, edu, gov, mil, net and org.
*   The subsequent components of the package name are different according to the organization's own internal naming convention.

```java
java.util.Scanner ;
java.io.*;
```

顾名思义，在第一种情况下，我们试图从 java.util 包访问 Scanner 类，在其他所有类中(*代表所有)输入输出类，这使得另一个程序员很容易识别。

> **注:**
> 
> *   For classes and interfaces, the initial letter must be capitalized.
> *   For methods, variables, package_name and constants, the initial letter must be lowercase.

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[write.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。