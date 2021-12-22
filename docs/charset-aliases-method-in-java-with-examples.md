# Java 中的 Charset 别名()方法，带示例

> 原文:[https://www . geesforgeks . org/charset-alias-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-aliases-method-in-java-with-examples/)

**别名()**方法是 **java.nio.charset** 的内置方法，它返回一个包含该 charset 别名的集合。当一个对象可以被多个引用引用时，这意味着它们存储同一个对象的引用值，那么这样的引用被称为别名。

**语法** :

```
public final Set aliases()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个集合，该集合包含代表字符集内置别名的字符串。

下面是上述功能的实现:

**程序 1:**

```
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // Create a Map which
        // stores all available charsets
        Map<String, Charset> charsets
            = Charset.availableCharsets();

        // Declare an iterator
        Iterator<Charset> iterator
            = charsets.values().iterator();

        // Iterate till we have aliases
        while (iterator.hasNext()) {

            // Get the next iterator
            Charset all = (Charset)iterator.next();

            // Print the aliases
            System.out.println(all.aliases());
            System.out.println();
        }
    }
}
```

**输出:**

```
[csBig5]

[big5-hkscs, big5hk, Big5_HKSCS, big5hkscs]

[CESU8, csCESU-8]

[csEUCPkdFmtjapanese, x-euc-jp, eucjis, Extended_UNIX_Code_Packed_Format_for_Japanese, euc_jp, eucjp, x-eucjp]

[ksc5601-1987, csEUCKR, ksc5601_1987, ksc5601, 5601, euc_kr, ksc_5601, ks_c_5601-1987, euckr]

[gb18030-2000]

[gb2312, euc-cn, x-EUC-CN, euccn, EUC_CN, gb2312-80, gb2312-1980]

[CP936, windows-936]

[ibm-838, ibm838, 838, cp838]

[cp858, 858, PC-Multilingual-850+euro, cp00858, ccsid00858]

[cp1140, 1140, cp01140, ebcdic-us-037+euro, ccsid01140]

[1141, cp1141, cp01141, ccsid01141, ebcdic-de-273+euro]

[1142, cp1142, cp01142, ccsid01142, ebcdic-no-277+euro, ebcdic-dk-277+euro]

[1143, cp01143, ccsid01143, cp1143, ebcdic-fi-278+euro, ebcdic-se-278+euro]

[cp01144, ccsid01144, ebcdic-it-280+euro, cp1144, 1144]

[ccsid01145, ebcdic-es-284+euro, 1145, cp1145, cp01145]

[ebcdic-gb-285+euro, 1146, cp1146, cp01146, ccsid01146]

[cp1147, 1147, cp01147, ccsid01147, ebcdic-fr-277+euro]

[cp1148, ebcdic-international-500+euro, 1148, cp01148, ccsid01148]

[ebcdic-s-871+euro, 1149, cp1149, cp01149, ccsid01149]

[cp037, ibm037, ibm-037, csIBM037, ebcdic-cp-us, ebcdic-cp-ca, ebcdic-cp-nl, ebcdic-cp-wt, 037, cpibm37, cs-ebcdic-cp-wt, ibm-37, cs-ebcdic-cp-us, cs-ebcdic-cp-ca, cs-ebcdic-cp-nl]

[cp1026, ibm-1026, 1026, ibm1026]

[ibm-1047, 1047, cp1047]

[ibm-273, ibm273, 273, cp273]

[ibm277, 277, cp277, ibm-277]

[cp278, 278, ibm-278, ebcdic-cp-se, csIBM278, ibm278, ebcdic-sv]

[ibm280, 280, cp280, ibm-280]

[csIBM284, ibm-284, cpibm284, ibm284, 284, cp284]

[csIBM285, cp285, ebcdic-gb, ibm-285, cpibm285, ibm285, 285, ebcdic-cp-gb]

[ibm290, 290, cp290, EBCDIC-JP-kana, csIBM290, ibm-290]

[297, csIBM297, cp297, ibm297, ibm-297, cpibm297, ebcdic-cp-fr]

[ibm420, 420, cp420, csIBM420, ibm-420, ebcdic-cp-ar1]

[ebcdic-cp-he, csIBM424, ibm-424, ibm424, 424, cp424]

[ibm437, 437, ibm-437, cspc8codepage437, cp437, windows-437]

[ibm-500, ibm500, 500, ebcdic-cp-bh, ebcdic-cp-ch, csIBM500, cp500]

[ibm-775, ibm775, 775, cp775]

[cp850, cspc850multilingual, ibm850, 850, ibm-850]

[csPCp852, ibm-852, ibm852, 852, cp852]

[ibm855, 855, ibm-855, cp855, cspcp855]

[ibm857, 857, cp857, csIBM857, ibm-857]

[ibm860, 860, cp860, csIBM860, ibm-860]

[cp861, ibm861, 861, ibm-861, cp-is, csIBM861]

[csIBM862, cp862, ibm862, 862, cspc862latinhebrew, ibm-862]

[csIBM863, ibm-863, ibm863, 863, cp863]

[csIBM864, ibm-864, ibm864, 864, cp864]

[ibm-865, csIBM865, cp865, ibm865, 865]

[ibm866, 866, ibm-866, csIBM866, cp866]

[ibm868, 868, cp868, csIBM868, ibm-868, cp-ar]

[cp869, ibm869, 869, ibm-869, cp-gr, csIBM869]

[870, cp870, csIBM870, ibm-870, ibm870, ebcdic-cp-roece, ebcdic-cp-yu]

[ibm871, 871, cp871, ebcdic-cp-is, csIBM871, ibm-871]

[918, ibm-918, ebcdic-cp-ar2, cp918]

[csISO2022CN, ISO2022CN]

[csjisencoding, iso2022jp, jis_encoding, jis, csISO2022JP]

[csISO2022JP2, iso2022jp2]

[csISO2022KR, ISO2022KR]

[819, ISO8859-1, l1, ISO_8859-1:1987, ISO_8859-1, 8859_1, iso-ir-100, latin1, cp819, ISO8859_1, IBM819, ISO_8859_1, IBM-819, csISOLatin1]

[iso_8859-13, ISO8859-13, iso8859_13, 8859_13]

[ISO8859-15, LATIN0, ISO8859_15_FDIS, ISO8859_15, cp923, 8859_15, L9, ISO-8859-15, IBM923, csISOlatin9, ISO_8859-15, IBM-923, csISOlatin0, 923, LATIN9]

[ISO8859-2, ibm912, l2, ISO_8859-2, 8859_2, cp912, ISO_8859-2:1987, iso8859_2, iso-ir-101, latin2, 912, csISOLatin2, ibm-912]

[ISO8859-3, ibm913, 8859_3, l3, cp913, ISO_8859-3, iso8859_3, latin3, csISOLatin3, 913, ISO_8859-3:1988, ibm-913, iso-ir-109]

[8859_4, latin4, l4, cp914, ISO_8859-4:1988, ibm914, ISO_8859-4, iso-ir-110, iso8859_4, csISOLatin4, iso8859-4, 914, ibm-914]

[ISO_8859-5:1988, csISOLatinCyrillic, iso-ir-144, iso8859_5, cp915, 8859_5, ibm-915, ISO_8859-5, ibm915, 915, cyrillic, ISO8859-5]

[ASMO-708, 8859_6, iso8859_6, ISO_8859-6, csISOLatinArabic, ibm1089, arabic, ibm-1089, 1089, ECMA-114, iso-ir-127, ISO_8859-6:1987, ISO8859-6, cp1089]

[greek, 8859_7, greek8, ibm813, ISO_8859-7, iso8859_7, ELOT_928, cp813, ISO_8859-7:1987, sun_eu_greek, csISOLatinGreek, iso-ir-126, 813, iso8859-7, ECMA-118, ibm-813]

[8859_8, ISO_8859-8, ISO_8859-8:1988, cp916, iso-ir-138, ISO8859-8, hebrew, iso8859_8, ibm-916, csISOLatinHebrew, 916, ibm916]

[ibm-920, ISO_8859-9, 8859_9, ISO_8859-9:1989, ibm920, latin5, l5, iso8859_9, cp920, 920, iso-ir-148, ISO8859-9, csISOLatin5]

[JIS0201, csHalfWidthKatakana, X0201, JIS_X0201]

[JIS0212, iso-ir-159, x0212, jis_x0212-1990, csISO159JISX02121990]

[koi8_r, koi8, cskoi8r]

[koi8_u]

[shift_jis, x-sjis, sjis, shift-jis, ms_kanji, csShiftJIS]

[tis620, tis620.2533]

[ANSI_X3.4-1968, cp367, csASCII, iso-ir-6, ASCII, iso_646.irv:1983, ANSI_X3.4-1986, ascii7, default, ISO_646.irv:1991, ISO646-US, IBM367, 646, us]

[UTF_16, unicode, utf16, UnicodeBig]

[X-UTF-16BE, UTF_16BE, ISO-10646-UCS-2, UnicodeBigUnmarked]

[UnicodeLittleUnmarked, UTF_16LE, X-UTF-16LE]

[UTF_32, UTF32]

[X-UTF-32BE, UTF_32BE]

[X-UTF-32LE, UTF_32LE]

[unicode-1-1-utf-8, UTF8]

[cp1250, cp5346]

[cp5347, ansi-1251, cp1251]

[cp5348, cp1252]

[cp1253, cp5349]

[cp1254, cp5350]

[cp1255]

[cp1256]

[cp1257, cp5353]

[cp1258]

[MS932, windows-932, csWindows31J]

[Big5_HKSCS_2001, big5-hkscs-2001, big5hk-2001, big5-hkscs:unicode3.0, big5hkscs-2001]

[Big5_Solaris]

[COMPOUND_TEXT, x-compound-text, x11-compound_text]

[euc_jp_linux, euc-jp-linux]

[euctw, cns11643, EUC-TW, euc_tw]

[eucJP-open, EUC_JP_Solaris]

[ibm1006, ibm-1006, 1006, cp1006]

[ibm-1025, 1025, cp1025, ibm1025]

[ibm1046, ibm-1046, 1046, cp1046]

[ibm1097, ibm-1097, 1097, cp1097]

[ibm-1098, 1098, cp1098, ibm1098]

[ibm1112, ibm-1112, 1112, cp1112]

[cp1122, ibm1122, ibm-1122, 1122]

[ibm1123, ibm-1123, 1123, cp1123]

[ibm-1124, 1124, cp1124, ibm1124]

[cp1166, ibm1166, ibm-1166, 1166]

[cp1364, ibm1364, ibm-1364, 1364]

[cp1381, ibm-1381, 1381, ibm1381]

[ibm1383, ibm-1383, 1383, cp1383]

[cp300, ibm300, 300, ibm-300]

[33722, ibm-33722, cp33722, ibm33722, ibm-5050, ibm-33722_vascii_vpua]

[cp737, ibm737, 737, ibm-737]

[ibm833, cp833, ibm-833]

[ibm834, 834, cp834, ibm-834]

[ibm856, 856, cp856, ibm-856]

[ibm-874, ibm874, 874, cp874]

[ibm-875, ibm875, 875, cp875]

[ibm921, 921, ibm-921, cp921]

[ibm922, 922, cp922, ibm-922]

[ibm-930, ibm930, 930, cp930]

[ibm933, 933, cp933, ibm-933]

[cp935, ibm935, 935, ibm-935]

[ibm-937, ibm937, 937, cp937]

[ibm-939, cp939, ibm939, 939]

[ibm-942, cp942, ibm942, 942]

[ibm942C, cp942C, ibm-942C, 942C]

[ibm943, 943, ibm-943, cp943]

[943C, cp943C, ibm943C, ibm-943C]

[ibm-948, ibm948, 948, cp948]

[ibm-949, ibm949, 949, cp949]

[ibm949C, ibm-949C, cp949C, 949C]

[cp950, ibm950, 950, ibm-950]

[ibm-964, cp964, ibm964, 964]

[ibm970, ibm-eucKR, 970, cp970, ibm-970]

[ISCII91, iso-ir-153, iscii, ST_SEV_358-88, csISO153GOST1976874]

[ISO2022CN_CNS, ISO-2022-CN-CNS]

[ISO2022CN_GB, ISO-2022-CN-GB]

[iso-8859-11, iso8859_11]

[JIS0208, JIS_C6226-1983, iso-ir-87, x0208, JIS_X0208-1983, csISO87JISX0208]

[JISAutoDetect]

[ms1361, ksc5601_1992, johab, ksc5601-1992]

[MacArabic]

[MacCentralEurope]

[MacCroatian]

[MacCyrillic]

[MacDingbat]

[MacGreek]

[MacHebrew]

[MacIceland]

[MacRoman]

[MacRomania]

[MacSymbol]

[MacThai]

[MacTurkish]

[MacUkraine]

[]

[MS950_HKSCS]

[MS950_HKSCS_XP]

[ms936, ms_936]

[pck]

[]

[UnicodeLittle]

[UTF_32BE_BOM, UTF-32BE-BOM]

[UTF_32LE_BOM, UTF-32LE-BOM]

[cp50220, ms50220]

[cp50221, ms50221]

[ms-874, ms874, windows-874]

[windows949, ms949, windows-949, ms_949]

[ms950, windows-950]

[windows-iso2022jp]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html #别名–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#aliases--)