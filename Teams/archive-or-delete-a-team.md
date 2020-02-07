---
title: 在 Microsoft 團隊中封存或刪除小組
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 瞭解如何封存或永久刪除小組。
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
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826401"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>在 Microsoft 團隊中封存或刪除小組
===========================================

隨著時間的推移，在 Microsoft 團隊中建立的小組可能不在使用中，或者您可能想要在專案結束時封存或刪除小組。 如果您是 Microsoft 團隊管理員，請按照本文所述的步驟來封存或刪除不再需要的小組。

當您封存小組時，該小組的所有活動都會停止。 封存小組也會將小組及其相關網站集合中的私人頻道存檔。  不過，您仍然可以新增或移除成員並更新角色，您仍然可以在標準和私人通道、檔案和聊天中查看所有團隊活動。

刪除小組時，也會刪除標準和專用頻道（以及相關聯的網站集合）、檔案和聊天中的小組活動。

> [!IMPORTANT]
> 封存的團隊可以重新啟用，但您無法直接還原已刪除的小組。 考慮先封存團隊，然後推遲刪除，直到您確定不再需要團隊為止。

## <a name="archive-a-team"></a>封存團隊

請依照下列步驟封存小組。

1. 在 Microsoft [團隊管理中心] 中，選取 [**團隊**]。
2. 按一下團隊名稱以選取團隊。
3. 選取 **[** 封存]。 隨後便會出現下列訊息。

    ![[小組封存] 訊息的螢幕擷取畫面](media/teams-archive-message.png)

4. 如果您想要將小組的 SharePoint 網站設為唯讀，請選取核取方塊。
5. 選取 **[** 封存] 以封存小組。 團隊的狀態將會變更為 [已**存檔**]。

## <a name="make-an-archived-team-active"></a>使封存的小組成為使用中狀態

請依照下列步驟，讓封存的小組再次生效。

1. 在 Microsoft [團隊管理中心] 中，選取 [**團隊**]。
2. 按一下團隊名稱以選取團隊。
3. 選取 [ **Unarchive**]。 團隊的狀態將會**變更為 [作用中]**。

## <a name="delete-a-team"></a>刪除小組

如果將來不需要該小組，您可以將它刪除，而不是將它封存。 請依照下列步驟刪除小組。

1.  在 Microsoft [團隊管理中心] 中，選取 [**團隊**]。
2.  按一下團隊名稱以選取團隊。
3.  選取 [**刪除**]。 隨即會出現一則確認訊息。
4.  選取 [**刪除**] 以永久刪除該小組。

## <a name="restore-a-deleted-team"></a>還原已刪除的小組

若要還原已刪除的小組，請執行下列步驟，還原與小組相關聯的 Office 365 群組。 還原小組的 Office 365 群組、還原小組內容，包括索引標籤、標準通道、專用通道及其相關網站集合。

根據預設，已刪除的 Office 365 群組會保留30天。 此30天期間稱為「虛刪除」，因為您可以還原該群組。 若要深入瞭解，請參閱[還原已刪除的 Office 365 群組](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)。

### <a name="install-the-azureadpreview-module"></a>安裝 AzureADPreview 模組

1. 以系統管理員身分開啟 Windows PowerShell。
2. 如果您已安裝舊版的 AzureADPreview 模組，或已安裝 AzureAD 模組，請執行下列其中一項操作以將它卸載：

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. 若要安裝最新版本的 AzureADPreview 模組，請執行下列動作：

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>還原已刪除的 Office 365 群組

1. 若要連線到 Azure AD，請執行下列動作：
    ```PowerShell
    Connect-AzureAD
    ```
    出現提示時，請使用您的系統管理員帳戶和密碼登入。  
2. 執行下列動作，以顯示仍在30天保留期間內的所有虛刪除 Office 365 群組清單。 如果您有許多群組，請使用 **-All $True**參數。
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. 找出您要還原的群組，然後記下 Id。
4. 執行下列動作來還原群組，其中 [Id] 是 [群組識別碼]。
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  執行下列動作以驗證群組已順利還原，其中 [Id] 是群組識別碼。
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    完成還原程式最多可能需要24小時，之後，小組中就會顯示與小組相關的小組和內容，包括索引標籤和頻道。
