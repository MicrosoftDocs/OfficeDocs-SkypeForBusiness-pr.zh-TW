---
title: 直接路由國碼
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
description: 請閱讀本文以找出直接路由的媒體路徑國碼，以便選取最佳媒體路徑。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a70dad128987a5fb0df639984be07b623f9ff425
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812670"
---
# <a name="direct-routing-media-path-country-codes"></a>直接路由媒體路徑國碼

選擇媒體的路由路徑時，根據預設，直接路由一律會根據會話框線控制器的公用 IP 位址指派資料中心 (SBC) ，並且一律選取最接近 SBC 資料中心的路徑。

不過，在某些情況下，預設媒體路徑可能不是最佳媒體路徑;例如，來自美國範圍的公用 IP 可能會指派給位於歐洲的 SBC。 

您可以將 -MediaRelayRoutingLocationOverride 參數搭配New-CsOnlinePSTNGateway和Set-CsOnlinePSTNGateway Cmdlet 使用，為媒體流量指定慣用區域。 例如，下列命令指定慣用地區為德國：

Set-CSOnlinePSTNGateway - 身分識別 sbc1.contoso.com – MediaRelayRoutingLocationOverride DE 

請注意，只有在通話記錄檔明確指出媒體路徑的資料中心預設指派並未使用最接近 SBC 資料中心的路徑時，Microsoft 才建議設定此參數。 
 
## <a name="country-code-reference-table"></a>國碼參照表格

下表顯示 -MediaRelayRoutingLocationOverride 參數的國家/地區代碼值：

| 國家         | 代碼 
|-----------------|--------------------|
| 阿富汗     | Af |
| Aland Islands   | 斧頭 |
| 阿爾巴尼亞         | 鋁 |
| 阿爾及利亞         | Dz |
| 美屬薩摩亞  | AS |
| 安道爾         | 廣告 |
| 安哥拉          | 坳 |
| 安奎拉        | 艾 |
| 南極洲      | Aq | 
| 安地卡及巴布達 | 銀 |
| 阿根廷       | Ar |
| 亞美尼亞         | 是 |
| 荷屬阿魯巴           | AW |
| 澳洲       | 金 |
| 奧地利         | 在 |
| 亞塞拜然      | Az |
| 巴哈馬         | Bs |
| 巴林         | Bh |
| 孟加拉      | 屋宇 署 |
| 巴貝多        | Bb |
| 白俄羅斯         | BY |
| 比利時         | BE |
| 貝里斯          | Bz |
| 貝南           | 北京 |
| 百慕達         | Bm |
| 不丹          | Bt |
| 玻利維亞         | 博 |
| 波奈         | BQ |
| 波士尼亞與赫塞哥維納 | 八 |
| 波札那        | Bw |
| 布威島   | Bv |
| 巴西          | Br |
| 英屬印度洋領土 | Io |
| 英屬維爾京群島 | Vg |
| 汶萊          | 億 |
| 保加利亞        | Bg |
| 布吉納法索    | 高爐 |
| 蒲隆地         | BI |
| 維德角      | 簡歷 |
| 柬埔寨        | Kh |
| 喀麥隆        | 釐米 |
| 加拿大          | 約 |
| 開曼群島  | 肯塔基州 |
| 中非共和國 | Cf |
| 乍得            | Td |
| 智利           | Cl |
| 中國           | 快遞 之 家 |
| 聖誕島 | 殘雪 |
| 科克斯 (基靈) 群島 | Cc |
| 哥倫比亞        | CO |
| 葛摩         | 公里 |
| 剛果           | Cg |
|  (DRC)      | Cd |
| 科克群島    | Ck |
| 哥斯大黎加      | 鉻 |
| Cote d'Semiconductor   | 詞 |
| 克羅埃西亞         | 人力資源 |
| 古巴            | 銅 |
| 古拉梳島         | 連續 |
| 賽普勒斯          | CY |
| 捷克         | Cz |
| 丹麥         | Dk |
| 吉布地        | Dj |
| 多米尼克        | Dm |
| 多明尼加 | DO |
| 厄瓜多         | 電子商務 |
| 埃及           | EG |
| 薩爾瓦多     | Sv |
| 赤道幾內亞 | Gq |
| 厄利垂亞         | 二 |
| 愛沙尼亞         | Ee |
| Eswatini        | 深圳 |
| 衣索比亞        | Et |
| 福蘭群島 | Fk |
| 法羅群島   | 佛 |
| 斐濟            | 福建 |
| 芬蘭         | FI |
| 法國          | FR |
| 法屬圭亞那   | 女朋友 |
| 法屬玻里尼西亞 | PF |
| 法屬南半球領土 | Tf |
| 加蓬           | Ga |
| 岡比亞          | 通用 汽車 |
| 喬治亞         | 通用 電氣 |
| 德國         | 德 |
| 迦納           | Gh |
| 直布羅陀       | Gi |
| 希臘          | Gr |
| 格陵蘭       | Gl |
| 格瑞那達         | Gd |
| 瓜地洛普      | Gp |
| 關島            | 古 |
| 瓜地馬拉       | 燃氣輪機 |
| 格恩西島        | Gg |
| 幾內亞          | Gn |
| Guinea-Bissau   | Gw |
| 蓋亞那          | Gy |
| 海地           | 你好 |
| Heard Island 和 Mc Island Islands | HM |
| 宏都拉斯        | Hn |
| 香港特別行政區   | 香港 |
| 匈牙利         | 胡 |
| 冰島         | 是 |
| 印度           | IN |
| 印尼       | Id |
| 伊朗            | 紅外 |
| 伊拉克            | 智商 |
| 愛爾蘭         | 即 |
| 曼城島     | IM |
| 以色列          | I l |
| 義大利           | IT |
| 牙買加         | Jm |
| Jan Mayen       | Xj |
| 日本           | Jp |
| 球衣          | 流行性乙型腦炎 |
| 約旦          | 喬 |
| 哈薩克      | KZ |
| 肯亞           | 科 |
| 吉里巴斯        | K i |
| 韓國           | KR |
| 科索沃          | Xk |
| 科威特          | 千瓦 |
| 吉爾吉斯      | KG |
| 老撾            | 洛杉磯 |
| 拉脫維亞          | 低壓 |
| 黎巴嫩         | 磅 |
| 賴索托         | LS |
| 賴比瑞亞         | Lr |
| 利比亞           | LY |
| 列支敦斯登   | 李 |
| 立陶宛       | LT |
| 盧森堡      | 路 |
| 澳門特別行政區       | 莫 |
| 馬達加斯加      | 鎂 |
| 馬拉威          | M w |
| 馬來西亞        | 我 |
| 馬爾地夫        | Mv |
| 馬利            | 毫升 |
| 馬爾他           | MT |
| 馬紹爾群島 | MH |
| 馬丁尼克      | Mq |
| 茅利塔尼亞      | 先生 |
| 模里西斯       | 木 |
| 馬約特島         | 劉日東 |
| 墨西哥          | Mx |
| 密克羅尼西亞      | 調頻 |
| 摩爾多瓦         | Md |
| 摩納哥          | Mc |
| 蒙古        | 錳 |
| 蒙特內哥羅      | 我 |
| 蒙哲臘      | 女士 |
| 摩洛哥         | 馬 |
| 莫三比克      | Mz |
| 緬甸         | 毫米 |
| 納米比亞         | 那 |
| 瑙魯           | 星期日 |
| 尼泊爾           | Np |
| 荷蘭     | 吧 |
| 新喀里多尼亞   | 數控 |
| 紐西蘭     | 紐西蘭 |
| 尼加拉瓜       | 鎳 |
| 尼日           | NE |
| 奈及利亞         | 議員 |
| 紐埃            | 女 |
| 諾裡安島  | Nf |
| 朝鮮     | Kp |
| 北馬其頓 | Mk |
| 北馬利安納群島 | Np |
| 挪威          | 不 |
| 阿曼            | Om |
| 巴基斯坦        | PK |
| 帛琉           | PW |
| 巴勒斯坦民族權力機構 | PS |
| 巴拿馬          | Pa |
| 巴布亞紐幾內亞 | Pg |
| 巴拉圭        | PY |
| 秘魯            | 體育 |
| 菲律賓     | Ph |
| 皮托文群島 | Pn |
| 波蘭          | Pl |
| 葡萄牙        | 鉑 |
| 波多黎各     | PR |
| 卡達           | Qa |
| 留尼汪         | RE |
| 羅馬尼亞         | Ro |
| 俄羅斯          | 如 |
| 盧安達          | 烏爾曼 |
| 薩巴            | Xs |
| 聖巴瑟米 | BL |
| 聖克里斯多福及尼維斯 | KN |
| 聖露西亞     | 立法會 |
| 法屬聖馬丁    | Mf |
| 聖皮埃和密克隆群島 | 下午 |
| 聖文森及格瑞那丁 | Vc |
| 薩摩亞           | Ws |
| 聖馬利諾      | Sm |
| 聖多美及普林西比 | 聖 |
| 沙烏地阿拉伯    | Sa |
| 塞內加爾         | 錫 |
| 塞爾維亞          | Rs |
| 塞席爾      | Sc |
| 塞拉里昂    | Sl | 
| 新加坡       | S g |
| 聖歐達修斯  | 氙氣 |
| 聖馬丁    | Sx |
| 斯洛伐克        | Sk |
| 斯洛維尼亞        | Sl |
| 索羅門群島 | 某人 |
| 索馬里         | 所以 |
| 南非    | 咱 |
| 南喬治亞及南三明治群島 | Gs |
| 南蘇丹     | SS |
| 西班牙           | ES |
| 斯里蘭卡       | 路 |
| 聖赫勒拿、阿森松、特裡斯坦達庫尼亞群島 | Sh |
| 蘇丹           | Sd |
| 蘇利南        | 鍶 |
| 斯瓦爾巴特        | Sj |
| 瑞典          | 硒 |
| 瑞士     | CH |
| 敘利亞           | Sy |
| 台灣          | TW |
| 塔吉克      | Tj |
| 坦尚尼亞        | TZ |
| 泰國        | TH |
| Timor-Leste     | Tl |
| 多哥            | Tg |
| 托凱羅         | TK |
| 湯加           | 自 |
| 千里達及托巴哥 | Tt |
| 突尼西亞         | Tn |
| 土耳其          | Tr |
| 土庫曼    | Tm |
| 土克斯及開科斯群島 | Tc |
| 吐瓦魯          | 電視 |
| 美國外島 | UM |
| 美屬維爾京群島 | 六 |
| 烏干達          | UG |
| 烏克蘭         | Ua |
| 阿拉伯聯合大公國 | Ae |
| 英國  | G b |
| 美國   | 我們 |
| 烏拉圭         | UY |
| 烏茲別克      | UZ |
| 瓦努阿圖         | Vu |
| 梵蒂岡城    | Va |
| 委內瑞拉       | VE |
| 越南         | VN |
| 瓦利斯群島和富圖那群島 | WF |
| 葉門           | 你們 |
| 尚比亞          | Zm |
| 辛巴威        | ZW |
