---
title: 設定共同區域電話授權
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '瞭解如何設定大廳、接待區和會議室的公用區域電話 '
ms.openlocfilehash: e2d81c047f4bf26d43da4fd8f9fc31c0702c28d8
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045559"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>設定公用區域電話授權Microsoft Teams
> [!NOTE]
> 一般地區電話不支援語音信箱。

一般地區電話會放在大廳等區域，或是許多人可以撥打的另一個區域;例如，接待區、大廳或會議電話。 一般地區電話會使用與公用區域或授權系結的帳戶電話。 也必須適當設定 TeamsIPPhone 政策，讓手機擁有共同的區域使用者體驗。

在下列步驟中，我們會協助您設定帳戶電話系統為貴組織部署一般地區電話。 為獲得更完整的會議室體驗 ，包括音訊會議，請考慮使用會議室裝置會議室專用會議室授權。 

首先，您需要購買通用區域電話 (CAP) 授權，並確認您擁有經過認證的電話。 若要搜尋並深入瞭解認證電話，請前往[Microsoft Teams裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。 

## <a name="step-1---buy-the-licenses"></a>步驟 1 - 購買授權

1. 在 Microsoft 365 系統管理中心中，前往帳單  >  **購買服務**，然後展開其他 **方案**。

    ![螢幕擷取畫面顯示共同區域電話磚。](media/set-up-common-area-phone-image1.png)

2. 選取 **公用區域電話**  >  **立即購買**。

3. 在 [結帳」 頁面上，按一下 [ **立即購買**> 。

4. 展開 **附加元件訂閱，** 然後按一下以購買通話方案。 選擇國內 **通話方案或****國內及國際通話方案**。

> [!NOTE]
> 如果您使用的是 Microsoft 電話直接路由，則不需要通話方案授權。

> [!NOTE]
> 您不需要新增授權電話系統授權。 它包含在共同區域電話授權中。

有關授權詳細資訊，請參閱Microsoft Teams[附加元件授權。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

共同區域電話授權支援： 


| &nbsp;  |  共同區域電話  |
|---------|---------|
|商務用 Skype |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|電話系統 |    &#x2714; |
|音訊會議 |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|全球可用性 |       &#x2718; &sup2;  |
|通道可用性 |    EA、EAS、CSP、GCC、EES、Web Direct  |
|      |         |

&sup1;一般地區電話可以透過會議召集人提供的撥入號碼加入音訊會議

&sup2;在主權雲端中不可用  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>步驟 2 - 為手機建立新使用者帳戶並指派授權

1. 在 Microsoft 365 系統管理中心，請前往 **使用者**  >  **使用中使用者**  >  **新增使用者**。

2. 輸入使用者名稱，例如名字的「主」，第二個名稱的「接收」。

3. 如果顯示名稱無法像「主要接收」一樣自動生成，請輸入顯示名稱。

4. 輸入使用者名稱，例如「MainReception」或「Mainlobby」。

5. 對於一般地區電話，您可能會想要手動設定密碼，或針對所有公用區域電話設定相同的密碼。 此外，您可能會考慮清除讓此使用者第一次 **登錄時變更** 其密碼核取方塊。

6. 指派授權給使用者。 在同一頁上，按一下 以展開 **[產品授權>**。 開啟共同區域電話電話選擇國內通話 **方案或****國內及國際通話方案**。 

    ![螢幕擷取畫面顯示已強調國內通話方案及國內和國際方案選項的授權指派。](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> 如果您使用的是 Microsoft 電話直接路由，則不需要指派通話方案授權。

詳細資訊，請參閱指派 [授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>步驟 3 - 將電話號碼指派給共同電話使用者帳戶

使用 Teams系統管理中心將號碼指派給使用者。

1. 在系統管理Teams，選取 **語音電話**  >  **號碼**。

3. 從電話號碼清單中選取一個數位，然後按一下 [ **指派**。

4. 在 **指派** 頁面的語音使用者方塊中，輸入將會使用電話的使用者名稱，然後在選取語音使用者下拉式清單中選取使用者。 

5. 接下來，您需要新增緊急位址。 選擇 **下拉** 式清單的按城市搜尋、按描述搜尋，或按位置搜尋，然後在文字方塊中輸入城市、描述或位置。 搜尋後，請在選取 **緊急位址** 下尋找，以挑選適合您的位址。

6. 按一下 **[儲存** ，您的使用者應該看起來像這樣：

   ![螢幕擷取畫面顯示範例使用者授權指派。](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 使用者只有在已申請授權電話系統顯示。 如果您只是這麼做，有時候使用者需要一點時間，才顯示在清單中。

詳細資訊，請參閱 [取得使用者的電話號碼](getting-phone-numbers-for-your-users.md)。

您也可以將您擁有的電話號碼帶至其他電信公司，並「移轉」或移轉至Microsoft 365或Office 365。 請參閱[將電話號碼轉接到 Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
