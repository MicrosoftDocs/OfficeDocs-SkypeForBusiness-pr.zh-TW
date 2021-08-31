---
title: 查看貴組織的電話號碼清單
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
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
ms.openlocfilehash: d7de480508020dac24a63b5923af9cf2481c691b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733972"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>查看貴組織的電話號碼清單

您可以為使用者或其他服務指派不同類型的電話號碼 (服務號碼) ，例如適用于 Microsoft 365 或 Office 365。
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>查看貴組織所有電話號碼的清單

![顯示標誌圖示Teams圖示。](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 請前往 Microsoft Teams **系統管理中心**。

2. 在左側流覽中，前往 **Voice**  >  **電話號碼**。

    > [!IMPORTANT]
    > 若要在 商務用 Skype系統管理中心左側流覽中查看語音選項，您必須先購買至少一個 **Enterprise E5** 授權、一個 **電話系統** 附加元件授權或一個音訊會議附加元件授權。 

3. 若要查看指派的電話號碼，請參閱 **狀態列。**

4. 若要篩選您的視圖，請按一下篩選圖示。 在篩選 **窗格中** ，您可以使用下拉式清單來篩選您的視圖，方法為：

   - **您設定** 的數量範圍。 您可以根據最低數位或最高數位來搜尋。

   - 以您指定的數位開始的數位。

   - 號碼 **啟用狀態**。

   - 數位 **類型**。

   - 電話號碼 **狀態**。

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>查看指派給使用者的所有電話號碼

當您設定使用者時，您可能只想查看已指派給使用者的電話號碼清單，以及可指派給使用者的電話號碼。
  
![顯示標誌圖示Teams圖示。](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 請前往 Microsoft Teams **系統管理中心**。

2. 在左側流覽中，前往 **Voice**  >  **電話號碼**。

    > [!IMPORTANT]
    > 若要在 Microsoft Teams系統管理中心左側流覽中查看語音選項，您必須先購買至少一 **個 Enterprise E5** 授權、一 **個 電話系統** 附加元件授權或一個音訊會議附加元件授權。 

3. 若要快速排序數位，以便查看指派的號碼，請按一下 [ **狀態列** 標題。 或者，您可以按一下篩選圖示，然後篩選您的視圖，以查看已指派給使用者的電話號碼，或您可以指派給使用者的未指定號碼。 您可以篩選：

   - **指派給使用者**

   - **已指派給會議橋接器** 

   - **未指定**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>查看指派給語音使用者的電話號碼

當您在組織中設定使用者撥打和接聽電話時，您必須先取得電話號碼，然後將電話號碼指派給使用者。 在您獲得電話號碼之後，您可能只想查看號碼指派的啟用狀態。

![顯示標誌圖示Teams圖示。](media/teams-logo-30x30.png) **使用 Microsoft Teams系統管理中心**！
  
1. 請前往 Microsoft Teams **系統管理中心**。

2. 在左側流覽中，前往 **Voice**  >  **電話號碼**。

    > [!IMPORTANT]
    > 若要在 Microsoft Teams系統管理中心左側流覽中查看語音選項，您必須先購買至少一 **個 Enterprise E5** 授權、一 **個 電話系統** 附加元件授權或一個音訊會議附加元件授權。 

3. 按一下篩選圖示以根據啟用狀態篩選您的 **視圖：您可以** 篩選：

   - **啟動**

   - **待處理的工作分派**

   - **作業失敗**

   - **更新擱置中**

   - **更新失敗**

## <a name="using-the-teams-powershell-module"></a>使用 Teams PowerShell 模組

您可以使用 Teams PowerShell 模組從前一節取得相同的資訊，但需要版本 1.1.6 或更新版本，包括整合 商務用 Skype Online 連接器。 有關模組詳細資訊，請參閱[powerShell Microsoft Teams概觀](teams-powershell-overview.md)。

您可以使用 [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber) Cmdlet 來查看貴組織擁有的所有電話號碼清單。 例如，您可以執行下列命令來查看每個電話號碼及其狀態：

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

您可以使用 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) Cmdlet 查看指派給使用者的所有電話號碼。 例如，您可以執行下列命令來查看指派電話號碼的所有使用者：

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](./phone-number-calling-plans/port-order-overview.md)

[用於通話方案的各種電話號碼](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)