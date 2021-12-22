# Java 中的 BreakIterator getAvailableLocales()方法，示例

> 原文:[https://www . geeksforgeeks . org/breakiterator-getavailablelocales-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-getavailablelocales-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **getAvailableLocales()** 方法用于提供所有地区的数组。

**语法:**

```
public static Locale[] getAvailableLocales()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法提供了一个所有区域设置的**数组**，对于这个数组，所有 getInstance 方法都可以为每个方法返回一个本地化实例。

以下是说明 **getAvailableLocales()** 方法的示例:

**例 1:**

**输出:**

> [，ar_AE，ar_JO，ar_SY，hr_HR，fr_BE，es_PA，mt_MT，es_VE，bg，zh_TW，it，ko，uk，lv，da_DK，es _ co en、ro_RO、en_PH、ca、ar_TN、sr_ME_#Latn、es_GT、sl、ko_KR、el_CY、es_MX、ru_RU、es_HN、zh_HK、no_NO_NY、hu_HU、th_TH、ar_IQ、es_CL、fi、ar_MA、ga_IE、mk、tr_TR 和 _EE、ar_QA、sr _ _ #latn、pt_PT、fr_LU、ar_OM、th、sq

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # getavailable locales–](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#getAvailableLocales--)