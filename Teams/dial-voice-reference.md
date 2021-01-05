---
title: 自動語音應答和通話佇列撥號及語音辨識參考
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 瞭解團隊中的 [自動語音應答] 和 [通話佇列撥號] 和 [語音辨識] 選項。
ms.openlocfilehash: 4ff2e60a1d785a035ee20c6547108f1b8916bcfb
ms.sourcegitcommit: 7c6a9e851d2fbf055d15e681e367d9dceee0b917
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749442"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自動語音應答和通話佇列撥號及語音辨識參考

[依名稱撥號] 是自動語音應答的功能，也稱為目錄搜尋。 它可讓呼叫您自動接聽的人員使用語音 (語音辨識) 或其電話鍵台 (DTMF) 回應，以輸入完整或部分名稱來搜尋公司的目錄、找出該人員，然後將來電轉接給對方。 當您在自動語音應答中設定 [[通話流程設定](create-a-phone-system-auto-attendant.md#call-flow)] 時，您可以依名稱設定撥號。

## <a name="searching-for-users"></a>搜尋使用者

您想要使用電話撥入及撥出的使用者 **，不需要有電話號碼或有指派通話方案，但是他們必須是針對商務用 Skype Server 使用者啟用的企業語音**。 透過名稱撥號，您甚至可以尋找並將來電轉接給在不同國家或地區的多國組織所託管的 Microsoft 團隊使用者。 考慮到所需的先決條件，您可以在自動語音應答中明確啟用 [透過名稱撥號]。

[透過分機號碼撥號] 是自動語音應答的一項功能，也就是目錄搜尋的一部分。 它可讓呼叫您自動接聽的人員使用語音 (語音辨識) 或他們的電話鍵台 (DTMF) 回應，以輸入他們想要達到的使用者的電話副檔名，然後將來電轉接給對方。 您想要使用電話撥入及到達的使用者  **，不需要有電話號碼或有指派通話方案，但是他們必須是針對商務用 Skype Server 使用者啟用的企業語音**。 您也必須為使用者設定適當的撥號方案。 透過分機號碼撥號，您甚至可以尋找並將來電轉接給在不同國家或地區的多國組織所託管的 Microsoft 團隊使用者。 根據所涉及的先決條件，您可以明確啟用自動語音應答中的 [透過分機撥號]。

### <a name="maximum-directory-size"></a>目錄大小上限

在來電者搜尋特定人員時，[依名稱撥號] 和 [撥打電話] 的號碼不會受到限制。 來電者可以輸入部分或完整名稱 (FirstName + 姓氏，也可以輸入姓氏 + FirstName) ，但需要完整的分機號碼。 使用語音辨識可支援的單一自動語音應答的最大名稱清單大小為80000使用者。
  
|輸入類型|搜尋格式|組織中的使用者數目上限|
|:-----|:-----|:-----|
|DTMF (鍵台專案)  |部分  <br/> FirstName + 姓氏  <br/> 姓氏 + FirstName |無限制  |
|語音 (語音輸入)  |段  <br/> 姓名  <br/> FirstName + 姓氏  <br/> 姓氏 + FirstName  | 80000使用者 |

> [!NOTE]
> 如果您是使用語音辨識進行撥號，但貴組織的 Active Directory 大於80000的使用者，而且您還沒有使用撥號作用中的名稱限制撥號作用中，[按名稱撥號] 仍可供您使用電話鍵的呼叫者使用，而語音輸入則適用于所有其他案例。 您可以使用 [撥號作用中] 功能，透過針對特定自動語音應答變更撥號作用中的名稱，來縮小所能達到的名稱。
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>撥號方式：按名稱鍵台 (DTMF) 專案
撥入的人員可透過指定使用者的完整或部分名稱來使用撥號，以取得使用者的名稱。 輸入名稱時，可以使用各種不同的格式。

在搜尋貴組織的目錄時，使用者可以使用「0」 (零) 鍵，以表示名字與姓氏或姓氏及名字之間的空格。 輸入名稱時，系統會要求使用者以 # 金鑰結束其鍵台專案。 例如，在您輸入您想要到達的人員名稱之後，請按 #。 如果找到多個名稱，則會為呼叫者提供一個名稱清單供您選取。
  
使用者可以使用其電話鍵盤上的下列搜尋格式，在您的組織中搜尋名稱：
  
|名稱格式|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + 姓氏 |填  |Amos0Marble# |Amos 大理石 |
|姓氏 + FirstName |填 |Marble0Amos#  |Amos 大理石 |
|段  |填   |Amos#   |按1以 Amos 大理石  <br/> 針對 Amos Marcus 按2 |
|姓名 |填 |式#  |按1以 Amos 大理石  <br/> 按下 [Mary 大理石] 的2 |
|[名字] 或 [姓氏] |部分 |Mar# |針對 Mary 大理石按1  <br/> 按下 [Mary 1]  <br/> 按下 Amos Marcus 的3 |
|FirsName + LastName |部分 |Amos0Mar# |按1以 Amos 大理石  <br/> 針對 Amos Marcus 按2 |
|姓氏 + FirstName |部分 |Mar0Am# |按1以 Amos 大理石  <br/> 針對 Amos Marcus 按2 |

搜尋使用電話鍵台的人員時，會用到幾個特殊字元。 例如，系統會要求使用者使用井號鍵 ( # ) ，而零 (0) 鍵則用於名稱間的空格。 按下 ( * ) 的星號鍵，就會將匹配名稱的清單重複給該人員。
  
|特殊的電話鍵台字元|所代表的意義|
|:-----|:-----|
|#   |輸入名稱時的結束字元。 |
|0   |名稱之間的間距。 |
|*    |重複 [相符的名稱] 清單。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>使用語音撥打名稱-名稱識別

使用者可以使用語音 (語音辨識) 在組織中搜尋其他人。 他們也可以透過說要尋找的人員的完整或部分名稱，在 Active Directory 中與任何人取得聯繫。 使用語音輸入可以辨識各種格式的名稱，包括 FirstName、姓氏、名字 + 姓氏或姓氏 + 名字。
  
您可以為自動語音應答啟用語音辨識功能，但不會停用手機小數位專案 (DTMF) 。 即使已在自動語音應答上啟用語音辨識功能，您也可以在任何時候使用電話鍵台專案。
  
就像電話鍵台專案一樣，如果找到多個名稱，呼叫者會聽到要選取的名稱清單。
  
來電者可以說出下列格式的名稱：
  
|使用語音命名|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + 姓氏 |填 |Amos 大理石 |Amos 大理石 |
|姓氏 + FirstName |填  |大理石 Amos |Amos 大理石 |
|段 |填 |Amos |針對 Amos 大理石按或說1  <br/> 按下或說出2的 Amos。 |
|姓名 |填 |式 |針對 Amos 大理石按或說1  <br/> 針對 Ben 大理石按下或說出2 |
|[名字] 或 [姓氏] |部分 |Mar |按或說 [Mary 大理石 1]  <br/> 按下或說 [Mary 2]。  <br/> 針對 Amos Marcus 按下或說出3 |
|FirsName + LastName |部分 |Amos Mar |針對 Amos 大理石按或說1  <br/> 針對 Amos Marcus 按下或說出2 |


> [!NOTE]
> 新的使用者可能需要長達36小時，才能使用語音辨識將其名稱列在目錄中，因為 Active Directory 複製延隔時間。
  
## <a name="language-support"></a>語言支援

下列語言適用于與外寄提示搭配使用的文字轉換語音：
  
|-|-|-|
|:-----|:-----|:-----|
|阿拉伯文 (例如)   |英文 (NZ)   |朝鮮文 (KO)   |
|中文 (HK)   |英文 (英國)  |挪威文 (無)   |
|中文 (隸書)  |英文 (美國)  |波蘭文 (PL)   |
|中文 (ZH-CN&PLATFORM)  |芬蘭文 (FI)  |葡萄牙 (BR)  |
|丹麥文 (DA)   |法文 (CA)   |葡萄牙文 (PT)  |
|荷蘭 (NL-NL&PLATFORM)    |法文 (FR)   |俄羅斯 (RU)  |
|英文 (AU)   |德語 (DE)  |西班牙文 (ES)   |
|英文 (CA)   |義大利文 ()  |西班牙文 (MX) |
|) 中的英文 (  |日文 (JP)  |瑞典文 (SV) |

可使用下列語言提供自動語音應答的語音辨識輸入：
  
|-|-|
|:-----|:-----|
|中文 (ZH-CN&PLATFORM)   |法文 (FR)   |
|英文 (AU)   |德語 (DE)   |
|英文 (CA)   |義大利文 ()   |
|) 中的英文 (  |日文 (JP)   |
|英文 (英國)   |葡萄牙 (BR)   |
|英文 (美國)   |西班牙文 (ES)   |
|法文 (CA)    |西班牙文 (MX)   |

下列語音命令可在支援語音辨識的14種語言中使用：
  
|語音命令| 對應至 |
|:-----|:-----|
|是 | 如果是，請按1。 |
|否 | 按 [2] 鍵。 |
|執行 |重複清單中的選項。 按下鍵盤上的 * 以重複選項清單。 |
|運算子 | 按0以取得「運算子」 |
|主功能表  |會將來電者帶入自動語音應答的主要功能表。 |
|零時 | 依預設按 0 (與「運算子」 ) 。|
|單個 | 按1。 |
|兩個 | 按2。 |
|三維| 按3。|
|條 | 按下4。 |
|五點 | 按5。 |
|六筆  | 按6。 |
|占 | 按7。|
|8 |按8。|
|九個  |按9。|

## <a name="related-topics"></a>相關主題

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[小型企業範例 - 設定自動語音應答](/microsoftteams/tutorial-org-aa)
