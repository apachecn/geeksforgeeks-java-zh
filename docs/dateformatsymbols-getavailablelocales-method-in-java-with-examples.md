# 日期格式符号 getAvailableLocales()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-getavailablelocales-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-getavailablelocales-method-in-java-with-examples/)

Java 中**日期格式符号**类的 **getAvailableLocales()** 方法用于返回该类的 getInstance 方法的本地化日期格式符号实例中可用的所有区域设置的数组。

**语法:**
公共静态 Locale[] getAvailableLocales()

**参数:**该方法不取任何参数。

返回值:该方法返回本地化日期格式符号实例可用的所有区域设置的数组。

下面的程序说明了 getAvailableLocales()方法的工作原理。
**例 1:**

```
// Java code to illustrate
// getAvailableLocales() method

import java.text.*;
import java.util.*;

public class Main {

    public static void main(String args[])
    {

        // Get the available locales
        Locale loc_list[]
            = DateFormatSymbols.getAvailableLocales();

        // Print the locales
        // along with display names
        System.out.println(
            "DateFormatSymbols Locales"
            + " :: Display names\n");

        for (int count = 0;
             count < loc_list.length;
             count++) {

            System.out.println(
                loc_list[count].toString()
                + " :: "
                + loc_list[count]
                      .getDisplayName());
        }

        for (int count = 0;
             count < loc_list.length; count++) {
            System.out.println(
                loc_list[count]
                    .getDisplayName(Locale.ITALY));
        }
    }
}
```

**Output:**

```
DateFormatSymbols Locales :: Display names

 :: 
ar_AE :: Arabic (United Arab Emirates)
ar_JO :: Arabic (Jordan)
ar_SY :: Arabic (Syria)
hr_HR :: Croatian (Croatia)
fr_BE :: French (Belgium)
es_PA :: Spanish (Panama)
mt_MT :: Maltese (Malta)
es_VE :: Spanish (Venezuela)
bg :: Bulgarian
zh_TW :: Chinese (Taiwan)
it :: Italian
ko :: Korean
uk :: Ukrainian
lv :: Latvian
da_DK :: Danish (Denmark)
es_PR :: Spanish (Puerto Rico)
vi_VN :: Vietnamese (Vietnam)
en_US :: English (United States)
sr_ME :: Serbian (Montenegro)
sv_SE :: Swedish (Sweden)
es_BO :: Spanish (Bolivia)
en_SG :: English (Singapore)
ar_BH :: Arabic (Bahrain)
pt :: Portuguese
ar_SA :: Arabic (Saudi Arabia)
sk :: Slovak
ar_YE :: Arabic (Yemen)
hi_IN :: Hindi (India)
ga :: Irish
en_MT :: English (Malta)
fi_FI :: Finnish (Finland)
et :: Estonian
sv :: Swedish
cs :: Czech
sr_BA_#Latn :: Serbian (Latin, Bosnia and Herzegovina)
el :: Greek
uk_UA :: Ukrainian (Ukraine)
hu :: Hungarian
fr_CH :: French (Switzerland)
in :: Indonesian
es_AR :: Spanish (Argentina)
ar_EG :: Arabic (Egypt)
ja_JP_JP_#u-ca-japanese :: Japanese (Japan, JP)
es_SV :: Spanish (El Salvador)
pt_BR :: Portuguese (Brazil)
be :: Belarusian
is_IS :: Icelandic (Iceland)
cs_CZ :: Czech (Czech Republic)
es :: Spanish
pl_PL :: Polish (Poland)
tr :: Turkish
ca_ES :: Catalan (Spain)
sr_CS :: Serbian (Serbia and Montenegro)
ms_MY :: Malay (Malaysia)
hr :: Croatian
lt :: Lithuanian
es_ES :: Spanish (Spain)
es_CO :: Spanish (Colombia)
bg_BG :: Bulgarian (Bulgaria)
sq :: Albanian
fr :: French
ja :: Japanese
sr_BA :: Serbian (Bosnia and Herzegovina)
is :: Icelandic
es_PY :: Spanish (Paraguay)
de :: German
es_EC :: Spanish (Ecuador)
es_US :: Spanish (United States)
ar_SD :: Arabic (Sudan)
en :: English
ro_RO :: Romanian (Romania)
en_PH :: English (Philippines)
ca :: Catalan
ar_TN :: Arabic (Tunisia)
sr_ME_#Latn :: Serbian (Latin, Montenegro)
es_GT :: Spanish (Guatemala)
sl :: Slovenian
ko_KR :: Korean (South Korea)
el_CY :: Greek (Cyprus)
es_MX :: Spanish (Mexico)
ru_RU :: Russian (Russia)
es_HN :: Spanish (Honduras)
zh_HK :: Chinese (Hong Kong)
no_NO_NY :: Norwegian (Norway, Nynorsk)
hu_HU :: Hungarian (Hungary)
th_TH :: Thai (Thailand)
ar_IQ :: Arabic (Iraq)
es_CL :: Spanish (Chile)
fi :: Finnish
ar_MA :: Arabic (Morocco)
ga_IE :: Irish (Ireland)
mk :: Macedonian
tr_TR :: Turkish (Turkey)
et_EE :: Estonian (Estonia)
ar_QA :: Arabic (Qatar)
sr__#Latn :: Serbian (Latin)
pt_PT :: Portuguese (Portugal)
fr_LU :: French (Luxembourg)
ar_OM :: Arabic (Oman)
th :: Thai
sq_AL :: Albanian (Albania)
es_DO :: Spanish (Dominican Republic)
es_CU :: Spanish (Cuba)
ar :: Arabic
ru :: Russian
en_NZ :: English (New Zealand)
sr_RS :: Serbian (Serbia)
de_CH :: German (Switzerland)
es_UY :: Spanish (Uruguay)
ms :: Malay
el_GR :: Greek (Greece)
iw_IL :: Hebrew (Israel)
en_ZA :: English (South Africa)
th_TH_TH_#u-nu-thai :: Thai (Thailand, TH)
hi :: Hindi
fr_FR :: French (France)
de_AT :: German (Austria)
nl :: Dutch
no_NO :: Norwegian (Norway)
en_AU :: English (Australia)
vi :: Vietnamese
nl_NL :: Dutch (Netherlands)
fr_CA :: French (Canada)
lv_LV :: Latvian (Latvia)
de_LU :: German (Luxembourg)
es_CR :: Spanish (Costa Rica)
ar_KW :: Arabic (Kuwait)
sr :: Serbian
ar_LY :: Arabic (Libya)
mt :: Maltese
it_CH :: Italian (Switzerland)
da :: Danish
de_DE :: German (Germany)
ar_DZ :: Arabic (Algeria)
sk_SK :: Slovak (Slovakia)
lt_LT :: Lithuanian (Lithuania)
it_IT :: Italian (Italy)
en_IE :: English (Ireland)
zh_SG :: Chinese (Singapore)
ro :: Romanian
en_CA :: English (Canada)
nl_BE :: Dutch (Belgium)
no :: Norwegian
pl :: Polish
zh_CN :: Chinese (China)
ja_JP :: Japanese (Japan)
de_GR :: German (Greece)
sr_RS_#Latn :: Serbian (Latin, Serbia)
iw :: Hebrew
en_IN :: English (India)
ar_LB :: Arabic (Lebanon)
es_NI :: Spanish (Nicaragua)
zh :: Chinese
mk_MK :: Macedonian (Macedonia)
be_BY :: Belarusian (Belarus)
sl_SI :: Slovenian (Slovenia)
es_PE :: Spanish (Peru)
in_ID :: Indonesian (Indonesia)
en_GB :: English (United Kingdom)

arabo (Emirati Arabi Uniti)
arabo (Giordania)
arabo (Siria)
croato (Croazia)
francese (Belgio)
spagnolo (Panama)
maltese (Malta)
spagnolo (Venezuela)
bulgaro
cinese (Taiwan)
italiano
coreano
ucraino
lettone
danese (Danimarca)
spagnolo (Puerto Rico)
vietnamita (Vietnam)
inglese (Stati Uniti)
serbo (Montenegro)
svedese (Svezia)
spagnolo (Bolivia)
inglese (Singapore)
arabo (Bahrain)
portoghese
arabo (Arabia Saudita)
slovacco
arabo (Yemen)
hindi (India)
irlandese
inglese (Malta)
finlandese (Finlandia)
estone
svedese
ceco
serbo (Latino, Bosnia-Erzegovina)
greco
ucraino (Ucraina)
ungherese
francese (Svizzera)
indonesiano
spagnolo (Argentina)
arabo (Egitto)
giapponese (Giappone, JP)
spagnolo (El Salvador)
portoghese (Brasile)
bielorusso
islandese (Islanda)
ceco (Repubblica Ceca)
spagnolo
polacco (Polonia)
turco
catalano (Spagna)
serbo (Serbia e Montenegro)
malese (Malaysia)
croato
lituano
spagnolo (Spagna)
spagnolo (Colombia)
bulgaro (Bulgaria)
albanese
francese
giapponese
serbo (Bosnia-Erzegovina)
islandese
spagnolo (Paraguay)
tedesco
spagnolo (Ecuador)
spagnolo (Stati Uniti)
arabo (Sudan)
inglese
rumeno (Romania)
inglese (Filippine)
catalano
arabo (Tunisia)
serbo (Latino, Montenegro)
spagnolo (Guatemala)
sloveno
coreano (Corea del Sud)
greco (Cipro)
spagnolo (Messico)
russo (Russia)
spagnolo (Honduras)
cinese (Hong Kong)
norvegese (Norvegia, Nynorsk)
ungherese (Ungheria)
thai (Thailandia)
arabo (Iraq)
spagnolo (Cile)
finlandese
arabo (Marocco)
irlandese (Irlanda)
macedone
turco (Turchia)
estone (Estonia)
arabo (Qatar)
serbo (Latino)
portoghese (Portogallo)
francese (Lussemburgo)
arabo (Oman)DateFormatSymbols
thai
albanese (Albania)
spagnolo (Repubblica Dominicana)
spagnolo (Cuba)
arabo
russo
inglese (Nuova Zelanda)
serbo (Serbia)
tedesco (Svizzera)
spagnolo (Uruguay)
malese
greco (Grecia)
ebraico (Israele)
inglese (Sudafrica)
thai (Thailandia, TH)
hindi
francese (Francia)
tedesco (Austria)
neerlandese
norvegese (Norvegia)
inglese (Australia)
vietnamita
neerlandese (Paesi Bassi)
francese (Canada)
lettone (Lettonia)
tedesco (Lussemburgo)
spagnolo (Costa Rica)
arabo (Kuwait)
serbo
arabo (Libia)
maltese
italiano (Svizzera)
danese
tedesco (Germania)
arabo (Algeria)
slovacco (Slovacchia)
lituano (Lituania)
italiano (Italia)
inglese (Irlanda)
cinese (Singapore)
rumeno
inglese (Canada)
neerlandese (Belgio)
norvegese
polacco
cinese (Cina)
giapponese (Giappone)
tedesco (Grecia)
serbo (Latino, Serbia)
ebraico
inglese (India)
arabo (Libano)
spagnolo (Nicaragua)
cinese
macedone (Macedonia)
bielorusso (Bielorussia)
sloveno (Slovenia)
spagnolo (Per?)
indonesiano (Indonesia)
inglese (Regno Unito)

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/dateformatsymbols . html # getAvailableLocales–](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#getAvailableLocales--)