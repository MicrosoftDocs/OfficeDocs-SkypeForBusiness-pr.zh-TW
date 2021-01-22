---
title: 什麼是雲端自動 attendants？
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
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
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解雲端自動語音回應，以及如何使用它們讓來電者在功能表系統中移動，以尋找及撥打或將電話轉接給使用者或部門。
ms.openlocfilehash: 862272ffe0cb42edc092c513823f421ab1c5bd95
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918939"
---
# <a name="what-are-cloud-auto-attendants"></a>什麼是雲端自動 attendants？

電話系統提供自動語音回應，可用來讓外部和內部來電者在功能表系統中移動，以尋找及撥打或將電話轉接至您組織的使用者或部門。
  
自動語音留言機通常是系統的節點，為來電者提供一系列的語音提示或音訊檔案，而非由接線生聆聽。 當人員撥打與自動參與人員關聯的號碼時，他們的選擇可以將電話重新導向至使用者，或找到您組織中某個人，然後連接到該使用者。 他們可以使用數位鍵台或語音辨識來表達 (功能表系統) 互動。 他們所做的選擇也可以將通話重新導向至另一個自動 attendant 或通話佇列。
  
若要設定電話系統的自動 Attendant，請前往設定[雲端自動 Attendant。](create-a-phone-system-auto-attendant.md)
  
雲端自動 Attendant 具有下列功能：
  
- 它可以提供公司或資訊歡迎詞。
- 它可以提供自訂的公司功能表。 您可以將這些功能表自訂為多個層級。
- 它提供目錄搜尋功能，讓來電者在組織目錄中搜尋名稱。
- 此功能可讓來電者聯繫或留下訊息給貴組織的人。
- 它支援多種語言的提示、文字到語音和語音辨識。
- 支援指定假日和上班時間。
- 支援將通話轉接至運算子、其他使用者、通話佇列和自動有話方。
- 它支援讓來電者留言給組織的共用語音信箱。

> [!NOTE]
> 本文同時適用于 Microsoft Teams 和商務用 Skype Online。

## <a name="getting-started"></a>快速入門

若要開始使用自動 attendants，請記得這一點：

- 需要自動 Attendant，才能有相關聯的資源帳戶。 請參閱 [在 Teams 中管理資源](manage-resource-accounts.md) 帳戶，以瞭解有關資源帳戶的詳細資訊。 <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- 當您將電話號碼指派給自動 Attendant 時，請嚴格來說，您將電話號碼指派給與該自動 Attendant 相關聯的資源帳戶。 如此一來，可讓多個電話號碼存取自動 Attendant。 通常資源帳戶會使用無成本的電話系統虛擬使用者授權。 此授權提供組織層級的電話號碼的電話系統功能，並可讓您建立自動撥打和通話佇列。

> [!NOTE]
> Microsoft Teams 使用者和通話代理程式只支援自動撥打服務佇列和通話佇列的直接路由服務號碼。

   > [!TIP]
   > 若要將電話重新導向至具有電話系統授權之線上使用者的運算子或功能表選項，您必須為其啟用企業語音帳戶，或將通話方案指派給他們。 請參閱 [指派 Microsoft Teams 附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。 您也可以使用 Windows PowerShell。 例如，執行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要取得及使用自動撥打的免付費服務號碼，您必須設定通訊信用額度。 若要這麼做，請參閱 [什麼是通訊信用額度？](what-are-communications-credits.md) 以及為貴組織設定 [通訊信用額度](set-up-communications-credits-for-your-organization.md)。

    > [!IMPORTANT]
    > 使用者 (指派) 自動參與，只能使用服務付費或免付費電話號碼。

- 完整的自動參與系統通常會涉及多個自動 Attendant。
- 有可能是將多個電話號碼適用于進入層級的自動 Attendant。
- 若非進入層級的自動參與或整個系統的通話佇列，只要撥打出線 PSTN 電話，就只需要電話號碼。
  
## <a name="feature-overview"></a>功能概觀

### <a name="searching-for-users"></a>搜尋使用者

按名稱撥號是自動 Attendant 的一項功能，亦稱為目錄搜尋。 它可讓撥打自動語音應答的人使用語音 (語音辨識) 或電話鍵盤 (DTMF) 回應，以輸入完整或部分名稱來搜尋公司的目錄、尋找人員，然後將電話轉接給他們。 想要使用名稱撥號來尋找和聯繫的使用者，不需要有電話號碼或已指派通話方案給他們，但是如果他們是線上使用者，或為商務用 **Skype Server** 使用者啟用企業語音，則必須擁有電話系統授權。 使用名稱撥號甚至可以為在多國組織所託管的不同國家/地區中的 Microsoft Teams 使用者尋找和轉接電話。 基於先決條件，您可以在自動參與中明確啟用按名稱撥號。

分機號碼是自動參與的一項功能，也是目錄搜尋的一部分。 讓撥打自動語音應答的人使用語音 (語音辨識) 或電話鍵盤 (DTMF) 回應，輸入他們嘗試聯繫之使用者的電話分機，然後將電話轉接給他們。 您可能想要使用撥號分機號碼來尋找和聯繫的使用者，不需要有電話號碼或已指派通話方案給他們，但是如果他們是線上使用者，或為商務用  **Skype Server** 使用者啟用企業語音，則必須擁有電話系統授權。 您也需要為使用者適當配置的撥號方案。 撥打分機號碼甚至可以為在多國組織所託管的不同國家/地區中的 Microsoft Teams 使用者尋找和轉接電話。 在先決條件中，您可以明確啟用自動 Attendant 中的 Dial by extension。

#### <a name="maximum-directory-size"></a>目錄大小上限

當來電者搜尋特定人員時，Active Directory 使用者按名稱撥號及撥號者分機號碼可支援的數量沒有限制。 來電者可以輸入名字 + 姓氏 (部分或全名，也可以輸入 LastName + 名字) ，但需要完整的分機號碼。 單一自動語音語音機支援使用語音辨識的名稱清單大小上限為 80，000 個使用者。
  
|輸入類型|搜尋格式|組織中使用者數目上限|
|:-----|:-----|:-----|
|DTMF (鍵台專案)  |部分  <br/> FirstName + LastName  <br/> LastName + FirstName |沒有限制  |
|語音 (語音輸入)  |FirstName  <br/> 姓氏  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80，000 個使用者 |

> [!NOTE]
> 如果您使用具有語音辨識的按名稱撥號，但貴組織的 Active Directory 超過 80，000 個使用者，而且您沒有限制使用撥號範圍功能按名稱撥號的範圍，則使用電話鍵盤的來電者仍可使用撥號鍵台，而且語音輸入也可供所有其他情況使用。 您可以使用撥號範圍功能，變更特定自動 Attendant 的撥號方式範圍，縮小可聯繫的名稱。
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>按名稱撥號 - 數位鍵台 (DTMF) 專案

撥入的使用者可以使用撥號名稱來聯繫使用者，方法為指定嘗試聯繫之人員的完整名稱或部分名稱。 輸入名稱時，可以使用各種不同的格式。

搜尋組織的目錄時，人員可以使用 '0' (零) 鍵來表示名字與姓氏或姓氏之間的空格。 當他們輸入名稱時，會要求他們使用 # 鍵終止鍵盤專案。 例如，「輸入您嘗試聯繫的人名後，請按 #」。 如果找到多個名稱，來電者會提供一份名稱清單以選取。
  
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

#### <a name="dial-by-name---name-recognition-with-speech"></a>按名稱撥號 - 使用語音辨識

人員可以使用語音和語音辨識功能在組織中 (其他人) 。 他們也可以說出想要尋找的人名，與 Active Directory 中的任何人聯繫。 使用語音輸入可識別不同格式的名稱，包括名字、姓氏、名字 + 姓氏或 LastName + 名字。
  
您可以為自動語音語音機啟用語音辨識，但是 DTMF (鍵盤輸入) 不會停用。 電話鍵盤專案隨時都可以使用，即使自動語音機上已啟用語音辨識也一樣。
  
與電話鍵盤專案一樣，如果找到多個名稱，來電者會聽到要選取的名稱清單。
  
來電者可以使用下列格式說出名稱：
  
|具有語音的名稱|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |全 |Amos Marble |Amos Marble |
|LastName + FirstName |全  |Marble Amos |Amos Marble |
|FirstName |全 |阿莫斯 |按或說出 1 for Amos Marble  <br/> 按或說出 2 for Amos Press |
|姓氏 |全 |大理石 |按或說出 1 for Amos Marble  <br/> 按或說出 2 以使用 Ben Marble |

> [!NOTE]
> 由於 Active Directory 複寫延遲，新使用者最多可能需要 36 小時，才能將名稱列在具有語音辨識的撥號者名稱目錄中。
  
### <a name="language-support"></a>語言支援

下列語言適用于與外發提示一起使用的文字到語音語音：
  
|A-E|E-J|K-Z|
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
  
|A-F|F-Z|
|:-----|:-----|
|中文 (ZH)   |法文 (FR)   |
|英文 (AU)   |德 (DE)   |
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
|運算元 | 按 0 以使用"運算子" |
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

### <a name="the-operator-option"></a>運算子選項

您可以選擇性地設定自動語音語音機，讓來電者選擇與接線生通話。
  
根據預設，按鍵 0 和語音命令「運算子」將呼叫引導至指定的運算子。 這是語音辨識支援之所有語言的情況。 您也可以使用設定 **功能表選項** 來設定運算子的自訂值。
  
運算子可以設定為：
  
- Microsoft Teams 使用者或已啟用企業語音功能的商務用 Skype Server 使用者。
- 為您的組織所設定的另一個自動 Attendant。
- 在貴組織中設定的任何現有通話佇列。 若要查看通話佇列的更多資訊，請參閱建立 [雲端通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

### <a name="business-hours-and-call-handling"></a>上班時間和來電處理

您可以設定每個自動 Attendant 的上班時間。 如果未設定上班時間，則一天中所有的天和小時會被視為上班時間，因為預設會設定 24/7 排程。 您可以設定上班時間與一天中的時間，未設定為上班時間的所有小時會被視為後半小時。 您可以設定不同的來電處理選項和不同的問候語 (為) 與上班時間選擇。
  
每個自動 attendant 都有數種可能的來電處理選項：
  
- 播放問候語後，通話可能會中斷連接。
- 您也可以：
  - 將通話重新導向至擁有已啟用企業語音功能的電話系統授權或已指派通話方案給 Microsoft Teams 使用者的 Microsoft Teams 使用者。 您可以設定讓來電者可以撥打語音信箱。 若要這麼做，請選取您 **公司** 中的某個人員，並設定讓此人的電話自動直接轉到語音信箱。

  - 將通話重新導向至通話佇列。 若要查看通話佇列的更多資訊，請參閱建立 [雲端通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

  - 將來電重新導向至另一個自動 Attendant。

當自動語音機在播放功能表提示時，自動語音回應會向來電者表示這些選項。 例如：「按 1 for Sales，按 2 for Services。 若要與運算子說話，隨時請按 0。」

### <a name="set-menu-options"></a>設定功能表選項

雲端自動語音回應允許您建立功能表提示 (「按 1 for Sales，按 2 for Services」) 並設定功能表選項，根據使用者的選擇來路由通話。 自動語音導覽的功能表選項，讓組織提供一系列選項，引導來電者更快抵達目的地，而不需要仰賴接線生處理來電。 功能表提示可能是使用文字到語音 (系統產生的提示) 或上傳錄製的音訊檔案所建立。 語音辨識可接受免手流覽的語音命令，但來電者也可使用電話鍵盤來流覽功能表。
  
您可以使用商務用 Skype 系統管理中心，將按鍵 0 到 9 指派給自動 Attendant 中的撥號鍵。 您可以針對上班時間和後半小時建立不同的功能表選項組，而且您可以在功能表選項中啟用或停用按名稱 **撥號**。 按鍵可以對應至以下專案：
  
- 一個預設對應到按鍵 0 的運算子。 不過，您可以將其重新指派給任何其他金鑰，或移除功能表中的金鑰。
- 通話佇列。
- 另一個自動 Attendant。 您可以設定多層次功能表，將一個自動 Attendant中的功能表選項指向另一個自動 Attendant，並擁有自己的功能表選項組 ，稱為「巢中」自動 Attendant。
- 擁有已啟用企業語音功能的電話系統授權或已指派通話方案給 Microsoft Teams 使用者的 Microsoft Teams 使用者。 您可以設定讓來電者可以撥打語音信箱。 若要這麼做，請選取您 **公司** 中的某個人員，並設定讓此人的電話自動直接轉到語音信箱。
  
如果已啟用語音辨識，每個功能表選項的名稱就會變成語音辨識關鍵字。 例如，來電者可以說「一」以選取對應到按鍵 1 的功能表選項，或說出「銷售」以選取名為「銷售」的相同功能表選項。
  
若要設定自動 Attendant 和功能表選項，請前往設定[雲端自動 attendant。](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>為自動 Attendant 指派電話號碼

您可以指派 Microsoft 服務號碼、直接路由號碼或混合式號碼到自動 Attendant 的連結資源帳戶 (或多個資源帳戶 ，如果需要多個電話號碼) 。 請參閱 [規劃直接路由以](direct-routing-plan.md) 進一步查看詳細資料。

若要指派服務號碼，您必須取得或埠現有的付費或免付費服務號碼。 當您取得付費或免付費服務電話號碼後，這些號碼會顯示在商務用 **Skype 系統管理中心**  >  **語音**  >  **電話號碼中**。 **號碼類型** 列為服務 **- 免付費**。 若要取得您的服務號碼，請參閱取得商務用 Skype 和[Microsoft Teams](/microsoftteams/getting-service-phone-numbers)的服務電話號碼;如果您想要移轉現有服務號碼，請參閱將電話號碼移轉[至 Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> 如果您位於美國以外的地區，您不可以使用 Microsoft Teams 系統管理中心取得服務號碼。 請 [改為前往管理您組織](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 的電話號碼，查看如何執行。
  
## <a name="related-topics"></a>相關主題

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
