# 用示例自定义 Java 注释

> 原文:[https://www . geesforgeks . org/customize-Java-annotation-with-examples/](https://www.geeksforgeeks.org/customize-java-annotation-with-examples/)

Java 注释是一种向我们的源代码(程序)添加元数据信息的机制。它们是添加到 JDK5 中的 Java 的一个强大部分。注释提供了使用 XML 描述符的替代方法。此外，我们能够将它们附加到包、类、接口、方法和字段，注释本身对源代码(程序)的执行没有影响。在本文中，我们将重点关注如何创建和处理自定义注释。我们可以通过示例详细阅读如何定制 [Java 注释](https://www.geeksforgeeks.org/annotations-in-java/)

### 创建自定义注释

我们将创建三个自定义注释，目标是将对象序列化为 JSON 字符串。那就是–

*   **类级标注**
*   **场级标注**
*   **方法级注释**

### 1.类级注释

创建自定义注释的第一步是**使用@interface 关键字:**声明它

```java
public @interface GFG {
}
```

下一步是**指定我们自定义标注的范围和目标:**

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.Type)
public @interface GFG {
}
```

### 2.字段级注释

使用同样的方式，我们创建第二个注释来**标记将要包含在生成的 JSON 中的字段:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.FIELD)
public @interface GFGElement {
    public String key() default "";
}
```

### 3.方法级注释

为了将对象序列化为 JSON 字符串，我们希望执行一些方法来初始化对象。因此，我们将创建一个注释来标记这个方法。首先，声明一个具有运行时可见性的公共注释，我们可以将其应用于我们的类方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface Init {
}
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.admfactory.annotation;

import java.lang.annotation.Documented;
import java.lang.annotation.ElementType;
import java.lang.annotation.Inherited;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Documented
@Target(ElementType.FIELD)
@Inherited
@Retention(RetentionPolicy.RUNTIME)
public @interface DBField {
    String name();

    Class< ?> type();

    boolean isPrimaryKey() default false;
}
```

### 用法:

#### 带注释的类

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.admfactory.annotation;

import java.util.Date;

public class User {

    @DBField(name = "id", isPrimaryKey = true, type = Long.class)
    private long id;

    @DBField(name = "name", type = String.class)
    private String name;

    @DBField(name = "email", type = String.class)
    private String email;

    @DBField(name = "created", type = Date.class)
    private Date created;

    public long getId() {
        return id;
    }

    public void setId(long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public Date getCreated() {
        return created;
    }

    public void setCreated(Date created) {
        this.created = created;
    }
}
```

#### 可运行代码

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.admfactory.annotation;

import java.lang.reflect.Field;
import java.util.Date;

public class AnnotationExample {

    public static void main(String[] args) throws Exception {
        System.out.println("Java Custom Annotation Example");
        System.out.println();

        User usr = new User();
        usr.setEmail("john.doe@example.com");
        usr.setName("John Doe");
        usr.setId(112);
        usr.setCreated(new Date());

        for (Field field : usr.getClass().getDeclaredFields()) {
            DBField dbField = field.getAnnotation(DBField.class);
            System.out.println("field name: " + dbField.name());

            // changed the access to public
            field.setAccessible(true);
            Object value = field.get(usr);
            System.out.println("field value: " + value);

            System.out.println("field type: " + dbField.type());
            System.out.println("is primary: " + dbField.isPrimaryKey());
            System.out.println();
        }
    }
}
```

**输出:**

```java
Java Custom Annotation Example

field name: id
field value: 112
field type: class java.lang.Long
is primary: true

field name: name
field value: John Doe
field type: class java.lang.String
is primary: false

field name: email
field value: john.doe@example.com
field type: class java.lang.String
is primary: false

field name: created
field value: Wed Jul 25 17:10:05 BST 2018
field type: class java.util.Date
is primary: false
```