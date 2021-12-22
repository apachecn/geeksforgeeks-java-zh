# Java 中的 Java.lang.string.replace()方法

> 原文:[https://www . geesforgeks . org/Java-lang-string-replace-method-Java/](https://www.geeksforgeeks.org/java-lang-string-replace-method-java/)

以下是**替换()**方法的三个**变体。本文对它们全部进行了描述，如下:
**1。String replace() :** 此方法**返回**一个新字符串，该字符串是用新字符替换字符串中所有出现的旧字符而得到的。**

```
Syntax:
public String replace(char oldch, char newch)
Parameters:
oldch : the old character.
newch : the new character.
Return Value
It returns a string derived from this string by replacing every occurrence of oldch with newch.

```

```
// Java code to demonstrate the
// working of  replace() 
public class rep1 {
   public static void main(String args[]) {

      // Initialising String
      String Str = new String("Welcome to geeksforgeeks");

      // Using replace to replace characters
      System.out.print("After replacing all o with T : " );
      System.out.println(Str.replace('o', 'T'));

      // Using replace to replace characters
      System.out.print("After replacing all e with D : " );
      System.out.println(Str.replace('e', 'D'));

   }
}
```

输出:

```
After replacing all o with T : WelcTme tT geeksfTrgeeks
After replacing all e with D : WDlcomD to gDDksforgDDks

```

**2。String replaceAll() :** 此方法用给定的 replace_str 替换与给定正则表达式匹配的字符串的每个子字符串**。**

```
Syntax:
public String replaceAll(String regex, String replace_str)
Parameters:
regex: the regular expression to which this string is to be matched.
replace_str:the string which would replace found expression.
Return Value
This method returns the resulting String.

```

```
// Java code to demonstrate the
// working of  replaceAll() 
public class rep2 {
   public static void main(String args[]) {

      // Initialising String
      String Str = new String("Welcome to geeksforgeeks");

      // original string 
      System.out.print("Original String : " );
      System.out.println(Str);

      // Using replaceAll to replace regex with replace_str
      System.out.print("After replacing regex with replace_str : " );
      System.out.println(Str.replaceAll("(.*)geeks(.*)", "ASTHA TYAGI"));

   }
}
```

输出:

```
Original String : Welcome to geeksforgeeks
After replacing regex with replace_str : ASTHA TYAGI

```

**3。String replaceFirst() :** 该方法用给定的 replace_str 替换该字符串中与给定正则表达式匹配的第一个子字符串**。**

```
**Syntax**
public String replaceFirst(String regex, String replace_str)
**Parameters**
**regex :**the regular expression to which this string is to be matched.
**replace_str :** the string which would replace found expression.
**Return Value :** 
This method returns a resulting String. 
```

```
// Java code to demonstrate the
// working of  replaceFirst() 
public class rep3 {
   public static void main(String args[]) {

      // Initialising String
      String Str = new String("Welcome to geeksforgeeks");

      // original string 
      System.out.print("Original String : " );
      System.out.println(Str);

      // Using replaceFirst to replace regex with replace_str
      // Replaces 1st occurrence of geeks with ASTHA
      System.out.print("After replacing 1st occurrence of regex with replace_str  : " );
      System.out.println(Str.replaceFirst("geeks", "ASTHA"));

   }
}
```

**输出:**

```
Original String : Welcome to geeksforgeeks
After replacing 1st occurrence of regex with replace_str  : Welcome to ASTHAforgeeks 
```

**本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**