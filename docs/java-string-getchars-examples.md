# Java String getChars()带示例

> 原文:[https://www . geesforgeks . org/Java-string-getchars-examples/](https://www.geeksforgeeks.org/java-string-getchars-examples/)

**java 字符串 getChars()** 方法将给定的**字符串**中的字符复制到目标**字符数组**中。

**语法:**

```
public void **getChars**(int srhStartIndex, 
int srhEndIndex, char[] destArray, int destStartIndex)     
Parameters:
srhStartIndex : Index of the first character in the string to copy. 
srhEndIndex : Index after the last character in the string to copy.
destArray : Destination array where chars wil get copied.
destStartIndex : Index in the array starting from where the chars
                 will be pushed into the array.
Return: It does not return any value.
```

**异常:****StringIndexOutOfBoundsException–**如果 srhStartIndex、srhEndIndex 不在适当的范围内。

**示例:**展示 **getChars()** 方法的工作

```
// Java program to demonstrate
// working of getChars() method

class Gfg1 {
    public static void main(String args[])
    {
        String str = "Welcome! to GeeksforGeeks";

        char[] destArray = new char[20];
        try {
            str.getChars(12, 25, destArray, 0);
            System.out.println(destArray);
        }
        catch (Exception ex) {
            System.out.println(ex);
        }
    }
}
```

**输出:**

```
GeeksforGeeks

```

```
// Java program to demonstrate
// exception condition in
// working of getChars() method

class Gfg2 {
    public static void main(String args[])
    {
        String str = "Welcome! to GeeksforGeeks";

        char[] destArray = new char[20];
        try {
            // Starting index 0 and ending index 24
            str.getChars(12, 26, destArray, 0);
            System.out.println(destArray);
        }
        catch (Exception ex) {
            System.out.println(ex);
        }
    }
}
```

**输出:**

```
java.lang.StringIndexOutOfBoundsException: String index out of range: 26

```