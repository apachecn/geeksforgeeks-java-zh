# 将字符串转换为布尔值的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-a-string-to-boolean/](https://www.geeksforgeeks.org/java-program-to-convert-a-string-to-boolean/)

给定字符串 **str** ，任务是编写一个 Java 程序，将给定字符串转换为其布尔值。

**示例:**

```
*Input: str = "true"*
*Output: true*
*Explanation: The boolean equivalent of true is true itself.*

*Input: str = "false"* 
*Output: false* 
*Explanation: The boolean equivalent of false is false itself.*

*Input: str = "yes"* 
*Output: false*
*Explanation: The boolean equivalent of yes is false since the given value is not equal to true.*
```

**字符串–**Java 中的字符串是由一个字符数组在内部支持的对象。由于数组是不可变的，而字符串也是一种保存字符的特殊数组，因此字符串也是不可变的。

**布尔–**布尔数据类型仅由两个值组成–**真**和**假。**如果字符串为真(忽略大小写)，则布尔等价为真，否则为假。

### 方法

在 Java 中，有许多方法可以将给定的字符串转换为布尔值。下面列出了其中的一些。

*   使用布尔.解析布尔()方法
*   使用布尔值()方法

### 1.使用布尔.解析布尔()方法

*   使用 [*布尔.帕斯布尔()*](https://www.geeksforgeeks.org/boolean-parseboolean-method-in-java-with-examples/) 方法。这是将字符串转换为布尔值的最常见方法。
*   此方法用于将给定字符串转换为其原始布尔值。
*   如果给定的字符串包含值*真*(忽略案例)，则该方法返回*真*。如果字符串包含除*真*以外的任何其他值，则该方法返回*假*。

**语法:**

```
boolean boolValue = Boolean.parseBoolean(String str) 
```

以下是上述方法的实施–

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert a String to Boolean

class GFG {

    // Function to convert a string
    // to its boolean value
    public static boolean
    stringToBoolean(String str)
    {
        // convert a given string to
        // its primitive boolean value
        // using parseBoolean() method
        boolean b1
            = Boolean.parseBoolean(str);

        // returns primitive boolean value
        return b1;
    }

    // Driver code
    public static void main(String args[])
    {
        // Given String str
        String str = "yes";

        // print the result
        System.out.println(
            stringToBoolean(str));

        // Given String str
        str = "true";

        // print the result
        System.out.println(
            stringToBoolean(str));

        // Given String str
        str = "false";

        // print the result
        System.out.println(
            stringToBoolean(str));
    }
}
```

**Output**

```
false
true
false
```

### 2.使用布尔值()方法

它类似于 [Boolean.parseBoolean()](https://www.geeksforgeeks.org/boolean-parseboolean-method-in-java-with-examples/) 方法，但它返回的是一个布尔对象，而不是一个基元布尔值。

**语法:**

```
boolean boolValue = Boolean.valueOf(String str) 
```

以下是上述方法的实施–

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert a String to Boolean

class GFG {

    // Function to convert a string
    // to its boolean object
    public static boolean
    stringToBoolean(String str)
    {
        // convert a given string to
        // its boolean object using
        // valueOf() method
        boolean b1 = Boolean.valueOf(str);

        // returns boolean object
        return b1;
    }

    // Driver code
    public static void main(String args[])
    {
        // Given String str
        String str = "yes";

        // print the result
        System.out.println(
            stringToBoolean(str));

        // Given String str
        str = "true";

        // print the result
        System.out.println(
            stringToBoolean(str));

        // Given String str
        str = "false";

        // print the result
        System.out.println(
            stringToBoolean(str));
    }
}
```

**Output**

```
false
true
false
```