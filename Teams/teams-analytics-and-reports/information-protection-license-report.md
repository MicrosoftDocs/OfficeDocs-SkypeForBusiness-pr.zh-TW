---
title: Microsoft Teams資訊保護授權報告
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: 瞭解如何在系統管理中心Teams資訊保護授權報告Microsoft Teams查看貴組織中應用程式如何使用變更通知事件訂閱 API。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73ce4b5720c42cdb4e468182d6290912baf95d7e
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435857"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams資訊保護授權報告


Teams資訊保護授權報告提供 Microsoft Graph授權和付款要求的[API 使用方式深入資訊](/graph/teams-licenses)。 此報表會強調在 model=A 中使用這些 API [的所有應用程式](/graph/teams-licenses#modela-requirements)。 當 API 在 model [=B](/graph/teams-licenses#modelb-requirements) 或評估模式中使用時，不會 [顯示使用方式](/graph/teams-licenses#evaluation-mode-default-requirements)。 


## <a name="view-the-information-protection-license-report"></a>查看資訊保護授權報告

您必須是 Teams 服務系統管理員才能進行這些變更。 請參閱[使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 在系統管理中心的左側導Microsoft Teams，選取分析 **&報表**  >  **。** On the **View reports** tab, under **Report**, select **Information Protection License**.
2. 在 **日期範圍** 下，選取範圍。
3. 在 **應用程式** 下，選取應用程式，然後選取執行 **報表**。

    ![系統管理中心內Teams資訊保護授權報告下拉Teams圖。](../media/teams-info-protection-license-report-dropdown-with-callouts.png "系統管理中心內Teams資訊保護授權報告下拉Teams圖。")

4. 您可以針對每個類別，查看具有授權的使用者、沒有授權的使用者、已設定容量及已使用容量的度量。 

    ![系統管理中心中Teams資訊保護授權報告摘要圖表的螢幕擷取畫面Teams包含圖說圖的變更通知。](../media/teams-info-protection-license-report-chart-with-callouts.png "系統管理中心中Teams資訊保護授權報告摘要圖表的螢幕擷取畫面Teams包含圖說圖的變更通知。")

5. 您可以按一下匯出按鈕來匯出資料。 您可以按一下 Teams 變更通知 API、Teams 修補程式 API、Teams 匯出 API (聊天) ，以及 Teams 匯出 API (teams) 的索引點來切換資料表資料。 

    ![在包含圖說Teams之 Teams管理中心中，顯示資訊保護授權報告的不同Teams螢幕擷取畫面。](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "在包含圖說Teams之 Teams管理中心中，顯示資訊保護授權報告的不同Teams螢幕擷取畫面。")

    ![系統管理中心中Teams資訊保護授權報告的變更通知Teams螢幕擷取畫面。](../media/teams-info-protection-license-report-change-notification-with-callouts.png "系統管理中心中Teams資訊保護授權報告的變更通知Teams螢幕擷取畫面。")


## <a name="interpret-the-report"></a>解譯報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以針對過去三個月的趨勢來查看資訊保護授權報告。 |
|**2**   |應用程式名稱會顯示已使用[Microsoft Graph API](/graph/teams-licenses)的所有應用程式清單，這些應用程式在所選時段內具有授權和付款需求。|
|**3**   |擁有有效授權的使用者 [數目](/graph/teams-licenses#required-licenses-for-modela)。  |
|**4**   |沒有有效授權的使用者 [數目](/graph/teams-licenses#required-licenses-for-modela)。  |
|**5**   |應用程式允許的 API 通話總流量，超出此費用，每個 API 通話的消費費用將會向應用程式收費。 |
|**6**   |應用程式用於給定日期範圍的總 API 通話量。 |
|**7**   |將報表匯出至 CSV 檔案，進行離線分析。 選取 **匯出Excel**，然後 **選取下載選項卡**。選取下載以在報表準備就緒時下載報表。 此匯出只會匯出目前選取的定位停駐點。|
|**8**   |選取任何特定的標籤，以在圖表中顯示或隱藏該標籤。 |
|**9**   |每個選項卡會顯示一組特定 API 的使用方式，即變更 [通知](/graph/api/resources/webhooks)、 [匯出 API](/microsoftteams/export-teams-content)和更新 [郵件 API](/graph/api/message-update)。 選取一個選項卡來查看該 API 的使用詳細資料。 |
|**10**   |**變更通知 API 使用量**<li>**顯示名稱** - 觸發變更通知的使用者顯示名稱。</li><li>**必要的授權** - 指定使用者是否擁有成功將變更通知傳送至應用程式所需的授權。</li><li>**嘗試計數** - 此使用者所觸發的變更通知總數。</li><li>**變更已送出通知** - 已送出至 App 的變更通知總數。 這將會小於如果使用者沒有有效授權時所觸發的變更通知總數。</li>|
|**11**|**修補程式 API**<li>**顯示名稱** - 顯示嘗試更新郵件的使用者名稱。</li> <li>**必要的授權** - 指定使用者是否擁有郵件成功更新所需的授權。</li><li>**嘗試計數** - 更新郵件的嘗試總數。</li><li>**郵件已修補** - 已成功更新的郵件總數。</li>|
|**12**|**聊天匯出 API 使用量**<li>**顯示名稱** - 顯示嘗試匯出使用者聊天訊息的使用者名稱。</li><li>**必要的授權** - 指定使用者是否擁有成功匯出郵件所需的授權。</li><li>**嘗試計數** - 匯出聊天訊息的嘗試總數。</li><li>**已匯出訊息** - 成功匯出聊天訊息的嘗試總數。</li> |
|**13**|**小組匯出 API 使用量**<li>**顯示名稱** - 顯示嘗試匯出該團隊訊息的團隊名稱。</li><li>**嘗試計數** - 匯出小組訊息的嘗試總數。</li><li>**郵件已匯出** - 成功匯出小組郵件的嘗試總數。</li> |


## <a name="make-the-user-specific-data-anonymous"></a>將使用者特定資料匿名

若要將使用者活動報告中Teams匿名，您必須是全域系統管理員。 這會隱藏可辨識的資訊，例如顯示名稱、電子郵件，以及Azure AD及其匯出中的識別碼。

1. 在 Microsoft 365 系統管理中心，前往 \> 設定 **組織** 設定，然後選擇在服務 **選項卡****下，選擇** 報告。
    
2. 選取 **報表**，然後選擇顯示 **匿名識別碼**。 此設定會同時適用于系統管理中心Microsoft 365 系統管理中心使用方式Teams報表。
  
3. 選取 **儲存變更**。