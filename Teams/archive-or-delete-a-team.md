---
title: 在 Microsoft Teams 中封存或刪除團隊
manager: serdars
ms.author: mikeplum
author: MikePlumleyMSFT
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 在本文中，您將瞭解如何封存或永久刪除 Microsoft Teams 中的團隊。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79a9472286a7e08e8c6dce4c4f40d76b7e4f2b4e
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198965"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a>在 Microsoft Teams 中封存或刪除團隊

經過一段時間後，在 Microsoft Teams 中建立的小組可能不再使用，或是您可能想要在專案結束時封存或刪除小組。 如果您是 Microsoft Teams 的系統管理員，請按照本文所述的步驟封存或刪除不再需要的小組。  (如果您是團隊擁有者，您也可以 [封存團隊](https://support.microsoft.com/office/dc161cfd-b328-440f-974b-5da5bd98b5a7)。) 

當您封存小組時，該小組的所有活動都會停止。 封存小組也會封存小組的私人頻道及其相關網站集合。  但是，您仍然可以新增或移除成員、更新角色，而且仍然可以在標準和私人頻道、檔案、聊天中檢視所有的小組活動。

當您刪除團隊時，也會刪除標準和私人頻道中的團隊活動 (以及相關聯的網站集合) 、檔案和聊天。

> [!IMPORTANT]
> 您可以重新啟用已封存的團隊，但您無法直接還原已刪除的團隊。 請先考慮封存小組，並延後刪除，直到確定您不再需要小組。

## <a name="archive-a-team"></a>封存小組

按照這些步驟以封存小組。 您必須是 Teams 服務系統管理員才能進行這些變更。 請參閱[使用 Teams 系統管理員角色來管理 Teams](./using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 在系統管理中心中，選 **取 [Teams]**。
2. 按一下小組名稱以選取小組。
3. 選取 [封存]。 將會出現下列訊息。

    ![Teams 封存訊息的螢幕擷取畫面。](media/teams-archive-message.png)

4. 若要防止人員編輯 SharePoint 網站中的內容，以及與小組相關聯的 Wiki 索引標籤，請選取 [ **讓小組成員唯讀 SharePoint 網站]**。  (Teams 擁有者仍然可以編輯此內容。) 
5. 選取 [封存] 以封存小組。 團隊的狀態會變更為 [ **已封存**]，暫時可在位於團隊清單底部的 [ **隱藏的團隊** ] 內使用，並在旁邊新增一個代表封存狀態的小圖示。 從 **[隱藏的團隊** ] 中移除後，它就會出現在 [封存] 下的 [ **管理團隊** ] **檢視中**。 若要檢視及搜尋封存團隊的內容，請在 [ **封存** ] 清單中選取其名稱。

## <a name="make-an-archived-team-active"></a>讓封存的小組成為使用中

按照下列步驟，讓封存的小組成為使用中。

1. 在系統管理中心中，選 **取 [Teams]**。
2. 按一下小組名稱以選取小組。
3. 選取 **[還原]**。 團隊的狀態會變更為 [ **使用中]**。 請注意，系統不會自動將它移回 **[您的團隊]** 內。

## <a name="delete-a-team"></a>刪除小組

如果未來不再需要小組，您可以將它刪除，而不只是封存。 按照下列步驟刪除小組。

1. 在系統管理中心中，選 **取 [Teams]**。
2. 按一下小組名稱以選取小組。
3. 選取 [刪除]。 將會出現確認訊息。
4. 選取 [刪除] 以永久刪除小組。

## <a name="restore-a-deleted-team"></a>還原刪除的小組

請依照下列步驟還原與團隊關聯的Microsoft 365 群組，以還原已刪除的團隊。 還原團隊的 Microsoft 365 群組會還原團隊內容，包括索引標籤、標準頻道和私人頻道及其相關聯的網站集合。

根據預設，已刪除Microsoft 365 群組會保留 30 天。 此 30 天期間稱為「虛刪除」，因為您可還原該群組。 若要深入瞭解，請參閱 [還原已刪除的群組](/microsoft-365/admin/create-groups/restore-deleted-group)。

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

### <a name="restore-the-deleted-microsoft-365-group"></a>還原已刪除的Microsoft 365 群組

1. 執行下列命令連線到 Azure AD：

    ```PowerShell
    Connect-AzureAD
    ```

    當您看到提示時，使用您的系統管理員帳戶和密碼登入。

1. 執行下列動作以顯示 30 天保留期間內的所有虛刪除Microsoft 365 群組清單。 如果您有許多群組，請使用 **-All $True** 參數。

    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```

1. 尋找您要還原的群組，然後記下 `Id` 。
1. 執行下列動作以還原群組，其所在為 `[Id]` 群組識別碼。

    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```

1. 執行下列動作以確認群組已成功還原，群組識別碼在哪裡 `[Id]` 。

    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    完成還原程序最多可能需要 24 小時，之後就會在 Teams 中顯示小組以及小組相關聯的內容 (包括索引標籤和頻道) 。

## <a name="related-topics"></a>相關主題

- [封存或還原團隊](https://support.microsoft.com/office/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

