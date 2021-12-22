# Java 中的 Java.lang.Character 类

> 原文:[https://www.geeksforgeeks.org/character-class-java/](https://www.geeksforgeeks.org/character-class-java/)

Java 在 java.lang 包中提供了一个包装类 **Character** 。字符类型的对象包含一个类型为字符的字段。

*   **Creating a Character object :**

    ```
    Character ch = new Character('a');

    ```

    上面的语句创建了一个字符对象，它包含一个字符类型的。字符类中只有一个构造函数需要 char [数据类型](https://www.geeksforgeeks.org/data-types-in-java/)的参数。

*   如果我们将一个基本字符传递给一个需要对象的方法，编译器会自动将该字符转换为一个字符类对象。该功能称为[自动装箱和取消装箱](https://docs.oracle.com/javase/tutorial/java/data/autoboxing.html)。
*   **注意:**字符类像字符串类一样是不可变的，即一旦创建了它的对象，它**就不能**被更改。

**人物类中的方法:**

1.  **boolean isLetter(char ch)** : This method is used to determine whether the specified char value(ch) is a letter or not. The method will return true if it is letter([A-Z],[a-z]), otherwise return false. In place of character, we can also pass ASCII value as an argument as char to int is implicitly typecasted in java.

    ```
    Syntax : 
    boolean isLetter(char ch)
    Parameters : 
    ch - a primitive character
    Returns :
    returns true if ch is a alphabet, otherwise return false

    ```

    ```
    // Java program to demonstrate isLetter() method
    public class Test
    {
        public static void main(String[] args)
        {
            System.out.println(Character.isLetter('A')); 

            System.out.println(Character.isLetter('0')); 

         }
    }
    ```

    输出:

    ```
    true
    false

    ```

2.  **boolean isDigit(char ch)** : This method is used to determine whether the specified char value(ch) is a digit or not. Here also we can pass ASCII value as an argument.

    ```
    Syntax : 
    boolean isDigit(char ch)
    Parameters : 
    ch - a primitive character 
    Returns :
    returns true if ch is a digit, otherwise return false

    ```

    ```
    // Java program to demonstrate isDigit() method
    public class Test
    {
        public static void main(String[] args)
        {
            // print false as A is character
            System.out.println(Character.isDigit('A')); 

            System.out.println(Character.isDigit('0')); 

        }
    }
    ```

    输出:

    ```
    false
    true

    ```

3.  **[boolean isWhitespace(char ch](https://www.geeksforgeeks.org/character-iswhitespace-method-in-java-with-examples/))** : It determines whether the specified char value(ch) is white space. A whitespace includes space, tab, or new line.

    ```
    Syntax : 
    boolean isWhitespace(char ch)
    Parameters : 
    ch - a primitive character 
    Returns :
    returns true if ch is a whitespace.
    otherwise return false

    ```

    ```
    // Java program to demonstrate isWhitespace() method
    public class Test
    {
        public static void main(String[] args)
        {
            System.out.println(Character.isWhitespace('A')); 
            System.out.println(Character.isWhitespace(' ')); 
            System.out.println(Character.isWhitespace('\n')); 
            System.out.println(Character.isWhitespace('\t')); 

            //ASCII value of tab
            System.out.println(Character.isWhitespace(9));

            System.out.println(Character.isWhitespace('9')); 
        }
    }
    ```

    输出:

    ```
    false
    true
    true
    true
    true
    false

    ```

4.  **boolean isUpperCase(char ch)** : It determines whether the specified char value(ch) is uppercase or not.

    ```
    Syntax : 
    boolean isUpperCase(char ch)

    ```

    ```
    // Java program to demonstrate isUpperCase() method
    public class Test
    {
      public static void main(String[] args)
      {
        System.out.println(Character.isUpperCase('A'));
        System.out.println(Character.isUpperCase('a'));
        System.out.println(Character.isUpperCase(65)); 
      }
    }
    ```

    输出:

    ```
    true
    false
    true

    ```

5.  **boolean isLowerCase(char ch)** : It determines whether the specified char value(ch) is lowercase or not.

    ```
    Syntax : 
    boolean isLowerCase(char ch)

    ```

    ```
    // Java program to demonstrate isLowerCase() method
    public class Test
    {
      public static void main(String[] args)
      {
        System.out.println(Character.isLowerCase('A')); 
        System.out.println(Character.isLowerCase('a')); 
        System.out.println(Character.isLowerCase(97)); 
       }
    }
    ```

    输出:

    ```
    false
    true
    true

    ```

6.  **char toUpperCase(char ch)** : It returns the uppercase of the specified char value(ch). If an ASCII value is passed, then the ASCII value of it’s uppercase will be returned.

    ```
    Syntax : 
    char toUpperCase(char ch)
    Parameters : 
    ch - a primitive character 
    Returns :
    returns the uppercase form of the specified char value.

    ```

    ```
    // Java program to demonstrate toUpperCase() method
    public class Test
    {
       public static void main(String[] args)
       {
         System.out.println(Character.toUpperCase('a')); 
         System.out.println(Character.toUpperCase(97)); 
         System.out.println(Character.toUpperCase(48));
       }
    }
    ```

    输出:

    ```
    A
    65
    48

    ```

7.  **char toLowerCase(char ch)** : It returns the lowercase of the specified char value(ch).

    ```
    Syntax : 
    char toLowerCase(char ch)
    Parameters : 
    ch - a primitive character 
    Returns :
    returns the lowercase form of the specified char value.

    ```

    ```
    // Java program to demonstrate toLowerCase() method
    public class Test
    {
       public static void main(String[] args)
       {
         System.out.println(Character.toLowerCase('A')); 
         System.out.println(Character.toLowerCase(65)); 
         System.out.println(Character.toLowerCase(48)); 
       }
    }
    ```

    输出:

    ```
    a
    97
    48

    ```

8.  **toString(char ch)** : It returns a String class object representing the specified character value(ch) i.e a one-character string. Here we **cannot** pass ASCII value.

    ```
    Syntax : 
    String toString(char ch)
    Parameters : 
    ch - a primitive character 
    Returns :
    returns a String object.

    ```

    ```
    // Java program to demonstrate toString() method
    public class Test
    {
       public static void main(String[] args)
       {
        System.out.println(Character.toString('x')); 
        System.out.println(Character.toString('Y')); 
       }
    }
    ```

    输出:

    ```
    x
    y

    ```

9.  **[静态 int charCount(int codePoint)](https://www.geeksforgeeks.org/java-character-charcount-with-examples/)**:此方法确定表示指定字符(Unicode 代码点)所需的字符值数量。
10.  **[char charValue ()](https://www.geeksforgeeks.org/character-charvalue-in-java-with-examples/)** :这个方法返回这个 Character 对象的值。
11.  **静态 int codePointAt (char[] a，int index)** :此方法返回 char 数组给定索引处的代码点。
12.  **静态 int codePointAt (char[] a，int index，int limit)** :此方法返回 char 数组给定索引处的代码点，这里只能使用索引小于 limit 的数组元素。
13.  **静态 int codePointAt (CharSequence seq，int index)** :此方法返回 CharSequence 给定索引处的代码点。
14.  **静态 int codePointBefore (char[] a，int index)** :此方法返回 char 数组给定索引之前的代码点。
15.  **静态 int codePointBefore (char[] a，int index，int start)** :此方法返回 char 数组给定索引之前的代码点，其中只能使用索引大于等于 start 的数组元素。
16.  **静态 int codePointBefore(CharSequence seq，int index)** :此方法返回 CharSequence 给定索引之前的代码点。
17.  **静态 int codePointCount (char[] a，int offset，int count)** :此方法返回 char 数组参数的子数组中的 Unicode 码点数。
18.  **静态 int codePointCount(CharSequence seq，int beginIndex，int endIndex)** :此方法返回指定字符序列文本范围内的 Unicode 码点数。
19.  **静态 int codePointOf(字符串名称)**:此方法返回给定 Unicode 字符名称指定的 Unicode 字符的代码点值。
20.  **静态 int compare (char x，char y)** :此方法对两个 char 值进行数值比较。
21.  **int compare to(Character other Character)**:该方法对两个 Character 对象进行数值比较。
22.  **[【静态 int 数字(char ch，int 基数)](https://www.geeksforgeeks.org/character-digit-in-java-with-examples/)** :该方法返回指定基数下字符 ch 的数值。
23.  **[静态 int 数字(int codePoint，int 基数)](https://www.geeksforgeeks.org/character-digit-in-java-with-examples/)** :此方法返回指定基数内指定字符(Unicode 码点)的数值。
24.  **[布尔等于(Object obj)](https://www.geeksforgeeks.org/character-equals-method-in-java-with-examples/)** :此方法将此对象与指定对象进行比较。
25.  **整数(int digit，int radix)** 的静态字符:此方法确定指定基数中特定数字的字符表示。
26.  **[静态字节 getDirectionality(char ch)](https://www.geeksforgeeks.org/character-getdirectionality-method-in-java-with-examples/)**:此方法返回给定字符的 Unicode directionality 属性。
27.  **[静态字节 getDirectionality(int codePoint)](https://www.geeksforgeeks.org/character-getdirectionality-method-in-java-with-examples/)**:此方法返回给定字符(Unicode 代码点)的 Unicode directionality 属性。
28.  **静态 String getName (int codePoint)** :此方法返回指定字符 codePoint 的 Unicode 名称，如果代码点未赋值则返回 null。
29.  **静态 int getNumericValue (char ch)** :此方法返回指定 Unicode 字符表示的 int 值。
30.  **静态 int getNumericValue(int codePoint)**:此方法返回指定字符(Unicode 代码点)表示的 int 值。
31.  **[静态 int getType (char ch)](https://www.geeksforgeeks.org/character-equals-method-in-java-with-examples/)** :这个方法返回一个值，表示一个角色的一般类别。
32.  **[静态 int getType(int codePoint)](https://www.geeksforgeeks.org/character-equals-method-in-java-with-examples/)**:这个方法返回一个值，表示一个角色的一般类别。
33.  **[int hashCode ()](https://www.geeksforgeeks.org/character-hashcode-in-java-with-examples/)** :这个方法返回这个字符的 hash 码；等于调用 charValue()的结果。
34.  **[静态 int hashCode (char 值)](https://www.geeksforgeeks.org/character-hashcode-in-java-with-examples/)** :这个方法返回一个 char 值的 hash 码；与 Character.hashCode()兼容。
35.  **静态 char highrogate(int codePoint)**:此方法返回表示 UTF-16 编码中指定补充字符(Unicode 代码点)的代理项对的前导代理项(高代理项代码单元)。
36.  **静态布尔 isAlphabetic (int codePoint)** :此方法确定指定的字符(Unicode 代码点)是否为字母表。
37.  **静态布尔 isBmpCodePoint(int codePoint)**:此方法确定指定字符(Unicode 码点)是否在基本多语言平面(BMP)中。
38.  **静态布尔 isDefined (char ch)** :这个方法确定一个字符是否用 Unicode 定义。
39.  **静态布尔 isDefined (int codePoint)** :此方法确定字符(Unicode 代码点)是否定义在 Unicode 中。
40.  **[静态布尔 ishighrogsurrogate(char ch)](https://www.geeksforgeeks.org/character-ishighsurrogate-method-in-java-with-examples/)**:此方法确定给定的 char 值是否为 Unicode 高代理代码单元(也称为前导代理代码单元)。
41.  **[静态布尔 isiidentifier ignorable(char ch)](https://www.geeksforgeeks.org/character-isidentifierignorable-in-java-with-examples/)**:此方法确定在 Java 标识符或 Unicode 标识符中指定的字符应该被视为可忽略字符。
42.  **[静态布尔 isiidentifier ignorable(int codePoint)](https://www.geeksforgeeks.org/character-isidentifierignorable-in-java-with-examples/)**:这个方法决定了指定的字符(Unicode 代码点)应该被视为 Java 标识符中的可忽略字符还是 Unicode 标识符中的可忽略字符。
43.  **静态布尔 isIdeographic (int codePoint)** :此方法确定指定字符(Unicode 代码点)是否为 Unicode 标准定义的 CJKV(中文、日文、韩文和越南语)表意字符。
44.  **[静态布尔 isISOControl (char ch)](https://www.geeksforgeeks.org/character-isisocontrol-method-with-examples-in-java/)** :此方法确定指定字符是否为 ISO 控制字符。
45.  **[静态布尔 isISOControl(int codePoint)](https://www.geeksforgeeks.org/character-isisocontrol-method-with-examples-in-java/)**:此方法确定引用的字符(Unicode 代码点)是否为 ISO 控制字符。
46.  **[静态布尔 isjavaindiferepart(char ch)](https://www.geeksforgeeks.org/character-isjavaidentifierpart-method-in-java-with-examples/)**:此方法确定指定的字符是否可能是 Java 标识符的一部分，而不是第一个字符。
47.  **[静态 boolean isjavaidentifier part(int codePoint)](https://www.geeksforgeeks.org/character-isjavaidentifierpart-method-in-java-with-examples/)**:此方法确定字符(Unicode 代码点)是否可能是 Java 标识符的一部分，而不是第一个字符。
48.  **[静态布尔 isjavaidentifier start(char ch)](https://www.geeksforgeeks.org/character-isjavaidentifierstart-method-in-java-2/)**:此方法确定指定的字符是否允许作为 Java 标识符中的第一个字符。
49.  **[静态布尔 isJavaIdentifierStart(int codePoint)](https://www.geeksforgeeks.org/character-isjavaidentifierstart-method-in-java/)**:此方法确定字符(Unicode 代码点)是否允许作为 Java 标识符中的第一个字符。
50.  **[静态布尔 isLowSurrogate (char ch)](https://www.geeksforgeeks.org/character-islowsurrogate-method-in-java-with-examples/)** :此方法确定给定的 char 值是否为 Unicode 低代理代码单元(也称为尾随代理代码单元)。
51.  **[静态布尔 isLetterOrDigit (char ch)](https://www.geeksforgeeks.org/character-isletterordigit-in-java-with-examples/)** :这个方法确定指定的字符是字母还是数字。
52.  **[静态布尔 isLetterOrDigit(int codePoint)](https://www.geeksforgeeks.org/character-isletterordigit-in-java-with-examples/)**:此方法确定指定字符(Unicode 代码点)是字母还是数字。
53.  **[静态布尔 isMirrored (char ch)](https://www.geeksforgeeks.org/character-ismirrored-method-in-java/)** :此方法决定字符是否按照 Unicode 规范镜像。
54.  **[静态布尔 is mirrored(int codePoint)](https://www.geeksforgeeks.org/character-ismirrored-method-in-java/)**:此方法确定指定字符(Unicode 码点)是否按照 Unicode 规范镜像。
55.  **[静态 boolean is spacechar(char ch)](https://www.geeksforgeeks.org/character-isspacecharchar-ch-method-java/)**:此方法确定指定字符是否为 Unicode 空格字符。
56.  **[静态布尔值 isSpaceChar(int codePoint)](https://www.geeksforgeeks.org/character-isspacecharchar-ch-method-java/)**:此方法确定指定字符(Unicode 代码点)是否为 Unicode 空格字符。
57.  **[静态布尔 issuementarycode point(int codePoint)](https://www.geeksforgeeks.org/character-issupplementarycodepoint-method-in-java/)**:此方法判断指定字符(Unicode 码点)是否在补充字符范围内。
58.  **静态布尔 issuerrogate(char ch)**:此方法确定给定的 char 值是否是 Unicode 代理代码单元。
59.  **静态 boolean isSurrogatePair(char high，char low)** :此方法确定指定的字符值对是否是有效的 Unicode 代理项对。
60.  **[静态布尔 isTitleCase (char ch)](https://www.geeksforgeeks.org/character-istitlecase-in-java-with-examples/)** :此方法判断指定字符是否为 TitleCase 字符。
61.  **[静态布尔 isTitleCase(int codePoint)](https://www.geeksforgeeks.org/character-istitlecase-in-java-with-examples/)**:此方法确定指定字符(Unicode 代码点)是否为 TitleCase 字符。
62.  **[静态布尔 isunicodeidentifier part(char ch)](https://www.geeksforgeeks.org/character-isunicodeidentifierpart-method-in-java-with-examples/)**:此方法确定指定字符是否可能是 Unicode 标识符的一部分，而不是第一个字符。
63.  **[静态布尔 isunicodeidentifier part(int codePoint)](https://www.geeksforgeeks.org/character-isunicodeidentifierpart-method-in-java-with-examples/)**:此方法确定指定字符(Unicode 代码点)是否可能是 Unicode 标识符的一部分，而不是第一个字符。
64.  **静态布尔 isunicodeidentifier start(char ch)**:此方法确定指定字符是否允许作为 Unicode 标识符中的第一个字符。
65.  **静态布尔 isunicodeidentifier start(int codePoint)**:此方法确定指定字符(Unicode 代码点)是否允许作为 Unicode 标识符中的第一个字符。
66.  **[静态布尔 is validacodepoint(int codePoint)](https://www.geeksforgeeks.org/character-isvalidcodepoint-method-in-java-with-examples/)**:此方法确定指定的代码点是否为有效的 Unicode 代码点值。
67.  **静态 char low surrogate(int codePoint)**:此方法返回表示 UTF-16 编码中指定补充字符(Unicode 代码点)的代理项对的尾随代理项(低代理项代码单位)。
68.  **[静态 int offsetByCodePoints (char[] a，int start，int count，int index，int codePointOffset)](https://www.geeksforgeeks.org/character-offsetbycodepoints-in-java-with-examples/)** :此方法返回给定 char 子数组内的索引，该索引从给定索引偏移了 codePointOffset 代码点。
69.  **[静态 int offset by codepoints(CharSequence seq，int index，int codePointOffset)](https://www.geeksforgeeks.org/character-offsetbycodepoints-method-in-java/)** :此方法返回给定字符序列内的索引，该索引从给定索引偏移了 codePointOffset 代码点。
70.  **静态 char reverseBytes (char ch)** :此方法返回通过反转指定 char 值中字节的顺序获得的值。
71.  **静态 char[] toChars (int codePoint)** :此方法将指定字符(Unicode 代码点)转换为存储在 char 数组中的 UTF-16 表示形式。
72.  **静态 int toChars (int codePoint，char[] dst，int dsindex)**:此方法将指定字符(Unicode 代码点)转换为其 UTF-16 表示形式。
73.  **静态 int to deppoint(char 高，char 低)**:此方法将指定的代理项对转换为其补充代码点值。
74.  **静态 char toitlecase(char ch)**:这个方法使用来自 UnicodeData 文件的大小写映射信息，将字符参数转换为 TitleCase。
75.  **静态 int ToitLecase(int CodePoint)**:此方法使用 Unicode 数据文件中的大小写映射信息将字符(Unicode 代码点)参数转换为 TitleCase。
76.  **[【静态字符值 Of (char c)](https://www.geeksforgeeks.org/character-valueof-in-java-with-examples/)** :此方法返回一个表示指定字符值的字符实例。

**转义序列:**
以反斜杠(\)开头的字符是转义序列，对编译器有特殊意义。下表显示了 Java 转义序列:

| 换码顺序 | 描述 |
| `\t` | 此时在文本中插入一个制表符。 |
| `\b` | 此时在文本中插入退格。 |
| `\n` | 此时在文本中插入一个换行符。 |
| `\r` | 此时在文本中插入回车。 |
| `\f` | 此时在文本中插入一个 formfeed。 |
| `\'` | 此时在文本中插入一个单引号字符。 |
| `\"` | 此时在文本中插入一个双引号字符。 |
| `\\` | 此时在文本中插入一个反斜杠字符。 |

当在 print 语句中遇到转义序列时，编译器会相应地解释它。例如，如果要在引号内加上引号，必须在内部引号上使用转义序列“\”。打印句子

```
She said "Hello!" to me.

```

你会写

```
System.out.println("She said \"Hello!\" to me.");

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。