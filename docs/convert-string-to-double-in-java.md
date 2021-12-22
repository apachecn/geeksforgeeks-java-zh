# 在 Java 中将字符串转换为双精度

> 原文:[https://www . geesforgeks . org/convert-string-to-double-in-Java/](https://www.geeksforgeeks.org/convert-string-to-double-in-java/)

给定一个字符串，任务是在 Java 中将其转换为 Double。

**示例:**

```
Input: String = "20.156"
Output: 20.156

Input: String = "456.21"
Output: 456.21

```

我们可以使用各种方法来执行任务:

1.  **Using [Double.parseDouble()](https://www.geeksforgeeks.org/double-parsedouble-method-in-java-with-examples/)**

    **语法:**

    ```
    double str1 = Double.parseDouble(str); 

    ```

    ```
    // Java program to convert String to Double
    // using parseDouble()

    public class GFG {

        // main method
        public static void main(String args[])
        {

            // create a String
            String str = "2033.12244";

            // convert into Double
            double str1 = Double.parseDouble(str);

            // print String as Double
            System.out.println(str1);
        }
    }
    ```

    **Output:**

    ```
    2033.12244

    ```

2.  **Using [Double.valueOf()](https://www.geeksforgeeks.org/data-conversion-using-valueof-method-java/)**

    **语法:**

    ```
    double str1 = Double.valueOf(str); 

    ```

    **示例:**

    ```
    // Java program to convert String to Double
    // using parseDouble()

    public class GFG {

        // main method
        public static void main(String args[])
        {

            // create a String
            String str = "2033.12244";

            // convert into Double
            double str1 = Double.valueOf(str);

            // print String as Double
            System.out.println(str1);
        }
    }
    ```

    **Output:**

    ```
    2033.12244

    ```

3.  **Using constructor of [Double class](https://www.geeksforgeeks.org/java-lang-double-class-java/)**

    **语法:**

    ```
    Double str1 = new Double(str); 

    ```

    **示例:**

    ```
    // Java program to convert String to Double
    // using parseDouble()

    public class GFG {

        // main method
        public static void main(String args[])
        {

            // create a String
            String str = "2033.12244";

            // convert into Double
            Double str1 = new Double(str);

            // print String as Double
            System.out.println(str1);
        }
    }
    ```

    **Output:**

    ```
    2033.12244

    ```