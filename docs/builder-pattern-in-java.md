# Java 中的构建器模式

> 原文:[https://www.geeksforgeeks.org/builder-pattern-in-java/](https://www.geeksforgeeks.org/builder-pattern-in-java/)

**方法链接:**在 java 中，方法链接用于在同一个对象上调用多个方法，这些方法作为单个语句出现。方法链接由一系列方法实现，这些方法为类实例返回[这个](https://www.geeksforgeeks.org/this-reference-in-java/)引用。

**实现:**由于链中方法的返回值是[这个](https://www.geeksforgeeks.org/this-reference-in-java/)引用，这个实现允许我们通过对链中前一个方法的返回值进行下一个方法调用来调用链中的方法。

```
// Java code to demonstrate method chaining
final class Student {

    // instance fields
    private int id;
    private String name;
    private String address;

    // Setter Methods
    // Note that all setters method
    // return this reference
    public Student setId(int id)
    {
        this.id = id;
        return this;
    }

    public Student setName(String name)
    {
        this.name = name;
        return this;
    }

    public Student setAddress(String address)
    {
        this.address = address;
        return this;
    }

    @Override
    public String toString()
    {
        return "id = " + this.id + ", name = " + this.name + 
                               ", address = " + this.address;
    }
}

// Driver class
public class MethodChainingDemo {
    public static void main(String args[])
    {
        Student student1 = new Student();
        Student student2 = new Student();

        student1.setId(1).setName("Ram").setAddress("Noida");
        student2.setId(2).setName("Shyam").setAddress("Delhi");

        System.out.println(student1);
        System.out.println(student2);
    }
}
```

输出:

```
id = 1, name = Ram, address = Noida
id = 2, name = Shyam, address = Delhi

```

**构建器模式的需求:**方法链接是一种有用的设计模式，但是如果**同时访问**，线程可能会观察到一些字段包含不一致的值。虽然上面例子中的所有 setter 方法都是*原子*，但是当对象被并发修改时，方法链中的调用会导致对象状态不一致。下面的例子可以让我们看到一个*学生*处于**不一致状态**的实例，比如一个名字为 *Ram* 地址为*德里*的学生。

```
// Java code to demonstrate need of Builder Pattern

// Server Side Code
final class Student {

    // instance fields
    private int id;
    private String name;
    private String address;

    // Setter Methods
    // Note that all setters method
    // return this reference
    public Student setId(int id)
    {
        this.id = id;
        return this;
    }

    public Student setName(String name)
    {
        this.name = name;
        return this;
    }

    public Student setAddress(String address)
    {
        this.address = address;
        return this;
    }

    @Override
    public String toString()
    {
        return "id = " + this.id + ", name = " + this.name + 
                               ", address = " + this.address;
    }
}

// Client Side Code
class StudentReceiver {

    private final Student student = new Student();

    public StudentReceiver()
    {

        Thread t1 = new Thread(new Runnable() {
            @Override
            public void run()
            {
                student.setId(1).setName("Ram").setAddress("Noida");
            }
        });

        Thread t2 = new Thread(new Runnable() {
            @Override
            public void run()
            {
                student.setId(2).setName("Shyam").setAddress("Delhi");
            }
        });

        t1.start();
        t2.start();
    }

    public Student getStudent()
    {
        return student;
    }
}

// Driver class
public class BuilderNeedDemo {
    public static void main(String args[])
    {
        StudentReceiver sr = new StudentReceiver();
        System.out.println(sr.getStudent());
    }
}
```

输出可能是:

```
id = 2, name = Shyam, address = Noida

```

另一个不一致的输出可能是

```
id = 0, name = null, address = null

```

**注意:**尝试循环运行 *main* 方法语句(即同时向服务器发出多个请求)。

为了解决这个问题，有 Builder 模式来保证对象创建的**线程安全**和**原子性**。

**实现:**在构建器模式中，我们在服务器类中有一个名为*构建器*的[内部静态类](https://www.geeksforgeeks.org/nested-classes-java/)，该类有实例字段，并且还有一个[工厂方法](https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/)，用于在每次调用时返回*构建器*类的一个**新**实例。setter 方法现在将返回 *Builder* 类引用。我们还将有一个*构建*方法来返回服务器端类，即外部类的实例。

```
// Java code to demonstrate Builder Pattern

// Server Side Code
final class Student {

    // final instance fields
    private final int id;
    private final String name;
    private final String address;

    public Student(Builder builder)
    {
        this.id = builder.id;
        this.name = builder.name;
        this.address = builder.address;
    }

    // Static class Builder
    public static class Builder {

        /// instance fields
        private int id;
        private String name;
        private String address;

        public static Builder newInstance()
        {
            return new Builder();
        }

        private Builder() {}

        // Setter methods
        public Builder setId(int id)
        {
            this.id = id;
            return this;
        }
        public Builder setName(String name)
        {
            this.name = name;
            return this;
        }
        public Builder setAddress(String address)
        {
            this.address = address;
            return this;
        }

        // build method to deal with outer class
        // to return outer instance
        public Student build()
        {
            return new Student(this);
        }
    }

    @Override
    public String toString()
    {
        return "id = " + this.id + ", name = " + this.name + 
                               ", address = " + this.address;
    }
}

// Client Side Code
class StudentReceiver {

    // volatile student instance to ensure visibility
    // of shared reference to immutable objects
    private volatile Student student;

    public StudentReceiver()
    {

        Thread t1 = new Thread(new Runnable() {
            @Override
            public void run()
            {
                student = Student.Builder.newInstance()
                              .setId(1)
                              .setName("Ram")
                              .setAddress("Noida")
                              .build();
            }
        });

        Thread t2 = new Thread(new Runnable() {
            @Override
            public void run()
            {
                student = Student.Builder.newInstance()
                              .setId(2)
                              .setName("Shyam")
                              .setAddress("Delhi")
                              .build();
            }
        });

        t1.start();
        t2.start();
    }

    public Student getStudent()
    {
        return student;
    }
}

// Driver class
public class BuilderDemo {
    public static void main(String args[])
    {
        StudentReceiver sr = new StudentReceiver();
        System.out.println(sr.getStudent());
    }
}
```

输出保证为以下之一:

```
id = 1, name = Ram, address = Noida

```

运筹学

```
id = 2, name = Shyam, address = Delhi

```

也可以使用任何必需的参数调用 *Builder.newInstance()* 工厂方法，通过重载获得一个 *Builder* 实例。*学生*类的对象是通过调用 *build()* 方法构建的。
Builder 模式的上述实现使得*学生*类**不变**，从而**线程安全**。

还要注意客户端代码中的*学生*字段不能声明为[最终](https://www.geeksforgeeks.org/final-keyword-java/)，因为它被分配了一个新的不可变对象。但是它被声明为[易变的](https://www.geeksforgeeks.org/volatile-keyword-in-java/)，以确保对不可变对象的共享引用的可见性。 *Builder* 类的私有成员也维护封装。

请查看 *java.lang* 包中 *[StringBuilder](https://contribute.geeksforgeeks.org/conversion-between-types-of-strings-in-java-combined-with-httpwww-geeksforgeeks-orgg-fact-27-string-vs-stringbuilder-vs-stringbuffer/)* 类的[追加](https://github.com/openjdk-mirror/jdk7u-jdk/blob/master/src/share/classes/java/lang/StringBuilder.java)方法，了解更多 Builder 模式的实现。