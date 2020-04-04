---
title: 對內容進行 eDiscovery 調查
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解當您需要提交以電子形式儲存的法律訴訟資訊時，該怎麼辦。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136683"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft 團隊中進行 eDiscovery 調查內容

大型企業通常會面臨大量要求提交所有以電子方式儲存資訊（ESI）的法律訴訟。

所有團隊1:1 或群組聊天都會在各個使用者的信箱中進行歸檔，而所有標準通道訊息都會在代表小組的群組信箱中進行歸檔。 在標準頻道中上傳的檔案涵蓋在 SharePoint Online 和商務用 OneDrive 的 eDiscovery 功能底下。 電子檔探索[私人通道](private-channels.md)中的訊息和檔案，與在標準通道中的運作方式不同。 若要深入瞭解，請參閱電子檔探索（[私人頻道](#ediscovery-of-private-channels)）。

> [!NOTE]
> 目前，我們不支援在來賓使用者是1:1 或1： N 聊天的唯一參與者的情況下，使用 eDiscovery 訊息。 這些聊天類型也稱為*來賓對訪客*聊天，因為他們不包含家用租使用者。

1. 若要使用 Microsoft 團隊內容進行 eDiscovery 調查，請參閱[此](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)連結中的步驟1。

2. Microsoft 團隊資料會以 IM 或交談的方式顯示在 Excel eDiscovery 匯出輸出中，您可以在 Outlook 中開啟該 PST，以查看匯出後的訊息。

    針對團隊查看 PST 時，請注意，所有交談都會保留在 [交談歷程記錄] 底下的 [小組聊天] 資料夾中。 郵件標題會對應到 [小組] 和 [頻道]。 從 [查看] 下方的影像，您可以看到來自 Bob 的訊息，messaged 製造規範小組的專案7標準頻道。

    ![Outlook 中使用者信箱的小組聊天資料夾螢幕擷取畫面](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. 若要查看使用者信箱中的私人聊天，他們也位於 [交談歷程記錄] 底下的 [小組聊天] 資料夾中。

## <a name="ediscovery-of-private-channels"></a>電子檔探索（私人頻道）

在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。 記錄的標題會有格式設定，指出寄自哪一個私人頻道。

因為每個私人通道都有自己的 SharePoint 網站集合與父小組網站分開，所以專用通道中的檔案會獨立于父團隊進行管理。

小組不支援單一頻道的 eDiscovery，所以必須搜尋整個小組。 若要在私人頻道中執行電子檔探索搜尋，請在整個小組中搜尋、與私人頻道相關聯的網站集合（包括檔案），以及私人頻道成員的信箱（以包含郵件）。

使用下列步驟來識別您在 eDiscovery 搜尋中包含的私人頻道中的檔案和訊息。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在 eDiscovery 搜尋中包含私人通道檔案

在執行這些步驟之前，請先安裝[Sharepoint Online 管理命令介面並聯機至 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

1. 執行下列動作，以取得與團隊中的私人頻道相關聯的所有 SharePoint 網站集合的清單。

    ```PowerShell
    Get-SPOSite
    ```

2. 執行下列 PowerShell 腳本，以取得與團隊中的私人頻道與父團隊群組識別碼相關聯的所有 SharePoint 網站集合 Url 清單。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. 針對每個團隊或群組識別碼，請執行下列 PowerShell 腳本來找出所有相關的專用通道網站，其中 $groupID 是團隊的群組識別碼。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>在 eDiscovery 搜尋中包含私人通道訊息

在執行這些步驟之前，請確定您已安裝[最新版本的團隊 PowerShell 模組](teams-powershell-overview.md)。

1. 執行下列動作，取得小組中的私人頻道清單。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 執行下列動作以取得私人頻道成員的清單。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 從小組中的每個私人頻道包含所有成員的信箱，成為 eDiscovery 搜尋查詢的一部分。

## <a name="related-topics"></a>相關主題

- [團隊 PowerShell 概覽](teams-powershell-overview.md)
