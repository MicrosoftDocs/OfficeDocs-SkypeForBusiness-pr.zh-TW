---
title: 在搜尋中Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 瞭解如何在 Microsoft 365 合規性中心 中使用內容搜尋Microsoft Teams搜尋儲存在 Exchange Online、SharePoint Online、商務用 OneDrive 和 OneNote 中的內容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6810355304371564a2a305c82290df7667f5efd41889e598021636cc9ccd11d4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278211"
---
# <a name="use-content-search-in-microsoft-teams"></a>在搜尋中Microsoft Teams

> [!NOTE]
> 私人頻道中郵件和檔案的內容 [搜尋](private-channels.md) 與標準頻道不同。 若要深入瞭解，請參閱 [私人頻道的內容搜尋](#content-search-of-private-channels)。

內容搜尋提供一種查詢Microsoft Teams、Exchange、SharePoint和商務用 OneDrive。

若要深入瞭解，請參閱在 Microsoft 365[中搜尋內容](/microsoft-365/compliance/content-search)。

例如，針對您的製造規格信箱和製造規格 SharePoint 網站使用內容搜尋，您可以搜尋 Exchange 中的 Teams 標準頻道交談、SharePoint Online 的檔案上傳和修改，以及 OneNote 變更。

您也可以在內容搜尋中新增查詢 **準則** ，以縮小結果的返回範圍。 在上例中，您可以尋找使用關鍵字「**新工廠規格」** 的內容。

> [!TIP]
> 新增搜尋條件之後，您可以將報表或實際內容匯出至電腦進行分析。

## <a name="content-search-of-private-channels"></a>私人頻道的內容搜尋

在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。 記錄的標題會有格式設定，指出寄自哪一個私人頻道。

由於每個私人頻道都有SharePoint與父小組網站分開的網站集合，因此私人頻道中的檔案會獨立于父團隊管理。

Teams不支援單一頻道的內容搜尋，因此必須搜尋整個團隊。 若要執行私人頻道的內容搜尋，請搜尋整個小組、與私人頻道關聯的網站集合 (以包含檔案) ，以及私人頻道成員的信箱 (以包含郵件) 。

使用下列步驟來識別私人頻道中的檔案和郵件，以納入內容搜尋。

### <a name="include-private-channel-files-in-a-content-search"></a>在內容搜尋中納入私人頻道檔案

執行這些步驟之前，請安裝[SharePoint管理命令殼，然後連線至 SharePoint Online。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. 執行下列操作，以取得小組中SharePoint私人頻道的所有網站集合清單。

    ```PowerShell
    Get-SPOSite
    ```
2. 執行下列 PowerShell 腳本，以取得SharePoint中與私人頻道相關聯的所有網站集合 URL 清單，以及父團隊群組識別碼。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 針對每個小組或群組識別碼，執行下列 PowerShell 腳本，以識別所有相關的私人頻道網站。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>在內容搜尋中納入私人頻道訊息

執行這些步驟之前，請確定已安裝最新版本的 PowerShell 模組Teams [PowerShell 模組](teams-powershell-overview.md)。

1. 執行下列操作以取得團隊中的私人頻道清單。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 執行下列操作以取得私人頻道成員的清單。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 在內容搜尋查詢中，包含團隊中每個私人頻道中所有成員的信箱。

## <a name="related-topics"></a>相關主題

- [Microsoft 365規範中心中的電子Microsoft 365案例](/Office365/SecurityCompliance/ediscovery-cases)