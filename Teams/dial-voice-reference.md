---
title: 自動語音留言和通話佇列撥號和語音辨識參照
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
description: 瞭解自動語音留言和通話佇列撥號和語音辨識選項，Teams。
ms.openlocfilehash: 6dfb1265d3eb5e1200a2b0638d66415c025ed7682c222aa51767d8a5fea3e0f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344302"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自動語音留言和通話佇列撥號和語音辨識參照

按名稱撥號是自動總機的功能，也稱為目錄搜尋。 它可讓撥打您的自動語音應答的人使用語音 (語音辨識) 或電話鍵台 (DTMF) 回應，以輸入完整或部分名稱來搜尋公司的目錄、尋找該人員，然後將電話轉接給他們。 當您在自動電話機中設定通話 [流程](create-a-phone-system-auto-attendant.md#call-flow)設定時，您可以設定按名稱撥號。

## <a name="searching-for-users"></a>搜尋使用者

您用名稱撥號來尋找和聯繫的使用者不需要擁有電話號碼，或已指派通話方案給他們，但他們必須企業語音使用者商務用 Skype Server **啟用**。 使用名稱撥號甚至可以尋找並轉接電話給Microsoft Teams國家/地區為多國組織託管的使用者。 根據相關先決條件，您可以在自動話務員中明確啟用按名稱撥號。

分機撥號功能是一項自動總機功能，也是目錄搜尋的一部分。 它可讓撥打您的自動語音應答的使用者使用語音 (語音辨識) 或電話鍵台 (DTMF) 回應，輸入他們嘗試聯繫之使用者的電話分機，然後將通話轉接給他們。 您用分機撥號來尋找和聯繫的使用者不需要擁有電話號碼，或已指派通話方案給他們，但他們必須企業語音使用者 **商務用 Skype Server。** 您也需要為使用者提供適當的撥號方案。 撥打分機甚至能尋找並轉接電話給Microsoft Teams國家/地區為多國組織託管的使用者。 根據相關先決條件，您可以在自動話務員中明確啟用分機撥號。

### <a name="maximum-directory-size"></a>目錄大小上限

當來電者搜尋特定人員時，Active Directory 使用者按名稱撥號和分機撥號可支援的數量沒有限制。 來電者可以在 FirstName + 姓氏 (中輸入部分或全名，也可以輸入姓氏 + 名字) ，但需要完整的分機號碼。 單一自動語音機可以使用語音辨識支援的名稱清單大小上限為 80，000 個使用者。
  
|輸入類型|搜尋格式|組織中使用者數上限|
|:-----|:-----|:-----|
|DTMF (鍵盤輸入)  |部分  <br/> FirstName + LastName  <br/> LastName + FirstName |沒有限制  |
|語音 (語音輸入)  |FirstName  <br/> 姓氏  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80，000 個使用者 |

> [!NOTE]
> 如果您使用具有語音辨識的撥號名稱，但貴組織的 Active Directory 超過 80，000 個使用者，而且您尚未使用撥號範圍功能限制按名稱撥號的範圍，則使用電話鍵台撥號的來電者仍可使用名稱撥號，而語音輸入則適用于所有其他案例。 您可以使用撥號範圍功能，變更特定自動總機的撥號範圍，縮小可到達的名稱。
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>按名稱撥號 - 鍵盤 (DTMF) 專案
撥入的使用者可以使用撥號名稱來聯繫使用者，指定他們嘗試聯繫之人員的完整名稱或部分名稱。 輸入名稱時，可以使用各種格式。

搜尋貴組織的目錄時，人員可以使用 "0" () 鍵來表示名字與姓氏或姓氏與名字之間的空格。 當他們輸入名稱時，會要求他們以 # 鍵終止鍵盤輸入。 例如，「輸入您嘗試聯繫之人員的名稱之後，請按 #」。 如果找到多個名稱，通話者會獲得一份名稱清單，以選取名稱。
  
人員可以使用電話鍵臺上的下列搜尋格式來搜尋貴組織的名稱：
  
|名稱格式|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |全  |Amos0Marble# |Amos Marble |
|LastName + FirstName |全 |Marble0有一些#  |Amos Marble |
|FirstName  |全   |阿莫斯#   |按 1 for Amos Marble  <br/> 按 2 for Amos Marus |
|姓氏 |全 |大理石#  |按 1 for Amos Marble  <br/> 按 2 for Mary Marble |
|FirstName 或 LastName |部分 |三月# |按 1 for Mary Marble  <br/> 按 2 for Mary Jones  <br/> 按 3 for Amos Marus |
|FirsName + LastName |部分 |Amos0Mar# |按 1 for Amos Marble  <br/> 按 2 for Amos Marus |
|LastName + FirstName |部分 |Mar0Am# |按 1 for Amos Marble  <br/> 按 2 for Amos Marus |

使用電話鍵台搜尋人員時，會使用幾個特殊字元。 例如，系統將會要求該人員使用井號鍵 (#) ，而零 (0) 鍵則用於名稱之間的空格。 按星號鍵 (*) 會重複該人員符合的名稱清單。
  
|特殊電話鍵台字元|代表什麼|
|:-----|:-----|
|#   |輸入名稱時結束字元。 |
|0   |名稱之間的空格。 |
|*    |重複符合名稱的清單。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>按名稱撥號 - 使用語音辨識名稱

使用者可以使用語音和語音辨識功能搜尋 (組織) 。 他們也可以說出他們嘗試尋找之人員的完整或部分名稱，來聯繫 Active Directory 中的任何人。 使用語音輸入可以識別各種格式的名稱，包括名字、姓氏、名字 + 姓氏或姓氏 + 名字。
  
您可以為自動語音機啟用語音辨識，但 DTMF (鍵盤輸入) 不會停用。 電話自動語音機已啟用語音辨識，也隨時都可以使用鍵盤輸入功能。
  
與電話鍵盤專案一樣，如果找到多個名稱，通話者會聽到要選取的名稱清單。
  
來電者可以使用下列格式說出名稱：
  
|具有語音的名稱|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |全 |Amos Marble |Amos Marble |
|LastName + FirstName |全  |Marble Amos |Amos Marble |
|FirstName |全 |阿莫斯 |按或說出 1 for Amos Marble  <br/> 按或說出 2 for AmosJojos |
|姓氏 |全 |大理石 |按或說出 1 for Amos Marble  <br/> 按或說出 2 for Ben Marble |
|FirstName 或 LastName |部分 |三月 |按或說出 1 for Mary Marble  <br/> 按或說出 2 for Mary Jones  <br/> 按或說出 3 for Amos |
|FirsName + LastName |部分 |Amos Mar |按或說出 1 for Amos Marble  <br/> 按或說出 2 for Amos |


> [!NOTE]
> 由於 Active Directory 複寫延遲，新使用者最多可能需要 36 小時，才能將名稱列在具有語音辨識的撥號名稱目錄中。
  
## <a name="language-support"></a>語言支援

這些支援的語言提供文字對語音和語音辨識 [的語言支援](create-a-phone-system-auto-attendant-languages.md)。

下列語音命令可用於語音辨識： 
  
|語音命令| 對應至 |
|:-----|:-----|
|是 | 按 1 表示是。 |
|否 | 按 2 表示否。 |
|重複 |重複選項清單。 按鍵盤上的 * 以重複選項清單。 |
|運算元 | 按 0 以尋找 「運算子」 |
|主功能表  |將來電者帶到自動語音機的主功能表。 |
|零 | 按 0 (，與 「運算子」) 。|
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

[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](./getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
