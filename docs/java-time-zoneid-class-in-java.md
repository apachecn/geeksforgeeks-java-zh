# java 中的 java.time.ZoneId 类

> 原文:[https://www . geesforgeks . org/Java-time-zoneid-class-in-Java/](https://www.geeksforgeeks.org/java-time-zoneid-class-in-java/)

一个[区域标识](https://www.geeksforgeeks.org/tag/java-zoneid/)用于标识用于在本地日期时间和即时时间之间转换的规则。描述偏移量变化的时间和方式的实际规则由 ZoneRules 定义。这个类只是一个用来获取底层规则的 ID。给定的方法之所以选择，是因为政府定义了规则并经常修改，而身份是稳定的。

有两种不同类型的标识:

1.  固定偏移是从世界协调时/格林威治时间完全解析的偏移，对所有本地日期时间使用相同的偏移
2.  地理区域是一个邻域，在该邻域中应用一组选定的规则来定位与世界协调时/格林威治的偏移

> **申报** [**爪哇时区类**](https://www.geeksforgeeks.org/tag/java-zoneid/)
> 
> 公共抽象类 ZoneId 扩展了实现可序列化的对象

区域地图覆盖启用短时区名称。在[Java . util . Tizone](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)中已经不推荐使用短区域标识。这个映射允许标识仍然通过(字符串，映射)工厂方法使用。此地图包含符合 TZDB 2005r 及更高版本的身份证映射，其中“东部标准时间”、“东部标准时间”和“西部标准时间”映射到不包括夏令时的身份证。

这映射如下:

<figure class="table">

| 东部时间 | five o'clock |
| 高速列车 | ten o'clock |
| 山地时间 | seven o'clock |
| 行动 | 澳大利亚/达尔文 |
| 氨乙异硫脲(Aminoethylisothiourea) | 澳大利亚/悉尼 |
| AGT

 | 美洲/阿根廷/布宜诺斯艾利斯 |
| 艺术 | 非洲/开罗 |
| 大西洋时间 | 美国/安克雷奇 |
| 赌注 | 美洲/圣保罗 |
| 牛生长激素 | 亚洲/达卡 |
| 猫 | 非洲/哈拉雷 |
| （cannot）不能 | 美国/圣约翰 |
| 中央标准时间 | 美国/芝加哥 |
| 同ＣAPITAL TRANSFER TAX | 亚洲/上海 |
| 吃 | 非洲/亚的斯亚贝巴 |
| 电惊厥疗法

 | 欧洲/巴黎 |
| 国际排放贸易 | 美国/印第安纳/印第安纳波利斯 |
| 胰岛素休克疗法(insulin shock therapy) | 亚洲/加尔各答 |
| japan standard time 日本标准时间 | 亚洲/东京 |
| 用它 | 太平洋/阿皮亚 |
| 网 | 亚洲/埃里温 |
| 期刊 | 太平洋/奥克兰 |
| PLT | 亚洲/卡拉奇 |
| 阵发性结性心动过速 | 美国/凤凰城 |
| 石油收入税(Petroleum Revenue Tax) | 美洲/波多黎各 |
| 悄悄话 | 美国/洛杉矶 |
| 超音速运输机 | 太平洋/瓜达尔卡纳尔 |
| VST | 亚洲/胡志明 |

</figure>

**注:**该图不可修改。

**ZoneId 类的方法:**

<figure class="table">

| **方法** | **描述** |
| --- | --- |
| 等于(对象对象) | 此方法检查此时区标识是否等于另一个时区标识。 |
| 来自(临时过程或临时) | 此方法从时态对象中获取 ZoneId 的实例。 |
| getAvailableZoneIds() | 此方法获取一组可用的区域标识。 |
| getDisplayName(文字型式本端) | 此方法获取区域的文本表示形式，如“英国时间”或“+02:00”。 |
| getId() | 此方法获取唯一的时区标识。 |
| getRules() | 此方法获取允许执行计算的此标识的时区规则。 |
| hashCode() | 此时区标识的哈希代码。 |
| 标准化() | 此方法将时区标识规范化，并在可能的情况下返回一个区域偏移量。 |
| 的(字符串区域标识) | 此方法从一个标识获取一个区域标识的实例，确保该标识有效并可供使用。 |
| (字符串区域标识，地图 <string>aliasMap)</string> | 此方法使用别名映射来补充标准区域标识，从而使用其标识来获取区域标识的实例。 |
| ofOffset(字符串前缀，ZoneOffset) | 此方法获取包装偏移量的 ZoneId 的实例。 |
| systemDefault() | 此方法获取系统默认时区。 |
| toString() | 此方法使用标识将该区域输出为字符串。 |

</figure>

下面是一些方法的实现示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java.time.ZoneId Class in Java with example
import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // Setting Zone1
        ZoneId zoneid1 = ZoneId.of("Asia/Kolkata");
        // Setting Zone2
        ZoneId zoneid2 = ZoneId.of("Europe/London");
        LocalTime time1 = LocalTime.now(zoneid1);
        LocalTime time2 = LocalTime.now(zoneid2);
        System.out.println(time1);
        System.out.println(time2);

        // Checking if the time of zone1
        // comes before time of second zone
        System.out.println(time1.isBefore(time2));
    }
}
```

**Output**

```
22:34:11.044312
17:04:11.044385
false
```