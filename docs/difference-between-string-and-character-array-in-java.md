# Java 中字符串和字符数组的区别

> 原文:[https://www . geesforgeks . org/Java 中字符串和字符数组的区别/](https://www.geeksforgeeks.org/difference-between-string-and-character-array-in-java/)

与 C/C++不同，字符数组和[字符串](https://www.geeksforgeeks.org/strings-in-java/)在 Java 中是两回事。字符数组和字符串都是字符的集合，但在属性方面有所不同。

 ****字符串**与**字符数组** :** 的区别

字符数组是可变的。

| **琴弦** | **字符数组** |
| --- | --- |
| 字符串是指表示为单一数据类型的字符序列。 | 字符数组是数据类型 char 的顺序集合。 |
| 字符串是不可变的。 |
| 像 substring()、charAt()等内置函数可以用在 Strings 上。 | 在 Java 中没有提供对字符数组进行操作的内置函数。 |
| “+”可以用来将附加的字符串组合在一起形成新的字符串。 | “+”不能用于追加两个字符数组。 |
| charAt()方法可用于访问字符串中特定索引处的字符。 | 字符数组中的字符可以像任何其他语言一样使用[]正常访问。 |
| 字符串可以任何方式存储在内存中。 | 字符数组中的元素连续存储在不断增加的内存位置。 |
| 所有字符串都存储在**字符串常量池**中。 | 所有字符数组都存储在**堆**中。 |
| 不首选用 Java 存储密码。 | 首选用 Java 存储密码。 |
| 可以使用 String 类的 [toCharArray()](https://www.geeksforgeeks.org/java-string-tochararray-example/) 方法将字符串转换为字符数组。
Eg:String s = " GEKES "；
char[]ch = s . tochararray()； | 通过将字符数组传递到**字符串构造器**中，可以将其转换为字符串。
Eg: char[] a = {'G '，' E '，' E '，' K '，' S ' }；
字符串 A =新字符串(A)； |