---
title: Microsoft Teams使用者活動報告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在系統管理中心Teams使用者活動Microsoft Teams，以查看貴組織中使用者如何使用Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13d2d261358fc5c373304c46b48684d1f116fc06
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646054"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams使用者活動報告

使用者Teams報告提供貴組織使用者于 Teams 中執行的活動類型深入Teams。 您可以在 1：1 和群組通話的未排 (，查看有多少使用者透過非計畫) 。 查看使用者已Teams的會議，以及使用者Teams參與的會議。 查看有關螢幕、視訊和音訊分鐘數及聊天通訊統計資料的詳細資訊，例如有多少使用者回復和張貼頻道訊息，以及有多少使用者參與 1：1 或群組聊天訊息。

> [!NOTE]
> 目前無法排程使用者活動報告。

## <a name="view-the-user-activity-report"></a>查看使用者活動報告

您必須是 Teams 服務系統管理員才能進行這些變更。 請參閱[使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 在系統管理中心的左側導Microsoft Teams，選取分析&**報告**  >  **使用方式報告**。 On the **View reports** tab, under **Report**, select **Teams user activity**.
2. 在 **日期範圍** 下，選取範圍，然後選取執行 **報表**。

    ![系統管理中心Teams圖的使用者活動報告Teams螢幕擷取畫面](../media/teams-reports-user-activity-with-callouts.png "系統管理中心Teams圖的使用者活動報告Teams螢幕擷取畫面")

## <a name="interpret-the-report"></a>解譯報表

| 標注 |描述  |
|--------|-------------|
|**1**   |您可以Teams使用者活動報告，查看過去 7 天、30 天或 90 天內的趨勢。 |
|**2**   |每個報表都有產生此報表的日期。 報告通常會反映啟用時間起 24 小時的延遲。 |
|**3**   |圖表中的時間系列資料點會顯示在租使用者處匯總的不同使用量度量。 |
|**4**   |表格式資料代表每個使用者匯總的不同使用量度量。 |
|**5**   |<ul><li>圖表上的 X 軸是報表的選取日期範圍。</li> <li> Y 軸是活動專案或活動的計數。</li> </ul>將游標停留在代表某個日期上某個專案或活動的點上，以查看該日期上該專案或活動的實例數目。|
|**6**   | 以租使用者層級的圖形表示的每個度量單位。 選取圖例中的專案，以篩選圖表上顯示的專案。 選取 **頻道訊息**、**回復訊息**、**聊天訊息** 或已組織會議，以查看每個訊息的相關資訊。 變更此選取範圍不會變更表格中的資訊。 |
|**7**   |下表提供使用者使用方式明細。   <ul><li>**顯示名稱** 是使用者的顯示名稱。 選取顯示名稱，以前往系統管理中心中的使用者Microsoft Teams頁面。</li><li>**頻道訊息** 是使用者在指定的時段內，在小組頻道中張貼的唯一訊息數目。</li><li>**回復訊息** 是使用者在指定的時段內，在小組頻道中張貼的唯一回復訊息數目。</li> <li>**張貼訊息** 是使用者在指定的時段內，在小組頻道中張貼的唯一張貼訊息數目。</li><li>**聊天訊息** 是使用者在指定的時段內，在私人聊天中張貼的唯一訊息數目。</li><li>**緊急訊息** 是使用者在指定的時段內張貼在聊天中的緊急訊息數目。</li><li>**已組織的會議** 總數是使用者在指定的時段內組織的一次排程、週期性、非計畫 <em></em>及未分類會議的總和。</li><li>**排定一次的會議** 是使用者在指定的時段內組織的一次排程會議數目。</li><li>**已排定的週期性會議** 是使用者在指定的時段內組織的週期性會議數目。</li><li>**組織的會議是** 使用者在指定的時段內所組織的非計畫會議數目。</li><li>**參與的會議** 總數是使用者在指定的時段內參與的一次性排程、週期性、非計畫及未分類 <em></em>會議的總和。</li><li>**已排程一次的會議** 是使用者在指定的時段內參與的一次排程會議數目。</li><li>**參與的會議已排定週期性** 是使用者在指定的時段內參與的週期性會議數目。</li><li>**參與的會議 adhoc** 是使用者在指定的時段內參與的未計畫會議數目。</li><li>**1：1** 通話是使用者在指定的時段內參與的 1：1 通話數。</li><li>**音訊時間** 是使用者 (時間) 參與的總音訊時間。</li><li>**視音訊時間** 是使用者 (期間) 視視時間的總) 分鐘數。</li><li>**螢幕共用時間** 是使用者 (時段) 參與的總螢幕共用時間。</li>  <li>**上次活動** 是使用者 (UTC) 最後一個Teams日期。</li><li>**其他活動** 會追蹤使用者被視為使用中狀態，但聊天訊息、1：1 通話、頻道訊息、會議總數及已組織會議的值為零。 例如，當使用者開啟頻道訊息文章，但無法回復該訊息，或使用者收到私人訊息並念出該訊息，但無法回復時，即會採取動作。</li> <li>**未分類** 的會議是無法歸類為排程、週期性或非計畫的會議。 這些數位很短，而且因為遙測資訊遭到竄改，因此大多無法識別</li> </ul>**群組通話** 已由會議 **組織 adhoc 和** Meetings 參與 **adhoc 取代**。 這兩個值的總和等於 Group 通話 **所測量的值**。
|**8**   |選取 **編輯欄** 以新增或移除表格中的欄。 |
|**9**   |將報表匯出為 CSV 檔案，進行離線分析。 選取 **匯出Excel，** 然後選取下載選項卡，選取下載以在報表準備就緒時下載報表。<br><br>![顯示要下載之匯出報表的下載清單的螢幕擷取畫面](../media/teams-reports-export-to-csv.png) <br>當您在 Excel中查看報表時，也會看到代表使用者 **識別碼的識別碼** 欄。 使用者識別碼通常是一個數位字串。 ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>將使用者特定資料匿名

若要將使用者活動報告中Teams匿名，您必須是全域系統管理員。 這會隱藏可辨識的資訊，例如顯示名稱、電子郵件和報表的 AAD 識別碼及其匯出。

1. 在 Microsoft 365 系統管理中心中，前往 設定 \> **組織** 設定，然後選擇在服務選項卡下，選擇報表。
    
2. 選取 **報表**，然後選擇顯示 **匿名識別碼**。 此設定會同時適用于系統管理中心Microsoft 365 系統管理中心Teams使用方式報告。
  
3. 選取 **儲存變更**。

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
