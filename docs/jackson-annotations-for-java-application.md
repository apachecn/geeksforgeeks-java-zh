# 【Java 应用的杰克逊注释

> 原文:[https://www . geesforgeks . org/Jackson-annotations-for-Java-application/](https://www.geeksforgeeks.org/jackson-annotations-for-java-application/)

Java 在编码领域有着巨大的应用，我们几乎都知道这个事实。它的一个特点是杰克逊注释。虽然这是编码界人士非常熟悉的术语，但却不太为人所知。Jackson 是一个流行且非常高效的 JAVA 库，用于将 JAVA 对象映射或序列化到 JSON，反之亦然。

由于 Jackson 是一个基于 JAVA 的库，所以在继续 Jackson 之前，必须了解 JAVA 的基础知识。它提供了如下所列的各种功能:

*   Jackson is an easy-to-use library that can simplify common cases.
*   Because the default mapping is provided, there is no need to create a mapping in Jackson.
*   Its commendable speed and low memory footprint make it suitable for large object systems.
*   The JSON results created by Jackson are compact and clean, and easy to read.
*   Jdk is the only library Jackson needs. Therefore, it has no dependency.
*   Most importantly, Jackson Library is free to use because it is open source.

在我们了解了使用 Jackson 的用途和优势之后， 我们现在需要了解的杰克森注解如下:

1.  @ jsonnegetter
2.  @ JsonGetter
3.  @ jsonpropertytorder
4.  @ JsonRawValue
5.  @ JsonValue
6.  @ JsonRootName
7.  @ JsonSerialize
8.  @ JsonCreator
9.  @ jacksoninjet
10.  @ jsonneysiter
11.  @ jsonnownwrapped
12.  @ JsonView
13.  @ jsonmanagerreference
14.  @ JsonBackReference
15.  @ JsonIdentityInfo
16.  @ JsonFilter
17.  @ jacksonnotationinside

让我们讨论每一个注释，以便通过实现它们并为它们提供片段代码来更深入地理解它们。

**注释 1:**JSON id

t 便于使用 getter 方法返回映射。稍后，这些映射被用来以与其他属性相同的方式序列化 JSON 的附加属性。

```java
public class ExtendableBean {

  public String name;
  private Map<String, String> properties;

  @JsonAnyGetter
  public Map<String, String> getProperties() {
    return properties;
  }
}
```

**注释 2:** @JsonGetter

这个注释便于将特定的方法标记为 getter 方法。

```java
public class MyBean {

  public int id;
  private String name;

  @JsonGetter("name")
  public String getTheName() {
    return name;
  }
}
```

注释 3: @JsonPropertyOrder

当您序列化一个 JSON 对象时，它的顺序可能会改变，但是这个注释有助于在这个过程中保持一个特定的顺序。

```java
@JsonPropertyOrder({ "name", "id" })

public class MyBean {

  public int id;
  public String name;
}
```

**注释 4:** @JsonRawValue

使用这个注释，可以序列化任何单词，而无需任何修饰或转义。

```java
public class RawBean {

  public String name;

  @JsonRawValue
  public String json;
}
```

**注释 5:**@ jsonalue

使用此注释，您可以使用单个方法序列化整个对象。

```java
public enum TypeEnumWithValue {

  TYPE1(1, "Type A"), TYPE2(2, "Type 2");

  private Integer id;
  private String name;

  // Standard constructors

  @JsonValue
  public String getName() {
    return name;
  }
}
```

**注释 6:** @JsonRootName

这个注释方便了在 JSON 上指定的根节点的外观。包装根值也需要启用。

```java
{
  "id": 1,
  "name": "John"
}
```

**注释 7:** @JsonSerialize

使用这个注释，您可以指定一个自定义序列化程序来整理 JSON 对象。

```java
public class EventWithSerializer {

  public String name;

  @JsonSerialize(using = CustomDateSerializer.class)
  public Date eventDate;
}
```

**注释 8:** @JsonCreator

在反序列化过程中，使用了一个工厂方法。此注释用于微调此方法。

```java
{
  "id": 1,
  "theName": "My bean"
}
```

**注释 9:** 杰克逊线

当我们不必解析属性值，而是将其注入到 JSON 输入中时，我们使用这个注释。

```java
public class BeanWithInject {

  @JacksonInject
  public int id;

  public String name;
}
```

**注释 10:**@ jsonnysetter

就像 getter 注释一样，这有助于使用 Map 的 setter 方法，然后使用 Map 以与其他属性相同的方式反序列化 JSON 的附加属性。

```java
public class ExtendableBean {

  public String name;
  private Map<String, String> properties;

  @JsonAnySetter
  public void add(String key, String value) {
    properties.put(key, value);
  }
}
```

**注释 11：** @JsonSetter

这个注释允许任何方法被标记为 setter 方法。

```java
public class MyBean {

  public int id;
  private String name;

  @JsonSetter("name")
  public void setTheName(String name) {
    this.name = name;
  }
}
```

**注释 12:**@ jsondeserial

此注释用于指定自定义反序列化程序，以便取消 JSON 对象的标记。

```java
public class EventWithSerializer {

  public String name;

  @JsonDeserialize(using = CustomDateDeserializer.class)
  public Date eventDate;
}
```

**注释 13:**@ jsonenterfill value

使用这个注释，我们使用默认值来反序列化未知的枚举值。

```java
public class AliasBean {

  @JsonAlias({ "fName", "f_name" })
  private String firstName;
  private String lastName;
}
```

**注释 14:**@ jsonignoperrietes

使用此注释，您可以将一个属性或一组属性标记为忽略。这是在班级级别完成的。

```java
@JsonIgnoreProperties({ "id" })
public class BeanWithIgnore {
    public int id;
    public String name;
}
```

**注释 15:** @JsonIgnore

这一个服务于与上面相同的目的，唯一的区别是它在现场使用。

```java
public class BeanWithIgnore {

  @JsonIgnore

  public int id;
  public String name;
}
```

**注释 16:**@ jsonignorettype

使用此注释，您可以将特定类型的属性标记为忽略。

```java
public class User {

  public int id;
  public Name name;

  @JsonIgnoreType
  public static class Name {

    public String firstName;
    public String lastName;
  }
}
```

**注释 17:** @JsonInclude

此注释用于那些具有空默认值的排除属性。

```java
@JsonInclude(Include.NON_NULL)

public class MyBean {

  public int id;
  public String name;
}
```

**注释 18:**@ jsonautodetent

此注释有助于检测不可见或无法访问的属性。

```java
@JsonAutoDetect(fieldVisibility = Visibility.ANY)

public class PrivateBean {

  private int id;
  private String name;
}
```

**注释 19:** @JsonTypeInfo

使用此注释，您可以指示序列化或反序列化期间必须包含的信息类型的详细信息。

**注释 20:** @JsonSubTypes

这一个用于指示已经被注释的类型的子类型。

**注释 21:** @JsonTypeName

使用这个可以设置注释类必须使用的类型名。

```java
public class Zoo {

  public Animal animal;

  @JsonTypeInfo(
    use = JsonTypeInfo.Id.NAME,
    include = As.PROPERTY,
    property = "type")

  @JsonSubTypes({
    @JsonSubTypes.Type(value = Dog.class, name = "dog"),
    @JsonSubTypes.Type(value = Cat.class, name = "cat")
  })

  public static class Animal {
    public String name;
  }

  @JsonTypeName("dog")
  public static class Dog extends Animal {
    public double barkVolume;
  }

  @JsonTypeName("cat")
  public static class Cat extends Animal {
    boolean likesCream;
    public int lives;
  }
}
```

**注释 22:** @JsonProperty

该注释用于标记非标准的 setter 或 getter 方法，这些方法必须与 JSON 属性相关联。

```java
public class MyBean {

  public int id;
  private String name;

  @JsonProperty("name")
  public void setTheName(String name) {
    this.name = name;
  }

  @JsonProperty("name")
  public String getTheName() {
    return name;
  }
}
```

**注释 23:**@ jsat

此注释通常用于日期字段，并在序列化或反序列化期间指定格式。

```java
public class EventWithFormat {

  public String name;

  @JsonFormat(
    shape = JsonFormat.Shape.STRING,
    pattern = "dd-MM-yyyy hh:mm:ss")
  public Date eventDate;
}
```

**注释 24:**@ jsonunwrapk

在序列化或反序列化过程中，需要解包对象的值。这个注释是用来实现目的的。

```java
public class UnwrappedUser {

  public int id;

  @JsonUnwrapped
  public Name name;

  public static class Name {

    public String firstName;
    public String lastName;
  }
}
```

**注释 25:** @JsonView

此注释用于控制要序列化或不序列化的值。

```java
public class Views {
    public static class Public {}
    public static class Internal extends Public {}
}
```

**注释 26:**@ jsonmanagerreference

这种注释用于显示具有父子关系的对象。

```java
public class ItemWithRef {

  public int id;
  public String itemName;

  @JsonManagedReference
  public UserWithRef owner;
}
```

**注释 27:**@ jsonackreference

这与前一个功能相同。

```java
private class Player {

  public int id;
  public Info info;
}

private class Info {

  public int id;
  public Player parentPlayer;
}

// Something like this will come into play
Player player = new Player(1);
player.info = new Info(1, player);
```

**注释 28:** @JsonIdentityInfo

此注释用于存在父子关系的情况。它用于指示在序列化和反序列化期间将使用对象标识。

## 爪哇

```java
@JsonIdentityInfo(
  generator = ObjectIdGenerators.PropertyGenerator.class,
  property = "id")
public class ItemWithIdentity {
    public int id;
    public String itemName;
    public UserWithIdentity owner;
}
```

**注释 29:** @JsonFilter

该注释可用于在序列化和反序列化过程中应用过滤器。

```java
@JsonFilter("myFilter")

public class BeanWithFilter {

  public int id;
  public String name;
}
```

**注释 30:**@ jacksonnotationinside

该注释可用于创建定制的杰克逊注释。

```java
@Retention(RetentionPolicy.RUNTIME)
@JacksonAnnotationsInside
@JsonInclude(Include.NON_NULL)
@JsonPropertyOrder({ "name", "id", "dateCreated" })

public @interface CustomAnnotation {}
```

> **注:**各种其他注释用于重命名属性或忽略它们或选择或多或少的特定类型。

在使用这些注释时，杰克逊自己在创建值实例时使用默认构造函数。但是，可以通过放置自定义构造函数来改变它。此外，Jackson 可以处理多态类型，即具有各种子类型的对象。这通过允许包含类型信息来实现。因此，这些是关于杰克逊注释、它们的使用以及它们在 Java 中的重要性的几点和基本信息。