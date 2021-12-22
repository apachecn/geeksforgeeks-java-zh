# Java 中的十进制样式 getAvailableLocales()方法，示例

> 原文:[https://www . geeksforgeeks . org/decimal style-getavailablelocales-method-in-Java-with-example/](https://www.geeksforgeeks.org/decimalstyle-getavailablelocales-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的 **getAvailableLocales()** 方法用于获取这个 decimal style 的所有可用 Locales 的列表。此方法返回一组可用的区域设置。

**语法:**

```java
public static Set<Locales> getAvailableLocales()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个十进制样式的所有可用区域设置的**集合**。

**异常:**这个方法不抛出任何异常。

**程序:**

**输出:**

> 可用的地方:[，ar_AE，ar_JO，ar_SY，hr_HR，fr_BE，es_PA，mt_MT，es_VE，bg，zh_TW，it，ko，uk，lv，da_DK ar_SD、en、ro、en_PH、ca、ar_TN、sr_ME_#Latn、es_GT、sl、ko_KR、el_CY、es_MX、ru_RU、es_HN、zh_HK、NO_NY、hu_HU、th_TH、ar_IQ、es_CL、fi、ar_MA、ga_IE、mk、tr_TR 和 _EE、ar_QA、sr _ _ #latn、pt_PT、fr_LU、ar_OM

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # getAvailableLocales()](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#getAvailableLocales())