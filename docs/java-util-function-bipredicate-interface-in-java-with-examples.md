# Java . util . function . Bipediate 接口在 Java 中用示例

> 原文:[https://www . geesforgeks . org/Java-util-function-bipediate-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/java-util-function-bipredicate-interface-in-java-with-examples/)

**双向< T、V>T1 接口在 **JDK 8** 中引入。该接口封装在 **java.util.function** 包中。它对两个对象进行操作，并基于该条件返回谓词值。这是一个[功能界面](https://www.geeksforgeeks.org/functional-interfaces-java/)，因此也可以用于[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)。**

```java
public interface BiPredicate<T, V>
```

**方法:**

1.  **test()** :该函数对两个对象进行条件检查，并返回一个表示结果的布尔值。

    ```java
    boolean test(T obj, V obj1)
    ```

2.  **和()**:这个函数对当前对象和作为参数接收的对象应用 and 运算，并返回新形成的谓词。此方法有默认实现。

    ```java
    default BiPredicate<T, V> and(BiPredicate<? super T, ? super V> other)
    ```

3.  **求反()**:此函数返回当前谓词的逆，即反转测试条件。此方法有默认实现。

    ```java
    default BiPredicate<T, V> negate() 
    ```

4.  **or()**: This function applies the OR operation on the current object and the object received as argument, and returns the newly formed predicate. This method has a default implementation.

    ```java
    default BiPredicate<T, V> or(BiPredicate<? super T, ? super V> other)
    ```

    **示例:**

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    // Java example to demonstrate BiPredicate interface

    import java.util.function.BiPredicate;

    public class BiPredicateDemo {
        public static void main(String[] args)
        {
            // Simple predicate for checking equality
            BiPredicate<Integer, String> biPredicate = (n, s) ->
            {
                if (n == Integer.parseInt(s))
                    return true;
                return false;
            };

            System.out.println(biPredicate.test(2, "2"));

            // Predicate for checking greater than
            BiPredicate<Integer, String> biPredicate1 = (n, s) ->
            {
                if (n > Integer.parseInt(s))
                    return true;
                return false;
            };

            // ANDing the two predicates
            BiPredicate<Integer, String> biPredicate2
                = biPredicate.and(biPredicate1);
            System.out.println(biPredicate2.test(2, "3"));

            // ORing the two predicates
            biPredicate2 = biPredicate.or(biPredicate1);
            System.out.println(biPredicate2.test(3, "2"));

            // Negating the predicate
            biPredicate2 = biPredicate.negate();
            System.out.println(biPredicate2.test(3, "2"));
        }
    }
    ```

    **Output:** 

    ```java
    true
    false
    true
    true
    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/function/bipredicate . html](https://docs.oracle.com/javase/8/docs/api/java/util/function/BiPredicate.html)