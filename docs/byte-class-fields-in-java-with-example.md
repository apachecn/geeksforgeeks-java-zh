# Java 中的字节类字段，示例

> 原文:[https://www . geesforgeks . org/byte-class-field-in-Java-with-example/](https://www.geeksforgeeks.org/byte-class-fields-in-java-with-example/)

[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)是一个用于原语类型字节的[包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)，它包含几种有效处理字节值的方法，比如将其转换为字符串表示，反之亦然。字节类的对象可以保存单个字节值。

字节类以**字段**的形式提供了四个常量。这些是:

*   **MAX_VALUE:**The **MAX_VALUE** is a instance variable of [Byte class](https://www.geeksforgeeks.org/java-lang-byte-class-java/) which is used to return the maximum byte value.

    **语法:**

    ```
    public static final byte MAX_VALUE
    ```

    用法:

    ```
    Byte.MAX_VALUE
    ```

    **返回值:**返回一个等于 127 的字节值。

    以下是 MAX_VALUE 的实现:

    ```
    // Java code to implement
    // MAX_VALUE of Byte class

    class GFG {
        public static void main(String[] args)
        {

            // byte variable
            byte max_value;

            // MAX_VALUE Byte class
            max_value = Byte.MAX_VALUE;

            // printing the MAX_VALUE
            System.out.println(max_value);
        }
    }
    ```

    **Output:**

    ```
    127

    ```

*   **MIN_VALUE:**The **MIN_VALUE** is a instance variable of [Byte class](https://www.geeksforgeeks.org/java-lang-byte-class-java/) which is used to return the minimum byte value.

    **语法:**

    ```
    public static final byte MIN_VALUE
    ```

    用法:

    ```
    Byte.MIN_VALUE
    ```

    **返回值:**返回一个等于-128 的字节值。

    下面是最小值的实现:

    ```
    // Java code to implement
    // MIN_VALUE of Byte class

    class GFG {
        public static void main(String[] args)
        {

            // byte variable
            byte min_value;

            // MIN_VALUE Byte class
            min_value = Byte.MIN_VALUE;

            // printing the MIN_VALUE
            System.out.println(min_value);
        }
    }
    ```

    **Output:**

    ```
    -128

    ```

*   **SIZE:**The **SIZE** is a instance variable of [Byte class](https://www.geeksforgeeks.org/java-lang-byte-class-java/) which is used to return number of bits required to represent a byte value in binary representation (two’s complement).

    **语法:**

    ```
    public static final int SIZE
    ```

    用法:

    ```
    Byte.SIZE
    ```

    **返回值:**返回一个等于 8 的整数值。

    以下是大小的实现:

    ```
    // Java code to implement
    // SIZE of Byte class

    class GFG {
        public static void main(String[] args)
        {

            // SIZE Byte class
            int output = Byte.SIZE;

            // printing the output
            System.out.println(output);
        }
    }
    ```

    **Output:**

    ```
    8

    ```

*   **TYPE:** The **TYPE** is a instance variable of [Byte class](https://www.geeksforgeeks.org/java-lang-byte-class-java/) which is used to return Class instance representing the primitive data type byte.

    **语法:**

    ```
    public static final Class<Byte> TYPE
    ```

    用法:

    ```
    Byte.TYPE
    ```

    **返回值:**它返回一个代表原始数据类型字节的类实例。

    以下是类型的实现:

    ```
    // Java code to implement
    // TYPE of Byte class

    class GFG {
        public static void main(String[] args)
        {

            // TYPE variable of Byte class
            Class<Byte> output = Byte.TYPE;

            // printing the output
            System.out.println(output);
        }
    }
    ```

    **Output:**

    ```
    byte

    ```