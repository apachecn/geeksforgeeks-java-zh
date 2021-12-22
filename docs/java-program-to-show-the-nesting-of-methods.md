# 显示方法嵌套的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-show-the-nesting-of-methods/](https://www.geeksforgeeks.org/java-program-to-show-the-nesting-of-methods/)

在 java 中，我们在一个类中创建的方法和变量只能用该类的对象来调用，或者在[静态方法](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)的情况下，我们可以直接用类名来调用。方法和变量可以在点运算符的帮助下调用。但是有一种特殊情况，一个方法也可以借助类名被另一个方法调用，但条件是它们应该存在于同一个类中。

**语法:**

```java
class Main
{
    method1(){ 

        // statements
    } 

    method2()
    {
       // statements

      // calling method1() from method2()
       method1();
    }
    method3()
    {
      // statements

      // calling of method2() from method3()
      method2();
    }
}
```

**例 1:**

在下面的示例中，该类包含两种方法，即面积()和体积()，后者用于计算球体的面积和体积。main()方法是调用 area()方法计算球体的面积，调用 volume()方法计算球体的体积，然后显示结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program implementing the Nesting of Methods

public class NestingMethodCalls1 {

    public void Area(double r)
    {
        // value of r is coming from main method from which
        // this method is called Math.pi is used for getting
        // the value of pi
        System.out.println(
            "****** Inside Area method ******");

          // calculate area
        double a = 4 * Math.PI * r * r;

          // print the area
        System.out.println("Surface area of a Sphere is : "
                           + a);
    }
    public void Volume(double r)
    {
        // value of r is coming from main method from which
        // this method is called Math.pi is used for getting
        // the value of pi
        System.out.println(
            "****** Inside Volume method ******");

          // calculate the volume
        double v = (4 / 3) * Math.PI * r * r * r;

          // print the volume
        System.out.println("Volume of a Sphere is : " + v);
    }
    public static void main(String args[])
    {
        // creating object of class GeeksforGeeks
        GeeksforGeeks gfg = new GeeksforGeeks();

        // calling of method Area() from main method
        gfg.Area(12);

        // calling of method Volume() from main method
        gfg.Volume(12);
    }
}
```

**Output**

```java
****** Inside Area method ******
Surface area of a Sphere is : 1809.5573684677208
****** Inside Volume method ******
Volume of a Sphere is : 5428.672105403162

```

**例 2:**

在下面的示例中，类包含两个方法，即 swap()和 gfg1()。swap()方法用于交换两个变量，gfg1()方法用于添加两个数字。main()方法调用带有两个值的 gfg1()方法来添加两个数字，gfg1()方法调用 swap()方法来执行两个数字的交换。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program implementing the Nesting of Methods

public class NestingMethodCalls2 {
    public void swap(int x, int y)
    {
        System.out.println(
            "*********This is swap method***********");
        System.out.println("Before swapping:x=" + x + " "
                           + "y=" + y);

          // swap the numbers
        int z = x;
        x = y;
        y = z;

        System.out.println("After Swapping:a=" + x + " "
                           + "b=" + y);
    }
    public void gfg1(int a, int b)
    {
        System.out.println(
            "*********This is gfg1 method***********");
        System.out.println("Before performing operation:a="
                           + a + " "
                           + "b=" + b);
        a = a + 10;
        b = b + 12;
        System.out.println("After operation:a=" + a + " "
                           + "b=" + b);
        // calling of swap() method from gfg1() method
        swap(a, b);
    }
    public static void main(String args[])
    {
        // creating the object of class GeeksforGeeks2
        GeeksforGeeks2 gfg2 = new GeeksforGeeks2();

        int a = 20, b = 30;
        // calling of method gfg1() from main method

        gfg2.gfg1(a, b);
    }
}
```

**Output**

```java
*********This is gfg1 method***********
Before performing operation:a=20 b=30
After operation:a=30 b=42
*********This is swap method***********
Before swapping:x=30 y=42
After Swapping:a=42 b=30

```

**例 3:**

在下面的示例中，类包含三个方法，即 a1()，a2()，a3()。main()方法用值 a 和 b 调用 a3()方法，然后 a2()调用另一个方法 a1()，然后这个方法执行所有操作，然后将它们的值传递给另一个方法，这意味着这个方法然后调用另一个方法，即 a2()，然后这个方法将执行，然后程序终止。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program implementing the Nesting of Methods

public class NestingMethodCalls3 {
    public void a1(int a, int b)
    {
        a = a + 10;
        b = b + 20;
        System.out.println(
            "****** Inside a1 method ******");
        System.out.println("a = " + a + " "
                           + "b = " + b);

        // calling method a2() from a1() with parameters a
        // and b
        a2(a, b);
    }
    public void a2(int x, int y)
    {
        x = x + 100;
        y = y + 200;
        System.out.println(
            "****** Inside a2 method ******");
        System.out.println("x = " + x + " "
                           + "y = " + y);
    }
    public void a3(int w, int z)
    {
        w = w + 50;
        z = z - 50;
        System.out.println(
            "****** Inside a3 method ******");
        System.out.println("w = " + w + " "
                           + "z = " + z);

        // calling method a1() from method a3() with
        // parameters w and z
        a1(w, z);
    }
    public static void main(String[] args)
    {
        // creating the object of class GeeksforGeeks3()
        GeeksforGeeks3 gfg3 = new GeeksforGeeks3();

        int a = 100, b = 200;

        // calling method a3() from main() method
        gfg3.a3(a, b);
    }
}
```

**Output**

```java
****** Inside a3 method ******
w = 150 z = 150
****** Inside a1 method ******
a = 160 b = 170
****** Inside a2 method ******
x = 260 y = 370

```