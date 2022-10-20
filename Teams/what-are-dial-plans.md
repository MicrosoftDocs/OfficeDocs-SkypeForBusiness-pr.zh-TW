---
title: 什麼是撥號對應表？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: '瞭解 Teams 提供哪些類型的撥號 (PSTN 撥號對應表) ，以及如何為貴組織選擇一種撥號對應表。  '
ms.openlocfilehash: 77ee7801d43bd6a7cf9ae9a9e3fc74c302f8caa0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614246"
---
# <a name="what-are-dial-plans"></a>什麼是撥號對應表？

撥號對應表是一組具名的正規化規則，將個別使用者的撥號電話號碼轉換為替代格式， (通常是 E.164) ，用於通話授權和語音路由。

撥號對應表包含一或多個正規化規則，可定義以各種格式表示的電話號碼如何轉換成替代格式。 相同的撥號字串可能會在不同的撥號對應表中以不同的方式解譯及翻譯，因此根據指派給特定使用者的撥號對應表，相同的撥號號碼可能會以不同的方式翻譯和路由。 最多可以有 1，000 個租使用者撥號對應表。

請參閱 [建立及管理撥號對應表](create-and-manage-dial-plans.md) 以建立及管理租使用者撥號對應表。

## <a name="tenant-dial-plan-scope"></a>租使用者撥號對應表範圍

撥號對應表的範圍會決定可以套用撥號對應表的階層。 用戶端會透過布建設定取得適當的撥號對應表，這些設定會在使用者登入 Teams 時自動提供。 身為系統管理員，您可以使用 Microsoft Teams 系統管理中心或遠端 PowerShell 來管理和指派撥號對應範圍層級。

在 Teams 中，有兩種類型的撥號對應表：服務範圍和租使用者範圍 (，適用于貴組織) 。 系統會針對電話系統可用的每個國家或地區定義服務範圍的撥號對應表。 系統會自動為每個使用者指派符合指派給使用者之使用位置的服務國家/地區撥號對應表。 您無法變更服務國家/地區撥號對應表，但您可以建立租使用者範圍的撥號對應表，這會放大服務國家/地區撥號對應表。 在布建用戶端時，用戶端會取得「有效的撥號對應表」，這是服務國家/地區撥號對應表和適當範圍租使用者撥號對應表的組合。 因此，不需要定義租使用者撥號對應表中的所有正規化規則，因為它們可能已經存在於服務國家/地區撥號對應表中。

租使用者撥號對應方案可以進一步分成兩個範圍：租使用者範圍或使用者範圍。 如果租使用者定義並指派使用者範圍的撥號對應表，該使用者將會布建使用者服務國家/地區撥號對應表和指派之使用者撥號對應表的有效撥號對應表。 如果租使用者定義租使用者範圍的撥號對應表，但未指派使用者範圍的撥號對應表，則該使用者將會布建使用者服務國家/地區撥號對應表和租使用者撥號對應表的有效撥號對應表。

以下是 Teams 中撥號對應表的繼承模型。

![在 Teams 中繼承撥號對應表的方式。](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

以下是可能的有效撥號對應表：

 **服務國家/地區** 如果未定義租使用者範圍的撥號對應方案，且未將租使用者範圍的撥號對應方案指派給布建的使用者，使用者將會收到與其使用位置相關聯的服務國家/地區對應的有效撥號對應方案。

 **租使用者全域 - 服務國家/地區** 如果已定義租使用者撥號對應表，但未指派給使用者，布建的使用者將會收到包含合併租使用者撥號對應表以及與其使用位置相關聯的服務國家/地區撥號對應表的有效撥號對應表。

 **租使用者使用者 - 服務國家/地區** 如果已定義租使用者的使用者撥號對應表並指派給使用者，布建的使用者將會收到有效的撥號對應表，其中包括合併的租使用者使用者撥號對應表，以及與其使用位置相關聯的服務國家/地區撥號對應表。

請參閱 [建立及管理撥號對應表](create-and-manage-dial-plans.md) 以建立租使用者撥號對應表。

> [!NOTE]
> 在沒有撥號對應表正規化規則套用至撥號號碼的情況下，撥號字串仍會正常化，以預先加上 「+CC」，其中 [副本] 是撥號使用者使用位置的國家/地區代碼。 這適用于通話方案、直接路由和 PSTN 會議撥出案例。 此外，如果租使用者撥號對應表正規化規則得出的號碼不是以 「+」 開頭，通話服務將會嘗試根據租使用者撥號對應表，且如果無法比對地區撥號對應方案，將從 Teams 用戶端收到的號碼正規化。 若要避免雙正規化，建議直接路由客戶將數位正規化以包含 +，然後使用主幹翻譯規則移除 +。 

## <a name="planning-for-tenant-dial-plans"></a>規劃租使用者撥號對應表

若要規劃自訂撥號對應表，請遵循下列步驟：

- **步驟 1** 決定是否需要自訂撥號對應表來增強使用者的撥號體驗。 一般而言，一個電話的需求是支援非 E.164 撥號，例如擴充功能或縮寫的國家電話撥號。

- **步驟 2** 判斷是否需要租使用者全域或租使用者使用者範圍的撥號對應表，或兩者皆需要。 如果使用者有不同的本機撥號需求，則需要使用者範圍的撥號對應表。

- **步驟 3** 找出每個必要的撥號對應表的有效號碼模式。 只有服務等級國家/地區撥號對應表中未定義的號碼模式才需要。

- **步驟 4** 開發整個組織的撥號對應表命名配置。 採用標準命名配置可確保整個組織的一致性，並讓維護與更新更輕鬆。


## <a name="creating-your-new-dial-plan"></a>建立新的撥號對應表

當您建立新的撥號對應表時，您必須輸入所需的資訊。

### <a name="name-and-simple-name"></a>名稱和簡易名稱

針對使用者撥號對應表，您應指定描述性名稱，以識別要指派撥號對應表的使用者。 撥號對應表的 [簡易名稱] 會預先填入衍生自撥號對應表名稱的字串。 [簡易名稱] 欄位可編輯，可讓您為您的撥號對應建立更具描述性的命名慣例。 [簡易名稱] 值不能是空值，而且必須是唯一的。 最佳作法是為整個組織開發命名慣例，然後在所有網站和使用者之間持續使用此慣例。

### <a name="description"></a>描述

我們建議您輸入適用對應撥號對應之使用者的地理位置或使用者群組常見且可辨識的名稱。

### <a name="external-access-prefix"></a>外部存取首碼
<a name="bkexternalprefix"> </a>

如果使用者需要撥打一個或多個額外的前置 (位數，) ，您可以指定最多四個字元 (#、*和 0-9) 的外部存取首碼，例如，9) 來取得外接線。

> [!NOTE]
> 如果您指定外部存取前置詞，就不需要建立額外的正規化規則來容納前置詞。

請參閱 [建立及管理撥號對應表](create-and-manage-dial-plans.md) 以建立租使用者撥號對應表。

## <a name="normalization-rules"></a>正規化規則
<a name="bknormalizationrule"> </a>

正規化規則會定義以各種格式表示的電話號碼的翻譯方式。 相同的數位字串可能會根據撥號的區域設定，以不同的方式解譯及翻譯。 如果使用者必須能夠撥打縮寫的內部或外部號碼，則可能需要正規化規則。

必須將一或多個正規化規則指派給撥號對應表。 正規化規則由上到下相符，因此它們出現在租使用者撥號對應表中的順序非常重要。 例如，如果租使用者撥號對應表有 10 個正規化規則，則會從第一個正規化規則開始嘗試撥打號碼比對邏輯，如果不符合則第二個規則，依此類推。 如果符合，則會使用該規則，而且不會費力比對任何其他定義的規則。 在指定的租使用者撥號對應表中，最多可以有 50 個正規化規則。

### <a name="determining-the-required-normalization-rules"></a>決定必要的正規化規則

由於任何租使用者撥號對應表都已有效與指定使用者的服務國家/地區撥號對應表合併，因此可能需要評估服務國家/地區撥號對應表的正規化規則，以判斷需要哪一個租使用者撥號對應表正規化規則。 **Get-CsEffectiveTenantDialPlan** Cmdlet 可用於此用途。 Cmdlet 會以使用者的身分識別做為輸入參數，並傳回所有適用于使用者的正規化規則。

### <a name="creating-normalization-rules"></a>建立正規化規則
<a name="createrule"> </a>

正規化規則會使用.NET Framework正則運算式來指定伺服器用來將撥號字串翻譯成 E.164 格式的數值比對模式。 您可以為比對專案指定一般運算式，並在找到相符專案時進行翻譯，藉此建立正規化規則。 完成後，您可以輸入測試編號以確認正規化規則如預期般運作。

如需使用.NET Framework正則運算式的詳細資訊，請[參閱.NET Framework正則運算式](/dotnet/standard/base-types/regular-expressions)。

請參閱 [建立及管理撥號對應表](create-and-manage-dial-plans.md) ，以建立及管理租使用者撥號對應表的正規化規則。

> [!NOTE]
> 3pip 裝置目前不支援具有選擇性第一個權杖的正規化規則，例如 Polycom VVX 601 型號)  (。 如果您想要在 3pip 裝置上套用具有選擇性的正規化規則，您應該建立兩個正規化規則，而不是一個。 例如，規則 ^0？ (999) $ 應由下列兩個規則取代： (999) $ (Translation：$1) 和 ^0 (999) $ (Translation：$1) 。


### <a name="sample-normalization-rules"></a>正規化規則範例

下表顯示以正則運算式撰寫為.NET Framework正規化規則的範例。 這些範例只是範例，不應做為建立您自己的正規化規則的規範參考。

<a name="regularexpression"> </a> 
 **使用.NET Framework正則運算式的正規化規則**

| 規則名稱<br/> | 描述<br/> | 數位模式<br/> | 翻譯<br/> | 範例<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |翻譯 4 位數的擴充功能。  <br/> |^ (\\ d {4}) $  <br/> |+1425555$1  <br/> |0100 會翻譯成 +14255550100  <br/> |
|5digitExtension  <br/> |翻譯 5 位數的擴充功能。  <br/> |^5 (\\ d {4}) $  <br/> |+1425555$1  <br/> |50100 會翻譯成 +14255550100  <br/> |
|7digitcallingRedmond  <br/> |將 7 位數數位翻譯成 Redmond 本機號碼。  <br/> |^ (\\ d {7}) $  <br/> |+1425$1  <br/> |5550100 會翻譯成 +14255550100  <br/>|
|RedmondOperator  <br/> |將 0 翻譯成 Redmond 運算子。  <br/> |^0$  <br/> |+14255550100  <br/> |0 會翻譯成 +14255550100  <br/> |
|RedmondSitePrefix  <br/> |將數位與網路前置詞 (6) ，而 Redmond 網站代碼 (222) 。  <br/> |^6222 (\\ d {4}) $  <br/> |+1425555$1  <br/> |62220100會翻譯成 +14255550100  <br/> |
|5digitRange  <br/> |將 5 位數的副檔名翻譯為從 3 到 7 含的位數範圍開始。  <br/> |^ ([3-7] \\ d {4}) $  <br/> |+142555$1 <br/> |54567 會翻譯成 +14255554567  <br/> |
|PrefixAdded  <br/> |在 9 位數數位前面加上國家/地區首碼，第一位數和第三位數有限制。  <br/> |^ ([2-9] \\ d \\ [2-9] \\ d {6}) $  <br/> |1$1  <br/> |4255554567會翻譯成 14255554567  <br/> |
|NoTranslation  <br/> |5 位數相符，但不相符翻譯。  <br/> |^ (\\ d {5}) $  <br/> |$1  <br/> |34567 已翻譯為 34567  <br/> |

 **根據上述正規化規則的 Redmond 撥號對應表。**

 下表說明華盛頓州雷德蒙市美國的撥號對應表範例，以上一個資料表中顯示的正規化規則為基礎。

| Redmond 撥號對應表<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> 上述資料表中顯示的正規化規則名稱不含空格，但這是您要選擇的問題。 例如，資料表中的第一個名稱可能是寫成「5 位數副檔名」或「5 位數擴充功能」，而且仍然有效。

## <a name="related-topics"></a>相關主題

[建立和管理撥號對應表](create-and-manage-dial-plans.md)

[通話方案所用的不同電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話條款及條件](emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
