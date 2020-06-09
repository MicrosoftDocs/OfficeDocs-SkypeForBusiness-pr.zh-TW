---
title: 在 Microsoft 團隊系統管理中心管理團隊
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 瞭解如何在 Microsoft 團隊系統管理中心中查看或更新貴組織已設定共同作業的團隊。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ffc71de13948be077c14699e98fca726bced3eb
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638492"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>在 Microsoft 團隊系統管理中心管理團隊
==========================================

## <a name="overview"></a>概觀

本文將為 Microsoft 團隊系統管理中心的小組提供管理工具的概覽。

如果您是系統管理員，您可能需要查看或更新貴組織設定的共同作業小組，或者您可能需要執行修正動作，例如指派 ownerless 小組的擁有者。 您可以透過 Microsoft 團隊 PowerShell 模組和 Microsoft 團隊系統管理中心來管理組織中使用的團隊。 您可以存取系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。 若要使用這兩種工具集的完整管理功能，您應該確認您已獲指派下列其中一個角色：

- 全域系統管理員
- Teams 服務管理員

您可以在團隊中進一步瞭解如何[使用 Microsoft 團隊管理員角色來管理團隊](using-admin-roles.md)，並進一步瞭解如何使用 PowerShell Cmdlet 來管理[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的團隊。



## <a name="teams-overview-grid"></a>團隊概覽格線

小組的管理工具位於 Microsoft 團隊系統管理中心的 [**小組**] 節點底下。 （在系統管理中心中，選取 [**團隊**  >  ]**管理團隊**。）每個團隊都是由 Microsoft 365 群組所支援，而這個節點提供已在貴組織中啟用 Microsoft 團隊的群組視圖。

![[團隊概覽] 格線的螢幕擷取畫面](media/manage-teams-in-modern-portal-grid.png)  

格線會顯示下列屬性：

- **團隊名稱**
- [**頻道**]-團隊中所有頻道的計數，包括預設的 [一般] 頻道。
- **小組成員**-總使用者數目，包括來自您租使用者的擁有者、來賓和成員。
- [**擁有**者]-此小組的擁有者人數。
- **來賓**-此團隊成員的 Azure ACTIVE Directory B2B 來賓使用者的計數。
- **隱私權**-支援的 Microsoft 365 群組的可見度/AccessType。
- [**狀態**]-此小組的已存檔或活動狀態。 進一步瞭解封存[或還原小組中的](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)團隊。
- **描述**-支援的 Microsoft 365 群組的描述。
- **分類**-指派給支援 Microsoft 365 群組的分類（如果您的組織使用的話）。 深入瞭解[貴組織中 Office 群組的建立分類](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。
- **GroupID** -支援的 Microsoft 365 群組的唯一 GroupID。

> [!NOTE]
> 如果您沒有在格線中看到所有這些屬性，請按一下 [**編輯欄**] 圖示。 在 [**編輯欄**] 窗格中，您可以使用切換來開啟或關閉格線中的欄。 完成後，**請按一下 [** 套用]。

### <a name="add"></a>Add

若要新增團隊，**請按一下 [新增]**。 在 [**新增團隊**] 窗格中，給予團隊名稱和描述，設定您要將它設為私人小組或公開團隊，並設定分類。

### <a name="edit"></a>編輯

若要編輯群組和小組專用的設定，請按一下團隊名稱左方，然後選取 [**編輯**]，以選取團隊。

### <a name="archive"></a>壓縮

您可以封存小組。 封存小組會將小組放入小組中的唯讀模式。 做為管理員，您可以在系統管理中心中代表您的組織封存和取消封存小組。 

### <a name="delete"></a>Delete

刪除小組是小組及對應的 Microsoft 365 群組的虛刪除。 若要還原錯誤刪除的小組，請依照[還原已刪除的群組](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)中的指示進行。

### <a name="search"></a>檢索

搜尋目前支援字串「開始于」，並搜尋 [**小組名稱**] 欄位。

## <a name="team-profile"></a>小組設定檔

您可以按一下 [團隊名稱]，從 [主要團隊概覽] 格線流覽至任何團隊的 [團隊個人檔案] 頁面。 [小組個人檔案] 頁面會顯示屬於小組（及其支援的 Microsoft 365 群組），以及小組的頻道與設定的成員、擁有者和來賓。 您可以從 [團隊設定檔] 頁面進行下列動作：

- 新增或移除成員和擁有者。
- 新增或移除頻道（請注意，您無法移除 [一般] 頻道）。
- 變更小組和群組設定。
 
![範例小組設定檔的螢幕擷取畫面](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>對團隊進行變更

在團隊的 [設定檔] 頁面上，您可以變更團隊的下列元素：

- [**成員**]-新增或移除成員以及提升或降級擁有者。
- **頻道**-新增頻道，以及編輯或移除現有頻道。 請記住，您無法刪除預設的 [一般] 頻道。
- **團隊名稱**
- **描述**
- **隱私權**-設定團隊是否為公用或私人。
- **分類**-這是由您的 Microsoft 365 群組分類所支援。 選擇 [**機密**]、[**高度機密**] 或 **[一般**]。
- [**交談設定**]-設定成員是否可以編輯及刪除已傳送的郵件。
- **頻道設定**-設定成員是否可以建立新的頻道，以及編輯現有的頻道，以及新增、編輯及移除索引標籤、連接器及應用程式。

您對小組所做的變更會記錄下來。 如果您要修改群組設定（變更名稱、描述、相片、隱私權、分類或團隊成員），這些變更將會透過審核管線進行設定。 如果您要針對特定團隊的設定執行動作，您的變更會在團隊的 [一般] 頻道中追蹤並設定為 [已設定]。

## <a name="troubleshooting"></a>疑難排解

**問題：團隊概覽格線中缺少團隊**

[團隊概述] 網格中的小組清單中遺失了一些團隊。

**原因**：當小組不正確（或尚未）由系統所分析，可能會導致其無法辨識某個缺少的屬性時，就會發生這個問題。

**解析度：透過 MS Graph 將屬性手動設定為正確的值**

在查詢中，使用「 ** [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) ** 」 Cmdlet 做為「**ExternalDirectoryObjectId**」屬性，取代 **{GroupId}** ，以取得實際的 groupid，您可以透過 Exchange Online powershell 取得該問題。

1. Access[圖形瀏覽器](https://developer.microsoft.com/graph/graph-explorer)。

2. 在左側功能表中登入圖表資源管理器。

3. 將查詢行變更為： PATCH > v 1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} 。

4. 在要求主體上加上下列值： {"resourceProvisioningOptions"： ["團隊"]}。

5. 在右上方執行查詢。

6. 確認小組已正確顯示在 Microsoft 團隊系統管理中心-小組概述中。

## <a name="learn-more"></a>深入了解

- [團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [使用團隊管理員角色管理團隊](using-admin-roles.md)
- [Teams 中的生命週期管理方案](plan-teams-lifecycle.md)
