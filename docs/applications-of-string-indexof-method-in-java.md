# 字符串 indexOf()方法在 Java 中的应用

> 原文:[https://www . geesforgeks . org/applications-of-string-index of-in-method-Java/](https://www.geeksforgeeks.org/applications-of-string-indexof-method-in-java/)

有 **四** 变型 [indexOf()法](https://www.geeksforgeeks.org/java-string-indexof/) 。

1.  **indexOf():** 此方法返回******索引** 在此字符串内的第一个出现指定字符，如果该字符没有出现则返回-1。****
2.  ******indexOf(char ch，int** start **):** 此方法返回第一个出现指定字符的字符串内的索引，在指定索引处开始搜索，如果该字符没有出现，则返回-1。****
3.  ******indexOf(String str):** 此方法返回指定子字符串的第一个匹配项的索引。如果它不作为子字符串出现，则返回-1。****
4.  ******indexOf(String str，int** start **):** 此方法返回第一个出现在指定的 **子串** ， **在指定的索引处开始** 的字符串内的索引。如果没有发生，则返回-1。****

****现在让我们想出 *indexOf()方法*在 java 中的应用，其中最常见的是下面列出的如下所示****:********

1.  ****要知道一个字符是元音还是辅音。****
2.  ****计算字符串中任何字符的出现次数。****
3.  ****了解字符串中是否存在字符。****
4.  ****查找字符串中是否存在子字符串。****
5.  ****查找输入是数字、字母还是特殊字符。****

****现在，让我们通过在干净的 java 程序的帮助下支持它们来讨论这些应用程序****

******应用 1******

****我们将检查字符是否出现在预定义的元音串中。如果它存在，那么它是一个元音或辅音。****

******例******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**class Vowels
{
        // function to check if the passed
        // character is a vowel
    public static boolean vowel(char c)
    {
        return "aeiou".indexOf(Character.toLowerCase(c))>=0;
    }

        // Driver program
    public static void main(String[] args)
    {
        boolean isVowel = vowel('z');

                // Printing the output
                if(isVowel)
            System.out.println("Vowel");
        else
            System.out.println("Consonant");
    }
}**
```

******Output**

```
Consonant
```**** 

******应用程序 2:** 统计字符串中任何字符的出现次数。****

****在这个程序中，我们将检查字符串中是否存在字符。如果存在，那么我们将递增计数器并再次执行 indexOf()函数，直到找不到索引。****

******例******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**import java.io.*;

class GFG {
    public static void main (String[] args) {
        String s="GeeksForGeeks";
      int count=0;

      for(int i=0;i<s.length();i++)
      {
      i=s.indexOf('e',i);
        if(i<0)
              break;
        count++;
      }
      System.out.println("Count is "+ count);
    }
}**
```

******Output**

```
Count is 4
```**** 

******应用 3:** 了解字符串中是否存在字符。****

****在这个程序中，我们将检查字符串中是否存在字符。****

******例******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**import java.io.*;

class GFG {
    public static void main (String[] args) {
        String s="GeeksForGeeks";
      System.out.println(s.indexOf('m')<0?"Character not found":"Character found");
    }
}**
```

******Output**

```
Character not found
```**** 

******应用程序 4:** 查找字符串中是否存在子字符串。****

****在这个程序中，我们将检查字符串中是否存在字符。****

******例******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**public class Geeks {
public static void main(String args[])
    {

        // Initialising string
        String Str = "Welcome to geeksforgeeks";

        // Initialising search string
        String subst = "geeks";

        System.out.println(Str.indexOf(subst)>=0?"Substring found at "+Str.indexOf(subst):"Substring not found");
}
}**
```

******Output**

```
Substring found at 11
```**** 

******应用 5:查找输入是数字** **还是字母或特殊字符。******

****在这个程序中，我们将检查字符是否存在于一组预定义的字符串中。****

******例******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**class Geek
{
    public static void check(char c)
    {
        if("0123456789".indexOf(c)>=0)
        {
          System.out.print("It is a digit\n");
        }
      else if("[abcdefghijklmnopqrstuvwxyz]".indexOf(Character.toLowerCase(c))>=0)
      {
        System.out.print("It is a Alphabet\n");
      }
      else{
        System.out.print("It is a Special Character\n");
      }
    }

        // Driver program
    public static void main(String[] args)
    {
      check('1');
      check('a');
      check('@');

    }
}**
```

******Output**

```
It is a digit
It is a Alphabet
It is a Special Character
```****