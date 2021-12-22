# JSON 使用 Jackson 在 REST API 中与 Spring Boot 实现

> 原文:[https://www . geesforgeks . org/JSON-using-Jackson-in-rest-API-implementation-with-spring-boot/](https://www.geeksforgeeks.org/json-using-jackson-in-rest-api-implementation-with-spring-boot/)

每当我们用 [Spring (Spring Boot)](https://www.geeksforgeeks.org/introduction-to-spring-boot/) 实现 [REST API](https://www.geeksforgeeks.org/rest-api-introduction/) 时，我们都会遇到在 API 的 [JSON](https://www.geeksforgeeks.org/difference-between-json-and-csv/) 响应中排除空值的要求。此外，可能需要将打开/关闭此功能具体化:**在 JSON 响应中排除空值**，从而允许应用编程接口的使用者根据需要进行定制。

在本文中，我们总结了使用 **Jackson 实现上述特性的 ON/OFF 外部化的方法，Jackson 是一个基于 java 的库，用于将 java 对象序列化或映射到 JSON，反之亦然。**

**不成功的方法:**

最初，我们尝试了 Spring Boot 现成的方法，但没有成功，例如:

*   在*应用程序中具有*属性。该属性取值为:*始终* / *非空* / *非空* / *非默认* / *非空*。**
*   扩展*WebMvcConfigurationSupport*类并定制 Spring Boot 配置，见下文。

## Java 语言(一种计算机语言，尤用于创建网站)

```
@Configuration
class WebMvcConfiguration extends WebMvcConfiguration{
    @Override
    protected void extendsMessageConverters
      (List<HttpMessageConverter<?>> converters)
    {
        for(HttpMessageConverter<?> converter: converters)
        {
            if(converter instnceof MappingJackson2HttpMessageConverter)
            {
                ObjectMapper mapper = 
                  ((MappingJackson2HttpMessageConverter)converter)
                  .getObjectMapper();
                mapper.setSerializationInclusion(Include.NON_NULL);
                }
            }
        }
```

现在，创建一个实例***org . spring framework . http . converter . JSON . Jackson 2 objectmapperbuilder customizer***，下面给出的代码供大家参考。

## Java

```
@Bean
Public Jackson2ObjectMapperBuilderCustomizer customJackson(){
    return new Jackson2ObjectMapperBuilderCustomizer(){
    @Override
    public void customize(Jackson2ObjectMapperBuilder builder){
        builder.serializationInclusion(Include.NON_NULL);
        builder.failonUnknownProperties(false);
        }
    };
}
```

**成功进场:**

创建一个 JSON 响应对象，如果没有创建的话。这是在序列化为 JSON 时，基于 ***应用程序中的属性，您想要“ ***排除/包含空字段*** 特征的对象。您可以在下面看到响应对象，以供参考。***

## ***Java***

```
***public class RegistrationResponse{

    @JsonProperty("success")
    private Boolean success = null;

    @JsonProperty("message")
    private String message = null;

    @JsonProperty("data")
    private String data = null;

    @JsonProperty("error_code")
    private Integer errorCode = null;

    public RegistrationResponse success(Boolean success){
        this.success = success;
        return this;
        }

        @NotNull
        public Boolean isSuccess(){
            return success;
            }
        public void setSuccess(Boolean success){
            this.success = success;
        }

        public RegistrationResponse message(String message){
            this.message = message;
            return this;
            }

        @NotNull
        public String getMessage(){
            return message;
        }

        public void setMessage(String message){
            this.message = message;
        }***
```

创建一个名为“***config . response . JSON . format . exclude _ null***”的属性，该属性可以将值取为“ ***【真】*** ”或“ ***【假】*** ”。值“ ***为真*** 表示在 JSON 响应中排除空字段&值“ ***为假*** 表示不排除空字段。此外，将此属性绑定到类级属性，以便可以读取该值。下面给出的代码供您参考。

```
config.response.json.format.exclude_null = false
```

```
@Value("${config.response.json.format.exclude_null}")
private boolean toExcludeNull;
```

通过创建 ***的实例来实现基于全局属性值排除空值的实际逻辑。***

****   Set the ***serialized inclusion*** attribute of the created mapper to ***inclusion. Not blank*** If the global attribute value is true, otherwise it is set to ***inclusive. Always*** .*   Serialize the response object into a string using the mapper & return the string. ***Ensure that JsonProcessingException*** is handled.***

让我们看看下面作为 API 实现的一部分构建 JSON 响应时要添加的实际代码片段。

## 爪哇

```
RegistrationResponse regResp = new RegistrationResponse();

regResp.setSuccess(true);
regResp.setErrorCode(null);
regResp.setData("testdata");
regResp.setMessage("success");

ObjectMapper mapper = new ObjectMapper()
mapper.enable(SerializationFeature.INDENT_OUTPUT);

if(toExcludeNull) mapper.setSerializationInclusion(Include.NON_NULL);
else mapper.serializationInclusion(Include.ALWAYS);

String regRespStr = null;
try{

    regRespStr = mapper.writeValueAsString(regResp);
    }
    catch(JsonProcessingException e)
        e.printStackTrace();
        }
    System.out.println("Formatted JSON Response:" + regRespStr);
```

这里，***是应用了空排除/包含的 JSON 字符串。***

**也可以查看 [Github 资源库](https://github.com/myblogs-demos/demo-jsonnullexclusion-proj)。**