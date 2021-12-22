# 如何创建和关闭 JsonGenerator？

> 原文:[https://www . geesforgeks . org/how-create-and-close-jsongenerator/](https://www.geeksforgeeks.org/how-to-create-and-close-jsongenerator/)

首先，什么是 **JSON** ？JSON 代表 **JavaScript 对象符号**。这是一种在服务器和客户端之间使用的数据交换格式。JSON 数据示例:

```
{
"name" : "Sonali Singh",
"age": 40,
"address" : {
"state": "Texas",
"city": "Houston"
            }
}
```

JSONGenerator 是一个接口，它以流的方式将 JSON 数据写入输出源。为了创建 JSONGenerator 的实例，我们需要使用 JSONFactory 实例。

```
JsonFactory factory = new JsonFactory();
```

这个工厂实例有一个名为 **CreateGenerator** 的方法，它将创建 JSONGenerator。

```
JsonGenerator generator = factory.createGenerator(new File("test.json"));
```

createGenerator 将我们希望写入 JSON 的目标作为第一个参数。如果我们使用 bytestream 作为第一个参数，我们还可以选择指定字符集

```
createGenerator(OutputStream out, Charset charset)
```

现在我们可以开始将 JSON 写入我们的流。从生成器对象调用的第一个方法是 **writeStartObject()** 写对象或者 **writeStartArray()** 写数组，之后我们可以指定键和值的名称。写完 JSON 后，我们指定 **writeEnd()** 函数，它标志着我们的 JSON 数据的结束。

### **例**

**写起始对象：**

```
generator.writeStartObject().write("name": "Sonali Singh").write("age":40).writeEnd().close()
```

```
The JSON generated is {"name" : "Sonali Singh","age": 40,}
```

**writestararray:**

```
generator
    .writeStartObject().write("name", "Sonali Singh").write("age", 25)
        .writeStartArray("education")
            .writeStartObject()
                .write("type", "college")
                .write("course", "B.Com")
            .writeEnd()
            .writeStartObject()
                .write("type", "Higher Secondary")
                .write("course", "Commerce")
            .writeEnd()
        .writeEnd()
    .writeEnd();
generator.close();
```

```
The JSON generated is 
{"name": :Sonali Singh", "age" : 25,
"education" : [ {"type", "college", "course", "B.Com},
                {"type", "Higher Secondary", "course", "Commerce"}
                ]
}
```

最后，我们称之为。生成器的 close()方法。此方法通过关闭相应的输出流来释放资源。