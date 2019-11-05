---
title: 在 Microsoft 團隊中使用內容搜尋
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 瞭解 Microsoft 團隊中的內容搜尋，以及如何搜尋來自 Exchange 的頻道交談、檔案上傳與 SharePoint 中的檔案上傳及修改，以及 OneNote 的變更。
appliesto:
- Microsoft Teams
ms.openlocfilehash: faed09a5fafaec559bc4277b75a60d8cc594fa85
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968284"
---
<a name="use-content-search-in-microsoft-teams"></a>在 Microsoft 團隊中使用內容搜尋
=====================================

> [!NOTE]
> 在[私人通道](private-channels.md)中，郵件和檔案的內容搜尋與在標準通道中的運作方式不同。 若要深入瞭解，請參閱[私人頻道的內容搜尋](#content-search-of-private-channels)。

[內容搜尋] 提供一種方式，可查詢 Microsoft 團隊資訊跨越 Exchange、SharePoint Online 和商務用 OneDrive。

若要深入瞭解，請參閱[Office 365 中的內容搜尋](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)。

例如，針對您的製造規格信箱和製造規格 SharePoint 網站使用**內容搜尋**，您可以從 sharepoint Online 的 Exchange、檔案上傳及修改等小組標準頻道交談進行搜尋。以及 OneNote 的變更。

您也可以將查詢準則新增至**內容搜尋**，以縮小傳回的結果範圍。 在上述範例中，您可以尋找已使用 [**新的工廠規格]** 關鍵字的內容。

> [!TIP]
> 新增搜尋條件之後，您可以將報表或資料匯出到您的電腦以進行分析。

## <a name="content-search-of-private-channels"></a>私人頻道的內容搜尋

在私人通道中傳送的訊息記錄會傳送到所有私人通道成員的信箱，而不是群組信箱。 記錄的標題會設定格式，以指出其傳送的是哪一種私人頻道。

因為每個私人通道都有自己的 SharePoint 網站集合與父小組網站分開，所以專用通道中的檔案會獨立于父團隊進行管理。

小組不支援在單一頻道中搜尋內容，所以必須搜尋整個小組。 若要執行私人頻道的內容搜尋，請在整個小組中搜尋、與私人頻道相關聯的網站集合（包括檔案），以及私人頻道成員的信箱（以包含郵件）。

使用下列步驟來識別私人頻道中要包含在內容搜尋中的檔案和訊息。

### <a name="include-private-channel-files-in-a-content-search"></a>在內容搜尋中包含私人通道檔案

在執行這些步驟之前，請先安裝[Sharepoint Online 管理命令介面並聯機至 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

1. 執行下列動作，以取得與團隊中的私人頻道相關聯的所有 SharePoint 網站集合的清單。

    ```
    Get-SPOSite
    ```
2. 執行下列 PowerShell 腳本，以取得與團隊中的私人頻道與父團隊群組識別碼相關聯的所有 SharePoint 網站集合 Url 清單。

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 針對每個團隊或群組識別碼，請執行下列 PowerShell 腳本來識別所有相關的專用通道網站。

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>在內容搜尋中包含私人通道訊息

在執行這些步驟之前，請確定您已安裝[最新版本的團隊 PowerShell 模組](teams-powershell-overview.md)。

1. 執行下列動作，取得小組中的私人頻道清單。

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 執行下列動作以取得私人頻道成員的清單。

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 從小組中的每個私人頻道包含所有成員的信箱，作為內容搜尋查詢的一部分。

## <a name="related-topics"></a>相關主題

- [Office 365 安全 & 合規性中心中的 eDiscovery 案例](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 