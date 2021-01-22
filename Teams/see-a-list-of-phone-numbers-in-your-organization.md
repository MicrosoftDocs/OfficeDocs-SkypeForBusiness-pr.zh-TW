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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 瞭解如何使用 Microsoft Teams 系統管理中心查看貴組織的所有電話號碼清單，以及指派給使用者或未指派的所有號碼。
ms.openlocfilehash: 61e1fb59ba5b68aeb2ab2af51b2ef91202e43678
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918899"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>查看貴組織的電話號碼清單

您可以指派不同類型的電話號碼給使用者或其他服務 (服務號碼) ，例如 Microsoft 365 或 Office 365 的音訊會議。
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>查看貴組織擁有的所有電話號碼清單

![使用 Microsoft Teams 系統管理中心 ](media/teams-logo-30x30.png) **顯示 Teams 標誌的圖示**

1. 請前往 **Microsoft Teams 系統管理中心**。

2. 在左側流覽區中，前往 **語音**  >  **電話號碼**。

    > [!IMPORTANT]
    > 若要在商務用Skype 系統管理中心的左側流覽區看到語音選項，您必須先購買至少一個企業版 **E5** 授權、一個電話系統附加元件授權，或一個音訊會議附加元件授權。

3. 若要查看指派的電話號碼，請參閱狀態 **欄** 。

4. 若要篩選您的視圖，請按一下篩選圖示。 在篩選 **窗格中** ，您可以使用下拉式清單來篩選您的視圖：

   - **您設定** 的數量範圍。 您可以根據最低數位或最高數位搜尋。

   - 以您指定之數位為起始的數位。

   - 數位 **啟用狀態**。

   - 數位 **類型**。

   - 電話號碼 **狀態**。

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>查看指派給使用者的所有電話號碼

設定使用者時，您可能只想查看已指派給使用者的電話號碼清單，以及可指派給使用者的電話號碼。
  
![使用 Microsoft Teams 系統管理中心 ](media/teams-logo-30x30.png) **顯示 Teams 標誌的圖示**

1. 請前往 **Microsoft Teams 系統管理中心**。

2. 在左側流覽區中，前往 **語音**  >  **電話號碼**。

    > [!IMPORTANT]
    > 若要在 Microsoft  Teams 系統管理中心的左側流覽區看到語音選項，您必須先購買至少一個企業 **版 E5** 授權、一個電話系統附加元件授權，或一個音訊會議附加元件授權。

3. 若要快速排序數位，以便查看已指派的數位，請按一下 [狀態 **欄位** 標題。 或者，您可以按一下篩選圖示，然後篩選您的視圖，以查看已指派給使用者的電話號碼，或您可以指派給使用者的未指派號碼。 您可以篩選：

   - **指派給使用者**

   - **已指派至會議橋接器** 

   - **未未指定**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>查看指派給語音使用者的電話號碼

當您設定讓貴組織的使用者撥打和接聽電話時，您必須先取得電話號碼，然後將電話號碼指派給使用者。 在獲得電話號碼後，您可能只想查看號碼指派的啟用狀態。

![使用 Microsoft Teams 系統管理中心 ](media/teams-logo-30x30.png) **顯示 Teams 標誌的圖示** ！
  
1. 請前往 **Microsoft Teams 系統管理中心**。

2. 在左側流覽區中，前往 **語音**  >  **電話號碼**。

    > [!IMPORTANT]
    > 若要在 Microsoft  Teams 系統管理中心的左側流覽區看到語音選項，您必須先購買至少一個企業 **版 E5** 授權、一個電話系統附加元件授權，或一個音訊會議附加元件授權。

3. 按一下篩選圖示，即可根據 **啟用狀態篩選** 您的視圖，您可以根據以下專案篩選：

   - **啟動**

   - **作業擱置中**

   - **作業失敗**

   - **更新擱置中**

   - **更新失敗**

## <a name="using-the-teams-powershell-module"></a>使用 Teams PowerShell 模組

您可以使用 Teams PowerShell 模組從前幾節取得相同資訊，但需要版本 1.1.6 或更新版本，包括整合商務用 Skype Online 連接器。 有關模組詳細資訊，請參閱 Microsoft [Teams PowerShell 概觀](teams-powershell-overview.md)。

您可以使用 [Get-CsOnlineTelephoneNumber](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber) Cmdlet，查看貴組織擁有的所有電話號碼清單。 例如，您可以執行下列命令來查看每個電話號碼及其狀態：

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

您可以使用 [Get-CsOnlineUser](https://docs.microsoft.com/powershell/module/skype/get-csonlineuser) Cmdlet 查看指派給使用者的所有電話號碼。 例如，您可以執行下列命令來查看指派電話號碼的所有使用者：

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](/microsoftteams/transferring-phone-numbers-common-questions)

[用於通話方案的電話號碼類型](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](https://docs.microsoft.com/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](https://docs.microsoft.com/powershell/module/skype/get-csonlineuser)
