# 使用 Java 中的 SimpleDateFormat 类查找星期几

> 原文:[https://www . geeksforgeeks . org/find-星期几-使用-simpledateformat-class-in-Java/](https://www.geeksforgeeks.org/find-day-of-week-using-simpledateformat-class-in-java/)

给定日、月、年，任务是使用 Java 中的 [SimpleDateFormat 类](https://www.geeksforgeeks.org/java-simpledateformat-set-1/)找到对应的星期几。

**示例**

> 输入:11-08-2020
> 
> 输出:星期二
> 
> 说明:2020 年 8 月 11 日对应的日子是星期二。
> 
> 输入:17-08-2006
> 
> 输出:星期四
> 
> 说明:2006 年 8 月 17 日对应的日子是星期四。

**进场:**

*   以整数类型输入用户的日期、月份和年份。
*   检查日期、月份和年份是否在要求的范围内。如果没有，则引发错误消息。
*   使用[简单日期格式](https://www.geeksforgeeks.org/java-simpledateformat-set-1/)类将输入转换为日期类型。
*   使用 SimpleDateFormat 类将日期格式化为一周中相应的一天。
*   打印一周中相应的一天。

**注意:**如果想要一天的全名(例如:周日、周一)，请使用“EEEE”。如果你想要一天中更短的名字(例如:孙，孟)，请使用“EE”。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for the above approach
import java.util.Date;
import java.text.SimpleDateFormat;
import java.text.ParseException;

public class GFG {

    public void findDay(int day, int month, int year)
    {
        String dayOfWeek = "";
        boolean wrongDate = false;

        if (day < 1 || day > 31) {
            dayOfWeek += "Give day in range. ";
            wrongDate = true;
        }

        if (month < 1 || month > 12) {
            dayOfWeek += "Give month in range. ";
            wrongDate = true;
        }

        if (year <= 0) {
            wrongDate = true;
            dayOfWeek += "Give year in range.";
        }

        if (!wrongDate) {

            SimpleDateFormat dateFormatter
                = new SimpleDateFormat("dd-MM-yyyy");
            String dateString
                = day + "-" + month + "-" + year;

            try {
                // Parse the String representation of date
                // to Date
                Date date = dateFormatter.parse(dateString);
                dayOfWeek
                    = "Day of week on " + dateString + " : "
                      + new SimpleDateFormat("EEEE").format(
                            date);
            }
            catch (ParseException e) {
                e.printStackTrace();
            }
        }

        System.out.println(dayOfWeek);
    }

    // Driver Code  
    public static void main(String arg[])
    {

        GFG gfg = new GFG();
        gfg.findDay(17, 8, 2006);
    }
}
```

**Output**

```java
Day of week on 17-8-2006 : Thursday
```