# 访问枚举中定义的所有常量的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-access-enum 中定义的所有常量/](https://www.geeksforgeeks.org/java-program-to-access-all-the-constant-defined-in-the-enum/)

An [**enum**](https://www.geeksforgeeks.org/enum-in-java/) 是代表一组常量的特殊类。要创建枚举，请使用 enum 关键字(而不是类或接口)，并用逗号分隔常数。

```java
enum Day{

SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY;
}
```

**values()方法**可用于返回枚举中存在的所有值。

我们在 Javadoc 中看不到这个方法，因为编译器添加了它。编译器在创建枚举时会自动添加一些特殊方法。例如，它们有一个静态值方法，该方法返回一个数组，该数组按照枚举值的声明顺序包含所有枚举值。

因此 values()函数列出了枚举的所有值。

```java
Day days[] = Day.values();  

for(Day d : days)  
  System.out.print(d);
```

## 爪哇

```java
// Java program to show the usage of  
// values() method of java enumeration  

enum Day{ 
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY; 
} 

class Main{ 

    public static void main(String args[]) 
    { 
       // Calling values()
       Day days[] = Day.values(); 

       for(Day d : days) 
       System.out.println( d ); 
    } 
}
```

**输出**

```java
SUNDAY
MONDAY
TUESDAY
WEDNESDAY
THURSDAY
FRIDAY
SATURDAY

```