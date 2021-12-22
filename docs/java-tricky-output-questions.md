# Java 棘手输出问题

> 原文:[https://www.geeksforgeeks.org/java-tricky-output-questions/](https://www.geeksforgeeks.org/java-tricky-output-questions/)

**问题 1:** 下面代码的输出是什么:

```
public class A {
    public static void main(String[] args)
    {
        if (true)
            break;
    }
}
```

**选择:**

*   没什么
*   错误

**回答:** b)错误
**原因:** Break 语句只能用于循环或开关。因此，使用 break with if 语句会导致“在开关或循环外中断”错误。

**问题 2:** 下面代码的输出会是什么:

```
public class A {
    public static void main(String[] args)
    {
        System.out.println('j' + 'a' + 'v' + 'a');
    }
}
```

**选择:**

*   a) java
*   b)其他东西(除了简单的连接)

**答案:** b)如果使用字符串文字(在双引号中)，会打印出其他内容(除了简单的连接)
**原因:**“Java”，但是在问题中，由于使用了字符文字，这些不会被连接。因此，在程序执行后，将获得字符的每个等价 ASCII(Unicode)值的加法。
因此输出为 **106 + 97 + 118 + 97 = 418**

**问题 3:** 下面代码的输出会是什么:

```
public class A {
    public static void main(String[] args)
    {
        int $_ = 5;
    }
}
```

**选择:**

*   没什么
*   错误

**回答:** a)没事
T3】原因:看起来$会造成错误，但不会。在 java 中，标识符规则表示，**标识符可以以任何字母或下划线(“_”)或美元(“{content}”)开头；)**。所以回答是没什么。

**问题 4:** 下面代码的输出会是什么:

```
public class Demo{
    public static void main(String[] arr){
        Integer num1 = 100;
        Integer num2 = 100;
        Integer num3 = 500;
        Integer num4 = 500;

        if(num1==num2){
            System.out.println("num1 == num2");
        }
        else{
            System.out.println("num1 != num2");
        }
        if(num3 == num4){
            System.out.println("num3 == num4");
        }
        else{
            System.out.println("num3 != num4");
        }
    }
}
```

**选择:**

*   (a)在 1 号编第 2 号编第 3 号编第 4 号编第 1 号编第 2 号编第 0 号编第 3 号编第 3 号编第 4 号编第 1 号编第 3 号编第 3 号编第 3 号编第 3 号编第 3 号编第 3 号编第 4 号编
*   b)第一季第二集
    第三集！=数字 4
*   (c)1 号！=第 2 季第 0 集-=第 3 季第 4 集
*   (d)1 号！=数字 2
    数字 3！=数字 4

**回答:** b)num1 == num2
num3！= num4
**原因:**我们一直认为，每当使用“==”比较两个对象引用时，它总是评估为“假”。但是在这里，整数缓存会改变结果。**整数类的缓存范围为-128 到 127。**当一个数字在这个范围内，并且使用自动装箱时，它分配相同的参考。这就是为什么对于值 100，num1 和 num2 将具有相同的引用，但是对于值 500(不在-128 到 127 的范围内)，num3 和 num4 将具有不同的引用。

**问题 5:** 下面代码的输出会是什么:

```
public class Demo{
    public static void main(String[] arr){

    }
    public static void main(String arr){

    }
}
```

**选择:**

*   没什么
*   错误

**回答:** a)没什么
T3】原因:我们也可以超负荷主()。但是 JVM 总是会调用有 String[]参数的 main()。

更多 [Java 输出问题](https://www.geeksforgeeks.org/tag/java-output/)