---
title: 設定公用區域電話授權
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '瞭解如何設定大廳、接待區和會議室的公用區域電話 '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117111"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>設定 Microsoft Teams 的公用區域電話授權
> [!NOTE]
> 一般地區電話不支援語音信箱。

一般地區電話會放在大廳等區域，或是許多人可以撥打的另一個區域;例如，接待區、大廳或會議電話。 一般地區電話會使用與共同區域電話授權相關的帳戶來登錄。 也必須適當設定 TeamsIPPhone 政策，讓手機擁有共同的區域使用者體驗。

在下列步驟中，我們會協助您設定電話系統帳戶，為貴組織部署常見的地區電話。 為獲得更完整的會議室體驗 ，包括音訊會議，請考慮使用會議室裝置購買專屬的會議室授權。 

首先，您必須購買一般地區電話 (CAP) 授權，並確認您擁有經過認證的電話。 若要搜尋並深入瞭解認證電話，請前往 Microsoft [Teams 裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。 

## <a name="step-1---buy-the-licenses"></a>步驟 1 - 購買授權

1. 在 Microsoft 365 系統管理中心，前往帳單  >  **購買服務**，然後展開 **其他方案**。

    ![顯示公用區域電話磚的螢幕擷取畫面](media/set-up-common-area-phone-image1.png)

2. 選取 **共同區域電話**  >  **立即購買**。

3. 在 [結帳」 頁面上，按一下 [ **立即購買**> 。

4. 展開 **附加元件訂閱，** 然後按一下以購買通話方案。 選擇國內 **通話方案或****國內及國際通話方案**。

> [!NOTE]
> 如果您使用的是 Microsoft Phone System Direct Routing，則不需要通話方案授權。

> [!NOTE]
> 您不需要新增電話系統授權。 它包含在共同區域電話授權中。

有關授權詳細資訊，請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

通用地區電話授權支援： 


|   |  公用區域電話  |
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

1. 在 Microsoft 365 系統管理中心，前往 **使用者**  >  **使用中使用者**  >  **新增使用者**。

2. 輸入使用者名稱，例如名字的「主」，第二個名稱的「接收」。

3. 如果顯示名稱無法像「主要接收」一樣自動生成，請輸入顯示名稱。

4. 輸入使用者名稱，例如「MainReception」或「Mainlobby」。

5. 對於一般地區電話，您可能會想要手動設定密碼，或針對所有公用區域電話設定相同的密碼。 此外，您可能會考慮清除讓此使用者第一次 **登錄時變更** 其密碼核取方塊。

6. 指派授權給使用者。 在同一頁上，按一下 以展開 **[產品授權>**。 開啟公用區域電話，然後挑選國內通話方案或 **國內及國際通話方案**。 

    ![顯示授權指派的螢幕擷取畫面](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> 如果您使用的是 Microsoft Phone System Direct Routing，則不需要指派通話方案授權。

詳細資訊，請參閱指派 [授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>步驟 3 - 將電話號碼指派給公用區域電話使用者帳戶

使用 Teams 系統管理中心將號碼指派給使用者。

1. 在 Teams 系統管理中心中，選取 **語音**  >  **電話號碼**。

3.    從電話號碼清單中選取一個數位，然後按一下 [ **指派**。

4. 在 **指派** 頁面的語音使用者方塊中，輸入將會使用電話的使用者名稱，然後在選取語音使用者下拉式清單中選取使用者。 

5. 接下來，您需要新增緊急位址。 從 **下拉** 式清單中，選擇按城市搜尋、按描述搜尋，或按位置搜尋，然後在文字方塊中輸入城市、描述或位置。 搜尋後，請在選取 **緊急位址** 下尋找，以挑選適合您的位址。

6. 按一下 **[儲存** ，您的使用者應該看起來像這樣：

   ![顯示授權指派的螢幕擷取畫面](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 使用者只有在已申請電話系統授權時，才能顯示。 如果您只是這麼做，有時候使用者需要一點時間，才顯示在清單中。

詳細資訊，請參閱 [取得使用者的電話號碼](getting-phone-numbers-for-your-users.md)。

您也可以將您擁有的電話號碼帶至其他電信公司，並「移轉」或移轉至 Microsoft 365 或 Office 365。 請參閱 [將電話號碼轉接至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。