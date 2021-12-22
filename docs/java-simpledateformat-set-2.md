# Java simple date format | set 2

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-simpledateformat-set-2/

[Java simpledate format | Set 1](https://www.geeksforgeeks.org/java-text-simpledateformat-class-set-1/)
**更多文字的方法。简单日期格式类:**

*   **clone():Java . text . SimpleDateFormat . clone()**创建 SimpleDateformat 的副本。

```
Syntax :
public Object clone()
Parameters : 
-------
Return : 
copy of the SimpleDateFormat
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of SimpleDateFormat.clone() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args) throws InterruptedException
    {
        // Date Formatter
        SimpleDateFormat geek = new SimpleDateFormat();

        // Initializing calendar Object
        Calendar c = Calendar.getInstance();

        // Use of clone() :
       System.out.println("Clone : " + geek.clone());

    }
}
```

**输出:**

```
Clone : java.text.SimpleDateFormat@a9427c06
```

*   **hashCode():Java . text . SimpleDateFormat . hashCode()**返回 SimpleDateformat 对象的哈希代码值。

```
Syntax :
public int hashCode()
Parameters : 
--------
Return : 
hash code value for the SimpleDateFormat object.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of SimpleDateFormat.hashCode() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args) throws InterruptedException
    {
        // Date Formatter
        SimpleDateFormat geek = new SimpleDateFormat();

        // Initializing calendar Object
        Calendar c = Calendar.getInstance();

        // Use of hashCode() :
       System.out.println("Hash Code : " + geek.hashCode());

    }
}
```

**输出:**

```
Hash Code : -1455260666
```

*   **等于(对象对象):Java . text . SimpleDateFormat . equals(对象对象对象)**比较两个 SimpleDateFormat 对象

```
Syntax :
public boolean equals(Object obj)
Parameters : 
obj : object to compare with
Return : 
true, if equal ; else false
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of SimpleDateFormat.equals() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args)
                throws InterruptedException, ParseException
    {

    // Setting formatter 
    SimpleDateFormat geek = new SimpleDateFormat();

    geek.applyPattern("MMM");

    // Use of equals() : 
    System.out.println("Is equal ? : " +
                      geek.equals(new SimpleDateFormat()));

    }
}
```

**输出:**

```
Is equal ? : false
```

*   **设置日期格式符号(日期格式符号新符号):Java . text . simpledateformat . setDateFormatSymbols(日期格式符号新符号)**设置所需日期格式的日期和时间格式符号。

```
Syntax :
public void setDateFormatSymbols(DateFormatSymbols newSymbols)
Parameters : 
newSymbols : new format symbols for data and time
Return : 
-------
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of DateFormatSymbols() method

import java.text.*;
import java.util.*;

public class NewClass
{
    public static void main(String[] args) throws InterruptedException, ParseException
    {

        DateFormatSymbols format_symb =
                     new DateFormatSymbols(new Locale("en", "US"));
        String[] days = format_symb.getShortWeekdays();

        int j = 1;
        for (int i = 1; i < days.length; i++)
        {

            System.out.print("Day" + j++ + " : " + days[i] + "\n");
        }       
    }
}
```

**输出:**

```
Day1 : Sun
Day2 : Mon
Day3 : Tue
Day4 : Wed
Day5 : Thu
Day6 : Fri
Day7 : Sat
```

*   **getDateFormatSymbols():Java . text . simpledateformat . getDateFormatSymbols()**返回日期和时间格式符号的副本。

```
Syntax :
public DateFormatSymbols getDateFormatSymbols()
Parameters : 
-------
Return : 
date and time format symbols.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of getDateFormatSymbols() method

import java.text.*;
import java.util.*;

public class NewClass
{
    public static void main(String[] args)
                   throws InterruptedException, ParseException
    {
        SimpleDateFormat geeks = new SimpleDateFormat();

        String g_date = geeks.format(new Date());

        // Use of getDateFormatSymbols () :
        System.out.println("" + geeks.getDateFormatSymbols());
        System.out.println("Date : " + g_date);
    }
}
```

**输出:**

```
java.text.DateFormatSymbols@f86e64e0
Date : 6/24/17 12:49 PM
```

*   **applyLocalizedPattern(字符串字符串):Java . text . SimpleDateformat . applylocalized pattern(字符串字符串)**将给定的本地化字符串模式应用于日期格式。

```
Syntax :
public void applyLocalizedPattern(String str)
Parameters : 
str : string pattern set to new date and time format
Return : 
-------
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustarting
// use of applyLocalizedPattern() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args)
                                throws InterruptedException
    {       
        SimpleDateFormat geek = new SimpleDateFormat();
        // Initializing calendar Object
        Calendar c = Calendar.getInstance();

        // Using 'arg' pattern
        String arg = "MM / dd / yy  HH:mm Z";

        // Use of applyLocalizedPattern()
        geek.applyLocalizedPattern(arg);

     System.out.println("Use of applyLocalizedPattern()
                             : "+geek.toLocalizedPattern());
    }
}
```

**输出:**

```
Use of applyLocalizedPattern() : MM / dd / yy  HH:mm Z
```

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。