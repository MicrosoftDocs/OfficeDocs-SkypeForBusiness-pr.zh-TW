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
description: '瞭解您可以使用哪些類型的撥號方案 (PSTN 呼叫撥號方案) 提供給小組，以及如何為您的組織選擇一個電話。  '
ms.openlocfilehash: 932440e0d94072da7ce3ef304438400963e17d2d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031369"
---
# <a name="what-are-dial-plans"></a>什麼是撥號對應表？

撥號方案是一組命名的正常化規則，其中個別使用者將撥打的電話號碼轉換成替代格式 (通常是) 的 E. 164，以供通話授權和呼叫路由使用。

撥號計畫由一或多個正常化規則所組成，這些規則定義以不同格式表示的電話號碼如何轉換為替代格式。 在不同的撥號方案中，相同的撥號字串可能會以不同的方式加以轉譯，因此，根據指派給特定使用者的撥號方案而定，相同的撥入號碼可能會以不同的方式進行轉換和路由。 最多可以有1000個租使用者撥號方案。

請參閱 [建立及管理撥號計畫](create-and-manage-dial-plans.md) ，以建立和管理租使用者撥號方案。

## <a name="tenant-dial-plan-scope"></a>租使用者撥號計畫範圍

撥號計畫的範圍決定您可以套用撥號方案的階層等級。 用戶端透過提供設定來取得適當的撥號方案，這些設定是在使用者登入小組時自動提供的。 以管理員身分，您可以使用 Microsoft 團隊系統管理中心或遠端 PowerShell 來管理和指派撥號計畫範圍階層。

在團隊中，有兩種類型的撥號方案：針對貴組織) 的服務範圍與租使用者範圍的 (。 系統會針對每個有電話系統的國家或地區定義服務範圍撥號方案。 系統會自動為每位使用者指派與指派給使用者的使用位置相符的服務國家撥入方案。 您無法變更服務國家/地區撥號方案，但您可以建立租使用者範圍撥號方案，這會增加服務的國家/地區撥號計畫。 隨著用戶端的設定，他們會取得「有效的撥號方案」，它會結合服務國家/地區撥號方案和適當範圍的租使用者撥號計畫。 因此，您不需要在租使用者撥號方案中定義所有正常化規則，因為它們可能已存在於服務國家/地區撥號計畫中。

租使用者撥號方案可進一步分為兩個作用中-租使用者範圍或使用者範圍。 如果租使用者定義並指派使用者範圍的撥號方案，該使用者將會提供使用者服務國家/地區撥號方案的有效撥號計畫，以及指派的使用者撥號方案。 如果租使用者定義租使用者範圍的撥號方案，但沒有指派使用者範圍的撥號方案，則該使用者將會使用使用者的服務國家/地區撥號方案和租使用者撥號方案的有效撥號方案進行設定。

下列是團隊中撥號方案的繼承模型。

![如何在團隊中繼承撥號方案](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

下列是可能的有效撥號方案：

 **服務國家/地區** 如果未定義租使用者範圍的撥號方案，且未將租使用者範圍的撥號計畫指派給已設定的使用者，則使用者將會收到對應至與其使用位置相關聯之服務國家/地區的有效撥號方案。

 **租使用者全域服務國家/地區** 如果已定義租使用者的撥號方案，但未指派給使用者，則已置備的使用者會收到一份有效的撥號方案，其中包含合併的租使用者撥號方案，以及與其使用位置相關聯的服務國家/地區撥號方案。

 **租使用者-服務國家/地區** 如果已定義租使用者的撥號方案並指派給使用者，則已置備的使用者會收到一份有效的撥號方案，其中包含合併的租使用者撥號方案，以及與其使用位置相關聯的服務國家/地區撥號方案。

請參閱 [建立及管理撥號計畫](create-and-manage-dial-plans.md) ，以建立您的租使用者撥號方案。

> [!NOTE]
> 在沒有撥號方案正常化規則套用至撥入號碼的情況下，撥號字串仍會正常化為 [+ CC]，其中 CC 是撥號使用者使用位置的國家/地區代碼。 這適用于通話方案、直接路由和 PSTN 會議撥出案例。

## <a name="planning-for-tenant-dial-plans"></a>規劃租使用者撥號方案

若要規劃自訂撥號方案，請遵循下列步驟：

- **步驟 1** 決定是否需要自訂撥號方案，以增強使用者的撥號體驗。 通常，必須支援非 E. 164 撥號，例如分機或縮寫國家撥號。

- **步驟 2** 判斷您是否需要承租人全域或租使用者範圍的撥號方案，或兩者皆可。 如果使用者有不同的本機撥號需求，就需要使用者範圍的撥號方案。

- **步驟 3** 針對每個所需的撥號方案，找出有效的數位模式。 只有服務層級撥號方案中未定義的數位模式是必要的。

- **步驟 4** 為命名撥號方案開發組織範圍的配置。 採用標準命名配置，可確保整個組織的一致性，並讓維護與更新變得更容易。


## <a name="creating-your-new-tenant-dial-plan"></a>建立新的租使用者撥號方案

當您建立新的撥號方案時，您必須放入所需的資訊。

### <a name="name-and-simple-name"></a>名稱與簡單名稱

針對使用者撥號方案，您應該指定一個描述名稱，以識別將指派撥號方案的使用者。 撥號計畫簡單名稱是使用從撥號方案名稱衍生的字串預先填入。 [簡易名稱] 欄位為 [可編輯]，可讓您為撥號方案建立更具描述性的命名慣例。 [簡易名稱] 值不能為空白，且必須是唯一的。 最佳做法是為您的整個組織開發一個命名慣例，然後在所有網站和使用者中統一使用這個慣例。

### <a name="description"></a>描述

我們建議您輸入適用之地理位置的通用、可識別名稱，或對應的撥號方案所屬的使用者群組。

### <a name="external-access-prefix"></a>外部存取首碼
<a name="bkexternalprefix"> </a>

您可以指定最多四個字元 ( #、* 及) 0-9 的外部存取前置詞，如果使用者需要撥一或多個額外的前導數位 (例如，9) 取得外部線路。

> [!NOTE]
> 如果您指定外部存取首碼，就不需要建立額外的正常化規則來容納該前置詞。

請參閱 [建立及管理撥號計畫](create-and-manage-dial-plans.md) ，以建立您的租使用者撥號方案。

## <a name="normalization-rules"></a>正規化規則
<a name="bknormalizationrule"> </a>

正常化規則定義以各種格式表示的電話號碼的翻譯方式。 根據撥號的地區設定，相同的數位字串可能會以不同的方式加以轉譯和翻譯。 如果使用者需要能夠撥號的內部或外部號碼的縮寫，可能需要正常化規則。

必須將一或多個正常化規則指派給撥號方案。 正常化規則是從上到下，因此它們在租使用者撥號方案中出現的順序非常重要。 例如，如果租使用者撥號方案有10個正常化規則，則在第一個正常化規則（如果沒有匹配的秒數）之後，就會嘗試從第一個正常化規則開始，依此類推。 如果進行了相符，就會使用該規則，而且不會對任何其他已定義的規則進行比較。 在指定的租使用者撥號方案中，最多可以有50正常化規則。

### <a name="determining-the-required-normalization-rules"></a>判斷所需的正常化規則

因為任何租使用者撥號方案都會與指定的使用者服務國家/地區撥號方案進行有效的合併，所以很可能必須評估服務國家/地區撥號方案的正常化規則，才能判斷需要哪些租使用者撥號規劃正常化規則。 CsEffectiveTenantDialPlan Cmdlet 可用來 **達到** 此目的。 這個 Cmdlet 會將使用者的身分識別當作輸入參數，並傳回所有適用于使用者的正常化規則。

### <a name="creating-normalization-rules"></a>建立正常化規則
<a name="createrule"> </a>

正常化規則使用 .NET Framework 正則運算式，指定伺服器用來將撥號字串轉換成 E. 164 格式的數位相符模式。 您可以透過指定相符的正則運算式來建立正常化規則，以及在找到相符專案時要完成的翻譯。 完成後，您可以輸入測試號碼來驗證正常化規則是否如預期的那樣運作。

如需使用 .NET Framework 正則運算式的詳細資料，請參閱 [.Net Framework 正則運算式](https://go.microsoft.com/fwlink/p/?linkId=140927)。

請參閱 [建立及管理撥號計畫](create-and-manage-dial-plans.md) ，以建立及管理您的租使用者撥號方案的正常化規則。

### <a name="sample-normalization-rules"></a>範例正常化規則

下表顯示已寫入為 .NET Framework 一般運算式的範例正常化規則。 這些範例只是範例，並不代表建立您自己的正常化規則的規範性參考。

<a name="regularexpression"> </a> 
 **使用 .net Framework 一般運算式的正常化規則**

| 規則名稱<br/> | 描述<br/> | 數位模式<br/> | 翻譯<br/> | 範例<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |翻譯4位數延伸。  <br/> |^ (\\ d {4}) $  <br/> |+ 1425555 $ 1  <br/> |0100已轉譯為 + 14255550100  <br/> |
|5digitExtension  <br/> |翻譯5位數的延伸。  <br/> |^ 5 (\\ d {4}) $  <br/> |+ 1425555 $ 1  <br/> |50100已轉譯為 + 14255550100  <br/> |
|7digitcallingRedmond  <br/> |將7位數的數位轉譯為雷德式當地電話號碼。  <br/> |^ (\\ d {7}) $  <br/> |+ 1425 $ 1  <br/> |5550100已轉譯為 + 14255550100  <br/>|
|RedmondOperator  <br/> |將0轉換為雷德運算子。  <br/> |^ $0  <br/> |+ 14255550100  <br/> |0已轉譯為 + 14255550100  <br/> |
|RedmondSitePrefix  <br/> |使用 (6) 和雷德蒙的網站程式碼 (222) 來轉譯含有網路上首碼的數位。  <br/> |^ 6222 (\\ d {4}) $  <br/> |+ 1425555 $ 1  <br/> |62220100已轉譯為 + 14255550100  <br/> |
|5digitRange  <br/> |翻譯5位數的延伸開始于3-7 （含）之間的數位範圍。  <br/> |^ ( [3-7] \\ d {4}) $  <br/> |+ 142555 $ 1 <br/> |54567已轉譯為 + 14255554567  <br/> |
|PrefixAdded  <br/> |在包含第一個和第三個數字限制的9位數數位的前面加上國家/地區的首碼。  <br/> |^ ( [2-9] \\ d \\ d [2-9] \\ d {6}) $  <br/> |1 $ 1  <br/> |4255554567已轉換為14255554567  <br/> |
|NoTranslation  <br/> |符合5位數但沒有翻譯。  <br/> |^ (\\ d {5}) $  <br/> |$1  <br/> |34567已轉換為34567  <br/> |

 **以上述正常化規則為基礎的雷蒙德撥號方案。**

 下表說明雷蒙德、華盛頓、英國的範例撥號方案，根據上表所示的正常化規則。

| 雷德蒙撥號方案<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> 上表所示的正常化規則名稱不會包含空格，但這是選擇的考慮。 例如，資料表中的第一個名稱可以是 "5 位數副檔名" 或 "5 位數副檔名"，但仍然有效。

## <a name="related-topics"></a>相關主題

[建立和管理撥號對應表](create-and-manage-dial-plans.md)

[通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話條款及條件](emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
