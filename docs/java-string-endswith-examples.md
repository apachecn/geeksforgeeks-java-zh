# Java 字符串 endsWith()带示例

> 原文:[https://www . geesforgeks . org/Java-string-end swith-examples/](https://www.geeksforgeeks.org/java-string-endswith-examples/)

**[java 字符串](https://www.geeksforgeeks.org/string-class-in-java/) endsWith()** 方法检查字符串是否以指定的后缀结束。此方法返回一个布尔值 true 或 false。

**签名:**

```
public boolean endsWith(String suff)     

```

**参数:**

```
suff- specified suffix part 

```

**返回:**

```
true or false

```

**示例:**显示 **endsWith()** 方法的工作

```
// Java program to demonstrate
// working of endsWith() method

class Gfg1 {
    public static void main(String args[])
    {
        String s = "Welcome! to GeeksforGeeks";

        // Output will be true as s ends with Geeks
        boolean gfg1 = s.endsWith("Geeks");
        System.out.println(gfg1);
    }
}
```

**输出:**

```
true

```

```
// Java program to demonstrate
// working of endsWith() method

class Gfg2 {
    public static void main(String args[])
    {
        String s = "Welcome! to GeeksforGeeks";

        // Output will be false as s does not
        // end with "for"
        boolean gfg2 = s.endsWith("for");
        System.out.println(gfg2);
    }
}
```

**输出:**

```
false

```

```
// Java program to demonstrate
// working of endsWith() method

class Gfg3 {
    public static void main(String args[])
    {
        String s = "Welcome! to GeeksforGeeks";

        // Output will be true if the argument
        // is the empty string
        boolean gfg3 = s.endsWith("");
        System.out.println(gfg3);
    }
}
```

**输出:**

```
true

```