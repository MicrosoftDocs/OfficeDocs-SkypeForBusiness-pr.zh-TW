---
title: 什麼是雲端自動總機？
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
description: 瞭解雲端自動語音服務，以及如何使用它們讓來電者在功能表系統之間移動，以尋找及撥打或轉接電話給使用者或部門。
ms.openlocfilehash: c8e5b3f608200036b8c9b9ed5338c558464b32d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100959"
---
# <a name="what-are-cloud-auto-attendants"></a>什麼是雲端自動總機？

電話系統自動語音機，可用來讓外部和內部來電者在功能表系統之間移動，以尋找及撥打或轉接電話給貴組織的使用者或部門。
  
自動語音留言通常是系統中的節點，為來電者提供一系列語音提示或音訊檔案，而不是由接線生聽到。 當人員撥打與自動話務員相關聯的號碼時，他們的選擇可以將通話重新導向給使用者，或找到您組織中的人，然後連至該使用者。 他們可以使用電話鍵台或 DTMF (或語音辨識) 功能表系統進行互動。 他們所做的選擇也可以將通話重新導向到另一個自動電話機或通話佇列。
  
若要設定自動電話系統，請前往 設定[雲端自動](create-a-phone-system-auto-attendant.md)助理。
  
雲端自動助理具有下列功能：
  
- 它可以提供公司或資訊問候語。
- 它可以提供自訂的公司功能表。 您可以將這些功能表自訂為具有多個層級。
- 它提供目錄搜尋功能，可讓來電者在組織的目錄中搜尋名稱。
- 它可讓來電者與貴組織人員聯繫或留言。
- 它支援多種語言的提示、文字到語音和語音辨識。
- 它支援指定假日和上班時間。
- 它支援將通話轉接給接線生、其他使用者、通話佇列和自動話務員。
- 它支援讓來電者為組織留言的共用語音信箱。

> [!NOTE]
> 本文適用于線上Microsoft Teams商務用 Skype。

## <a name="getting-started"></a>快速入門

若要開始使用自動話務員，請記得：

- 需要自動話務員才能擁有相關聯的資源帳戶。 請參閱[管理資源帳戶Teams，](manage-resource-accounts.md)以瞭解有關資源帳戶的詳細資訊。 <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- 當您將電話號碼指派給自動電話機時，請嚴格來說，您將電話號碼指派給與該自動電話機相關聯的資源帳戶。 這提供一種方式，讓多個電話號碼存取自動總機。 通常，資源帳戶會使用免費虛擬使用者電話系統授權。 此授權電話系統提供組織層級的電話號碼功能，並可讓您建立自動電話機和通話佇列。

> [!NOTE]
> 只有使用者和通話代理程式支援自動Microsoft Teams和通話佇列的直接路由服務號碼。

   > [!TIP]
   > 若要將通話重新導向至具有 電話系統 授權之線上使用者的運算子或功能表選項，您必須為其帳戶啟用 企業語音 或指派通話方案給他們。 請參閱[指派Microsoft Teams附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。 您也可以使用Windows PowerShell。 例如，執行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要取得及使用自動乘務員免付費服務號碼，您必須設定通訊信用額度。 若要這麼做，請參閱 [什麼是通訊信用額度？](what-are-communications-credits.md) 以及為貴組織設定 [通訊信用額度](set-up-communications-credits-for-your-organization.md)。

    > [!IMPORTANT]
    > 使用者 (訂閱) 無法指派給自動電話機 - 只能使用服務付費或免付費電話號碼。

- 完整的自動機務員系統通常會涉及多個自動總機。
- 有可能將多個電話號碼適用于進入層級的自動總機。
- 非進入層級的自動總機或通話佇列，只有在他們撥打外接 PSTN 通話時，才需要電話號碼。
  
## <a name="feature-overview"></a>功能概觀

### <a name="searching-for-users"></a>搜尋使用者

按名稱撥號是自動助理的一項功能，也稱為目錄搜尋。 它可讓撥打您的自動語音應答的人使用語音 (語音辨識) 或電話鍵台 (DTMF) 回應，以輸入完整或部分名稱來搜尋公司的目錄、尋找該人員，然後將電話轉接給他們。 您用名稱撥號來尋找和聯繫的使用者不需要擁有電話號碼，或已指派通話方案給他們，但他們必須有 電話系統 授權，如果他們是線上使用者，或 企業語音 使用者已啟用 **商務用 Skype Server 企業語音。** 按名稱撥號甚至可以尋找並轉接電話給Microsoft Teams國家/地區為多國組織託管的使用者。 根據相關先決條件，您可以在自動話務員中明確啟用按名稱撥號。

分機撥號功能是一項自動總機功能，也是目錄搜尋的一部分。 它可讓撥打您的自動語音應答的使用者使用語音 (語音辨識) 或電話鍵台 (DTMF) 回應，輸入他們嘗試聯繫之使用者的電話分機，然後將通話轉接給他們。 您用分機撥號來尋找和聯繫的使用者不需要擁有電話號碼，或已指派通話方案給他們，但他們必須有 電話系統 授權，如果他們是線上使用者，或 商務用 Skype Server 使用者已啟用 **企業語音。** 您也需要為使用者提供適當的撥號方案。 撥打分機甚至能尋找並轉接電話給Microsoft Teams國家/地區為多國組織託管的使用者。 根據相關先決條件，您可以在自動話務員中明確啟用分機撥號。

#### <a name="maximum-directory-size"></a>目錄大小上限

當來電者搜尋特定人員時，Active Directory 使用者按名稱撥號和分機撥號可支援的數量沒有限制。 來電者可以在 FirstName + 姓氏 (中輸入部分或全名，也可以輸入姓氏 + 名字) ，但需要完整的分機號碼。 單一自動語音機可以使用語音辨識支援的名稱清單大小上限為 80，000 個使用者。
  
|輸入類型|搜尋格式|組織中使用者數上限|
|:-----|:-----|:-----|
|DTMF (鍵盤輸入)  |部分  <br/> FirstName + LastName  <br/> LastName + FirstName |沒有限制  |
|語音 (語音輸入)  |FirstName  <br/> 姓氏  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80，000 個使用者 |

> [!NOTE]
> 如果您使用具有語音辨識的撥號名稱，但貴組織的 Active Directory 超過 80，000 個使用者，而且您尚未使用撥號範圍功能限制按名稱撥號的範圍，則使用電話鍵台撥號的來電者仍可使用名稱撥號，而語音輸入則適用于所有其他案例。 您可以使用撥號範圍功能，變更特定自動總機的撥號範圍，縮小可到達的名稱。
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>按名稱撥號 - 鍵盤 (DTMF) 專案

撥入的使用者可以使用撥號名稱來聯繫使用者，指定他們嘗試聯繫之人員的完整名稱或部分名稱。 輸入名稱時，可以使用各種格式。

搜尋貴組織的目錄時，人員可以使用 "0" () 鍵來表示名字與姓氏或姓氏與名字之間的空格。 當他們輸入名稱時，會要求他們以 # 鍵終止鍵盤輸入。 例如，「輸入您嘗試聯繫的人名之後，請按 #」。 如果找到多個名稱，通話者會獲得一份名稱清單，以選取名稱。
  
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

使用電話鍵台搜尋人員時，會使用幾個特殊字元。 例如，系統將會要求該人員使用井號鍵 (#) ，而零 (0) 鍵則用於名稱之間的空格。 按星號鍵 (*) 會重複該人員符合名稱的清單。
  
|特殊電話鍵台字元|代表什麼|
|:-----|:-----|
|#   |輸入名稱時結束字元。 |
|0   |名稱之間的空格。 |
|*    |重複符合名稱的清單。 |

#### <a name="dial-by-name---name-recognition-with-speech"></a>按名稱撥號 - 使用語音辨識名稱

使用者可以使用語音和語音辨識功能搜尋 (組織) 。 他們也可以說出他們嘗試尋找之人員的名稱，來聯繫 Active Directory 中的任何人。 使用語音輸入可以識別各種格式的名稱，包括名字、姓氏、名字 + 姓氏或姓氏 + 名字。
  
您可以為自動語音機啟用語音辨識，但 dTMF (鍵盤輸入) 不會停用。 電話自動語音機已啟用語音辨識，也隨時都可以使用鍵盤輸入功能。
  
與電話鍵盤專案一樣，如果找到多個名稱，通話者會聽到要選取的名稱清單。
  
來電者可以使用下列格式說出名稱：
  
|具有語音的名稱|搜尋類型|範例|搜尋結果|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |全 |Amos Marble |Amos Marble |
|LastName + FirstName |全  |Marble Amos |Amos Marble |
|FirstName |全 |阿莫斯 |按或說出 1 for Amos Marble  <br/> 按或說出 2 for AmosJojos |
|姓氏 |全 |大理石 |按或說出 1 for Amos Marble  <br/> 按或說出 2 for Ben Marble |

> [!NOTE]
> 由於 Active Directory 複寫延遲，新使用者最多可能需要 36 小時，才能將名稱列在具有語音辨識的撥號名稱目錄中。
  
### <a name="language-support"></a>語言支援

下列語言適用于與外發提示一起使用的文字到語音：
  
|A-E|E-J|K-Z|
|:-----|:-----|:-----|
|阿拉伯文 (EG)   |英文 (NZ)   |韓文 (KO)   |
|中文 (香港)   |英國 (英文)  |挪威 (否)   |
|中文 (TW)  |英文 (英文)  |波蘭 (PL)   |
|中文 (ZH)  |芬蘭文 (FI)  |葡萄牙文 (BR)  |
|丹麥文 (DA)   |法文 (CA)   |葡萄牙文 (PT)  |
|荷蘭文 (NL)    |法文 (FR)   |俄文 (RU)  |
|英文 (AU)   |德文 (DE)  |西班牙文 (ES)   |
|英文 (CA)   |義大利 (IT)  |西班牙文 (MX) |
|英文 (IN)   |日文 (JP)  |瑞典文 (SV) |

自動語音機的語音辨識輸入以下列語言提供：
  
|A-F|F-Z|
|:-----|:-----|
|中文 (ZH)   |法文 (FR)   |
|英文 (AU)   |德文 (DE)   |
|英文 (CA)   |義大利 (IT)   |
|英文 (IN)   |日文 (JP)   |
|英國 (英文)   |葡萄牙文 (BR)   |
|英文 (英文)   |西班牙文 (ES)   |
|法文 (CA)    |西班牙文 (MX)   |

下列語音命令提供語音辨識支援的 14 種語言：
  
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

### <a name="the-operator-option"></a>運算子選項

您可以選擇設定自動語音機，讓來電者選擇與接線生通話。
  
按鍵 0 和語音命令 「運算子」預設會將通話引導至指定的運算子。 語音辨識支援的所有語言都是這種情況。 您也可以使用設定功能表 **選項** 來設定運算子的自訂值。
  
運算子可以設定為：
  
- 已Microsoft Teams使用者或商務用 Skype Server使用者企業語音使用者。
- 為貴組織設定的另一個自動助理。
- 在貴組織中設定的任何現有通話佇列。 若要查看通話佇列的更多資訊，請參閱 [建立雲端通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

### <a name="business-hours-and-call-handling"></a>上班時間和通話處理

每一個自動總機都可以設定上班時間。 如果未設定上班時間，則一天中所有的天數和所有時數會視為上班時間，因為預設會設定 24/7 排程。 工作時間可以設定為一天中的休息時間，所有未設定為上班時間的時數會視為後小時。 您可以設定不同的來電處理選項和不同的問候語 (為) 上班時間和上班時間的選擇性問候語。
  
每個自動電話機都有數種可能的通話處理選項：
  
- 播放問候語後，通話可能會中斷。
- 您也可以：
  - 將通話重新導向Microsoft Teams使用者，電話系統已啟用企業語音或已指派通話方案給他們的使用者。 您可以設定電話，讓來電者能將電話送到語音信箱。 若要這麼做， **請選取公司** 中的人員，並設定此人的通話會自動直接轉往語音信箱。

  - 將通話重新導向到通話佇列。 若要查看通話佇列的更多資訊，請參閱 [建立雲端通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

  - 將通話重新導向到另一個自動電話機。

當來電者播放功能表提示時，自動語音機會向來電者表達這些選項。 例如：「按 1 for Sales，按 2 for Services。 若要與運算子說話，請隨時按 0。」

### <a name="set-menu-options"></a>設定功能表選項

雲端自動語音機允許您建立功能表提示 (按 1 for Sales，按 2 for Services") 並設定功能表選項，以根據使用者選擇路由通話。 自動語音機的功能表選項，讓組織提供一系列選項，引導來電者更快速地前往目的地，而不需要依靠接線生來處理來電。 功能表提示可以是使用文字到語音 (系統產生的提示) 或上傳錄製的音訊檔案。 語音辨識接受免手流覽的語音命令，但來電者也可以使用電話鍵台流覽功能表。
  
您可以使用系統管理中心將按鍵 0 到 9 指派給自動商務用 Skype按鍵。 您可以針對上班時間和上班時間建立不同的功能表選項組，而且您可以在功能表選項中啟用或停用按名稱 **撥號**。 按鍵可以對應以將通話轉接至：
  
- 預設對應到 Key 0 的運算子。 不過，您可以將其重新指派給任何其他金鑰，或從功能表移除。
- 通話佇列。
- 另一個自動助理。 您可以設定多層次功能表，將一個自動助理中的功能表選項指向另一個自動助理，並擁有自己的一組功能表選項，稱為「巢式」自動總機。
- 具有Microsoft Teams授權的使用者電話系統已啟用企業語音，或已指派通話方案給他們。 您可以設定電話，讓來電者能將電話送到語音信箱。 若要這麼做， **請選取公司** 中的人員，並設定此人的通話會自動直接轉往語音信箱。
  
如果已啟用語音辨識，每個功能表選項的名稱會變成語音辨識關鍵字。 例如，來電者可以說「一」，以選取對應到按鍵 1 的功能表選項，或說「銷售」以選取同一個名為「銷售」的功能表選項。
  
若要設定自動總機和功能表選項，請前往 [設定雲端自動總機](create-a-phone-system-auto-attendant.md)。
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>指派自動電話機的電話號碼

如果需要多個電話號碼，您可以將 Microsoft 服務號碼、直接路由號碼或混合式號碼指派給自動乘務員的連結資源帳戶 (或多個資源帳戶) 。 請參閱 [規劃直接路由](direct-routing-plan.md) 以瞭解其他詳細資料。

若要指派服務號碼，您必須取得或移植現有的付費或免付費服務號碼。 一旦收到付費或免付費服務電話號碼後，這些電話號碼會顯示在系統管理中心商務用 Skype  >  **語音** 電話  >  **號碼** 中。 **號碼類型** 列為服務 **- 免付費**。 若要取得您的服務號碼，請參閱[](./getting-service-phone-numbers.md)取得 商務用 Skype 和 Microsoft Teams 的服務電話號碼，或者如果您想要傳輸現有服務號碼，請參閱將電話號碼轉接到[Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> 如果您在美國以外，則無法使用 Microsoft Teams系統管理中心取得服務號碼。 請 [改為前往管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) ，以查看執行方式。
  
## <a name="related-topics"></a>相關主題

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](./getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)