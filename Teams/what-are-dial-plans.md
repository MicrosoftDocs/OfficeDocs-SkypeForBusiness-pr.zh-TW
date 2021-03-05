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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: '瞭解 Teams 提供哪些類型的 (PSTN 通話撥號) 方案，以及如何為貴組織選擇一種。  '
ms.openlocfilehash: adb5f46296423b6339c62029d27111345c2fd646
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460813"
---
# <a name="what-are-dial-plans"></a>什麼是撥號對應表？

撥號表是一組命名的標準化規則，將個別使用者撥打的電話號碼轉換成替代格式 (通常是 E.164) ，用於通話授權和呼叫路由。

撥號表包含一或多個標準化規則，可定義以各種格式表示的電話號碼如何轉換成替代格式。 同一個撥號字串在不同的撥號計畫中可能會有不同的解譯和翻譯方式，因此根據指派給特定使用者的撥號表，相同的撥號號碼可能會以不同方式翻譯和路由。 租使用者撥號方案最多可以有 1，000 個。

請參閱 [建立及管理撥號表，](create-and-manage-dial-plans.md) 以建立及管理租使用者撥號方案。

## <a name="tenant-dial-plan-scope"></a>租使用者撥號表範圍

撥號表的範圍會決定可適用撥號表的階層式層級。 用戶端會透過使用者註冊 Teams 時自動提供的設定，取得適當的撥號方案。 系統管理員可以使用 Microsoft Teams 系統管理中心或遠端 PowerShell 管理及指派撥號表範圍層級。

在 Teams 中，有兩種撥號方案類型：服務範圍和租使用者範圍 (適用于貴組織) 。 服務範圍撥號方案會針對有電話系統的每個國家/地區定義。 系統會自動指派與指派給使用者的使用位置一樣的服務國家/地區撥號方案。 您無法變更服務國家/地區撥號方案，但您可以建立租使用者範圍撥號方案，強化服務國家/地區撥號方案。 在布備用戶端時，他們會取得「有效的撥號表」，這是服務國家/地區撥號方案與適當範圍租使用者撥號方案的組合。 因此，不需要在租使用者撥號計畫中定義所有標準化規則，因為規則可能已經存在於服務國家/地區撥號計畫中。

租使用者撥號方案可以進一步細分為兩種範圍：租使用者範圍或使用者範圍。 如果租使用者定義並指派使用者範圍撥號表，該使用者會提供使用者服務國家/地區撥號方案的有效撥號方案，以及指派的使用者撥號表。 如果租使用者定義租使用者範圍的撥號方案，但未指派使用者範圍撥號方案，則該使用者會提供使用者服務國家/地區撥號表和租使用者撥號方案的有效撥號方案。

以下是 Teams 中撥號表的繼承模型。

![如何在 Teams 中繼承撥號方案](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

以下是可能的有效撥號方案：

 **服務國家/地區** 如果未定義租使用者範圍撥號對應表，而且未指派租使用者使用者範圍撥號對應表給已配置的使用者，使用者將會收到對應到與其使用位置相關聯的服務國家/地區的有效撥號對應方案。

 **租使用者全域 - 服務國家/地區** 如果已定義租使用者使用者撥號表，但並未指派給使用者，則已配置的使用者會收到有效的撥號方案，包括合併的租使用者撥號表，以及與其使用位置相關聯的服務國家/地區撥號方案。

 **租使用者使用者 - 服務國家/地區** 如果已定義租使用者使用者撥號表並指派給使用者，則已配置的使用者會收到有效的撥號方案，包括合併的租使用者使用者撥號表，以及與其使用位置相關聯的服務國家/地區撥號方案。

請參閱 [建立及管理撥號表，](create-and-manage-dial-plans.md) 以建立您的租使用者撥號方案。

> [!NOTE]
> 在未將撥號方案正規化規則適用于撥號號碼的情況下，撥號字串仍會標準化為在 "+CC" 的開頭，其中 CC 是撥號使用者的使用位置國碼。 這適用于通話方案、直接路由和 PSTN 會議撥出案例。

## <a name="planning-for-tenant-dial-plans"></a>規劃租使用者撥號方案

若要規劃自訂撥號表，請遵循下列步驟：

- **步驟 1** 決定是否需要自訂撥號方案，以增強使用者的撥號體驗。 一般來說，您需要支援非 E.164 撥號，例如分機或縮寫的國內撥號。

- **步驟 2** 判斷是否需要租使用者全域或租使用者使用者範圍撥號方案，或兩者同時使用。 如果使用者有不同的當地撥號需求，則需要使用者範圍撥號方案。

- **步驟 3** 識別每個所需撥號表的有效號碼模式。 只需要服務層級國家/地區撥號方案未定義的號碼模式。

- **步驟 4** 為撥號表命名，開發全組織的規劃。 採用標準命名配置可確保整個組織的一致性，並簡化維護和更新。


## <a name="creating-your-new-dial-plan"></a>建立新的撥號表

當您建立新撥號表時，必須填入所需資訊。

### <a name="name-and-simple-name"></a>名稱和簡單名稱

對於使用者撥號表，您應指定描述性名稱，以識別要指派撥號方案的使用者。 撥號表簡單名稱會預先填入從撥號表名稱衍生的字串。 簡易名稱欄位可編輯，這可讓您為撥號表建立更具描述性的命名慣例。 簡易名稱值不能是空白的，而且必須是唯一的。 最佳做法是為整個組織開發命名慣例，然後在所有網站和使用者之間一致地使用此慣例。

### <a name="description"></a>說明

建議您輸入對應撥號對應表所適用的地理位置或使用者群組的常見、可識別名稱。

### <a name="external-access-prefix"></a>外部存取首碼
<a name="bkexternalprefix"> </a>

如果使用者需要撥打一或多個額外的前置字元 (例如，9) ，您可以指定最多四個字元的外部存取首碼 (#、*和 0-9) 。

> [!NOTE]
> 如果您指定外部存取首碼，就不需要建立額外的標準化規則來容納首碼。

請參閱 [建立及管理撥號表，](create-and-manage-dial-plans.md) 以建立您的租使用者撥號方案。

## <a name="normalization-rules"></a>正規化規則
<a name="bknormalizationrule"> </a>

標準化規則會定義要如何翻譯以各種格式表示的電話號碼。 根據撥號位置的不同，相同的數位字串可能有不同的解譯和翻譯方式。 如果使用者需要撥打縮寫的內部或外部號碼，可能需要使用標準化規則。

一或多個標準化規則必須指派給撥號表。 標準化規則會由上而下相符，因此它們在租使用者撥號計畫中顯示的順序非常重要。 例如，如果租使用者撥號方案有 10 個標準化規則，則從第一個標準化規則開始嘗試撥號號碼比對邏輯，如果沒有符合第二個規則，依此類推。 如果相符，即會使用規則，而且不會比對任何其他已定義規則。 在一個租使用者撥號計畫中，最多可以有 50 個標準化規則。

### <a name="determining-the-required-normalization-rules"></a>決定必要的標準化規則

由於任何租使用者撥號方案都是有效地與使用者的服務國家/地區撥號方案合併，因此可能需要評估服務國家/地區撥號計畫的常態化規則，才能判斷需要哪些租使用者撥號方案標準化規則。 **Get-CsEffectiveTenantDialPlan** Cmdlet 可用於此用途。 Cmdlet 會以使用者的身分識別做為輸入參數，並會返回所有適用于使用者的標準化規則。

### <a name="creating-normalization-rules"></a>建立標準化規則
<a name="createrule"> </a>

正規化規則使用 .NET Framework 正則運算式指定伺服器用來將撥號字串轉換為 E.164 格式的數值比對模式。 您可以指定比對的正則運算式，以及找到相符專案時要進行的翻譯，以建立正規化規則。 完成時，您可以輸入測試編號，確認標準化規則如預期般運作。

有關使用 .NET Framework 正則運算式的詳細資訊，請參閱 [.NET Framework 正則運算式](https://go.microsoft.com/fwlink/p/?linkId=140927)。

請參閱 [建立及管理撥號表](create-and-manage-dial-plans.md) ，以建立和管理租使用者撥號表的標準化規則。

> [!NOTE]
> 3pip 裝置目前不支援將第一個權杖作為選擇性的標準化規則 (例如 Polycom VVX 601) 。 如果您想要在 3pip 裝置上以選擇性性來申請標準化規則，您應該建立兩個標準化規則，而不是一個。 例如，規則 ^0？ (999) $ 應該由下列兩個規則取代： (999) $ (翻譯：$1) 和 ^0 (999) $ (翻譯：$1) 。


### <a name="sample-normalization-rules"></a>範例標準化規則

下表顯示以 .NET Framework 正則運算式撰寫的正規化規則範例。 範例僅供範例使用，不應做為建立您自己的標準化規則之規範參照。

<a name="regularexpression"></a> 
 **使用 .NET Framework 正則運算式的正規化規則**

| 規則名稱<br/> | 說明<br/> | 數位模式<br/> | 翻譯<br/> | 範例<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |翻譯 4 位數的分機。  <br/> |^ (\\ d {4}) $  <br/> |+1425555$1  <br/> |0100 會翻譯成 +14255550100  <br/> |
|5digitExtension  <br/> |翻譯 5 位數的分機。  <br/> |^5 (\\ d {4}) $  <br/> |+1425555$1  <br/> |50100 會轉換為 +14255550100  <br/> |
|7digitcallingRedmond  <br/> |將 7 位數的數位轉換成 Redmond 當地號碼。  <br/> |^ (\\ d {7}) $  <br/> |+1425$1  <br/> |5550100 會轉換成 +14255550100  <br/>|
|RedmondOperator  <br/> |將 0 轉換為 Redmond 運算子。  <br/> |^0$  <br/> |+14255550100  <br/> |0 會翻譯成 +14255550100  <br/> |
|RedmondSitePrefix  <br/> |將網路首碼為 6 的號碼 (6) Redmond 網站代碼 (222) 。  <br/> |^6222 (\\ d {4}) $  <br/> |+1425555$1  <br/> |62220100 會轉換成 +14255550100  <br/> |
|5digitRange  <br/> |從包含 3 到 7 位數的位數範圍開始翻譯 5 位數的分機。  <br/> |^ ([3-7] \\ d {4}) $  <br/> |+142555$1 <br/> |54567 會翻譯成 +14255554567  <br/> |
|PrefixAdded  <br/> |在 9 位數號碼前面加上國家/地區首碼，並限制第一位數和第三位數。  <br/> |^ ([2-9] \\ \\ d[2-9] \\ d {6}) $  <br/> |1$1  <br/> |4255554567 會轉換為 14255554567  <br/> |
|NoTranslation  <br/> |比對 5 位數，但無法翻譯。  <br/> |^ (\\ d {5}) $  <br/> |$1  <br/> |34567 會翻譯成 34567  <br/> |

 **根據上述的標準化規則，Redmond 撥號方案。**

 下表說明美國華盛頓州雷德蒙市範例撥號表，以上一個資料表所示的標準化規則為基礎。

| Redmond 撥號方案<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> 上一個資料表中顯示的標準化規則名稱不包含空格，但這是一種選擇。 例如，資料表中的第一個名稱可能撰寫為「5 位數分機」或「5 位數分機號碼」，但仍有效。

## <a name="related-topics"></a>相關主題

[建立和管理撥號對應表](create-and-manage-dial-plans.md)

[用於通話方案的電話號碼類型](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話條款及條件](emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
