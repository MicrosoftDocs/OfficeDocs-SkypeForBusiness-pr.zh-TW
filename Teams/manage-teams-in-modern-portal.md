---
title: 在 Microsoft Teams 系統管理中心管理團隊
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 瞭解如何在 Microsoft Teams 系統管理中心中，查看或更新貴組織為共同合作所設定的團隊。
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
ms.openlocfilehash: 6bf864fefd3ac60c7531bd339a5587c8f2f0dd72
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094233"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理團隊
==========================================

## <a name="overview"></a>概觀

本文提供 Microsoft Teams 系統管理中心的 Teams 管理工具概觀。

作為系統管理員，您可能需要查看或更新貴組織為共同合作所設定的團隊，或者您可能需要執行補救動作，例如指派無擁有者團隊的擁有者。 您可以透過 Microsoft Teams PowerShell 模組和 Microsoft Teams 系統管理中心來管理貴組織中所使用的團隊。 您可以在 存取系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。 針對使用這兩個工具集的完整管理功能，您應該確定已指派下列其中一個角色：

- 全域系統管理員
- Teams 服務管理員

您可以在使用 [Microsoft Teams](using-admin-roles.md)系統管理員角色管理 Teams 中深入瞭解 Teams 中的系統管理員角色，並深入瞭解如何使用 PowerShell Cmdlet 在 Microsoft [Teams Cmdlet](/powershell/teams/?view=teams-ps)參照中管理團隊。



## <a name="teams-overview-grid"></a>Teams 概觀格線

團隊管理工具位於 Microsoft Teams 系統管理中心的 **Teams** 節點下。  (在系統管理中心中，選取Teams Manage teams .) 每個團隊都有 Microsoft 365 群組的支援，此節點會提供組織中已啟用 Microsoft Teams 的群組  >  的視圖。

![Teams 概觀格線螢幕擷取畫面](media/manage-teams-in-modern-portal-grid.png)  

格線會顯示下列屬性：

- **團隊名稱**
- **頻道** - 團隊中所有頻道的計數，包括預設的一般頻道。
- **小組成員** - 來自租使用者的使用者總數，包括擁有者、來賓和成員。
- **擁有者** - 此團隊的擁有者計數。
- **來賓** - 此小組成員的 Azure Active Directory B2B 來賓使用者計數。
- **隱私權** - 支援 Microsoft 365 群組的可見度/AccessType。
- **狀態** - 此團隊的已存檔或活動狀態。 深入瞭解在檔案或還原團隊中[將團隊存檔。](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)
- **描述** - 支援 Microsoft 365 群組的描述。
- **分類** ： (組織中使用的分類) 指派給支援 Microsoft 365 群組。 若要深入瞭解分類，請至為貴組織的 [Office 群組建立分類](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。
- **GroupID** - 支援 Microsoft 365 群組的唯一 GroupID。

> [!NOTE]
> 如果您在格線中沒看到所有這些屬性，請按一下 [ **編輯欄圖示** 。 在編輯 **欄** 窗格中，您可以使用切換開關來開啟或關閉格線中的欄。 完成後，按一下 **[Apply.**

### <a name="add"></a>添加

若要新增團隊，請按一下 [ **新增**。 在新增 **團隊窗格中** ，為團隊命名和描述，設定您是否要將其設為私人或公開團隊，並設定分類。

> [!NOTE]
> 新建立的團隊可以馬上在 Teams 系統管理中心管理，不像 Outlook 等其他用戶端的體驗。

### <a name="edit"></a>編輯

若要編輯群組和團隊特定設定，請按一下團隊名稱左側的選取團隊，然後 **選取編輯**。

### <a name="archive"></a>檔案

您可以存檔團隊。 將小組歸檔後，團隊會進入 Teams 中的唯讀模式。 做為系統管理員，您可以在系統管理中心代表貴組織來存檔和取消存檔團隊。 

### <a name="delete"></a>刪除

刪除團隊是小組和對應的 Microsoft 365 群組的輕柔刪除。 若要還原誤刪除的團隊，請遵循還原已刪除的群組 [中的指示](/microsoft-365/admin/create-groups/restore-deleted-group)。

### <a name="search"></a>搜索

搜尋目前支援字串「開頭」，並搜尋 **團隊名稱** 欄位。

## <a name="team-profile"></a>小組設定檔

您可以按一下團隊名稱，從主要團隊概觀格線流覽至任何團隊的小組設定檔頁面面。 小組設定檔頁面面會顯示屬於小組 (的成員、擁有者和來賓及其支援 Microsoft 365 群組) ，以及團隊的頻道和設定。 從小組設定檔頁面面，您可以：

- 新增或移除成員和擁有者。
- 新增或移除 (，請注意，您無法移除一般) 。
- 變更小組和群組設定。
 
![範例小組設定檔的螢幕擷取畫面](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>變更團隊

在小組的設定檔頁面面上，您可以變更團隊的下列元素：

- **成員** - 新增或移除成員，並提升或降級擁有者。
- **頻道** - 新增頻道，以及編輯或移除現有的頻道。 請記住，您無法刪除預設的一般頻道。
- **團隊名稱**
- **描述**
- **隱私權** - 設定團隊是公開還是私人。
- **分類** - 這是由您的 Microsoft 365 群組分類所支援。 選擇 **機密**、 **高度機密** 或 **一般**。
- **交談設定** - 設定成員是否可以編輯和刪除已送出的郵件。
- **頻道設定** - 設定成員是否可以建立新頻道及編輯現有的頻道，以及新增、編輯及移除定位停駐點、連接器和應用程式。

您對團隊的變更會記錄。 如果您要修改群組設定 (變更名稱、描述、相片、隱私權、分類或小組成員) ，這些變更會透過稽核管道歸您所有。 如果您針對 Teams 特定設定執行動作，系統會追蹤您的變更，並歸結于團隊的一般頻道中。

## <a name="troubleshooting"></a>疑難排解

**問題：團隊概觀格線中缺少團隊**

Teams 概觀格線中的團隊清單中缺少部分團隊。

**原因**：當小組未正確 (或尚未) 系統所設定檔時，會發生此問題，可能會導致屬性遺失，無法識別。

**解析度：透過 MS Graph 手動將屬性設定為正確的值**

在查詢中將 **{groupid}** 取代為問題的實際 GroupId，您可以透過 Exchange Online Powershell 取得此名稱，以 **[「Get-UnifiedGroup」](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)** Cmdlet 取代為 **「ExternalDirectoryObjectId」** 屬性。

1. Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer)。

2. 在左側功能表上，請登錄 Graph Explorer。

3. 將查詢行變更為：PATCH > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >。

4. 在要求主體上新增下列值：{"resourceProvisioningOptions"：["Team"]}。

5. 在右上方執行查詢。

6. 確認小組正確顯示在 Microsoft Teams 系統管理中心 - 團隊概觀中。

## <a name="learn-more"></a>深入了解

- [Teams Cmdlet 參照](/powershell/teams/?view=teams-ps)  
- [使用 Teams 系統管理員角色來管理 Teams](using-admin-roles.md)
- [Teams 中的生命週期管理方案](plan-teams-lifecycle.md)