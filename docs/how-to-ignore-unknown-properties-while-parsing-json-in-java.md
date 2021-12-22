# 在 Java 中解析 JSON 时如何忽略未知属性？

> 原文:[https://www . geesforgeks . org/如何在解析时忽略未知属性-java 中的 JSON/](https://www.geeksforgeeks.org/how-to-ignore-unknown-properties-while-parsing-json-in-java/)

解析 java 中的 JSON 时存在未知属性，其中使用 Jackson API 解析 Java 中的 JSON 时最常见的问题是当 JSON 包含未知属性时会失败，这意味着 Java 类没有所有 JSON 属性对应的所有字段。例如，如果您正在使用来自 REST Web Service 的 JSON，第二天他们在 JSON 中添加了一个新字段，那么代码将会中断，因为 Jackson 将抛出**unrecognized property exception**并停止解析 JSON。这很麻烦，如果人们不知道，会在生产中引起问题。如果你熟悉杰克逊图书馆，这个问题本可以避免。

**方法:**

杰克逊应用编程接口提供了两种忽略未知字段的方法。这两种方法都将在这里讨论，我们还将看到如何使用它们，何时使用@ JsonIgnoreProperties，以及何时在对象映射器级别全局忽略 JSON 中的未知字段。它们如下:

1.  Use ***@ jsonignorperties*** annotation at the class level.
2.  Use the configure () method at the **object mapper** level.

**方法 1:** 使用@ JsonIgnoreProperties

如果正在创建一个模型类来表示 Java 中的 JSON，那么这个类可以被注释为@ jsonignorperties(ignoreuknown = true)来忽略任何未知的字段。这意味着，如果稍后在表示这个模型的 JSON 上添加了一个新字段，那么 Jackson 在用 Java 解析 JSON 时不会抛出 UnrecognizedPropertyException。这种方法不仅忽略了模型类的未知属性，而且提供了更多的控制。

**例:**

## 爪哇

```
// Java Program that demonstrates the use of
// @JsonIgnoreProperties

import com.fasterxml.jackson.annotation.JsonIgnoreProperties;
import com.fasterxml.jackson.databind.ObjectMapper;
import java.io.IOException;
import java.io.Serializable;

/*
 * Java Program to iterate over JSONObject of json-simple
 */
@JsonIgnoreProperties(ignoreUnknown = true)
class Student implements Serializable {
    private static final long serialVersionUID
        = -740085147914603262L;

    private String id;
    private String name;
    private String school;
    private String section;
    private String major;

    // getters and setters
    public String getID() { return id; }

    public void setID(String id) { this.id = id; }

    public String getName() { return name; }

    public void setName(String id) { this.name = name; }

    public String getSchool() { return school; }

    public void setSchool(String id) { this.id = id; }

    public String getSection() { return id; }

    public void setSection(String id) { this.id = id; }

    public String getMajor() { return id; }

    public void setMajor(String id) { this.id = id; }

    @Override public String toString()
    {

        return "Student{"
            + "name='" + name + '\'' + ", id='" + id + '\''
            + ", school='" + school + '\'' + ", section='"
            + section + '\'' + ", major='" + major + '\''
            + '}';
    }
}

class StudentMain {
    public static void main(String[] args)
        throws IOException
    {
        // JSON string
        String jsonString
            = "{\"name\":\"Krish\",\"id\":\"2019071075\"\"phone\":\"111-111-1111\"}";
        System.out.println("Input json string : ");
        System.out.println(jsonString);
        System.out.println("");

        // convert to object;
        Student s = toStudent(jsonString);

        // print information
        System.out.println("Generated java class:");
        System.out.println(s);
    }

    private static Student toStudent(String jsonData)
        throws IOException
    {
        // create object mapper instance
        ObjectMapper om = new ObjectMapper();

        // convert JSON string to Java Object
        return om.readValue(jsonData, Student.class);
    }
}
```

**输出:**

```
Input json string :
{"name":"Krish","phone":"111-111-1111"}

Generated java class:
Employee{name='Krish', id='2019071075', school='null', section='null', major='null'}
```

**输出说明:**

用@ JsonIgnoreProperties 注释类的方法允许更好地控制哪些对象应该忽略未知字段，哪些不应该。另一方面，开发人员可能会忘记将注释放在类中，这样就可能出现问题。

**方法 2:** 使用杰克逊

配置 ObjectMapper 是解析时处理 JSON 中未知属性的另一种方法，这样在遇到未知属性时就不会失败。这也解决了 UnrecognizedPropertyException 的问题。

通过调用 ***配置()方法*** 来启用此设置，如下所示:

```
import com.fasterxml.jackson.databind.DeserializationFeature; 
import com.fasterxml.jackson.databind.ObjectMapper; 

ObjectMapper objectMapper = new ObjectMapper(); 
objectMapper.configure(DeserializationFeature.FAIL_ON_UNKNOWN_PROPERTIES, false);
```

> **注意:**对于它要解析的任何 JSON，未知属性都将被忽略。只有当您不能用@ JsonIgnoreProperties 注释来注释一个类时，才应该使用这个选项。

**例:**

## 爪哇

```
// Java Program that demonstrates the use of ObjectMapper
// Configuration

import com.fasterxml.jackson.core.JsonParseException;
import com.fasterxml.jackson.core.JsonParser;
import com.fasterxml.jackson.databind.DeserializationContext;
import com.fasterxml.jackson.databind.DeserializationFeature;
import com.fasterxml.jackson.databind.JsonMappingException;
import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.databind.deser.std.StdDeserializer;
import java.io.IOException;

/* * Java Program to iterate over JSONObject of json-simple
 */
class JacksonTest {
    // JSON string
    private static String json
        = "{\r\n"
          + "\"name\" : \"Jack Ryan\",\r\n"
          + "\"id\" : \"2019071075\",\r\n"
          + "\"school\" : St. Jude's School,\r\n"
          + "\"section\" : B\r\n"
          + "}";
    public static void main(String args[])
        throws IOException
    {
        // create object mapper instance
        ObjectMapper om = new ObjectMapper();
        // configure ignore unknown properties
        om.configure(DeserializationFeature
                         .FAIL_ON_UNKNOWN_PROPERTIES,
                     false);
        // convert JSON string to Java Object
        Student effectiveJava
            = om.readValue(json, Student.class);
        System.out.println("Input json string");
        System.out.println(json);
        System.out.println("Generated java class: ");
        System.out.println(effectiveJava);
    }
}

class Student {
    private String name;
    private String id;
    private String school;

    public Student()
    {
        // no argument constructor required by Jackson
    }

    public Student(String name, String id, String school)
    {
        this.name = name;
        this.id = id;
        this.school = school;
    }
    // getters and setters
    public String getID() { return id; }

    public void setID(String id) { this.id = id; }

    public String getName() { return name; }

    public void setName(String id) { this.name = name; }

    public String getSchool() { return school; }

    public void setSchool(String id) { this.id = id; }

    @Override public String toString()
    {
        return "Student{"
            + "name='" + name + '\'' + ", id='" + id + '\''
            + ", school='" + school + '\'' + '}';
    }
}
```

**输出:**

```
Input json string
 {
   "name" : "Jack Ryan",
   "id" : "2019071075",
   "school" : "St. Jude's School",
   "section" : "B" 
  } 
 Generated java class:
 Student [name=Jack Ryan, id=2019071075, school=St. Jude's School]
```

**输出说明:**

根据依赖注入框架配置对象映射器的方法，确保在整个系统中使用相同的对象映射器，将保证在整个应用程序中消除异常，但让开发人员在使用 API 中发生的演变方面蒙上眼睛。

但是，首选的方法是使用@ jsonignorproperties(ignoreuknown = true)忽略类级别的未知属性，并且只有当您不能使用此注释来注释您的类，即您不拥有该类时，才在 ObjectMapper 级别执行此操作。用@ JsonIgnoreProperties 注释模型类也是避免问题的最佳实践。