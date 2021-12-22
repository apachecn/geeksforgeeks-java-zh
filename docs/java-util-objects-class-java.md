# Java 中的 Java.util.Objects 类

> 原文:[https://www.geeksforgeeks.org/java-util-objects-class-java/](https://www.geeksforgeeks.org/java-util-objects-class-java/)

Java 7 提出了一个新的类**对象**，它有 9 个静态实用方法来操作对象。这些实用程序包括用于计算对象的哈希代码、返回对象的字符串以及比较两个对象的空安全方法。

使用对象类方法，可以智能地处理[空指针异常](http://contribute.geeksforgeeks.org/null-pointer-exception-in-java/)，还可以显示定制的空指针异常消息(如果发生异常)。

1.  **String toString(Object o)** :这个方法对于非空参数返回 toString()方法的调用结果，对于空参数返回“null”。

    ```
    Syntax : 
    public static String toString(Object o)
    Parameters : 
    o - an object
    Returns :
    the result of calling toString() method for a non-null argument and 
    "null" for a null argument

    ```

2.  **String toString(Object o, String nullDefault)** : This method is overloaded version of above method. It returns the result of calling toString() method on the first argument if the first argument is not null and returns the second argument otherwise.

    ```
    Syntax : 
    public static String toString(Object o, String nullDefault)
    Parameters : 
    o - an object
    nullDefault - string to return if the first argument is null
    Returns :
    the result of calling toString() method on the first argument if it is not null and
    the second argument otherwise.

    ```

    ```
    // Java program to demonstrate Objects.toString(Object o) 
    // and Objects.toString(Object o, String nullDefault) methods

    import java.util.Objects;

    class Pair<K, V> 
    {
        public K key;
        public V value;

        public Pair(K key, V value) 
        {
            this.key = key;
            this.value = value;
        }

        @Override
        public String toString() {
            return "Pair {key = " + Objects.toString(key) + ", value = " + 
                        Objects.toString(value, "no value") + "}";

            /* without Objects.toString(Object o) and 
             Objects.toString(Object o, String nullDefault) method
             return "Pair {key = " + (key == null ? "null" : key.toString()) + 
         ", value = " + (value == null ? "no value" : value.toString()) + "}"; */
        }
    }

    class GFG
    {
        public static void main(String[] args) 
        {
            Pair<String, String> p1 = 
                            new Pair<String, String>("GFG", "geeksforgeeks.org");
            Pair<String, String> p2 = new Pair<String, String>("Code", null);

            System.out.println(p1);
            System.out.println(p2);
        }
    }
    ```

    输出:

    ```
    Pair {key = GFG, value = geeksforgeeks.org}
    Pair {key = Code, value = no value}

    ```

3.  **boolean equals(Object a,Object b)** : This method true if the arguments are equal to each other and false otherwise. Consequently, if both arguments are null, true is returned and if exactly one argument is null, false is returned. Otherwise, equality is determined by using the equals() method of the first argument.

    ```
    Syntax : 
    public static boolean equals(Object a,Object b)
    Parameters : 
    a - an object
    b - an object to be compared with a for equality
    Returns :
    true if the arguments are equal to each other and false otherwise

    ```

    ```
    // Java program to demonstrate equals(Object a, Object b) method

    import java.util.Objects;

    class Pair<K, V> 
    {
        public K key;
        public V value;

        public Pair(K key, V value) 
        {
            this.key = key;
            this.value = value;
        }

        @Override
        public boolean equals(Object o)
        {
            if (!(o instanceof Pair)) {
                return false;
            }
            Pair<?, ?> p = (Pair<?, ?>) o;
            return Objects.equals(p.key, key) && Objects.equals(p.value, value);

        }
    }

    class GFG
    {
        public static void main(String[] args) 
        {
            Pair<String, String> p1 = 
                    new Pair<String, String>("GFG", "geeksforgeeks.org");

            Pair<String, String> p2 = 
                    new Pair<String, String>("GFG", "geeksforgeeks.org");

            Pair<String, String> p3 = 
                    new Pair<String, String>("GFG", "www.geeksforgeeks.org");

            System.out.println(p1.equals(p2));
            System.out.println(p2.equals(p3));

        }
    }
    ```

    输出:

    ```
    true
    false

    ```

4.  **布尔 deepEquals(对象 a，对象 b)** :如果参数*深度*相等，则该方法返回 true，否则返回 false。两个空值完全相等。如果两个参数都是数组，则使用 [Arrays.deepEquals](http://contribute.geeksforgeeks.org/geek/) 中的算法来确定是否相等。否则，通过使用第一个参数的 equals 方法来确定是否相等。

    ```
    Syntax : 
    public static boolean deepEquals(Object a,Object b)
    Parameters : 
    a - an object
    b - an object to be compared with a for equality
    Returns :
    true if the arguments are deeply equals to each other and false otherwise

    ```

5.  **T requireNonNull(T obj)** :此方法检查指定的对象引用是否不为空。该方法主要用于在方法和构造函数中进行参数验证，如下例所示:

    ```
    Syntax : 
    public static  T requireNonNull(T obj)
    Type Parameters:
    T - the type of the reference
    Parameters : 
    obj - the object reference to check for nullity
    Returns :
    obj if not null
    Throws:
    NullPointerException - if obj is null

    ```

6.  **T requireNonNull(T obj,String message)** : This method is overloaded version of above method with customized message printing if obj is null as demonstrated in below example:

    ```
    Syntax : 
    public static  T requireNonNull(T obj,String message)
    Type Parameters:
    T - the type of the reference
    Parameters : 
    obj - the object reference to check for nullity
    message - detail message to be used in the event that a NullPointerException is thrown
    Returns :
    obj if not null
    Throws:
    NullPointerException - if obj is null

    ```

    ```
    // Java program to demonstrate Objects.requireNonNull(Object o) 
    // and Objects.requireNonNull(Object o, String message) methods

    import java.util.Objects;

    class Pair<K, V> 
    {
        public K key;
        public V value;

        public Pair(K key, V value) 
        {
            this.key = key;
            this.value = value;
        }

        public void setKey(K key) {
            this.key = Objects.requireNonNull(key);
        }

        public void setValue(V value) {
            this.value = Objects.requireNonNull(value, "no value");
        }
    }

    class GFG
    {
        public static void main(String[] args) 
        {
            Pair<String, String> p1 = 
                        new Pair<String, String>("GFG", "geeksforgeeks.org");

            p1.setKey("Geeks");

            // below statement will throw NPE with customized message
            p1.setValue(null);

        }
    }
    ```

    输出:

    ```
    Exception in thread "main" java.lang.NullPointerException: no value
        at java.util.Objects.requireNonNull(Objects.java:228)
        at Pair.setValue(GFG.java:22)
        at GFG.main(GFG.java:36)

    ```

7.  **int hashCode(Object o)** : This method returns the hash code of a non-null argument and 0 for a null argument.

    ```
    Syntax : 
    public static int hashCode(Object o)
    Parameters : 
    o - an object
    Returns :
    the hash code of a non-null argument and 0 for a null argument

    ```

    ```
    // Java program to demonstrate Objects.hashCode(Object o) object

    import java.util.Objects;

    class Pair<K, V> 
    {
        public K key;
        public V value;

        public Pair(K key, V value) 
        {
            this.key = key;
            this.value = value;
        }

        @Override
        public int hashCode()
        {
            return (Objects.hashCode(key) ^ Objects.hashCode(value));

            /* without Objects.hashCode(Object o) method
            return (key == null ? 0 : key.hashCode()) ^ 
            (value == null ? 0 : value.hashCode()); */
        }
    }

    class GFG
    {
        public static void main(String[] args) 
        {
            Pair<String, String> p1 = 
                    new Pair<String, String>("GFG", "geeksforgeeks.org");
            Pair<String, String> p2 = 
                    new Pair<String, String>("Code", null);
            Pair<String, String> p3 = new Pair<String, String>(null, null);

            System.out.println(p1.hashCode());
            System.out.println(p2.hashCode());
            System.out.println(p3.hashCode());
        }
    }
    ```

    输出:

    ```
    450903651
    2105869
    0

    ```

8.  **int hash(Object… values)** : This method generates a hash code for a sequence of input values. The hash code is generated as if all the input values were placed into an array, and that array were hashed by calling Arrays.hashCode(Object[]).
    This method is useful for implementing Object.hashCode() on objects containing multiple fields. For example, if an object that has three fields, x, y, and z, one could write:

    ```
    @Override 
    public int hashCode() {
         return Objects.hash(x, y, z);
    }

    ```

    **注意**:当提供单个对象引用时，返回值不等于该对象引用的哈希码。这个值可以通过调用 hashCode(对象)来计算。

    ```
    Syntax : 
    public static int hash(Object... values)
    Parameters : 
    values - the values to be hashed
    Returns :
    a hash value of the sequence of input values

    ```

    ```
    // Java program to demonstrate Objects.hashCode(Object o) object

    import java.util.Objects;

    class Pair<K, V> 
    {
        public K key;
        public V value;

        public Pair(K key, V value) 
        {
            this.key = key;
            this.value = value;
        }

        @Override
        public int hashCode()
        {
            return (Objects.hash(key,value));
        }
    }

    class GFG
    {
        public static void main(String[] args) 
        {
            Pair<String, String> p1 = 
                    new Pair<String, String>("GFG", "geeksforgeeks.org");
            Pair<String, String> p2 = 
                    new Pair<String, String>("Code", null);
            Pair<String, String> p3 = new Pair<String, String>(null, null);

            System.out.println(p1.hashCode());
            System.out.println(p2.hashCode());
            System.out.println(p3.hashCode());
        }
    }
    ```

    输出:

    ```
    453150372
    65282900
    961

    ```

9.  **int compare(T a,T b,Comparator c)** : As usual, this method returns 0 if the arguments are identical and c.compare(a, b) otherwise. Consequently, if both arguments are null 0 is returned.

    请注意，如果其中一个参数为空，则可能会引发 NullPointerException，也可能不会引发，这取决于比较器为空值选择的排序策略(如果有)。

    ```
    Syntax : 
    public static  int compare(T a,T b,Comparator c)
    Type Parameters:
    T - the type of the objects being compared
    Parameters : 
    a - an object
    b - an object to be compared with a
    c - the Comparator to compare the first two arguments
    Returns :
    0 if the arguments are identical and c.compare(a, b) otherwise.

    ```

**注意:**在 Java 8 中，Objects 类还有 3 个方法。其中两个(*为空(对象 o)* 和*为非空(对象 o)* )用于检查*是否为空*引用。第三个是 requireNonNull 方法的另一个重载版本。这里参考。