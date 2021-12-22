# Java 中的 Java.lang.String 类|集合 2

> 原文:[https://www . geesforgeks . org/Java-lang-string-class-Java-set-2/](https://www.geeksforgeeks.org/java-lang-string-class-java-set-2/)

[Java 中的 Java.lang.String 类| Set 1](https://www.geeksforgeeks.org/string-class-in-java/)
在本文中，我们将讨论 Java 中的 java.lang.String 提供的不同构造函数和方法。字符串是不可变的。
现在让我们讨论一下 String 类提供的一些方法。
**方法:**

17.  **public int codePointAt(int index)**–它将一个*索引*作为参数，该索引必须从 0 到 length()–1。ad 返回一个索引的字符 *unicode 点*。
18.  **public int codepoint before(int index)**–它将一个*索引*作为参数，该索引必须从 0 到 length()–1。并返回索引前一个字符的 *unicode 点*。
19.  **public int codePointCount(int start_index, int end_index)** – It takes as parameter *start_index* and *end_index* and returns the count of *Unicode code points* between the range.

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    // Java Program to demonstrate codePointAt
    // codePointBefore and codePointCount
    public class GFG_1 {
    public static void main(String[] args)
        {

            String s = "GeeksforGeeks";

            // codePointAt()
            System.out.print("Character (unicode point) at index 1 : "
                             + s.codePointAt(1) + "  ");
            System.out.println(s.codePointAt(5));

            // codePointBefore()
            System.out.print("Character (unicode point) before index 1 : "
                             + s.codePointBefore(1) + "  ");
            System.out.println(s.codePointBefore(7));

            // codePointCount()
            s = "G eek123 G**k";
            System.out.println("Character code point count : "
                               + s.codePointCount(0, 5));
        }
    }
    ```

    输出:

    ```java
    Character (unicode point) at index 1 : 101  102
    Character (unicode point) before index 1 : 71  111
    Character code point count : 5

    ```

20.  **[public CharSequence subSequence(int start_index, int end_index)](https://www.geeksforgeeks.org/java-string-subsequence-method-examples/)** – This method returns [*CharSequence*](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html) which is a subsequence of the String on which this method is invoked.

    **注意:**它的行为类似于 **subString(int start_index，int end_index)** ，但是 **subString()** 返回 **String** ，而 **subSequence** 返回 **CharSequence。**

21.  **[公共布尔包含(CharSequence char _ seq)](https://www.geeksforgeeks.org/java-string-contains-method-example/)**–如果调用它的字符串中存在给定的 *CharSquence* ，它将返回 *true* 。
22.  **public boolean contentEquals(CharSequence char_seq)** – It returns *true* only if the given *CharSequence* exactly matches the String on which its invoked

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    // Java Program to demonstrate subSequence
    // and contains and contentEquals
    public class GFG_2 {
    public static void main(String[] args)
        {
            String s = "geeksforgeeks";

            // subSequence()
            // contains "for"
            CharSequence cs = s.subSequence(5, 8);

            // contains "geeks"
            CharSequence cs1 = s.subSequence(0, 5);

            String s_1 = "geekforgeek";

            // contains()
            System.out.println("Reult of contains on s_1 "
                               + "with charSequence cs " + s_1.contains(cs));
            System.out.println("Reult of contains on s_1 "
                               + "with charSequence cs1 " + s_1.contains(cs1));

            // contentEqual()

            System.out.print("Result of contentEqual ");
            System.out.println("geeks".contentEquals(cs1));

            System.out.print("Result of contentEqual ");
            System.out.println("geeksfor".contentEquals(cs1));
        }
    }
    ```

    输出:

    ```java
    Reult of contains on s_1 with charSequence cs true
    Reult of contains on s_1 with charSequence cs1 false
    Result of contentEqual true
    Result of contentEqual false

    ```

23.  **[公共布尔 endsWith(String suf)](https://www.geeksforgeeks.org/java-string-endswith-examples/)**–它接受参数字符串*后缀*，如果字符串具有相同的后缀，则返回 *true* 。
24.  **[public boolean startsWith(String pre)](https://www.geeksforgeeks.org/java-lang-string-startswith-java/)** – It takes in parameter a String *prefix* and returns *true* if the String has a same prefix

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    // Java Program to demonstrate endsWith
    // and startWith
    public class GFG_3 {
    public static void main(String[] args)
        {

            String s = "geeksforgeeks";

            // endsWith
            String ends_1 = "geeks";
            String ends_2 = "eks";
            String ends_3 = "for";

            System.out.println(s + "end with " + ends_1 + " " + s.endsWith(ends_1));
            System.out.println(s + "end with " + ends_2 + " " + s.endsWith(ends_2));
            System.out.println(s + "end with " + ends_3 + " " + s.endsWith(ends_3));

            // startWith
            String start_1 = "geeks";
            String start_2 = "for";

            System.out.println(s + " starts with " + start_1
                               + "  " + s.startsWith(start_1));
            System.out.println(s + " starts with " + start_2
                               + "  " + s.startsWith(start_2));
        }
    }
    ```

    输出:

    ```java
    geeksforgeeksend with geeks true
    geeksforgeeksend with eks true
    geeksforgeeksend with for false
    geeksforgeeks starts with geeks  true
    geeksforgeeks starts with for  false

    ```

25.  **[public void getChars(int start，int end，char[] destination，int destination_start)](https://www.geeksforgeeks.org/java-string-getchars-examples/)** :取四个参数， *start 和 end* 指的是要复制到字符数组的范围， *destination* 是要复制到的字符数组， *destination_start* 是目标数组的起始位置。
26.  **[public char[] toCharArray()](https://www.geeksforgeeks.org/java-string-tochararray-example/)** – It converts the entire String to the character array.

    **注意:-** **获取字符**提供更大的灵活性，当一个字符范围被复制到一个现有的数组或一个新的数组，而**获取字符串**将整个字符串转换成一个新的字符数组。

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    // Java Program to demonstrate getChars
    // and toCharArray
    public class GFG_4 {
    public static void main(String args[])
        {
            String s = "geeksforgeeks";

            // toCharArray
            char[] arr;
            arr = s.toCharArray();
            System.out.println("String toCharArray: ");
            for (char i : arr)
                System.out.print(i + " ");

            // getChars
            s.getChars(5, 8, arr, 0);
            System.out.println("\nSubString to existing "
                               + "char array");
            for (char i : arr)
                System.out.print(i + " ");
        }
    }
    ```

    输出:

    ```java
    String toCharArray: 
    g e e k s f o r g e e k s 
    SubString to existing char array
    f o r k s f o r g e e k s 

    ```

27.  **public int hashCode()**–返回给定字符串的 hashCode。有一个预定义的公式来计算字符串的哈希码:

    ```java
    s[0]*31^(n-1) + s[1]*31^(n-2) + ... + s[n-1]
    where,
    n - is the length of the String
    i - is the ith character of the string

    ```

28.  **[public String intern()](https://www.geeksforgeeks.org/interning-of-string/)** – It returns the canonical form of the String object on which it is invoked.
    ” When the intern method is invoked, if the pool already contains a string equal to this String object as determined by the equals(Object) method, then the string from the pool is returned. Otherwise, this String object is added to the pool and a reference to this String object is returned. ” – [Java String Documentation.](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#intern--)

    让我们看一个上述方法的例子:-
    为了更好地理解这个例子，请参考[初始化和比较字符串](https://www.geeksforgeeks.org/how-to-initialize-and-compare-strings-in-java/)
    **例子:**

    ```java
    // Java program to demonstrate
    // hashCode and intern
    class GFG_5 {
    public static void main(String[] args)
        {

            // hashCode
            String s = "geeks";
            System.out.println("Hashcode of String s is "
                               + s.hashCode());

            // intern()
            String s_1 = "geeks";
            String s_2 = new String("geeks");
            String s_3 = s_2.intern();

            // returns true
            System.out.println(s_1 == s_2);

            // returns false
            System.out.println(s_1 == s_3);
        }
    }
    ```

    输出:

    ```java
    Hashcode of String s is 98232047
    false
    true

    ```

29.  **[public boolean isEmpty()](https://www.geeksforgeeks.org/java-string-isempty-method-example/)**–如果字符串的*长度*为 *0* ，则返回 true。
30.  **[public static String format(String f, Object… arguments)](https://www.geeksforgeeks.org/java-string-format-examples/)** – Returns the formatted String according to the format specifier *f*, the *arguments* should exactly equal to the number of format specifier used .
    **Variation:**
    **[public static String format(Locale l, String f, Object… arguments)](https://www.geeksforgeeks.org/java-string-format-examples/)**– Returns the formatted String as per [*Locale*](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html) used.

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    import java.util.Locale;
    // Java program to demonstrate
    // isEmpty and format
    class GFG_6 {
    public static void main(String[] args)
        {

            String s = "geeksforgeeks";

            // format()
            String s1 = String.format("%s : %d", s, 10);
            System.out.println(s1);

            String s2 = String.format("%s = %f ",
                                      "Value of PI is", Math.PI);
            System.out.println(s2);

            // format() with locale
            // we are using the default locale here

            String s3 = String.format(Locale.getDefault(),
                                      "%s : %d", s, 10);
            System.out.println(s3);

            // isEmpty
            String s4 = "";
            System.out.println("is String s empty "
                               + s.isEmpty());

            System.out.println("is String s4 empty? "
                               + s4.isEmpty());
        }
    }
    ```

    输出:

    ```java
    geeksforgeeks : 10
    Value of PI is = 3.141593 
    geeksforgeeks : 10
    is String s empty false
    is String s4 empty? true

    ```

31.  **[公共布尔匹配(字符串 reg _ exp)](https://www.geeksforgeeks.org/java-lang-string-matches-java/)**–如果字符串匹配[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/) ( reg_exp)，则返回 true。
32.  **public boolean regionMatches(int start_OString, String another, int start_AString, int no_of_char)** – It returns true if the region of original string staring with index *start_OString* matches with the region of *another string* starting with *string_AString*, and *no_of_char* refers to the number of character to be compared.

    **变体:**
    **公共布尔 regionMatches(布尔 ignore_case，int start _ 奥斯特林，String another，int start _ 涩味，int no _ of _ char)**–当我们想要在比较子字符串时忽略大小写时，方法的这种变体提供了灵活性。如果第一个参数，即 *ignore_case* 为 *true* 则忽略该案例并进行比较，但是如果为 *false* 则与第一个版本的方法行为类似，不使用 *ignore_case*

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    // Java Program to demonstrate
    // matches and regionMatches
    class GFG_7 {
    public static void main(String[] args)
        {
            String s = "geeksforGeeks";

            // matches
            System.out.println("Matches 1 :"
                               + s.matches("(.*)Geeks"));
            System.out.println("Matches 2 :"
                               + s.matches("(.*)for(.*)"));
            System.out.println("Matches 3 :"
                               + s.matches("geeksfor"));

            // regionMatches(int, String, int, int)

            String s2 = "Geeksforgeeks";

            System.out.println("RegionMatches 1 :" + s.regionMatches(5, s2, 5, 3));
            System.out.println("RegionMatches 2 :" + s.regionMatches(5, s2, 6, 3));

            // regionMatches(boolean, int, String, int, int)
            // ignore the case while comparing
            System.out.println("Region Matches 3 :" + s.regionMatches(true, 0, s2, 0, 3));

            // consider the case while comparing
            System.out.println("Region Matches 3 :" + s.regionMatches(false, 0, s2, 0, 3));
        }
    }
    ```

    输出:

    ```java
    Matches 1 :true
    Matches 2 :true
    Matches 3 :false
    RegionMatches 1 :true
    RegionMatches 2 :false
    Region Matches 3 :true
    Region Matches 3 :false

    ```

33.  **[public String[] split(String reg_exp)](https://www.geeksforgeeks.org/split-string-java-examples/)** – It splits the string around the regular expression and returns a String array.

    **Variation:**
    **[public String[]split(String reg_exp，int limit)](https://www.geeksforgeeks.org/split-string-java-examples/)**–它在正则表达式周围拆分字符串， *limit* 指的是应用 *reg_exp* 的次数，它是*结果数组的长度*和 reg _ exp 为 n 只应用长度–1 次。

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    // Java Program to demonstrate
    // split
    class GFG_8 {
    public static void main(String[] args)
        {
            String s = "Geeks for Geeks";

            // split
            System.out.println("Splitting the string a"
                               + "round spaces");
            String[] geek_arr = s.split("\\s+");
            for (String i : geek_arr)
                System.out.println(i);

            System.out.println("\nSplitting the string around the spaces"
                               + "\nbut controlling the length of resulting array :");
            String s_1 = "Geeks for Geeks Geeks for Geeks";
            String[] geek_arr1 = s_1.split("\\s+", 2);
            for (String i : geek_arr1)
                System.out.println(i);

            System.out.println("\nSplitting the string around the spaces"
                               + "\nbut controlling the length of resulting array :");
            geek_arr1 = s_1.split("\\s+", 4);
            for (String i : geek_arr1)
                System.out.println(i);
        }
    }
    ```

    输出:

    ```java
    Splitting the string around spaces
    Geeks
    for
    Geeks

    Splitting the string around the spaces
    but controlling the length of resulting array :
    Geeks
    for Geeks Geeks for Geeks

    Splitting the string around the spaces
    but controlling the length of resulting array :
    Geeks
    for
    Geeks
    Geeks for Geeks

    ```

34.  **[public static String join(CharSequence de_limiter, CharSequence… elements)](https://www.geeksforgeeks.org/java-string-join-examples/)** – It returns a string which contains all the *elements* joins by the *de_limiter*.

    **Variation:**
    **[public static String join(CharSequence de _ limiter，Iterable elements)](https://www.geeksforgeeks.org/java-string-join-examples/)**–它执行相同的功能，但第二个参数是 *Iterable* ，这使得它可以灵活地处理不同的集合类。

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    // Java Program to demonstrate
    // join
    import java.util.LinkedList;
    class GFG_9 {
    public static void main(String[] args)
        {
            // join()
            System.out.print("Example of join 1 : ");
            System.out.println(
                String.join(", ", "Geeks", "for", "Geeks"));

            System.out.print("Example of join 2 : ");
            LinkedList ll = new LinkedList();
            ll.add("browsing");
            ll.add("geeks");
            ll.add("for");
            ll.add("geeks");
            ll.add("is");
            ll.add("fun");
            System.out.println(String.join("-a-", ll));
        }
    }
    ```

    输出:

    ```java
    Example of join 1 : Geeks, for, Geeks
    Example of join 2 : browsing-a-geeks-a-for-a-geeks-a-is-a-fun

    ```

35.  **公共字符串替换 All(String reg_exp，String replacement)**–它用*替换*替换与 *reg_exp* 匹配的原始字符串的所有子字符串，并返回修改后的字符串。
36.  **public String replaceFirst(String reg_exp, String replacement)** – It replaces the first occurrence of the *reg-exp* in the original string with the *replacement* and returns the modified String.
    **Note :-** **replaceAll** and **replaceFirst** does’nt changes the original String rather it creates a new string with modification.

    让我们看一个上述方法的例子:
    **例子:**

    ```java
    // Java Program to demonstrate
    // replaceAll and replaceFirst
    class GFG_10 {
    public static void main(String[] args)
        {
            String s = "GeeksforGeeks";
            ;

            // replaceAll()
            String s1 = s.replaceAll("Geeks", "Quiks");
            System.out.println("Replace all Geeks "
                               + "with Quiks :" + s1);

            System.out.print("Replace any UpperCase letter "
                             + "with F :");
            System.out.println(s.replaceAll("[A-Z]+", "F"));

            // replaceFirst()
            String s2 = s.replaceFirst("Geeks", "Quiks");
            System.out.println("Replace first Occurrence "
                               + "of Geeks with Quiks :" + s2);
        }
    }
    ```

    输出:

    ```java
    Replace all Geeks with Quiks :QuiksforQuiks
    Replace any UpperCase letter with F :FeeksforFeeks
    Replace first Occurrence of Geeks with Quiks :QuiksforGeeks

    ```

关于 String 的更多方法参考 java 中的 [String 类](https://www.geeksforgeeks.org/string-class-in-java/)
**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/lang/String . html](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)

本文由 **Sumit Ghosh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。