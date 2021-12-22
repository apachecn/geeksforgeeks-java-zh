# 将华氏温度转换为摄氏温度的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-华氏-摄氏/](https://www.geeksforgeeks.org/java-program-to-convert-fahrenheit-into-celsius/)

这里我们将华氏温度值转换为摄氏温度值。华氏温度和摄氏温度是温度的度量单位，单位为度，分别为华氏度的<sup>和摄氏度的<sup>。</sup></sup>

**公式**

```
Celsius = (Fahrenheit - 32) / 1.8
```

**逼近**

1.  Initialize the Fahrenheit temperature value to 50.0 and the Celsius temperature value to 0.0.
2.  Use the formula given above to calculate the centigrade temperature.
3.  Display the centigrade temperature.

**示例**

## Java

```
// Java Program to Convert Fahrenheit into Celsius

class fahrenheittocelsius {

    public static void main(String[] args)
    {
        // temperature in fahrenheit
        double fahrenheit = 50.0, celsius = 0.0;

        // calculate celsius temperature
        celsius = (fahrenheit - 32) / 1.8;

        // print the celsius temperature
        System.out.println(
            "value of temperature in celsius:" + celsius);
    }
}
```

**输出**

```
value of temperature in celsius:10.0

```

**时间复杂度:** O(1)