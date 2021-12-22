# Java SE 9:改进的资源试用语句

> 原文:[https://www . geesforgeks . org/Java-se-9-改良-try-resources-statements/](https://www.geeksforgeeks.org/java-se-9-improved-try-resources-statements/)

在 java 7 或 8 中，如果一个资源已经在 [try-with-resources](https://www.geeksforgeeks.org/automatic-resource-management-java/) 语句之外声明了，我们应该用局部变量重新引用它。这意味着我们必须在 try 块中声明一个新的变量。让我们看看解释上述论点的代码:

```
// Java code illustrating try-with-resource
import java.io.*;

class Gfg
{
    public static void main(String args[]) throws IOException
    {

        File file = new File("/Users/abhishekverma/desktop/hello.txt/");

        BufferedReader br = new BufferedReader(new FileReader(file));

        // Original try-with-resources statement from JDK 7 or 8
        try(BufferedReader reader = br)
        {
            String st = reader.readLine();
            System.out.println(st);
        }
    }         
}
```

在 Java 9 中，我们不需要创建这个局部变量。这意味着，如果我们有一个已经在资源尝试语句之外声明为 [final](https://www.geeksforgeeks.org/final-keyword-java/) 或*final*的资源，那么我们不必创建引用该声明资源的局部变量，该声明资源可以毫无问题地使用。让我们看看解释上述论点的 java 代码。

```
// Java code illustrating improvement made in java 9
// for try-with-resources statements

import java.io.*;

class Gfg
{
    public static void main(String args[]) throws IOException
    {

        File file = new File("/Users/abhishekverma/desktop/hello.txt/");

        BufferedReader br = new BufferedReader(new FileReader(file));

        // New and improved try-with-resources statement in JDK 9
        try(br)
        {
            String st = br.readLine();
            System.out.println(st);
        }

    }         
}
```

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。