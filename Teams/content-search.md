---
title: 在 Microsoft Teams 中使用內容搜尋
author: v-tophillips
ms.author: v-tophillips
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
description: 瞭解如何在 Microsoft Purview 合規性入口網站中使用內容搜尋來搜尋儲存在 Exchange Online、SharePoint Online、商務用 OneDrive 和 OneNote 中的Microsoft Teams內容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88f44bffaa3bf2dc125dad5f2d7595d08f49bffd
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031858"
---
# <a name="use-content-search-in-microsoft-teams"></a>在 Microsoft Teams 中使用內容搜尋

> [!NOTE]
> [私人頻道](private-channels.md)中訊息和檔案的內容搜尋運作方式與標準頻道不同。 若要深入瞭解，請參閱 [私人頻道的內容搜尋](#content-search-of-private-channels)。

內容搜尋可讓您查詢Exchange、SharePoint Online 和 商務用 OneDrive 等Microsoft Teams資訊。

若要深入瞭解，請參閱[Microsoft 365中的內容搜尋](/microsoft-365/compliance/content-search)。

例如，針對製造規格信箱和製造規格SharePoint網站使用 **內容搜尋**，您可以搜尋Exchange Teams的標準頻道交談、從 SharePoint Online 上傳檔案和修改，以及OneNote變更。

您也可以將查詢準則新增至 **內容搜尋** ，以縮小傳回的結果範圍。 在上述範例中，您可以尋找使用「**New Factory Specs」** 關鍵字的內容。

> [!TIP]
> 新增搜尋條件之後，您可以將報表或實際內容匯出至電腦進行分析。

## <a name="content-search-of-private-channels"></a>私人頻道的內容搜尋

在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。 記錄的標題會有格式設定，指出寄自哪一個私人頻道。

因為每個私人頻道都有專屬的SharePoint網站集合，與上層小組網站是分開的，因此私人頻道中的檔案會獨立于上層小組管理。

Teams不支援單一頻道的內容搜尋，因此必須搜尋整個團隊。 若要執行私人頻道的內容搜尋，請在整個小組中搜尋、與私人頻道關聯的網站集合 (包含檔案) ，以及私人頻道成員的信箱 (包含訊息) 。

使用下列步驟來識別私人頻道中的檔案和訊息，以包含在您的內容搜尋中。

### <a name="include-private-channel-files-in-a-content-search"></a>在內容搜尋中包含私人頻道檔案

執行這些步驟之前，請先安裝[SharePoint線上管理命令介面，然後連線至 SharePoint Online。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. 執行下列動作以取得與團隊中私人頻道關聯的所有SharePoint網站集合清單。

    ```PowerShell
    Get-SPOSite
    ```
2. 執行下列 PowerShell 腳本，以取得團隊中與私人頻道關聯的所有SharePoint網站集合 URL 清單，以及上層團隊群組識別碼。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 針對每個小組或群組識別碼，執行下列 PowerShell 腳本以識別所有相關的私人頻道網站。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>在內容搜尋中包含私人頻道訊息

執行這些步驟之前，請確定您已安裝[最新版本的 Teams PowerShell 模組](teams-powershell-overview.md)。

1. 執行下列動作以取得團隊中的私人頻道清單。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 執行下列動作以取得私人頻道成員清單。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 在內容搜尋查詢中，包含團隊中每個私人頻道的所有成員信箱。

## <a name="related-topics"></a>相關主題

- [Microsoft Purview 合規性入口網站中的電子檔探索案例](/Office365/SecurityCompliance/ediscovery-cases)