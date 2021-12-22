# 在 Java 中创建用户定义的可打印对类

> 原文:[https://www . geesforgeks . org/creating-a-user-defined-printable-pair-class-in-Java/](https://www.geeksforgeeks.org/creating-a-user-defined-printable-pair-class-in-java/)

C++标准库中的 pair 类被大量使用。我们可以在 Java 中实现我们自己的用户定义的 pair 类，它的对象可以像任何其他参数一样在任何地方使用。

**注:**

> 这个类相当于 java 中的 pair <int>类。您可以为其他数据类型创建自己的模板或类。</int>

**定义配对类的语法可以是:**

```java
class pair{
   int first,second;

   // constructor for assigning values
   pair(int first,int second){
       this.first = first;
       this.second = second;
   }

   // function which returns a pair
   pair values(){
       return new pair(first,second);
   }

   // printing the pair class
   @Override
   public String toString(){
       return "("+first+","+second+")";
   }
}
```

*   我们现在可以玩这个类，甚至创建一个对的数组，类似于 C++中的向量<pair>>。</pair>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create a pair class
// and initialize an array of that
// pair class object

public class pair_example {
    public static void main(String[] args)
    {
        pair[] arr = new pair[5];
        for (int i = 0; i < 5; i++) {
            arr[i] = new pair(i + 1, i + 2);
        }

        // printing an array of pairs easily
        for (pair i : arr) {
            System.out.println(i);
        }

        // to extract particular values
        int value = arr[3].second;
        System.out.println("Required Value = " + value);
    }
}

// user defined pair class of integer type
class pair {
    int first, second;

    // constructor for assigning values
    pair(int first, int second)
    {
        this.first = first;
        this.second = second;
    }

    // function which returns a pair
    pair values() { return new pair(first, second); }

    // printing the pair class
    @Override public String toString()
    {
        return first + "," + second;
    }
}
```

**Output**

```java
1,2
2,3
3,4
4,5
5,6
Required Value = 5
```

**实现示例:**

假设我们需要将第 I 个素数及其索引一起存储在一个结构中。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create a struct/pair class
// for storing a prime number with its index

class GFG {
    public static void main(String[] args)
    {
        // first N prime numbers
        int N = 30;

        // creating list of pairs
        java.util.ArrayList<pair> p = new java.util.ArrayList<>();

        int index = 1;
        for (int i = 1; i <= N; i++) {
            if (isPrime(i)) {

                // creating new pair object and appending to
                // list
                p.add(new pair(index++, i));
            }
        }

        System.out.println("i and the ith prime numbers are :");
        System.out.println(p);
    }

    // function to check prime
    static boolean isPrime(int n)
    {
        if (n < 2)
            return false;
        for (int i = 2; i * i <= n; i++) {
            if (n % i == 0)
                return false;
        }
        return true;
    }
}

// user defined pair class of integer type
class pair {
    int first, second;

    // constructor for assigning values
    pair(int first, int second)
    {
        this.first = first;
        this.second = second;
    }

    // function which returns a pair
    pair values() { return new pair(first, second); }

    // printing the pair class
    @Override public String toString()
    {
        return "(" + first + "," + second + ")";
    }
}
```

**Output**

```java
i and the ith prime numbers are :
[(1,2), (2,3), (3,5), (4,7), (5,11), (6,13), (7,17), (8,19), (9,23), (10,29)]
```