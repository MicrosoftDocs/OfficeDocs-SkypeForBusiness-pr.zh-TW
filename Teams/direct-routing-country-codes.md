---
title: 直接傳送國家/地區代碼
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 請閱讀本文，找出直接路由的媒體路徑國家/地區代碼。
ms.openlocfilehash: 8607b6720104e743243851ad7edac20811ecd29f
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572209"
---
# <a name="direct-routing-media-path-country-codes"></a>直接路由媒體路徑國家/地區代碼

選擇媒體的路由路徑時，[直接路由] 預設會根據會話邊界控制器（SBC）的公用 IP 位址來指派資料中心，且總是選取最接近 SBC 資料中心的路徑。

不過，在某些情況下，預設媒體路徑可能不是最佳的媒體路徑;例如，來自美國範圍的公用 IP 可能會指派給位於歐洲的 SBC。 

透過將-MediaRelayRoutingLocationOverride 參數與新的-CsOnlinePSTNGateway 和 Set CsOnlinePSTNGateway Cmdlet 結合使用，您就可以指定媒體流量的喜好區域。 例如，下列命令指定 [喜好] 區域為 [德國]：

CSOnlinePSTNGateway-身分識別 sbc1.contoso.com – MediaRelayRoutingLocationOverride DE 

請注意，如果通話記錄清楚指出媒體路徑中資料中心的預設指派不是使用最接近 SBC 資料中心的路徑，Microsoft 只建議設定此參數。 
 
## <a name="country-code-reference-table"></a>國家/地區代碼參考資料表

下表顯示-MediaRelayRoutingLocationOverride 參數的國家/地區代碼值：

| 國家         | 原始程式碼 
|-----------------|--------------------|
| 阿富汗     | AF |
| Aland 群島   | DPE-AX |
| 阿爾巴尼亞         | 亨茨維爾 |
| 阿爾及利亞         | DZ |
| 美屬薩摩亞  | 完工 |
| 安道爾         | 特定 |
| 安哥拉          | AO |
| Anguilla        | 亨茨維爾 |
| Antarctica      | AQ | 
| 安提瓜與巴布達 | 證券交易所 |
| 阿根廷       | AR |
| 亞美尼亞         | 為何 |
| Aruba           | AW |
| 澳大利亞       | X |
| 奧地利         | 的 |
| 亞塞拜然      | AZ |
| 巴哈馬         | BS |
| 巴林         | BH |
| 孟加拉國      | 過 |
| 島        | BB |
| 白俄羅斯         | 按照 |
| 比利時         | 不必 |
| 貝里斯          | BZ |
| Benin           | BJ |
| 百慕達         | BM |
| 不丹          | BT |
| 玻利維亞         | 標 |
| 波奈         | BQ |
| 波士尼亞和黑塞哥維那 | BA |
| 博茨瓦納        | 黑白 |
| Bouvet 島   | BV |
| 巴西          | < |
| 英屬印度洋領土 | 輸出 |
| 英屬維爾京群島 | VG |
| 汶萊          | BN-BD&PLATFORM |
| 保加利亞        | BG |
| 布吉納法索    | BF |
| 蒲隆地         | BI |
| 維德角      | 方便 |
| 柬埔寨        | KH |
| 喀麥隆        | ICD-10-CM |
| 加拿大          | 頒發 |
| 開曼群島  | KY-KG&PLATFORM |
| 中非共和國 | CF |
| Chad            | TD |
| 智利           | CL |
| 業務員           | CN |
| 聖誕島 | 陣列 |
| 科科斯（奇林）群島 | 單 |
| 哥倫比亞        | 條 |
| 群島         | 公里 |
| 剛果           | CG |
| 剛果（金）     | CD |
| 庫擁有群島    | CK |
| 哥斯大黎加      | CR |
| 象牙海岸   | CI |
| 克羅地亞         | 部門 |
| 古巴            | CU |
| Curacao         | 時針 |
| 賽普勒斯          | CY |
| Czechia         | CZ |
| 丹麥         | 深 |
| 吉布地        | DJ |
| Dominica        | 矩陣 |
| 多明尼加共和國 | 請 |
| 厄瓜多爾         | 成員國 |
| 埃及           | 例如 |
| 薩爾瓦多     | SV |
| 赤道幾內亞 | GQ |
| 省         | ER |
| 愛沙尼亞         | EE |
| Eswatini        | SZ |
| 埃塞俄比亞        | ET |
| 福克蘭群島 | FK |
| 法羅群島   | FO |
| 斐濟            | FJ |
| 芬蘭         | FI-FI&PLATFORM |
| 法國          | FR-FR |
| 法屬圭亞那   | GF |
| 法屬玻里尼西亞 | 公共 |
| 法屬南部領地 | SETTINGS |
| Gabon           | GA |
| 岡比亞          | 汽車 |
| 格魯吉亞         | 串聯 |
| 德國         | 卸載 |
| 加納           | GH |
| 直布羅陀       | GI |
| 希臘          | 凍結 |
| 東部       | 總帳 |
| 格瑞那達         | GD-GB&PLATFORM |
| Guadeloupe      | GP |
| 關島            | GU |
| 瓜地馬拉       | T |
| Guernsey        | GG |
| 新幾內亞          | GN |
| 幾內亞比索   | 網 |
| 蓋亞納          | GY |
| 海地           | 你好 |
| 赫德島與麥克唐納群島 | HM |
| 宏都拉斯        | HN |
| 香港特別行政區   | 香港 |
| 匈牙利         | HU |
| 冰島         | 是否 |
| 印度           | 中 |
| 印尼       | 標識號 |
| 伊朗            | 紅外光 |
| 伊拉克            | IQ |
| 愛爾蘭         | 亦 |
| 男人 Isle     | IM |
| 以色列          | 伊利諾斯 |
| 義大利           | 其 |
| 牙買加         | JM |
| 揚馬延       | XJ |
| 日本           | JA-JP |
| 澤西          | JE |
| 約旦          | JO |
| 哈薩克斯坦      | KZ |
| 肯雅           | KE |
| Kiribati        | KI |
| 韓國           | KR |
| Kosovo          | XK |
| 科威特          | KW |
| 吉爾吉斯斯坦      | 千克 |
| 老撾            | LA |
| 拉托維亞          | LV-LV&PLATFORM |
| 黎巴嫩         | LB |
| 賴索托         | 3 |
| 賴比瑞亞         | LR |
| 利比亞           | LY |
| 列支敦斯登   | 離子 |
| 立陶宛       | LT |
| 盧森堡      | LU |
| 澳門特別行政區       | MO |
| 島      | MG |
| 馬拉威          | MW |
| 馬來西亞        | 我的帳戶 |
| 群島        | MV |
| 馬里            | ML-IN&PLATFORM |
| 馬爾他           | 黑體 |
| 馬紹爾群島 | MH |
| 島      | .MQ |
| 茅利塔尼亞      | 先生 |
| 模里西斯       | MU |
| Mayotte         | YT |
| 墨西哥          | MX |
| Micronesia      | 電臺 |
| 摩爾多瓦         | 醫師 |
| 摩納哥          | MC |
| 蒙古        | MN |
| 蒙特內哥羅      | 我 |
| Montserrat      | 隸書 |
| 摩洛哥         | 購 |
| 莫三比克      | MZ |
| 緬甸         | 年 |
| 納米比亞         | NA |
| Nauru           | NR |
| 尼泊爾           | 站 |
| 荷蘭     | NL-NL&PLATFORM |
| 新赫里多尼亞   | NC |
| 紐西蘭     | NZ |
| 尼加拉瓜       | NI |
| 尼日爾           | 左下 |
| 奈及利亞         | NG |
| Niue            | NU |
| 諾福克島  | NF-E |
| 朝鮮     | KP |
| 北馬其頓共和國 | MK |
| 北馬里安納群島 | 站 |
| 挪威          | 不 |
| 阿曼            | 模型 |
| 巴基斯坦        | 主鍵 |
| Palau           | PW |
| 巴勒斯坦權力機構 | PS-AF&PLATFORM |
| 巴拿馬          | 賓夕法尼亞 |
| 巴布亞紐幾內亞 | PG |
| 巴拉圭        | .PY |
| 秘魯            | PE |
| 菲律賓     | 電話 |
| 皮特凱恩群島 | PN |
| 波蘭          | 損益 |
| 葡萄牙        | PT |
| 波多黎各     | / |
| 卡塔爾           | QA |
| 留尼旺島         | 重新 |
| 羅馬尼亞         | RO |
| 俄羅斯          | RU |
| 盧安達          | 燒錄 |
| 沙巴            | X |
| 聖 Barthelemy | BL |
| 聖基茨與尼維斯 | KN |
| 聖露西亞     | LC-FC |
| 聖聖馬丁    | 大型機 |
| 聖匹島 | 經理 |
| 聖文森特和格林納丁斯群島St.Vincent | VC |
| 美屬薩摩亞           | WS |
| 聖馬利諾      | 購買 |
| 聖多美聖多美及普林西比島 | 短期 |
| 沙烏地阿拉伯    | 南美洲 |
| 塞內加爾         | SN.EXE |
| 塞爾維亞          | SUPPORT.OFFICE.COM/ARTICLE/255A7D5E-92B0-47BC-8AB8-51DAD28414C2 |
| 群島      | SC |
| 塞拉里昂    | SL | 
| 新加坡       | SG |
| 聖尤斯特歇斯  | XE |
| 聖聖馬丁    | S |
| 斯洛伐克        | SK-SK&PLATFORM |
| 斯洛維尼亞        | SL |
| 索羅門群島 | SB |
| 索馬里         | 那 |
| 南非    | ZA |
| 南喬治亞與南桑威奇群島 | 全球 |
| 南蘇丹     | SS |
| 西班牙           | ES |
| 斯里蘭卡       | LK |
| 聖赫勒拿、阿森松、特裡斯坦達 da 尼亞 | SH |
| 蘇丹           | SD |
| 蘇利南        | SR |
| 斯瓦爾巴        | SJ |
| 瑞典          | 本身 |
| 瑞士     | 48 |
| 敘利亞           | SY |
| 臺灣          | 華文 |
| 塔吉克斯坦      | TJ |
| 聯合        | TZ |
| 泰國        | K |
| 東帝汶-Leste     | TL |
| Togo            | TG |
| Tokelau         | TK-TM&PLATFORM |
| 語           | 自 |
| 特立尼達和多巴哥 | TT-RU&PLATFORM |
| 突尼斯         | TN-ZA&PLATFORM |
| 土耳其          | TR |
| 土庫曼斯坦    | 153 |
| 特克斯與凱科斯群島 | 目錄 |
| Tuvalu          | 播放 |
| 美屬離島 | 嗯 |
| 美屬維爾京群島 | 六 |
| 烏干達          | UG-CN&PLATFORM |
| 烏克蘭         | UA |
| 阿拉伯聯合大公國 | AE |
| 英國  | GB |
| 美國   | 一下 |
| 烏拉圭         | UY |
| 烏茲別克斯坦      | UZ |
| 瓦努阿圖         | VU |
| 梵蒂岡城    | VA |
| 委內瑞拉       | 曾 |
| 民主         | VN |
| 瓦利斯與富圖納 | WF |
| 葉門           | YE |
| 尚比亞          | ZM |
| 辛巴威        | ZW |

