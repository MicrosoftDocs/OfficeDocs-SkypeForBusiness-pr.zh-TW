---
title: 自動語音應答和通話佇列撥號和語音辨識參照
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 瞭解 Teams 中的自動語音應答和通話佇列撥號和語音辨識選項。
ms.openlocfilehash: 93a20be62f09ed7b636c593ecac48927d70e237f
ms.sourcegitcommit: 55ba3ed53421da6619724a360d15e80262241079
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/28/2022
ms.locfileid: "67070724"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自動語音應答和通話佇列撥號和語音辨識參照

[依名稱或分機撥號] 是一種自動語音應答功能，可讓來電者與貴組織中的 Teams 使用者聯繫。 使用語音或電話鍵台來電者可以說出或輸入他們想要連絡之人員的完整或部分名稱或副檔名。 自動語音應答會搜尋公司目錄、找出該人員，然後將來電者轉接給他們。  [依名稱撥號] 或 [依擴充功能撥號] 是您 [在自動語音應答中設定通話流程設定](create-a-phone-system-auto-attendant.md?tabs=call-flow)時所設定的選項。

## <a name="searching-for-users"></a>搜尋使用者

使用 [依名稱撥號] 可以連絡的 Teams **使用者不需要有電話號碼或已指派通話方案給他們，但是必須為商務用 Skype Server使用者啟用企業語音**。 對於多國組織，[依名稱撥號] 會尋找來電者，並將來電轉移給位於不同國家或地區的 Microsoft Teams 使用者。

使用擴充功能可以使用撥號聯繫的 Teams 使用者 **不需要有電話號碼或已指派通話方案給他們，但是必須企業語音啟用商務用 Skype Server使用者**。 您也需要為使用者設定適當的撥號對應表。 如果是多國組織，「透過擴充功能撥號」可尋找來電者，並將來電者轉接給位於不同國家或地區的 Microsoft Teams 使用者。

在設定自動語音應答時，必須明確啟用 [依名稱撥號] 或 [擴充功能] 的必要條件。

### <a name="maximum-directory-size"></a>目錄大小上限

當來電者搜尋特定人員時，[依名稱撥號] 和 [由分機撥號] 可以支援的 Active Directory 使用者數量沒有限制。 來電者可以輸入部分或全名 (FirstName + LastName，也可以輸入 LastName + FirstName) ，但需要完整的分機號碼。 單一自動語音應答可使用語音辨識支援的最大名稱清單大小為 80，000 個使用者。
  
|輸入類型|搜尋格式|組織中的使用者人數上限|
|:-----|:-----|:-----|
|DTMF (鍵台專案)  |部分  <br/> FirstName + LastName  <br/> LastName + FirstName |沒有限制  |
|語音 (語音輸入)  |FirstName  <br/> 姓氏  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80，000 個使用者 |

> [!NOTE]
> 如果您在語音辨識中使用 [依名稱撥號]，但貴組織的 Active Directory 大於 80，000 個使用者，而且您尚未使用 [[撥號](create-a-phone-system-auto-attendant.md?tabs=dial-scope) 範圍] 功能限制 [依名稱撥號] 範圍，則使用電話鍵台的來電者仍可使用 [依名稱撥號]，而語音輸入則適用于所有其他案例。 您可以使用 [撥號範圍] 功能，藉由變更特定自動語音應答的 [依名稱撥號] 範圍，縮小可連絡的名稱範圍。

### <a name="search-considerations"></a>搜尋考慮

[依名稱撥號] 先搜尋整個組織的目錄，然後再套用任何已設定的 [撥號範圍包括] 或 [排除] 清單。 如果針對整個目錄的初始搜尋傳回超過 100 個使用者，則不會套用 [撥號範圍] 清單，搜尋將會失敗，而且會告知來電者發現太多名稱。

## <a name="dial-by-name---keypad-dtmf-entry"></a>依名稱撥號 - 鍵台 (DTMF) 專案

撥入的人員可以使用 [依名稱撥號] 與使用者聯繫，方法是指定他們嘗試連絡之人員的完整或部分名稱。 輸入名稱時，可以使用各種不同的格式。

搜尋貴組織的目錄時，人員可以使用「0」 (零) 鍵來表示名字與姓氏或名字和名字之間有空格。 當他們輸入名稱時，系統會要求他們使用 # 鍵終止其鍵盤輸入。 例如，「輸入您要連絡的人員名稱之後，請按 #」。 如果有找到多個名稱，通話者會收到一份要從中選取的名稱清單。

> [!NOTE]
> 如果套用了任何 [電話撥號範圍包括] 或 [排除] 清單之後，仍有 5 個以上的名稱，搜尋將會失敗，而且會告訴來電者發現太多名稱。
  
人員可以在手機鍵臺上使用下列搜尋格式搜尋貴組織中的名稱：
  
|名稱格式|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |全  |Amos0Marble# |Amos Marble |
|LastName + FirstName |全 |Marble0Amos#  |Amos Marble |
|FirstName  |全   |阿莫斯#   |按 1 以取得 Amos Marble  <br/> 按 2 以取得 Amos Lens |
|姓氏 |全 |大理石#  |按 1 以取得 Amos Marble  <br/> 按 2 以取得 Mary Marble |
|FirstName 或 LastName |部分 |三月# |按 1 以取得 Mary Marble  <br/> 按 2 以取得 MaryJones  <br/> 按 3 以取得 Amos Lens |
|FirsName + LastName |部分 |Amos0Mar# |按 1 以取得 Amos Marble  <br/> 按 2 以取得 Amos Lens |
|LastName + FirstName |部分 |Mar0Am# |按 1 以取得 Amos Marble  <br/> 按 2 以取得 Amos Lens |

搜尋使用手機鍵台的人員時，會使用幾個特殊字元。 例如，系統會要求人員使用井字型大小鍵 (#) ，而零 (0) 鍵則用於名稱之間的空格。 按下星鍵 (*) 會重複該人員的相符名稱清單。
  
|特殊手機鍵台字元|代表的意義|
|:-----|:-----|
|#   |輸入名稱時的結尾字元。 |
|0   |名稱之間的空格。 |
|*    |重複列出相符的名稱。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>依名稱撥號 - 使用語音進行名稱識別

人員可以使用語音 (語音辨識) 搜尋組織中的其他人。 他們也可以說出他們嘗試尋找之人員的完整或部分名稱，來連絡 Active Directory 中的任何人。 使用語音輸入可以辨識各種格式的名稱，包括 FirstName、LastName、FirstName + LastName 或 LastName + FirstName。
  
您可以為自動語音應答啟用語音辨識，但是 DTMF)  (手機鍵盤專案並不會停用。 即使自動語音應答已啟用語音辨識，也可以隨時使用手機鍵台專案。
  
與電話鍵台專案一樣，如果找到多個名稱，通話者會聽到要從中選取的名稱清單。

> [!NOTE]
> 如果套用了任何 [電話撥號範圍包括] 或 [排除] 清單之後，仍有 5 個以上的名稱，搜尋將會失敗，而且會告訴來電者發現太多名稱。
  
來電者可以使用下列格式說出名稱：
  
|使用語音命名|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |全 |Amos Marble |Amos Marble |
|LastName + FirstName |全  |Marble Amos |Amos Marble |
|FirstName |全 |阿莫斯 |按下或說出 Amos Marble 的 1  <br/> 按下或說 2 表示 AmosJoner |
|姓氏 |全 |大理石 |按下或說出 Amos Marble 的 1  <br/> 按下或說出 Ben Marble 的 2 |
|FirstName 或 LastName |部分 |三月 |按下或說出 Mary Marble 的 1  <br/> 為 MaryJones 按下或說 2  <br/> 按下或說出 3 表示 Amos Lens |
|FirsName + LastName |部分 |Amos Mar |按下或說出 Amos Marble 的 1  <br/> 按下或說 2 表示 Amos Lens |

> [!NOTE]
> 由於 Active Directory 複寫延遲，新使用者可能需要長達 36 小時，才會在具有語音辨識的 [依名稱撥號] 目錄中列出他們的名稱。

### <a name="dial-by-extension"></a>透過擴充功能撥號

您想要用於 **Dial By Extension** 的使用者必須將擴充功能指定為下列其中一個在 Active Directory 中定義的電話屬性的一部分， (並透過 Azure AD Connect) 或 Azure Active Directory 進行同步處理。  (如需詳細資訊，請參閱 [個別或大量新增使用者](/microsoft-365/admin/add-users/add-users) 。) 

- TelephoneNumber (AD 和 Azure AD) 
- HomePhone (AD) 
- 行動 (AD 和 Azure AD) 
- OtherTelephone (AD) 

在使用者電話號碼欄位中輸入擴充功能所需的格式可以是下列其中一種格式：

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- 範例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber 「+15555555678;ext=5678」
- 範例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber 「+15555555678x5678」
- 範例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber 「x5678」

您可以在[Microsoft 365 系統管理中心](https://admin.microsoft.com/)或[Azure Active Directory 系統管理中心](https://aad.portal.azure.com)中設定擴充功能。 自動語音應答和通話佇列最多可能需要 12 小時才能進行變更。

> [!NOTE]
>  如果使用 TelephoneNumber 功能變數來定義擴充功能，Microsoft 建議您使用 *;ext= \<extension> 格式 + \<phone number>*。 如果使用者也被指派了 Teams 電話號碼，您應該以相同的方式定義這兩個號碼。


## <a name="language-support"></a>語言支援

這些支援的語言提供文字轉換語音和語音辨識的 [語言支援](create-a-phone-system-auto-attendant-languages.md)。

下列語音命令適用于語音辨識：
  
|語音命令| 對應至 |
|:-----|:-----|
|是 | 按 1 表示是。 |
|否 | 按 2 表示 [否]。 |
|重複 |重複選項清單。 按下鍵臺上的 * 以重複選項清單。 |
|運算元 | 按 0 以取得「運算子」 |
|主功能表  |將來電者帶到自動語音應答的主功能表。 |
|零 | 根據預設，按 0 (，與 [運算子] ) 相同。|
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

[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](./getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
