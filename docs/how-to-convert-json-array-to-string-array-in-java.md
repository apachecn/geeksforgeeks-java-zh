# 如何在 Java 中将 JSON 数组转换成字符串数组？

> 原文:[https://www . geesforgeks . org/how-convert-JSON-array-to-string-array-in-Java/](https://www.geeksforgeeks.org/how-to-convert-json-array-to-string-array-in-java/)

[<u>【JSON】</u>](https://www.geeksforgeeks.org/javascript-json/)代表 JavaScript 对象符号。它是网络应用程序广泛使用的数据交换格式之一。JSON 数组和 [<u>JavaScript</u>](https://www.geeksforgeeks.org/introduction-to-javascript/) 中的数组几乎一样。它们可以理解为以索引方式收集的数据(字符串、数字、布尔值)。给定一个 JSON 数组，我们将讨论如何在 Java 中将它转换成 String 数组。

**创建 JSON 数组**

让我们从用 Java 创建一个 JSON 数组开始。在这里，我们将使用一些示例数据来输入到数组中，但是您可以根据自己的需求来使用这些数据。

**1。定义数组**

```java
JSONArray exampleArray = new JSONArray();
```

注意，为了使用这个命令，我们将导入 org.json 包。这将在后面的代码中讨论。

**2。将数据插入数组**

我们现在向数组中添加一些示例数据。

```java
exampleArray.put("Geeks ");
exampleArray.put("For ");
exampleArray.put("Geeks ");
```

请注意每个字符串后面的空格。这里这样做是因为当我们将它转换成字符串数组时，我们希望确保每个元素之间都有空间。

现在我们已经准备好了 JSON 数组，我们可以进入下一步，也是最后一步，将它转换成 String 数组。

**转换成字符串数组**

我们在这里使用的方法是，首先将所有的 JSON 数组元素插入到一个 [<u>列表</u>](https://www.geeksforgeeks.org/list-interface-java-examples/) 中，因为这样更容易将列表转换成数组。

**1。创建列表**

让我们从创建一个列表开始。

```java
List<String> exampleList = new ArrayList<String>();
```

**2。将 JSON 数组数据添加到列表中**

我们可以循环遍历 JSON 数组，将所有元素添加到我们的列表中。

```java
for(int i=0; i< exampleArray.length; i++){
    exampleList.add(exampleArray.getString(i));
}
```

现在我们将列表中的所有元素都作为字符串，我们可以简单地将列表转换为字符串数组。

**3。获取字符串数组作为输出**

我们将使用 [<u>toArray()</u>](https://www.geeksforgeeks.org/arraylist-toarray-method-in-java-with-examples/) 方法将列表转换为字符串数组。

```java
int size = exampleList.size();
String[] stringArray = exampleList.toArray(new String[size]);
```

这将把我们的 JSON 数组转换成字符串数组。下面提供了代码供参考。

实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// importing the packages
import java.util.*;
import org.json.*;

public class GFG {

    public static void main(String[] args)
    {
        // Initialising a JSON example array
        JSONArray exampleArray = new JSONArray();

        // Entering the data into the array
        exampleArray.put("Geeks ");
        exampleArray.put("For ");
        exampleArray.put("Geeks ");

        // Printing the contents of JSON example array
        System.out.print("Given JSON array: "
                         + exampleArray);
        System.out.print("\n");

        // Creating example List and adding the data to it
        List<String> exampleList = new ArrayList<String>();
        for (int i = 0; i < exampleArray.length; i++) {
            exampleList.add(exampleArray.getString(i));
        }

        // Creating String array as our
        // final required output
        int size = exampleList.size();
        String[] stringArray
            = exampleList.toArray(new String[size]);

        // Printing the contents of String array
        System.out.print("Output String array will be : ");
        for (String s : stringArray) {
            System.out.print(s);
        }
    }
}
```

**输出:**

```java
Given JSON array: ["Geeks ","For ","Geeks "]
Output String array will be : Geeks For Geeks
```