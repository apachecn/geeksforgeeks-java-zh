# Java 中的 Java . lang . character . unicode block 类

> 原文:[https://www . geesforgeks . org/Java-lang-character-unicodeblock-class-Java/](https://www.geeksforgeeks.org/java-lang-character-unicodeblock-class-java/)

**性格。Unicode 块类**代表 Unicode(使用十六进制值表示字符的标准–16 位)规范的特定**字符块**。字符块定义用于特定目的的字符。

**申报:**

```
public static final class Character.UnicodeBlock
   extends Character.Subset
```

**性格的方法。UnicodeBlock 类:**

*   **for name():****Java . lang . character . Unicode block . for name()**返回 Unicode 块的名称，由 Unicode 标准确定。
    根据 Unicode 标准，该方法接受作为规范块的参数。
    **语法:**

```
public static final Character.UnicodeBlock forName(String block)
Parameters : 
block : Name of UniCode Block.
Return  :
instance of UniCode Block.
Exception : 
-> IllegalArgumentException
-> NullPointerException

```

*   (char ch)的**:****Java . lang . character . subset of(char ch)**返回具有参数字符的 Unicode 块，如果该字符不是任何已定义的 UniCode 块的一部分，则返回 null。
    **语法:**

    ```
    public static Character.UnicodeBlock of(char ch)
    Parameters : 
    ch : character to be found.
    Return  :
    returns the UniCode Block or null.
    Exception : 
    -> IllegalArgumentException

    ```

    *   **of(int UCPoint) :** **java.lang.Character.Subset.of(int UCPoint)**returns the object having the argumented UniCode – Point or null if the character is not a part of any defined Unicode Block.
    **Syntax :**

    ```
    public final String toString()
    Parameters : 
    ---
    Return  :
    returns the object having the argumented UniCode - Point or null
    Exception : 
    -> IllegalArgumentException

    ```

    ```
    // Java Program illustrating the use of
    // Character.UnicodeBlock class Methods.
    import java.lang.*;

    public class CharacterSubsetDemo 
    {
       public static void main(String[] args) 
       {
          // Use of forName() : 
          // returns Unicode Blocks, as per Unicode Standards
          System.out.println("Using UnicodeBlock.forName() : ");
          System.out.println(Character.UnicodeBlock.forName("OLDITALIC"));
          System.out.println(Character.UnicodeBlock.forName("NUMBERFORMS"));
          System.out.println(Character.UnicodeBlock.forName("MALAYALAM") + "\n");

          // Use of(char ch) :
          System.out.println("Using UnicodeBlock.of(char ch) : ");
          System.out.println(Character.UnicodeBlock.of(' '));
          System.out.println(Character.UnicodeBlock.of('\u21ac') + "\n");

          // Use of(int UCPoint) : 
          System.out.println("Using UnicodeBlock.of(int UCPoint) : ");
          System.out.println(Character.UnicodeBlock.of(1609));    
          System.out.println(Character.UnicodeBlock.of(1565));

       }
    } 
    ```

    **输出:**

    ```
    Using UnicodeBlock.forName() : 
    OLD_ITALIC
    NUMBER_FORMS
    MALAYALAM

    Using UnicodeBlock.of(char ch) : 
    BASIC_LATIN
    ARROWS

    Using UnicodeBlock.of(int UCPoint) : 
    ARABIC
    ARABIC
    ```

    **注:**
    郎。字符。UnicodeBlock 类从 **lang 继承了其他方法。字符.子集类**类，它又继承了**语言的方法。人物.对象**类。

    有关 java.lang.Object 的更多详细信息，请参考:
    [lang。Java 中的字符.子集类](https://www.geeksforgeeks.org/java-lang-character-subset-class-java/)。
    Java 中的[对象类](https://www.geeksforgeeks.org/object-class-in-java/)。

    本文由 [<font color="green">**莫希特·古普塔 _OMG 供稿😀**</font>](https://www.facebook.com/profile.php?id=100016327034955) 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。