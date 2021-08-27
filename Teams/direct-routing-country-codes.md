---
title: 直接路由國家/地區代碼
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 請閱讀本文，找出直接路由的媒體路徑國家/地區代碼，以便選取最佳的媒體路徑。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36124a8aadc94bfd73ffd195ec8ee0a2acf0c2a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582347"
---
# <a name="direct-routing-media-path-country-codes"></a>直接路由媒體路徑國家/地區代碼

選擇媒體的路由路徑時，根據預設，直接路由一定根據會話邊界控制器 (SBC) 的公用 IP 位址指派資料中心，並一直選取最接近 SBC 資料中心的路徑。

不過，在某些情況下，預設媒體路徑可能並非最佳媒體路徑;例如，美國範圍的公用 IP 可能會指派給位於歐洲的 SBC。 

使用 -MediaRelayRoutingLocationOverride 參數搭配 New-CsOnlinePSTNGateway 和 Set-CsOnlinePSTNGateway Cmdlet，您可以指定媒體流量的偏好區域。 例如，下列命令指定偏好的地區為德國：

Set-CSOnlinePSTNGateway -身分識別 sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

請注意，只有在通話記錄清楚指出媒體路徑資料中心的預設指派不使用最接近 SBC 資料中心的路徑時，Microsoft 才建議設定此參數。 

> [!NOTE]
> MediaRelayRoutingLocationOverride 參數是保留用於受管理的電信公司。
 
## <a name="country-code-reference-table"></a>國碼參照資料表

下表顯示 -MediaRelayRoutingLocationOverride 參數的國家/地區代碼值：

| 國家         | 代碼 
|-----------------|--------------------|
| 阿富汗     | AF |
| 阿蘭群島   | 斧頭 |
| 阿爾巴尼亞         | 鋁 |
| 阿爾及利亞         | DZ |
| 美屬薩摩亞  | AS |
| 安道爾         | 廣告 |
| 安哥拉          | 坳 |
| 安奎拉        | 艾 |
| 南極洲      | AQ | 
| 安地卡及巴布達 | 銀 |
| 阿根廷       | AR |
| 亞美尼亞         | 是 |
| 荷屬阿魯巴           | AW |
| 澳洲       | 金 |
| 奧地利         | 在 |
| 亞塞拜然      | AZ |
| 巴哈馬         | BS |
| 巴林         | BH |
| 孟加拉      | 屋宇 署 |
| 巴貝多        | BB |
| 白俄羅斯         | BY |
| 比利時         | BE |
| 貝里斯          | BZ |
| 貝南           | 北京 |
| 百慕達         | BM |
| 不丹          | BT |
| 玻利維亞         | 博 |
| 波奈         | BQ |
| 波士尼亞與赫塞哥維納 | 八 |
| 波札那        | BW |
| 布維島   | BV |
| 巴西          | BR |
| 英屬印度洋地區 | IO |
| 英屬維爾京群島 | VG |
| 汶萊          | 億 |
| 保加利亞        | BG |
| 布吉納法索    | 高爐 |
| 蒲隆地         | BI |
| 卡波維德      | 簡歷 |
| 柬埔寨        | KH |
| 喀麥隆        | 釐米 |
| 加拿大          | 約 |
| 開曼群島  | 肯塔基州 |
| 中非共和國 | CF |
| 乍得            | TD |
| 智利           | CL |
| 中國           | 快遞 之 家 |
| 耶誕節島 | 殘雪 |
| 科科斯 (基林) 群島 | CC |
| 哥倫比亞        | CO |
| 葛摩         | 公里 |
| 剛果           | CG |
| 剛果 (剛果民主共和國)      | CD |
| 科克群島    | CK |
| 哥斯大黎加      | 鉻 |
| 象牙海岸   | 詞 |
| 克羅埃西亞         | 人力資源 |
| 古巴            | 銅 |
| 古拉梳島         | 連續 |
| 賽普勒斯          | CY |
| 捷克文         | CZ |
| 丹麥         | DK |
| 吉布地        | DJ |
| 多米尼克        | DM |
| 多明尼加 | DO |
| 厄瓜多         | 電子商務 |
| 埃及           | EG |
| 薩爾瓦多     | SV |
| 赤道幾內亞 | GQ |
| 厄利垂亞         | 二 |
| 愛沙尼亞         | EE |
| Eswatini        | 深圳 |
| 衣索比亞        | ET |
| 福克蘭群島 | FK |
| 法羅群島   | 佛 |
| 斐濟            | 福建 |
| 芬蘭         | FI |
| 法國          | FR |
| 法屬圭亞那   | 女朋友 |
| 法屬玻里尼西亞 | PF |
| 法屬南部地區 | TF |
| 加蓬           | GA |
| 岡比亞          | 通用 汽車 |
| 喬治亞         | 通用 電氣 |
| 德國         | 德 |
| 迦納           | GH |
| 直布羅陀       | GI |
| 希臘          | GR |
| 格陵蘭       | GL |
| 格瑞那達         | GD |
| 瓜地洛普      | GP |
| 關島            | 古 |
| 瓜地馬拉       | 燃氣輪機 |
| 格恩西島        | GG |
| 幾內亞          | GN |
| Guinea-Bissau   | GW |
| 蓋亞那          | GY |
| 海地           | 你好 |
| 赫德島和麥當勞群島 | HM |
| 宏都拉斯        | HN |
| 香港特別行政區   | 香港 |
| 匈牙利         | 胡 |
| 冰島         | 是 |
| 印度           | IN |
| 印尼       | ID |
| 伊朗            | 紅外 |
| 伊拉克            | 智商 |
| 愛爾蘭         | 即 |
| 曼城島     | IM |
| 以色列          | I L |
| 義大利           | IT |
| 牙買加         | JM |
| Jan Mayen       | XJ |
| 日本           | JP |
| 球衣          | 流行性乙型腦炎 |
| 約旦          | 喬 |
| 哈薩克      | KZ |
| 肯亞           | 科 |
| 吉里巴斯        | K I |
| 韓國           | KR |
| 科索沃          | XK |
| 科威特          | 千瓦 |
| 吉爾吉斯      | KG |
| 老撾            | 洛杉磯 |
| 拉脫維亞          | 低壓 |
| 黎巴嫩         | 磅 |
| 賴索托         | LS |
| 賴比瑞亞         | LR |
| 利比亞           | LY |
| 列支敦斯登   | 李 |
| 立陶宛       | LT |
| 盧森堡      | 路 |
| 澳門特別行政區       | 莫 |
| 馬達加斯加      | 鎂 |
| 馬拉威          | M W |
| 馬來西亞        | 我 |
| 馬爾地夫        | MV |
| 馬利            | ML |
| 馬爾他           | MT |
| 馬紹爾群島 | MH |
| 馬丁尼克      | MQ |
| 茅利塔尼亞      | 先生 |
| 模里西斯       | 木 |
| 馬約特島         | 劉日東 |
| 墨西哥          | MX |
| 密克羅尼西亞      | 調頻 |
| 摩爾多瓦         | MD |
| 摩納哥          | MC |
| 蒙古        | 錳 |
| 蒙特內哥羅      | 我 |
| 蒙哲臘      | 女士 |
| 摩洛哥         | 馬 |
| 莫三比克      | MZ |
| 緬甸         | 毫米 |
| 納米比亞         | 那 |
| 瑙魯           | 星期日 |
| 尼泊爾           | NP |
| 荷蘭     | 吧 |
| 新喀里多尼亞   | 數控 |
| 紐西蘭     | 紐西蘭 |
| 尼加拉瓜       | 鎳 |
| 尼日           | NE |
| 奈及利亞         | 議員 |
| 紐埃            | 女 |
| Norfolk Island  | NF |
| 朝鮮     | KP |
| 北馬其頓 | MK |
| 北馬利安納群島 | NP |
| 挪威          | 不 |
| 阿曼            | OM |
| 巴基斯坦        | PK |
| 帛琉           | PW |
| 巴勒斯坦民族權力機構 | PS |
| 巴拿馬          | PA |
| 巴布亞紐幾內亞 | PG |
| 巴拉圭        | PY |
| 秘魯            | 體育 |
| 菲律賓     | PH |
| 皮特凱恩群島 | PN |
| 波蘭          | PL |
| 葡萄牙        | 鉑 |
| 波多黎各     | PR |
| 卡達           | QA |
| 留尼汪         | RE |
| 羅馬尼亞         | RO |
| 俄羅斯          | 如 |
| 盧安達          | 烏爾曼 |
| 薩巴            | XS |
| 聖巴塞萊梅 | BL |
| 聖克里斯多福及尼維斯 | KN |
| 聖露西亞     | 立法會 |
| 聖馬德堡    | MF |
| 聖皮埃和密克隆 | 下午 |
| 聖文森及格瑞那丁 | VC |
| 薩摩亞           | WS |
| 聖馬利諾      | SM |
| 聖多美和 Principe | 聖 |
| 沙烏地阿拉伯    | SA |
| 塞內加爾         | 錫 |
| 塞爾維亞          | RS |
| 塞席爾      | SC |
| 塞拉里昂    | SL | 
| 新加坡       | S G |
| Sint Eustatius  | 氙氣 |
| Sint Maarten    | SX |
| 斯洛伐克        | SK |
| 斯洛維尼亞        | SL |
| 索羅門群島 | 某人 |
| 索馬里         | 所以 |
| 南非    | 咱 |
| 南喬治亞和南沙威奇群島 | GS |
| 南蘇丹     | SS |
| 西班牙           | ES |
| 斯里蘭卡       | 路 |
| 聖赫勒拿、阿森松、特裡斯坦達庫尼亞 | SH |
| 蘇丹           | SD |
| 蘇利南        | 鍶 |
| 斯瓦爾巴特        | SJ |
| 瑞典          | SE |
| 瑞士     | CH |
| 敘利亞           | SY |
| 台灣          | TW |
| 塔吉克      | TJ |
| 坦尚尼亞        | TZ |
| 泰國        | TH |
| Timor-Leste     | TL |
| 多哥            | TG |
| 烏裡達         | TK |
| 湯加           | 自 |
| 千里達及托巴哥 | TT |
| 突尼西亞         | TN |
| 土耳其          | TR |
| 土庫曼    | TM |
| 土克斯和凱科斯群島 | TC |
| 吐瓦魯          | 電視 |
| 美國外島 | UM |
| 美屬維爾京群島 | 六 |
| 烏干達          | UG |
| 烏克蘭         | UA |
| 阿拉伯聯合大公國 | AE |
| 英國  | G B |
| 美國   | 我們 |
| 烏拉圭         | UY |
| 烏茲別克      | UZ |
| 瓦努阿圖         | VU |
| 梵蒂岡城    | VA |
| 委內瑞拉       | VE |
| 越南         | VN |
| 瓦利斯和富圖納 | WF |
| 葉門           | 你們 |
| 尚比亞          | ZM |
| 辛巴威        | ZW |
