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
description: 瞭解如何使用 Microsoft Teams 系統管理中心的Teams資訊保護授權報告，以查看貴組織中的應用程式如何使用變更通知事件訂閱 API。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fade7b4d5d89061cdc1dd5eb231a80d5ee9e8938
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681534"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams資訊保護授權報告


Teams資訊保護授權報告提供具備[授權和付款需求的 Microsoft Graph API](/graph/teams-licenses)使用方式深入解析。 這份報告會醒目提示在 [model=A](/graph/teams-licenses#modela-requirements)中使用這些 API 的所有應用程式。 當 API 在 [model=B](/graph/teams-licenses#modelb-requirements) 或 [評估模式](/graph/teams-licenses#evaluation-mode-default-requirements)中使用時，不會顯示使用量。 


## <a name="view-the-information-protection-license-report"></a>檢視資訊保護授權報告

您必須是 Teams 服務系統管理員才能進行這些變更。 請參閱[使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 在Microsoft Teams系統管理中心的左側導覽中，選 **取 [分析&報告**  >  **使用方式報告。** 在 [**檢視報表]** 索引標籤的 [**報** 表] 底下，選 **取 [資訊保護授權]**。
2. 在 **[日期範圍]** 底下，選取範圍。
3. 在 [ **應用程式]** 底下，選取應用程式，然後選取 [ **執行報表]**。

    ![Teams系統管理中心內含圖說文字的Teams資訊保護授權報告下拉式清單螢幕擷取畫面。](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Teams系統管理中心內含圖說文字的Teams資訊保護授權報告下拉式清單螢幕擷取畫面。")

4. 針對每個類別，可以檢視擁有授權的使用者、沒有授權的使用者、種子容量及使用量的指派。 

    ![Teams系統管理中心內含圖說文字的變更通知之Teams資訊保護授權報告摘要圖表的螢幕擷取畫面。](../media/teams-info-protection-license-report-chart-with-callouts.png "Teams系統管理中心內含圖說文字的變更通知之Teams資訊保護授權報告摘要圖表的螢幕擷取畫面。")

5. 您可以按一下 [匯出] 按鈕來匯出資料。 您可以按一下Teams變更通知 API 的索引標籤、Teams修補程式 API、Teams匯出 API (聊天) ，以及Teams匯出 API (小組) 來切換表格資料。 

    ![含有圖說文字的索引標籤Teams系統管理中心中，Teams資訊保護授權報告之不同索引標籤的螢幕擷取畫面。](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "含有圖說文字的索引標籤Teams系統管理中心中，Teams資訊保護授權報告之不同索引標籤的螢幕擷取畫面。")

    ![Teams系統管理中心中Teams資訊保護授權報告之變更通知索引標籤的螢幕擷取畫面。](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Teams系統管理中心中Teams資訊保護授權報告之變更通知索引標籤的螢幕擷取畫面。")


## <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |資訊保護授權報告可以檢視過去三個月的趨勢。 |
|**2**   |應用程式名稱會顯示已使用 Microsoft 圖形 API的所有應用程式清單，這些應用程式在所選期間[內具有授權和付款需求](/graph/teams-licenses)。|
|**3**   |擁有有效 [授權的](/graph/teams-licenses#required-licenses-for-modela)使用者數目。  |
|**4**   |沒有有效 [授權](/graph/teams-licenses#required-licenses-for-modela)的使用者數目。  |
|**5**   |應用程式允許的 API 通話總音量，超出此限制後，每一個 API 通話的消費費用就會向應用程式收取費用。 |
|**6**   |應用程式用於指定日期範圍的 API 通話量總計。 |
|**7**   |將報表匯出為 CSV 檔案以進行離線分析。 選取 [**匯出至Excel**]，然後選取 [下載] 索 **引** 標籤。 選取 [**下載**] 以在報表準備就緒時下載報表。 此匯出只會匯出目前選取的索引標籤。|
|**8**   |選取任何特定標籤以在圖表中顯示或隱藏。 |
|**9**   |每個索引標籤都會顯示一組特定 API 的使用方式，也就是 [變更通知](/graph/api/resources/webhooks)、 [匯出 API](/microsoftteams/export-teams-content)，以及 [更新訊息 API](/graph/api/message-update)。 選取索引標籤以檢視該 API 的使用詳細資料。 |
|**10**   |**變更通知 API 使用量**<li>**顯示名稱** - 觸發變更通知之使用者的顯示名稱。</li><li>**必要授權** - 指定的使用者是否擁有成功傳送變更通知給應用程式的必要授權。</li><li>**嘗試計數** - 因此使用者而觸發的變更通知總數。</li><li>**已傳送變更通知** - 傳送到應用程式的變更通知總數。 這會小於使用者沒有有效授權時觸發的變更通知總數。</li>|
|**11**|**修補 API**<li>**顯示名稱** - 已嘗試更新郵件之使用者的顯示名稱。</li> <li>**必要授權** - 指定的使用者是否擁有訊息成功更新的必要授權。</li><li>**嘗試計數** - 更新郵件的總嘗試次數。</li><li>**郵件已修補** - 已成功更新的郵件總數。</li>|
|**12**|**聊天匯出 API 使用量**<li>**顯示名稱** - 已完成嘗試匯出使用者聊天訊息之使用者的顯示名稱。</li><li>**必要授權** - 指定的使用者是否擁有成功匯出郵件的必要授權。</li><li>**嘗試計數** - 匯出聊天訊息的總嘗試次數。</li><li>**郵件匯出** - 成功匯出聊天訊息的嘗試總數。</li> |
|**13**|**團隊匯出 API 使用量**<li>**顯示名稱** - 已嘗試匯出團隊訊息之團隊的顯示名稱。</li><li>**嘗試計數** - 匯出小組訊息的總嘗試次數。</li><li>**郵件匯出** - 成功匯出小組訊息的嘗試總數。</li> |


## <a name="make-the-user-specific-data-anonymous"></a>將使用者特定資料匿名化

若要將Teams使用者活動報告中的資料匿名化，您必須是全域系統管理員。 這會隱藏報表及其匯出中可識別的資訊，例如顯示名稱、電子郵件和 Azure AD ID。

1. 在 [Microsoft 365 系統管理中心 中，移至 **[設定** \> **組織設定**]，然後在 [**服務] 索** 引標籤下選擇 [**報告]**。
    
2. 選取 **[報告**]，然後選擇 **[顯示匿名識別碼]**。 此設定會同時套用至Microsoft 365 系統管理中心中的使用方式報告和Teams系統管理中心。
  
3. 選 **取 [儲存變更]**。