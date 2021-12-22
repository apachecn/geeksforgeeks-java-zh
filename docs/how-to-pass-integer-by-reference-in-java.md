# 如何在 Java 中引用传递整数

> 原文:[https://www . geesforgeks . org/如何通过 java 中的引用传递整数/](https://www.geeksforgeeks.org/how-to-pass-integer-by-reference-in-java/)

[Java 是按值传递](https://www.geeksforgeeks.org/g-fact-31-java-is-strictly-pass-by-value/)，在 Java 中不能直接按引用传递整数。在 Java 中创建的对象是通过值传递的引用。因此，可以通过如下一些方法来实现:

1.  **By creating Wrapper Class:** As we know that Integer is an immutable class, so we wrap an integer value in a mutable object through this method.

    **进场:**

    1.  获取要传递的整数
    2.  用这个整数创建另一个类的对象
    3.  使用包装类将整数值包装在可变对象中，该可变对象可以更改或修改
    4.  现在，无论何时需要整数，都必须通过类的对象来获取它
    5.  因此整数是通过引用传递的

    下面是上述方法的实现:

    **示例:**

    ```
    // Java program to pass the integer by reference

    class Test {
        public Integer value;

        Test(Integer value)
        {

            // Using wrapper class
            // so as to wrap integer value
            // in mutable object
            // which can be changed or modified
            this.value = value;
        }

        @Override
        public String toString()
        {
            return String.valueOf(value);
        }
    }

    class Main {
        public static void modification(Test x)
        {
            x.value = 1000;
        }

        public static void main(String[] args)
        {
            Test k = new Test(50);
            modification(k);

            // Modified value gets printed
            System.out.println(k);
        }
    }
    ```

    **输出:**

    ```
    1000
    ```

2.  **Wrapping primitive value using an array:** This process of wrapping is done by using an array of length one.

    **进场:**

    1.  获取要传递的整数
    2.  这个包装过程是通过使用长度为 1 的数组来完成的。
    3.  现在，每当您需要整数时，您必须通过数组的对象来获取它
    4.  因此整数是通过引用传递的

    下面是上述方法的实现:

    **示例:**

    ```
    // Java program to pass the integer by reference

    class PassByReference {
        public static void increment(int[] array)
        {

            // increment in the actual value
            array[0]++;
        }

        public static void main(String[] args)
        {
            int k = 100;

            // wrapping is done
            // by using array of length one
            int[] array = { k };

            // Reference is passed
            increment(array);

            // incremented value printed
            System.out.println(array[0]);
        }
    }
    ```

    **输出:**

    ```
    101
    ```

3.  **Using AtomicInteger:** This is a built in Java class which provides a single threaded environment.

    **进场:**

    1.  获取要传递的整数
    2.  通过将此整数作为参数传递给其构造函数来创建 AtomicInteger 对象
    3.  现在，每当您需要整数时，您必须通过 AtomicInteger 的对象来获取它
    4.  因此整数是通过引用传递的

    下面是上述方法的实现:

    **示例:**

    ```
    // Java program to pass the integer by reference

    import java.util.concurrent.atomic.AtomicInteger;

    class PassByReference {
        public static void setvalue(AtomicInteger x)
        {

            // setting new value
            // thus changing the actual value
            x.set(1000);
        }

        public static void main(String[] args)
        {

            // provides single threaded environment
            AtomicInteger k = new AtomicInteger(50);

            // passed by reference
            setvalue(k);

            System.out.println(k);
        }
    }
    ```

    **输出:**

    ```
    1000
    ```

4.  **Using Apache MutableInt Class:** We can use MutableInt class by importing the package from Commons Apache.

    **进场:**

    1.  获取要传递的整数
    2.  通过将此整数作为参数传递给其构造函数来创建一个可变对象
    3.  现在，无论何时需要整数，都必须通过变量的对象来获取它
    4.  因此整数是通过引用传递的

    下面是上述方法的实现:

    **示例:**

    ```
    // Java program to pass the integer by reference

    import org.apache.commons.lang3.mutable.MutableInt;

    class Main {
        public static void increment(MutableInt k)
        {
            k.increment();
        }

        public static void main(String[] args)
        {

            // Using Mutable Class whose object's fields
            // can be changed accordingly
            MutableInt k = new MutableInt(8);

            increment(k);
            System.out.println(k);
        }
    }
    ```

    **输出:**

    ```
    9
    ```