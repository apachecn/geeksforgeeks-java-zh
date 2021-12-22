# 将字符串的数组列表转换为 Java 中的字符串数组

> 原文:[https://www . geesforgeks . org/convert-an-ArrayList-of-string-to-string-array-in-Java/](https://www.geeksforgeeks.org/convert-an-arraylist-of-string-to-a-string-array-in-java/)

在 Java 中，众所周知 [ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 类是从 List 接口派生出来的。这里我们得到了一个字符串数组列表，任务是将数组列表转换成字符串数组。

插图:

```
Input : ArrayList = [ "Geeks", "for", "Geeks" ]
Output: String[] = {"Geeks", "for", "Geeks"}
```

```
Input : ArrayList = [ "Jupiter", "Saturn", "Uranus", "Neptune", "Sun"]
Output: String[] = {"Jupiter", "Saturn", "Uranus", "Neptune", "Sun"}
```

**方法:**

1.  使用数组列表类的 get()方法
2.  使用数组列表类的 toArray()方法
3.  使用数组类的 *copyOf()方法*

### 方法 1:使用数组列表类的 get()方法

**语法:**

```
str[j] = a1.get(j)
```

**进场:**

1.  获取字符串的数组列表。
2.  使用 *size()方法*找到数组列表的大小，创建一个这个大小的字符串数组。
3.  使用 *get()方法*逐个获取数组列表的每个元素。
4.  使用赋值(=)运算符将每个元素赋给字符串数组。
5.  打印字符串数组。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert ArrayList to Array
// using toArray() Method

// Importing required classes
import java.util.ArrayList;
import java.util.Arrays;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty ArrayList of string type
        ArrayList<String> al = new ArrayList<String>();

        // Populating the ArrayList by custom elements
        al.add("Anshul Aggarwal");
        al.add("Mayank Solanki");
        al.add("Abhishek Kelenia");
        al.add("Vivek Gupta");

        String[] str = new String[al.size()];

        for (int i = 0; i < al.size(); i++) {
            str[i] = al.get(i);
        }

        // Printing using for each loop
        for (String k : str) {
            System.out.println(k);
        }
    }
}
```

**Output**

```
Anshul Aggarwal
Mayank Solanki
Abhishek Kelenia
Vivek Gupta
```

### **方法 2:** 使用数组列表类的 toArray()方法

这里我们将创建一个对象数组，通过创建一个字符串数组来存储从数组列表中接收的元素。

**语法:**

```
Object[] arr = a1.toArray()
String str = (String)obj;
```

**进场:**

1.  获取字符串的数组列表。
2.  使用 toArray()方法将数组列表转换为对象数组。
3.  使用类型转换将每个元素迭代并转换为所需的类型。在这里，它被转换为字符串类型并添加到字符串数组中。
4.  打印字符串数组

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert ArrayList to Array
// using toArray() Method

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty ArrayList of string type
        ArrayList<String> al = new ArrayList<String>();

        // Populating the ArrayList by custom elements
        al.add("Anshul Aggarwal");
        al.add("Mayank Solanki");
        al.add("Abhishek Kelenia");
        al.add("Vivek Gupta");

        // Converting above List to array using toArray()
        // method and storing it in an string array
        String k[] = al.toArray(new String[al.size()]);

        // Iterating over above string array
        for (String str : k) {

            // Printing the elements in above array
            System.out.println(str);
        }
    }
}
```

**Output**

```
Anshul Aggarwal
Mayank Solanki
Abhishek Kelenia
Vivek Gupta
```

### **方法 3:** 使用数组类的 *copyOf()* 方法

**语法:**

```
Object[] gfg = a1.toArray()
String[] str = Arrays.copyOf(gfg, gfg.length, String[].class);
```

**进场:**

1.  获取字符串的数组列表。
2.  使用 toArray()方法将数组列表转换为对象数组。
3.  使用 Arrays.copyOf()方法将其转换为字符串数组。
4.  打印字符串数组。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert ArrayList to Array
// using toArray() Method

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty ArrayList of string type
        ArrayList<String> al = new ArrayList<String>();

        // Populating the ArrayList by custom elements
        al.add("Anshul Aggarwal");
        al.add("Mayank Solanki");
        al.add("Abhishek Kelenia");
        al.add("Vivek Gupta");

        String[] answer = Arrays.copyOf(
            al.toArray(), al.size(), String[].class);
        System.out.println(Arrays.toString(answer));
    }
}
```

**Output**

```
[Anshul Aggarwal, Mayank Solanki, Abhishek Kelenia, Vivek Gupta]
```