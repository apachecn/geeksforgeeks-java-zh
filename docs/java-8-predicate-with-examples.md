# Java 8 谓词示例

> 原文:[https://www . geesforgeks . org/Java-8-带有示例的谓词/](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)

一个[功能接口](https://www.geeksforgeeks.org/functional-interfaces-java/)是一个在接口范围内只允许一个抽象方法的接口。Java 中有一些预定义的功能接口，如谓词、消费者、供应商等。Lambda 函数的返回类型(在 JDK 1.8 中引入)也是一个函数接口。
功能接口**谓词**在 *java.util.function 包*中定义。它提高了代码的可管理性，有助于对它们进行单独的单元测试，并包含一些方法，如:

1.  **isEqual(Object targetRef):**返回一个谓词，该谓词根据 Objects.equals(Object，Object)测试两个参数是否相等。

```java
static  Predicate isEqual(Object targetRef)
Returns a predicate that tests if two arguments are 
equal according to Objects.equals(Object, Object).
T : the type of arguments to the predicate
Parameters:
targetRef : the object reference with which to 
compare for equality, which may be null
Returns: a predicate that tests if two arguments 
are equal according to Objects.equals(Object, Object)
```

1.  **和(谓词其他):**返回一个复合谓词，表示该谓词和另一个谓词的短路逻辑“与”。

```java
default Predicate and(Predicate other)
Returns a composed predicate that represents a 
short-circuiting logical AND of this predicate and another.
Parameters:
other: a predicate that will be logically-ANDed with this predicate
Returns : a composed predicate that represents the short-circuiting 
logical AND of this predicate and the other predicate
Throws: NullPointerException - if other is null
```

2.  **否定():**返回表示该谓词逻辑否定的谓词。

```java
default Predicate negate()
Returns:a predicate that represents the logical 
negation of this predicate
```

1.  **或(谓词其他):**返回一个组合谓词，表示该谓词和另一个谓词的短路逻辑或。

```java
default Predicate or(Predicate other)
Parameters:
other : a predicate that will be logically-ORed with this predicate
Returns:
a composed predicate that represents the short-circuiting 
logical OR of this predicate and the other predicate
Throws : NullPointerException - if other is null
```

2.  **测试(T ^ T):**根据给定的参数评估该谓词。布尔测试(T ^ T)

```java
test(T t) 
Parameters:
t - the input argument
Returns:
true if the input argument matches the predicate, otherwise false
```

**示例**

**例 1:简单谓语**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate Simple Predicate

import java.util.function.Predicate;
public class PredicateInterfaceExample1 {
    public static void main(String[] args)
    {
        // Creating predicate
        Predicate<Integer> lesserthan = i -> (i < 18); 

        // Calling Predicate method
        System.out.println(lesserthan.test(10)); 
    }
}
```

输出:

```java
True
```

**示例 2:谓词链接**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate Predicate Chaining

import java.util.function.Predicate;
public class PredicateInterfaceExample2 {
    public static void main(String[] args)
    {
        Predicate<Integer> greaterThanTen = (i) -> i > 10;

        // Creating predicate
        Predicate<Integer> lowerThanTwenty = (i) -> i < 20; 
        boolean result = greaterThanTen.and(lowerThanTwenty).test(15);
        System.out.println(result);

        // Calling Predicate method
        boolean result2 = greaterThanTen.and(lowerThanTwenty).negate().test(15);
        System.out.println(result2);
    }
}
```

输出:

```java
True
False
```

**示例 3:函数**中的谓词

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate 
// passing Predicate into function

import java.util.function.Predicate;
class PredicateInterfaceExample3 {
    static void pred(int number, Predicate<Integer> predicate)
    {
        if (predicate.test(number)) {
            System.out.println("Number " + number);
        }
    }
    public static void main(String[] args)
    {
        pred(10, (i) -> i > 7);
    }
}
```

输出:

```java
Number 10
```

**例 4:谓语 OR**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate OR Predicate

import java.util.function.Predicate;
class PredicateInterfaceExample4 {
    public static Predicate<String> hasLengthOf10 = new Predicate<String>() {
        @Override
        public boolean test(String t)
        {
            return t.length() > 10;
        }
    };

    public static void predicate_or()
    {

        Predicate<String> containsLetterA = p -> p.contains("A");
        String containsA = "And";
        boolean outcome = hasLengthOf10.or(containsLetterA).test(containsA);
        System.out.println(outcome);
    }
    public static void main(String[] args)
    {
        predicate_or();
    }
}
```

输出:

```java
True
```

**例 5:谓语和**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate AND Predicate

import java.util.function.Predicate;
import java.util.Objects;

class PredicateInterfaceExample5 {
    public static Predicate<String> hasLengthOf10 = new Predicate<String>() {
        @Override
        public boolean test(String t)
        {
            return t.length() > 10;
        }
    };

    public static void predicate_and()
    {
        Predicate<String> nonNullPredicate = Objects::nonNull;

        String nullString = null;

        boolean outcome = nonNullPredicate.and(hasLengthOf10).test(nullString);
        System.out.println(outcome);

        String lengthGTThan10 = "Welcome to the machine";
        boolean outcome2 = nonNullPredicate.and(hasLengthOf10).
        test(lengthGTThan10);
        System.out.println(outcome2);
    }
    public static void main(String[] args)
    {
        predicate_and();
    }
}
```

输出:

```java
False
True
```

**例 6:谓语否定()**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate 
// negate Predicate

import java.util.function.Predicate;
class PredicateInterfaceExample6 {
    public static Predicate<String> hasLengthOf10 = new Predicate<String>() {
        @Override
        public boolean test(String t)
        {
            return t.length() > 10;
        }
    };

    public static void predicate_negate()
    {

        String lengthGTThan10 = "Thunderstruck is a 2012 children's "
                                + "film starring Kevin Durant";

        boolean outcome = hasLengthOf10.negate().test(lengthGTThan10);
        System.out.println(outcome);
    }
    public static void main(String[] args)
    {
        predicate_negate();
    }
}
```

输出:

```java
False
```

**例 7:集合**中的谓词

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of predicates
// on collection. The program finds all admins in an
// arrayList of users.
import java.util.function.Predicate;
import java.util.*;
class User
{
    String name, role;
    User(String a, String b) {
        name = a;
        role = b;
    }
    String getRole() { return role; }
    String getName() { return name; }    
    public String toString() {
       return "User Name : " + name + ", Role :" + role;
    }

    public static void main(String args[])
    {      
        List<User> users = new ArrayList<User>();
        users.add(new User("John", "admin"));
        users.add(new User("Peter", "member"));
        List admins = process(users, (User u) -> u.getRole().equals("admin"));
        System.out.println(admins);
    }

    public static List<User> process(List<User> users, 
                            Predicate<User> predicate)
    {
        List<User> result = new ArrayList<User>();
        for (User user: users)        
            if (predicate.test(user))            
                result.add(user);
        return result;
    }
}
```

输出:

```java
[User Name : John, Role :admin]
```

同样的功能也可以通过使用自 JDK 1.8 在 Collections API 之上提供的[流 API](https://www.geeksforgeeks.org/stream-in-java/)
和 [lambda 函数](https://www.geeksforgeeks.org/lambda-expressions-java-8/#targetText=lambda%20expressions%20are%20added%20in,object%20and%20executed%20on%20demand.)来实现。
**流应用编程接口**允许对集合进行“流式”动态处理。流允许对数据进行并发和并行计算(使用内部迭代)，以支持类似数据库的操作，例如对数据进行分组和过滤(类似于 SQL 中的 GROUP BY 和 WHERE 子句)。这允许开发人员关注“需要什么数据”，而不是“如何需要数据”，因为流隐藏了实现的细节并提供了结果。这是通过向运行时在集合流上运行的函数提供谓词作为输入来实现的。在下面的示例中，我们说明了如何将流应用编程接口与谓词一起使用来过滤数据集合，如示例 7 所示。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of predicates
// on collection. The program finds all admins in an
// arrayList of users.
import java.util.function.Predicate;
import java.util.*;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class User
{
    String name, role;
    User(String a, String b) {
        name = a;
        role = b;
    }
    String getRole() { return role; }
    String getName() { return name; } 
    public String toString() {
    return "User Name : " + name + ",
    Role :" + role;
    }

    public static void main(String args[])
    { 
        List<User> users = 
            new ArrayList<User>();
        users.add(new User("John", "admin"));
        users.add(new User("Peter", "member"));

    // This line uses Predicates to filter
    // out the list of users with the role "admin".
    // List admins = process(users, (User u) -> 
    // u.getRole().equals("admin"));

    // Replacing it with the following line 
    // using Stream API and lambda functions 
    // produces the same output

    // the input to the filter() is a lambda 
    // expression that returns a predicate: a 
    // boolean value for each user encountered 
    // (true if admin, false otherwise)
    List admins = users.stream()
    .filter((user) -> user.getRole().equals("admin"))
    .collect(Collectors.toList());

    System.out.println(admins);
    }
}
```

**输出:**

```java
[User Name : John, Role :admin]
```