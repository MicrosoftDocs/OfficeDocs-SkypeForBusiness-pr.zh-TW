---
title: 查看貴組織中的電話號碼清單
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 瞭解如何使用 Microsoft Teams 系統管理中心查看貴組織中所有電話號碼的清單，以及指派給使用者或未指派的所有號碼。
ms.openlocfilehash: ac7c63515b34b8c199f8050933b6c3ccbc6f8d33
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606072"
---
# <a name="see-a-list-of-telephone-numbers"></a>查看電話號碼清單 

您可以將不同類型的電話號碼指派給使用者或語音應用程式，例如 [音訊會議](deploy-audio-conferencing-teams-landing-page.md) 或 [通話佇列](plan-auto-attendant-call-queue.md)。 如需詳細資訊，請參閱 [管理組織的電話號碼](/microsoftteams/manage-phone-numbers-landing-page)。

本文適用于通話方案、電信業者連線電信業者連線行動 (公開預覽版) 。 如需直接路由的相關資訊，請參閱 [設定電話號碼並啟用企業語音](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>若要查看貴組織中的所有電話號碼

若要查看貴組織中所有電話號碼的清單：

1. 移至 **Microsoft Teams 系統管理中心**。

2. 在左側導覽畫面中，移至 **[語音**  >  **電話號碼]**。

3. 若要檢視已指派的電話號碼，請參閱 [ **工作分派狀態** ] 欄，該欄也會顯示該號碼所指派的服務類型。

4. 若要篩選檢視，請按一下篩選圖示。 在 [ **篩選]** 窗格中，您可以使用下拉式清單來依下列方式篩選檢視：

   - 您設定 **的數位範圍**。 您可以使用最低數位或最高數位來搜尋。

   - 以您指定的數位開頭的數位。

   - 數位 **啟用狀態**。

   - 數位 **類型**。

   - 電話號碼 **狀態**。

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>查看指派給使用者的所有電話號碼

當您設定使用者時，您可能只想查看已指派給使用者的電話號碼清單，以及可以指派給他們的電話號碼。

1. 移至 **Microsoft Teams 系統管理中心**。

2. 在左側導覽畫面中，移至 **[語音**  >  **電話號碼]**。

    > [!IMPORTANT]
    > 若要在 Microsoft Teams 系統管理中心左側導覽中查看 **語音** 選項，您必須先購買至少一個 **企業版 E5 授權**、一個 **電話系統** 附加元件授權或一個 **音訊會議** 附加元件授權。

3. 若要快速排序數位，以便查看已指派的數位，請按一下 [ **作業狀態** ] 欄標題。 或者，您可以按一下篩選圖示，然後篩選檢視以查看已指派給使用者的電話號碼，或您可指派給使用者的未指派號碼。 您可以依據下列方法進行篩選：

   - **指派給使用者**
   - **指派給會議橋接器** 
   - **指派給語音應用程式 (自動語音應答/通話佇列)**
   - **未指派**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>查看指派給語音使用者的所有電話號碼

當您設定組織中的使用者撥打和接聽電話時，必須先取得電話號碼，然後指派給使用者。 取得電話號碼之後，您可能會想要查看號碼指派的啟用狀態。
  
1. 移至 **Microsoft Teams 系統管理中心**。

2. 在左側導覽畫面中，移至 **[語音**  >  **電話號碼]**。

3. 按一下篩選圖示，依 **[啟用狀態**] 篩選您的檢視。 您可以依據下列方法進行篩選：

   - **啟動**
   - **作業擱置中**
   - **作業失敗**
   - **更新擱置中**
   - **更新失敗**

## <a name="using-the-teams-powershell-module"></a>使用 Teams PowerShell 模組

您可以使用 Teams PowerShell 模組，從前幾節取得相同的資訊，但版本 1.1.6 或更新版本是必要的，包括整合 商務用 Skype Online 連接器。 如需模組的詳細資訊，請參閱 [Microsoft Teams PowerShell 概觀](teams-powershell-overview.md)。

若要查看貴組織擁有的所有電話號碼清單，請使用 [Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment) Cmdlet。 例如，若要查看每個電話號碼、其類型和狀態，請執行下列命令：

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

若要查看所有指派給使用者的電話號碼，請使用 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) Cmdlet。 例如，若要查看所有已指派電話號碼的使用者，請執行下列命令：

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>相關主題

[管理組織的電話號碼](manage-phone-numbers-landing-page.md)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsPhoneNumberAssignment](/powershell/module/teams/get-csphonenumberassignment)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)
