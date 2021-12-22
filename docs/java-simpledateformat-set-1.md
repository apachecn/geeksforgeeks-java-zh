# Java simple date format | set 1

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-simpledateformat-set-1/

SimpleDateFormat 类有助于格式化和解析数据。我们可以将日期从一种格式改为另一种格式。它允许用户将字符串日期格式解释为日期对象。我们可以根据需要修改日期。

**申报:**

```
public class SimpleDateFormat
extends DateFormat
```

**施工人员:**

*   **简单日期格式(String pattern_arg) :** 使用给定的模式–pattern _ arg(默认格式区域设置的默认日期格式符号)构建简单日期格式。
*   **简单日期格式(String pattern_arg，Locale _ Locale _ arg):**使用给定格式 Locale–Locale _ arg 的给定模式–pattern _ arg(默认日期格式符号)构建简单日期格式。
*   **简单日期格式(字符串模式 _arg，日期格式符号格式符号):**使用给定的模式–模式 _arg 和日期格式符号构建简单日期格式。

**演示简单日期格式类的 Java 程序**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating SimpleDateFormat class
import java.text.*;
import java.util.*;

public class NewClass
{
    public static void main(String[] args)
    {
        SimpleDateFormat geek = new SimpleDateFormat("dd / MM / yy");

        // Creating instance of the System date
        Calendar c = Calendar.getInstance();
        System.out.println("Present Date : " + c.getTime());

        // Formatting Date according "dd / MM / yy"
        String formattedDate = geek.format(c.getTime());
        System.out.println("Date formatted : "+formattedDate);

    }
}
```

**输出:**

```
Present Date : Wed Jun 21 18:21:13 IST 2017
Date formatted : 21 / 06 / 17
```

**方法:**

**1。set2 digitiyarstart():Java . text . simpledateformat . set2 digitiyarstart(Date start _ Date)**解析日期并将日期设置在 start _ Date 到 start _ Date+100 年的范围内。

**语法:**

```
public void set2DigitYearStart(Date starting_Date)
Parameters :
starting_Date : Date is set in the range - starting_Date to starting_Date + 100 years
Return  :
Returns void
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of set2DigitYearStart() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args) throws InterruptedException
    {
        SimpleDateFormat geek = new SimpleDateFormat("MM / dd / yy");
        try
        {
            Calendar c = Calendar.getInstance();
            c.setTime(geek.parse("10 / 27 / 16"));
            System.out.println("Initial Time : "+c.getTime());

            // Setting 1916 instead of 2016
            // Use of set2DigitYearStart() method
            geek.set2DigitYearStart(geek.parse("01 / 01 / 1900"));

            c.setTime(geek.parse("06 / 12 / 16"));
            System.out.println("New Time : "+c.getTime());

        }
        catch (ParseException except)
        {
            except.printStackTrace();
        }
    }
}
```

**输出:**

```
Initial Time : Thu Oct 27 00:00:00 IST 2016
New Time : Mon Jun 12 00:00:00 IST 1916
```

**2。get2 digitiyarstart():Java . text . simpledateformat . get2 digitiyarstart()**返回解析期间设置的 100 年期间的开始。

**语法:**

```
public void get2DigitYearStart()
Parameters :
-----
Return  :
Returns start of 100 year period that was set during parsing.
```

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of get2DigitYearStart() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args) throws InterruptedException
    {
        SimpleDateFormat geek = new SimpleDateFormat("MM / dd / yy");
        try
        {
            Calendar c = Calendar.getInstance();
            c.setTime(geek.parse("10 / 27 / 16"));       
            System.out.println("Initial Time : "+c.getTime());

            // Setting 1916 instead of 2016
            // Use of set2DigitYearStart() method
            geek.set2DigitYearStart(geek.parse("01 / 01 / 1900"));
            // Start Year is 1990.

            c.setTime(geek.parse("06 / 12 / 16"));
            System.out.println("New Time : "+c.getTime());

            // Use of get2DigitYearStart() method to check start year
            c.setTime(geek.get2DigitYearStart());
            System.out.println("START Year : "+c.get(Calendar.YEAR));

        }
        catch (ParseException except)
        {
            except.printStackTrace();
        }   
    }
}
```

**输出:**

```
Initial Time : Thu Oct 27 00:00:00 IST 2016
New Time : Mon Jun 12 00:00:00 IST 1916
START Year : 1900
```

**3。toPattern():Java . text . simpledate format . toPattern()**返回日期格式的模式。

**语法:**

```
public String toPattern()
Parameters :
-----
Return  :
Returns pattern of the Date format.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating use of toPattern() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args) throws InterruptedException
    {
        SimpleDateFormat geek = new SimpleDateFormat();

        // Initializing Calendar object
        Calendar c = Calendar.getInstance();

        // getting Current Date
        String dateToday = geek.format(c.getTime());

        System.out.println("Current Date : "+dateToday);

        // Use of toPattern() method
        // Printing Date Pattern
        System.out.println("Date Pattern : "+geek.toPattern());

    }
}
```

**输出:**

```
Current Date : 6/21/17 6:24 PM
Date Pattern : M/d/yy h:mm a
```

**4。parse():Java . text . simpledate format . parse()**将字符串中的文本解析为 Date 形式。它由类 SimpleDateFormat 中的分析指定。

**语法:**

```
public Date parse()
Parameters :
-----
Return  :
Returns Date parsed from a string.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of parse() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args) throws InterruptedException
    {
        SimpleDateFormat geek = new SimpleDateFormat("MM / dd / yy");
        try
        {
            Calendar c = Calendar.getInstance();

            // Use of .parse() method to parse Date From String 's'
            String s = "10 / 27 / 16" ;

            c.setTime(geek.parse(s));
            System.out.println("Time parsed from String : "+c.getTime());
        }
        catch (ParseException except)
        {
            except.printStackTrace();
        }
    }
}
```

**输出:**

```
Time parsed from String : Thu Oct 27 00:00:00 IST 2016
```

**5。apply pattern():Java . text . simpledate Format . apply pattern(String arg)**用于将定义的模式设置为日期格式。

**语法:**

```
public void applyPattern(String arg)
Parameters :
arg : defined pattern to be set to the Date Format.
Return  :
Void
```

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of applyPattern() method

import java.text.*;
import java.util.Calendar;
public class NewClass
{
    public static void main(String[] args) throws InterruptedException
    {
        SimpleDateFormat geek = new SimpleDateFormat();

        // Initializing calendar Object
        Calendar c = Calendar.getInstance();

        // Using 'arg' pattern
        String arg = "dd / MM / yyyy HH:mm Z";

        // Use of applyPattern() method to set date to 'arg' format
        geek.applyPattern(arg);

        // current date and time
        String currentdate = geek.format(c.getTime());
        System.out.println("Current Date : "+currentdate);

        // Print the pattern being used
        System.out.println("Pattern applied : "+geek.toPattern());
    }
}
```

**输出:**

```
Current Date : 21 / 06 / 2017 18:25 +0530
Pattern applied : dd / MM / yyyy HH:mm Z
```

**6。format():Java . text . simpledateformat . format(Date arg)**将日期或时间更改为字符串。

**语法:**

```
public final String format(Date arg)
Parameters :
arg : Date to be formatted to String
Return  :
Formatted String of Date
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of format() method

import java.text.*;
import java.util.Calendar;

public class NewClass
{
    public static void main(String[] args) throws InterruptedException
    {
        SimpleDateFormat geek = new SimpleDateFormat();

        // Initializing calendar Object
        Calendar c = Calendar.getInstance();

        System.out.println("Actual Date : "+c.getTime());

        // Use of format() method to format Date to String
        String currentdate = geek.format(c.getTime());
        System.out.println("Formatted Date to String : "+currentdate);

    }
}
```

**输出:**

```
Actual Date : Wed Jun 21 18:25:50 IST 2017
Formatted Date to String : 6/21/17 6:25 PM
```

**7。tolocalizedppattern():Java . text . simpledate format . tolocalizedppattern()**返回日期格式化程序的日期模式字符串。

**语法:**

```
public String toLocalizedPattern()
Parameters :
------
Return  :
Date pattern String used in the formatter
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program illustrating
// use of toLocalizedPattern() method

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

        System.out.println("Date : " + geek.format(c.getTime()));

        // Use of format() method to format Date to String
        System.out.println("Pattern in DateFormater 'geek' :"
                             + geek.toLocalizedPattern());

    }
}
```

**输出:**

```
Date : 6/21/17 6:27 PM
Pattern in DateFormater 'geek' : M/d/yy h:mm a
```

**下一个:**[Java . text . SimpleDateformat 类|集合 2](https://www.geeksforgeeks.org/java-text-simpledateformat-class-set-2/)

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。