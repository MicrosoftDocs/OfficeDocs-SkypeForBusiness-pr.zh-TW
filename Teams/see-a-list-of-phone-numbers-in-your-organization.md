---
title: 查看貴組織的電話號碼清單
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
description: 瞭解如何使用 Microsoft Teams管理中心查看貴組織的所有電話號碼清單，以及指派給使用者或未指定的所有號碼。
ms.openlocfilehash: 45d292ae1ba4ffd714f0c302fe140978968ba1c9
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763626"
---
# <a name="see-a-list-of-telephone-numbers"></a>查看電話號碼清單 

您可以指派不同類型的電話號碼給使用者或語音應用程式，例如音訊[會議或](deploy-audio-conferencing-teams-landing-page.md)[通話佇列](plan-auto-attendant-call-queue.md)。 詳細資訊，請參閱 [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-landing-page)。

本文適用于通話方案及接線連線。 有關直接路由的資訊，請參閱 [設定電話號碼並啟用企業語音](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>查看貴組織的所有電話號碼

若要查看貴組織中所有電話號碼的清單：

1. 請前往 Microsoft Teams **系統管理中心**。

2. 在左側流覽中，前往 **語音**  >  **電話號碼**。

3. 若要查看指派的電話號碼，請參閱工作分派狀態列，這也會顯示該號碼所指派的服務類型。

4. 若要篩選您的視圖，請按一下篩選圖示。 在篩選 **窗格中** ，您可以使用下拉式清單來篩選您的視圖，方法為：

   - **您設定** 的數量範圍。 您可以根據最低數位或最高數位來搜尋。

   - 以您指定的數位開始的數位。

   - 號碼 **啟用狀態**。

   - 數位 **類型**。

   - 電話號碼 **狀態**。

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>查看指派給使用者的所有電話號碼

當您設定使用者時，您可能只想查看已指派給使用者的電話號碼清單，以及可指派給使用者的電話號碼。

1. 請前往 Microsoft Teams **系統管理中心**。

2. 在左側流覽中，前往 **語音**  >  **電話號碼**。

    > [!IMPORTANT]
    > 若要在 Microsoft Teams 系統管理中心左側流覽中查看語音選項，您必須先購買至少一個 **Enterprise E5** 授權、一個 **電話系統** 附加元件授權或一個音訊會議附加元件授權。****

3. 若要快速排序數位，以便查看指派的編號，請按一下 [ **工作分派狀態>** 欄標題。 或者，您可以按一下篩選圖示，然後篩選您的視圖，以查看已指派給使用者的電話號碼，或您可以指派給使用者的未指定號碼。 您可以篩選：

   - **指派給使用者**
   - **已指派給會議橋接器** 
   - **已指派給語音應用程式 (自動語音留言/通話佇列)**
   - **未指定**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>查看指派給語音使用者的所有電話號碼

當您在組織中設定使用者撥打和接聽電話時，您必須先取得電話號碼，然後將電話號碼指派給使用者。 在您獲得電話號碼之後，您可能會想要查看號碼指派的啟用狀態。
  
1. 請前往 Microsoft Teams **系統管理中心**。

2. 在左側流覽中，前往 **語音**  >  **電話號碼**。

3. 按一下篩選圖示，以根據啟用狀態 **篩選您的視圖**。 您可以篩選：

   - **啟動**
   - **待處理作業**
   - **作業失敗**
   - **更新擱置中**
   - **更新失敗**

## <a name="using-the-teams-powershell-module"></a>使用 Teams PowerShell 模組

您可以使用 Teams PowerShell 模組從前一節取得相同的資訊，但需要版本 1.1.6 或更新版本，包括整合 商務用 Skype Online 連接器。 有關模組詳細資訊，請參閱[powerShell Microsoft Teams概觀](teams-powershell-overview.md)。

若要查看貴組織擁有的所有電話號碼清單，請使用 [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber) Cmdlet。 例如，若要查看每個電話號碼及其狀態，請執行下列命令：

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

若要查看指派給使用者的所有電話號碼，請使用 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) Cmdlet。 例如，若要查看已指派電話號碼的所有使用者，請執行下列命令：

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>相關主題

[管理貴組織的電話號碼](manage-phone-numbers-landing-page.md)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)