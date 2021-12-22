# Java 程序添加两个复数

> 原文:[https://www . geesforgeks . org/Java-程序添加两个复数/](https://www.geeksforgeeks.org/java-program-to-add-two-complex-numbers/)

**复数** 是由两部分组成的数——实数数和虚数数。复数是更复杂的数学的组成部分，比如代数。复数的标准格式是 a + bi，实数排在第一位，虚数排在最后。

**任何复数的一般形式为:**

```
a+ib

Where "a" is real number and "b" is Imaginary number.
```

**复数的构造**

为了创建一个复数，我们将传递虚数和实数作为构造函数的参数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to construct the complex number

class ComplexNumber {

    // variables to hold real and imaginary part of complex
    // number
    int real, image;

    // Constructor which will be used while creating complex
    // number
    public ComplexNumber(int r, int i)
    {
        this.real = r;
        this.image = i;
    }

    // function to print real number
    public void showC()
    {
        System.out.println(this.real + " +i " + this.image);
    }

    // we will implement  this function for addition
    public complex add(ComplexNumber, ComplexNumber);
}
```

**添加功能**

*   基本上，两个复数的相加是通过将第一个复数的实数部分与第二个复数的实数部分相加来完成的。
*   以及将第一复数的虚部与第二复数相加，得到第三复数。
*   所以这意味着我们的 **add()** 将返回另一个复数。

> 《出埃及记》两个复数的加法
> 
> (a1)+(B1)I –( 1)
> 
> (a2)+(B2)I –( 2)
> 
> 添加(1)和(2)看起来像
> 
> **(a1+a2) + (b1+b2)i**

**功能定义:**

```
ComplexNumber add(ComplexNumber n1, ComplexNumber n2){

  ComplexNumber res = new ComplexNumber(0,0); //creating blank complex number 

  // adding real parts of both complex numbers
  res.real = n1.real + n2.real;

  // adding imaginary parts
  res.image = n1.image + n2.image;

  // returning result
  return res;

}
```

**代号:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to add two complex numbers

class ComplexNumber {

    // variables to hold real and imaginary part of complex
    // number
    int real, image;

    // Constructor which will be used while creating complex
    // number
    public ComplexNumber(int r, int i)
    {
        this.real = r;
        this.image = i;
    }

    // function to print real number
    public void showC()
    {
        System.out.print(this.real + " +i" + this.image);
    }

    // function for addition
    public static ComplexNumber add(ComplexNumber n1,
                                    ComplexNumber n2)
    {

        // creating blank complex number
        // to store result
        ComplexNumber res = new ComplexNumber(0, 0);

        // adding real parts of both complex numbers
        res.real = n1.real + n2.real;

        // adding imaginary parts
        res.image = n1.image + n2.image;

        // returning result
        return res;
    }

    public static void main(String arg[])
    {

        // creating two complex numbers
        ComplexNumber c1 = new ComplexNumber(4, 5);
        ComplexNumber c2 = new ComplexNumber(10, 5);

        // printing complex numbers
          System.out.print("first Complex number: ");
        c1.showC();

        System.out.print("\nSecond Complex number: ");
        c2.showC();

        // calling add() to perform addition
        ComplexNumber res = add(c1, c2);

        // displaying addition
        System.out.println("\nAddition is :");
        res.showC();
    }
}
```

**Output**

```
first Complex number: 4 +i5
Second Complex number: 10 +i5
Addition is :
14 +i10
```