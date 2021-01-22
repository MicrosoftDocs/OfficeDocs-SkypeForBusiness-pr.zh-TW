---
title: 自動語音機和通話佇列撥號和語音辨識參考
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
description: 瞭解 Teams 中的自動語音語音機和通話佇列撥號和語音辨識選項。
ms.openlocfilehash: 1cb8da2d2e6625de5a1471d1051c1ca51f11bbae
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918959"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自動語音機和通話佇列撥號和語音辨識參考

按名稱撥號是自動 Attendant 的一項功能，亦稱為目錄搜尋。 它可讓撥打自動語音應答的人使用語音 (語音辨識) 或電話鍵盤 (DTMF) 回應，以輸入完整或部分名稱來搜尋公司的目錄、尋找人員，然後將電話轉接給他們。 當您在自動參與中設定通話流程設定時，可設定 [以名稱撥號](create-a-phone-system-auto-attendant.md#call-flow)。

## <a name="searching-for-users"></a>搜尋使用者

想要使用名稱撥號來尋找和聯繫的使用者，不需要有電話號碼或已指派通話方案給他們，但他們必須為商務用 **Skype Server** 使用者啟用企業語音。 使用名稱撥號甚至可以為在多國組織所託管的不同國家/地區中的 Microsoft Teams 使用者尋找和轉接電話。 基於先決條件，您可以在自動參與中明確啟用按名稱撥號。

分機號碼是自動參與的一項功能，也是目錄搜尋的一部分。 讓撥打自動語音應答的人使用語音 (語音辨識) 或電話鍵盤 (DTMF) 回應，輸入他們嘗試聯繫之使用者的電話分機，然後將電話轉接給他們。 不需要電話號碼或指派通話方案給使用者，就不需要使用撥號分機來尋找和聯繫的使用者，但是必須為商務用  **Skype Server** 使用者啟用企業語音。 您也需要為使用者適當配置的撥號方案。 撥打分機號碼甚至可以為在多國組織所託管的不同國家/地區中的 Microsoft Teams 使用者尋找和轉接電話。 基於先決條件，您可以在自動 Attendant 中明確啟用 Dial by extension。

### <a name="maximum-directory-size"></a>目錄大小上限

當來電者搜尋特定人員時，Active Directory 使用者按名稱撥號及撥號者分機號碼可支援的數量沒有限制。 來電者可以輸入名字 + 姓氏 (部分或全名，也可以輸入 LastName + 名字) ，但需要完整的分機號碼。 單一自動語音語音機支援使用語音辨識的名稱清單大小上限為 80，000 個使用者。
  
|輸入類型|搜尋格式|組織中使用者數目上限|
|:-----|:-----|:-----|
|DTMF (鍵台專案)  |部分  <br/> FirstName + LastName  <br/> LastName + FirstName |沒有限制  |
|語音 (語音輸入)  |FirstName  <br/> 姓氏  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80，000 個使用者 |

> [!NOTE]
> 如果您使用具有語音辨識的按名稱撥號，但貴組織的 Active Directory 超過 80，000 個使用者，而且您沒有限制使用撥號範圍功能按名稱撥號的範圍，則使用電話鍵盤的來電者仍可使用撥號鍵台，而且語音輸入適用于所有其他情況。 您可以使用撥號範圍功能，變更特定自動 Attendant 的撥號方式範圍，縮小可聯繫的名稱。
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>按名稱撥號 - 數位鍵台 (DTMF) 專案
撥入的使用者可以使用撥號名稱來聯繫使用者，方法為指定嘗試聯繫之人員的完整名稱或部分名稱。 輸入名稱時，可以使用各種不同的格式。

搜尋組織的目錄時，人員可以使用 '0' (零) 鍵來表示名字與姓氏或姓氏之間的空格。 當他們輸入名稱時，會要求他們使用 # 鍵終止鍵盤專案。 例如，「輸入您嘗試聯繫的人名後，請按 #」。 如果找到多個名稱，來電者會獲得一份名稱清單以選取。
  
人員可以在其電話鍵盤上，使用下列搜尋格式搜尋貴組織的名稱：
  
|名稱格式|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |全  |Amos0Marble# |Amos Marble |
|LastName + FirstName |全 |Marble0 Marbles#  |Amos Marble |
|FirstName  |全   |阿莫斯#   |按 1 以使用 Amos Marble  <br/> 按 2 for AmosUs |
|姓氏 |全 |大理石#  |按 1 以使用 Amos Marble  <br/> 按 2 for Mary Marble |
|FirstName 或 LastName |部分 |三月# |按 1 for Mary Marble  <br/> 按 2 for Mary Mary  <br/> 按 3 for AmosUs |
|FirsName + LastName |部分 |Amos0Mar# |按 1 以使用 Amos Marble  <br/> 按 2 for AmosUs |
|LastName + FirstName |部分 |Mar0Am# |按 1 以使用 Amos Marble  <br/> 按 2 for AmosUs |

搜尋使用電話鍵盤搜尋人員時，會使用一些特殊字元。 例如，系統將會要求該人員使用井號鍵 (#) ，而零 (0) 則用於姓名之間的空格。 按星號鍵 (*) 會重複該人員符合的名稱清單。
  
|特殊電話鍵盤字元|代表什麼|
|:-----|:-----|
|#   |輸入名稱時結束字元。 |
|0   |名稱之間的空格。 |
|*    |重複符合名稱的清單。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>按名稱撥號 - 使用語音辨識

人員可以使用語音和語音辨識功能在組織中 (其他人) 。 他們也可以說出嘗試尋找之人員的完整或部分名稱，來聯繫 Active Directory 中的任何人。 使用語音輸入可識別不同格式的名稱，包括名字、姓氏、名字 + 姓氏或 LastName + 名字。
  
您可以為自動語音語音機啟用語音辨識，但是 DTMF (鍵盤輸入) 不會停用。 電話鍵盤專案隨時都可以使用，即使自動語音機上已啟用語音辨識也一樣。
  
與電話鍵盤輸入一樣，如果找到多個名稱，來電者會聽到要選取的名稱清單。
  
來電者可以使用下列格式說出名稱：
  
|具有語音的名稱|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |全 |Amos Marble |Amos Marble |
|LastName + FirstName |全  |Marble Amos |Amos Marble |
|FirstName |全 |阿莫斯 |按或說出 1 for Amos Marble  <br/> 按或說出 2 for Amos Press |
|姓氏 |全 |大理石 |按或說出 1 for Amos Marble  <br/> 按下或說出 2 for Ben Marble |
|FirstName 或 LastName |部分 |三月 |按或說出 1 for Mary Marble  <br/> 按 2 for Mary Mary  <br/> 按或說出 3 for AmosUs |
|FirsName + LastName |部分 |Amos Mar |按或說出 1 for Amos Marble  <br/> 按或說出 2 for AmosUs |


> [!NOTE]
> 由於 Active Directory 複寫延遲，新使用者最多可能需要 36 小時，才能將名稱列在具有語音辨識的撥號者名稱目錄中。
  
## <a name="language-support"></a>語言支援

下列語言適用于與外發提示一起使用的文字到語音語音：
  
|-|-|-|
|:-----|:-----|:-----|
|阿拉伯文 (EG)   |英文 (NZ)   |韓 (KO)   |
|中文 (至香港)   |英國 (英文)  |挪威 (否)   |
|中文 (TW)  |美國 (英文)  |波蘭文 (PL)   |
|中文 (ZH)  |芬蘭 (FI)  |葡萄牙文 (BR)  |
|丹麥文 (DA)   |法文 (CA)   |葡萄牙文 (PT)  |
|荷蘭文 (NL)    |法文 (FR)   |俄 (俄羅斯)  |
|英文 (AU)   |德 (DE)  |西班牙文 (ES)   |
|英文 (CA)   |義大利 (IT)  |西班牙文 (MX) |
|英文 (以英文)   |日 (或 JP)  |瑞典文 (SV) |

自動語音語音機的語音辨識輸入提供下列語言：
  
|-|-|
|:-----|:-----|
|中文 (ZH)   |法文 (FR)   |
|英文 (AU)   |德文 (DE)   |
|英文 (CA)   |義大利 (IT)   |
|英文 (以英文)   |日 (或 JP)   |
|英國 (英文)   |葡萄牙文 (BR)   |
|美國 (英文)   |西班牙文 (ES)   |
|法文 (CA)    |西班牙文 (MX)   |

下列語音命令提供語音辨識支援的 14 種語言：
  
|語音命令| 對應至 |
|:-----|:-----|
|是 | 按 1 表示是。 |
|否 | 按 2 尋找 No。 |
|重複 |重複選項清單。 按鍵盤上的 * 以重複選項清單。 |
|運算元 | 按 0 以使用 "運算子" |
|主功能表  |將來電者帶到自動語音機的主功能表。 |
|零 | 預設按 0 (，與 "Operator" 鍵相同) 。|
|一個 | 按 1。 |
|兩 | 按 2。 |
|三| 按 3。|
|四 | 按 4。 |
|五 | 按 5。 |
|六  | 按 6。 |
|七 | 按 7。|
|八 |按 8。|
|九  |按 9。|

## <a name="related-topics"></a>相關主題

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
