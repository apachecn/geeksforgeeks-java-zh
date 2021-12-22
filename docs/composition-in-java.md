# Java 中的合成

> 原文:[https://www.geeksforgeeks.org/composition-in-java/](https://www.geeksforgeeks.org/composition-in-java/)

组合是 java 中的一种设计技术，用于实现**与**的关系。Java [继承](https://www.geeksforgeeks.org/inheritance-in-java/)用于代码重用，同样我们也可以通过使用组合来实现。合成是通过使用引用其他对象的实例变量来实现的。如果一个对象包含另一个对象，而被包含的对象没有该对象的存在就不能存在，那么这就叫做合成。更具体地说，组合是一种使用实例变量描述两个或多个类之间引用的方式，在使用实例之前应该创建一个实例。

![](img/39009a598c779f469189e9ed1965a87b.png)

使用合成的好处如下:

1.  组合允许代码的重用。
2.  Java 不支持[多重继承](https://www.geeksforgeeks.org/java-and-multiple-inheritance/)但是通过使用复合我们可以实现。
3.  作文提供了一个班级更好的测试能力。
4.  通过使用组合，我们足够灵活，可以用更好的改进版本替换组合类的实现。
5.  通过使用组合，我们还可以在运行时更改成员对象，以动态更改程序的行为。

一定要记住 java 编写的某些要点，如下所示:

*   它代表一个 [**有-一个**关系](https://www.geeksforgeeks.org/what-is-has-a-relation-in-java/)。
*   在组合中，两个实体相互依赖。
*   当两个实体之间存在组合时，没有另一个实体，组合的对象就不能存在。例如，一个图书馆可以有相同或不同主题的**本**的数量。所以，如果图书馆被摧毁了，那么那个特定图书馆里的所有书都会被摧毁。这是没有图书馆书籍就无法存在的。
*   合成是通过使用引用其他对象的实例变量来实现的。
*   我们必须支持合成而不是继承。

现在，让我们最后参考下图，为了获得关于聚合的模糊提示，并更好地理解合成是如何工作的，让我们以实时库系统为例。

> **实景示例:**图书馆系统**T3】**
> 
> 让我们以书籍和图书馆为例来理解 Java 中的组成。在这个例子中，我们创建了一个类 *Book* ，它包含数据成员如作者和标题，并创建了另一个类 *Library* ，它有一个引用来引用图书列表。一个图书馆可以有许多相同或不同主题的**书籍**。所以，如果图书馆被摧毁了，那么那个特定图书馆里的所有书都会被摧毁。也就是说，没有图书馆，书就不能存在。图书馆和书籍的关系是构成。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate Concept of Composition

// Importing required classes
import java.io.*;
import java.util.*;

// Class 1
// Helper class
// Book class
class Book {

    // Member variables of this class
    public String title;
    public String author;

    // Constructor of this class
    Book(String title, String author)
    {

        // This keyword refers top current instance
        this.title = title;
        this.author = author;
    }
}

// Class 2
// Helper class
// Library class contains list of books.
class Library {

    // Reference to refer to list of books.
    private final List<Book> books;

    // Constructor of this class
    Library(List<Book> books)
    {

        // This keyword refers to current instance itself
        this.books = books;
    }

    // Method of this class
    // Getting the list of books
    public List<Book> getListOfBooksInLibrary()
    {
        return books;
    }
}

// Class 3
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating the objects of class 1 (Book class)
        // inside main() method
        Book b1
            = new Book("EffectiveJ Java", "Joshua Bloch");
        Book b2
            = new Book("Thinking in Java", "Bruce Eckel");
        Book b3 = new Book("Java: The Complete Reference",
                           "Herbert Schildt");

        // Creating the list which contains the
        // no. of books.
        List<Book> book = new ArrayList<Book>();

        // Adding books to List object
        // using standard add() method
        book.add(b1);
        book.add(b2);
        book.add(b3);

        // Creating an object of class 2
        Library library = new Library(book);

        // Calling method of class 2 and storing list of
        // books in List Here List is declared of type
        // Books(user-defined)
        List<Book> books
            = library.getListOfBooksInLibrary();

        // Iterating over for each loop
        for (Book bk : books) {

            // Print and display the title and author of
            // books inside List object
            System.out.println("Title : " + bk.title
                               + " and "
                               + " Author : " + bk.author);
        }
    }
}
```

**Output**

```java
Title : EffectiveJ Java and  Author : Joshua Bloch
Title : Thinking in Java and  Author : Bruce Eckel
Title : Java: The Complete Reference and  Author : Herbert Schildt
```