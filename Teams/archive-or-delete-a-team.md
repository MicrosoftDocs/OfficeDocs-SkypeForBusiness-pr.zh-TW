---
title: 在 Microsoft Teams 中封存或刪除團隊
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 瞭解如何永久封存或刪除小組。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e367fe85f1af35391fa00b4a416b6e796383d962
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826401"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>在 Microsoft Teams 中封存或刪除團隊
===========================================

經過一段時間後，在 Microsoft Teams 中建立的小組可能不再使用，或是您可能想要在專案結束時封存或刪除小組。 如果您是 Microsoft Teams 的系統管理員，請按照本文所述的步驟封存或刪除不再需要的小組。

當您封存小組時，該小組的所有活動都會停止。 封存小組也會封存小組的私人頻道及其相關網站集合。  但是，您仍然可以新增或移除成員、更新角色，而且仍然可以在標準和私人頻道、檔案、聊天中檢視所有的小組活動。

當您刪除小組時，也會刪除標準和私人頻道 (以及相關聯的網站集合)、檔案、聊天中的小組活動。

> [!IMPORTANT]
> 封存的小組可以重新啟用，但是您無法直接還原已刪除的小組。 請先考慮封存小組，並延後刪除，直到確定您不再需要小組。

## <a name="archive-a-team"></a>封存小組

按照這些步驟以封存小組。

1. 在 Microsoft Teams 系統管理中心，選取 [小組]****。
2. 按一下小組名稱以選取小組。
3. 選取 [封存]****。 將會出現下列訊息。

    ![螢幕擷取畫面：Teams 封存訊息](media/teams-archive-message.png)

4. 如果您想要讓小組的 SharePoint 網站變成唯讀，請選取該核取方塊。
5. 選取 [封存]**** 以封存小組。 小組的狀態會變更為 [已封存]****。

## <a name="make-an-archived-team-active"></a>讓封存的小組成為使用中

按照下列步驟，讓封存的小組成為使用中。

1. 在 Microsoft Teams 系統管理中心，選取 [小組]****。
2. 按一下小組名稱以選取小組。
3. 選取 [解除封存]****。 小組的狀態會變更為 [使用中]****。

## <a name="delete-a-team"></a>刪除小組

如果未來不再需要小組，您可以將它刪除，而不只是封存。 按照下列步驟刪除小組。

1.  在 Microsoft Teams 系統管理中心，選取 [小組]****。
2.  按一下小組名稱以選取小組。
3.  選取 [刪除]****。 將會出現確認訊息。
4.  選取 [刪除]**** 以永久刪除小組。

## <a name="restore-a-deleted-team"></a>還原刪除的小組

請按照下列步驟，藉由還原與小組相關聯的 Office 365 群組，來還原已刪除的小組。 還原小組的 Office 365 群組，會還原小組內容，包括索引標籤、標準頻道和私人頻道、及其關聯的網站集合。

依預設，刪除的 Office 365 群組會保留 30 天。 此 30 天期間稱為「虛刪除」，因為您可還原該群組。 如需深入了解，請參閱[還原已刪除的 Office 365 群組](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)。

### <a name="install-the-azureadpreview-module"></a>安裝 AzureADPreview 模組

1. 以系統管理員身分開啟 Windows PowerShell。
2. 如果您已安裝舊版 AzureADPreview 模組或 AzureAD 模組，請執行下列其中一項操作將其解除安裝：

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. 執行以下命令安裝最新版 AzureADPreview 模組：

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>還原刪除的 Office 365 群組

1. 執行下列命令連線到 Azure AD：
    ```PowerShell
    Connect-AzureAD
    ```
    當您看到提示時，使用您的系統管理員帳戶和密碼登入。  
2. 執行以下命令以顯示所有仍在 30 天保留期限內的虛刪除 Office 365 群組清單： 如果有大量群組，請使用 **-All $True** 參數。
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. 尋找您要還原的群組，然後記下識別碼。
4. 執行下列命令來還原群組，其中 [Id] 是群組識別碼。
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  執行下列命令來確認群組還原是否成功，其中 [Id] 是群組識別碼。
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    完成還原程序最多可能需要 24 小時，之後就會在 Teams 中顯示小組以及小組相關聯的內容 (包括索引標籤和頻道) 。
