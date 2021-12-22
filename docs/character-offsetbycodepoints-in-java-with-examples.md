# Java 中的 Character.offsetByCodePoints()示例

> 原文:[https://www . geeksforgeeks . org/character-offsetbycodepoints-in-Java-with-examples/](https://www.geeksforgeeks.org/character-offsetbycodepoints-in-java-with-examples/)

**character . offset by codepoints(char[]a，int start，int count，int index，int codePointOffset)** 是 Java 中的一个内置方法，它返回给定 char 子数组内的索引，该索引从给定索引偏移了 codePointOffset 代码点。start 和 count 参数指定 char 数组的子数组。由索引和代码点偏移量给定的文本范围内的不成对的替代项各计为一个代码点。
chart 类的 offsetByCodePoints(char[] a，int start，int count，int index，int codePointOffset)方法是静态的，因此应该静态访问。
非静态方法通常通过声明 method_name(参数)来调用。但是在这种情况下，由于它是一个静态方法，类名在调用过程中作为后缀被追加。如果试图以非静态方式调用 java offsetByCodePoints()方法，可能会遇到编译问题。

**语法:**

```java
public static int offsetByCodePoints(char[] a, int start, int count, int index,
int codePointOffset)
```

**参数:**

*   *a:* 字符数组
*   *开始:*子阵列第一个字符的索引
*   *计数:*子数组的长度，以字符为单位
*   *索引:*要偏移的索引
*   *代码点偏移量:*代码点的偏移量

**返回值:**这个方法返回一个整型值，即子数组内的索引。

**异常:**

*   NullPointerException:如果 *a* 为空。
*   IndexOutOfBoundsException:如果*开始*或*计数*为负，或者如果*开始+计数*大于给定数组的长度，或者如果*索引*小于*开始*或大于*开始+计数*，或者如果*码点偏移量*为正并且文本范围从*索引*开始到*开始+计数–1 或者如果*代码点偏移量*为负，并且以索引–1 开始和结束的文本范围小于代码点偏移量代码点的绝对值。*

下面的程序说明了 Character.offsetByCodePoints()方法:

```java
//Java program for offsetByCodePoints() method
import java.lang.*;
public class gfg {
   public static void main(String[] args) {
      // Creating a char array c_arr and assigning values
      char[] c_arr = new char[] {'g','e','e','k','s'};

      // Integer primitives 
      int s = 1;
      int c= 4;

      // Creating and assigning result of offsetByCodePoints
      // On subarray of c_arr to r
     int r = Character.offsetByCodePoints(c_arr, s, c, 1, 2);

      String st = "The index within the subarray is " + r;

      System.out.println(st);
   }
}
```

**Output:**

```java
The index within the subarray is 3

```

参考:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # offsetByCodePoints(char[]，%20int，%20int，%20int，%20int)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#offsetByCodePoints(char[],%20int,%20int,%20int,%20int))