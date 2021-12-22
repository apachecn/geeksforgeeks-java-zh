# 将摄氏温度转换为华氏温度的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-摄氏度-华氏度/](https://www.geeksforgeeks.org/java-program-to-convert-celsius-into-fahrenheit/)

摄氏度刻度是一个温度刻度，它基于水在 0°C 时的冰点和水在 100°C 时的沸点。华氏度刻度是一个温度刻度，它具有水在 32°F 时的 a 冰点和水在 212°F 时的沸点。

**<u>例:</u>**

```java
Input : 0
Output: 32
Input :-40
Output:-40

```

> 华氏=(摄氏度*1.8)+32

**进场:**

1.  初始化摄氏值为 10.0，华氏值为 0.0
2.  使用以下公式计算华氏温度
3.  华氏=(摄氏度* 1.8)+32；
4.  显示华氏温度。

下面是上述方法的实现:

T3】JavaT5

```java
// Java Program to Convert Celsius into Fahrenheit
class celsiustofahrenheit {
    public static void main(String[] args)
    {
        // initialising
        double celsius = 10.0, fahrenheit = 0.0;

        // formula for conversion
        fahrenheit = (celsius * 1.8) + 32;
        System.out.println(
            " value of temperature in fahrenheit:"
            + fahrenheit);
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(1)

**空间复杂度:** O(1)