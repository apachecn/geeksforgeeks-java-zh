# Java 中的 MessageDigest isEqual()方法，带示例

> 原文:[https://www . geesforgeks . org/messagedigest-isequal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/messagedigest-isequal-method-in-java-with-examples/)

**Java . security . messagedigest**类的 **isEqual()** 方法用于测试两个消息摘要是否相等。

**语法:**

```
public static boolean
  isEqual(byte[] digesta, byte[] digestb)
```

**参数:**该方法取 2 个字节数组进行比较。
**返回值:**该方法提供布尔值，如果两个摘要相等则为真，否则为假。

以下是说明 isEqual()方法的示例:
**示例 1:** 对于相等的摘要值

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isEqual() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating object of MessageDigest
            MessageDigest msd1
                = MessageDigest.getInstance("SHA-256");

            // creating object of MessageDigest
            MessageDigest msd2
                = MessageDigest.getInstance("SHA-256");

            // getting provider used in object msd
            // using getAlgorithm() method
            boolean status
                = MessageDigest
                      .isEqual(msd1.digest(),
                               msd2.digest());

            // check the condition
            if (status)
                System.out.println("msd1 is equals to msd2");
            else
                System.out.println("msd1 is not equals to msd2");
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
msd1 is equals to msd2
```

**示例 2:** 对于不相等的摘要值

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isEqual() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {

            // creating object of MessageDigest
            MessageDigest msd1
                = MessageDigest.getInstance("MD5");

            // creating object of MessageDigest
            MessageDigest msd2
                = MessageDigest.getInstance("SHA-256");

            // getting provider used in object msd
            // using getAlgorithm() method
            boolean status
                = MessageDigest.isEqual(msd1.digest(),
                                        msd2.digest());

            // check the condition
            if (status)
                System.out.println("msd1 is equals to msd2");
            else
                System.out.println("msd1 is not equals to msd2");
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
msd1 is not equals to msd2
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/security/messagedigest . html # isEqual-byte:A-byte:A-](https://docs.oracle.com/javase/9/docs/api/java/security/MessageDigest.html#isEqual-byte:A-byte:A-)