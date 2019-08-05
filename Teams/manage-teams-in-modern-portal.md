---
title: 在 Microsoft 團隊系統管理中心管理團隊
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 瞭解如何在 Microsoft 團隊系統管理中心中查看或更新您的小組。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183858"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>在 Microsoft 團隊系統管理中心管理團隊
==========================================


## <a name="overview"></a>概觀

做為 IT 系統管理員, 您可能需要查看或更新貴組織已設定共同作業的小組, 或者您可能需要執行修正動作, 例如指派 ownerless 小組的擁有者。 您可以透過 Microsoft 團隊 PowerShell 模組和 Microsoft 團隊系統管理中心來管理組織中使用的團隊。 若要使用這兩種工具集的完整管理功能, 您應該確認您已獲指派下列其中一個角色:

- 全域系統管理員
- 團隊服務管理員

您可以在團隊中進一步瞭解如何[使用 Microsoft 團隊管理員角色來管理團隊](using-admin-roles.md), 並進一步瞭解如何使用 PowerShell Cmdlet 來管理[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的團隊。  

本文將為 Microsoft 團隊系統管理中心的小組提供管理工具的概覽。

## <a name="teams-overview-grid"></a>團隊概覽格線

小組的管理工具位於 Microsoft 團隊系統管理中心的 [**小組**] 節點底下。 (在系統管理中心中, 選取 [**團隊** > **管理團隊**])。每個團隊都受 Office 365 群組的支援, 而且這個節點提供已在貴組織中啟用 Microsoft 團隊的群組視圖。

![[團隊概述] 格線的螢幕擷取畫面](media/manage-teams-in-modern-portal-image1.png)  

格線會顯示下列屬性:

- **團隊名稱**
- [**頻道**]-團隊中所有頻道的計數, 包括預設的 [一般] 頻道。
- **使用者**-使用者總數, 包括您租使用者的擁有者、來賓和成員。
- [**擁有**者]-此小組的擁有者人數。
- **來賓**-此團隊成員的 Azure ACTIVE Directory B2B 來賓使用者的計數。
- **隱私權**-支援 Office 365 群組的可見度/AccessType。
- [**狀態**]-此小組的已存檔或活動狀態。  進一步瞭解封存[或還原小組](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)中的團隊。
- **GroupID** -支援 Office 365 群組的唯一 GroupID
- **分類**-指派給支援 Office 365 群組的分類 (如果您的組織使用的話)。  深入瞭解[貴組織中 Office 群組的建立分類](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。
- **描述**-針對支援的 Office 365 群組設定的描述

### <a name="search"></a>檢索

搜尋目前支援字串「開始于」, 並搜尋 [**小組名稱**] 欄位。

### <a name="edit"></a>編輯

您可以從格線選取小組, 然後選取 [**編輯**] 按鈕, 以編輯群組和小組特定的設定。

![[編輯團隊選項] 的螢幕擷取畫面](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>小組設定檔

您可以按一下團隊名稱, 從 [主要團隊概覽] 格線流覽至任何團隊的 [團隊個人檔案] 頁面。 [小組個人檔案] 頁面會顯示屬於小組 (及其後備 O365 群組), 以及小組的頻道與設定的成員、擁有者和來賓。 您可以從 [團隊設定檔] 頁面進行下列動作:

- 新增或移除成員和擁有者。
- 新增或移除頻道 (請注意, 您無法移除 [一般] 頻道)。
- 更新小組和群組設定。
 
![範例小組設定檔的螢幕擷取畫面](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>對團隊進行變更

您可以變更團隊的下列元素:
- **小組中的使用者**-您可以新增或移除成員, 以及提升或降級擁有者
- **頻道**-您可以新增頻道, 或移除現有的頻道。  您無法刪除預設的「一般」通道, 一旦建立之後就只能編輯頻道名稱, 不能編輯描述。
- **團隊名稱**
- **團隊描述**
- **小組隱私權**-公開或私人
- **團隊分類**-由您的 Office 365 群組分類支援
- **小組成員設定**-選取團隊成員設定

## <a name="other-supported-changes-to-teams"></a>小組所支援的其他變更

- **刪除**-刪除小組是小組和對應 Office 365 群組的虛刪除。  若要還原錯誤刪除的小組, 請依照[還原已刪除的 Office 365 群組](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)中的指示進行。
- **** 封存封存小組會將小組放入 Microsoft 團隊中的唯讀模式。  做為管理員, 您可以透過管理入口網站代表您的組織來封存及 unarchive 小組。


您對小組所做的變更會記錄下來。 如果您要修改群組設定 (變更名稱、描述、相片、隱私權、分類或團隊成員), 這些變更將會透過審核管線進行設定。 如果您要針對團隊特定設定執行動作, 您的變更將會在團隊的 [一般] 頻道中追蹤並設定為 [已設定]。

## <a name="troubleshooting"></a>疑難排解

**問題: 團隊概覽格線中缺少團隊**

當您輸入 Microsoft 團隊系統管理中心時, 請在 [**團隊**] 選項下的 [團隊總覽] 格線清單中找不到某些團隊。

**原因**: 當小組不正確 (或尚未) 由系統所分析, 可能會導致其無法辨識某個缺少的屬性時, 就會發生這個問題。

**解析度: 透過 MS Graph 將屬性手動設定為正確的值**

在查詢中, 使用「 ** [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps) ** 」 Cmdlet 做為「**ExternalDirectoryObjectId**」屬性, 取代 **{GroupId}** , 以取得實際的 groupid, 您可以透過 Exchange Online powershell 取得該問題。

1. Access[圖形瀏覽器](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. 在左側功能表中登入圖表資源管理器

3. 將查詢行變更為: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. 在要求主體上加上下列值: {"resourceProvisioningOptions": ["團隊"]}

5. 在右上方執行查詢。

6. 確認團隊在 Microsoft 團隊系統管理中心中正確顯示-小組概述


## <a name="learn-more"></a>瞭解更多資訊

[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Microsoft 團隊中的管理員角色](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

