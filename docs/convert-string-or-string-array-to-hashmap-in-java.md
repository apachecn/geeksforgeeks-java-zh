# 将字符串或字符串数组转换为 Java 中的 HashMap

> 原文:[https://www . geesforgeks . org/convert-string-or-string-array-to-hashmap-in-Java/](https://www.geeksforgeeks.org/convert-string-or-string-array-to-hashmap-in-java/)

考虑一个字符串对象，它包含用逗号分隔的学生姓名和学号，每个学生包含用冒号分隔的姓名和学号。现在需要的是将字符串转换成一个 Map 对象，这样每个学生的学号就变成了 HashMap 的键，名字就变成了 HashMap 对象的值。

为了将字符串转换为 HashMap，该过程分为两个部分:

*   输入字符串被转换为字符串数组作为输出。
*   字符串数组形式的输入被转换为[哈希映射](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)。

输入字符串元素，如下所示:

```
Input : "Aashish:1, Bina:2, Chintu:3"
```

**进场:**

*   **阶段 1:** 输入字符串转换为字符串数组作为输出。
*   **阶段 2:** 作为字符串数组的输入被转换为[哈希映射](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)。

**第一阶段:**

*   首先，我们用逗号分割字符串，并将其存储在数组部分中。拆分后我们有以下内容:

```
"Aashish:1","Bina:2", "Chintu:3"
```

*   然后在零件上迭代，分割学生数据，得到学生姓名和学号。并将 roll no 设置为键，将名称设置为 HashMap 的值。

**第 2 阶段:**

我们也可以将一个字符串数组转换成一个 HashMap。假设我们有一个学生名字的字符串数组和一个卷号数组，我们想把它转换成 HashMap，这样卷号就变成了 HashMap 的键，名字就变成了 HashMap 的值。

**注意:**两个数组的大小应该相同。

字符串元素的输入数组如下，将在第 1 阶段输出

```
String stuName[] = {"Aashish","Bina","Chintu"}
Integer stuRollNo[] = {1,2,3}
```

**进场:**

*   迭代数组，并将滚动号设置为键，将名称设置为哈希表中的值。

**第 1 阶段**–字符串到字符串数组

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Convert String or String array to HashMap In Java

// Phase 1: Input- String converted to ArrayofStrings

// Importing java generic libraries
import java.util.*;

class GFG {

  // Main driver method
    public static void main(String[] args)
    {
        // String object that contains the student name and
        // roll number separated by a comma
        String student = "Aashish:1, Bina:2, Chintu:3";

        // New HashMap obj
        Map<String, String> hashMap
            = new HashMap<String, String>();

        // split the String by a comma
        String parts[] = student.split(",");

        // iterate the parts and add them to a HashMap
        for (String part : parts) {

            // split the student data by colon to get the
            // name and roll number
            String stuData[] = part.split(":");

            String stuRollNo = stuData[0].trim();
            String stuName = stuData[1].trim();

            // Add to map
            hashMap.put(stuRollNo, stuName);
        }

        // Print hashMap
        System.out.println("String to HashMap: " + hashMap);
    }
}
```

**Output**

```
String to HashMap: {Chintu=3, Bina=2, Aashish=1}
```

**阶段 2**–字符串到数组到哈希映射

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Convert String or String array to HashMap In Java

// Phase 2: Input- Array of strings converted to HashMap.

// Importing java generic libraries
import java.util.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // String array that contains the student name
        String stuName[] = { "Aashish", "Bina", "Chintu" };

        // Integer array that contains roll number of the
        // students
        Integer stuRollNo[] = { 1, 2, 3 };

        // New HashMap obj
        Map<Integer, String> hashMap
            = new HashMap<Integer, String>();

        // Iterating over array of strings
        for (int i = 0; i < stuName.length; i++) {

            // And set roll no as key and the name as value
            hashMap.put(stuRollNo[i], stuName[i]);
        }

        // Printing HashMap
        System.out.println("String to hashmap: " + hashMap);
    }
}
```

**Output**

```
String to hashmap: {1=Aashish, 2=Bina, 3=Chintu}
```