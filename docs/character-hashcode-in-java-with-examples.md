# Java 中的 Character.hashCode()，示例

> 原文:[https://www . geesforgeks . org/character-hashcode-in-Java-with-examples/](https://www.geeksforgeeks.org/character-hashcode-in-java-with-examples/)

Java.lang.Character.hashCode()是 Java 中的一个内置方法，它为这个字符返回一个哈希代码。返回的哈希代码等于调用 charValue()的结果。

**语法:**

```
public int hashCode()

This function does not accepts any parameter.

```

**返回值:**该方法返回该字符的哈希码值。

下面的程序说明了 Java.lang.Character.hashCode()函数:

**程序 1** :

```
// Java program to demonstrate the
// function when the value passed in the parameter
// is a character 
import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {
        // parameter ch
        char ch = 'B';
        // assigns character values
        Character c = Character.valueOf(ch);

        // assign hashcodes of c1, c2 to i1, i2
        int i = c.hashCode();

        // prints the character values
        System.out.println("Hashcode of " + ch + " is " + i);
    }
}
```

**Output:**

```
Hashcode of B is 66

```

**程序 2** :

```
// Java program to demonstrate the
// function when the value passed in the parameter
// is a number 
import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {
        // parameter ch
        char ch = '6';
        // assigns character values
        Character c = Character.valueOf(ch);

        // assign hashcodes of ch 
        int i = c.hashCode();

        // prints the character values
        System.out.println("Hashcode of " + ch + " is " + i);
    }
}
```

**Output:**

```
Hashcode of 6 is 54

```