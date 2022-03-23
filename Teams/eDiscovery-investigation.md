---
title: 對內容進行電子檔探索調查
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解執行電子檔探索時該做什麼，例如當您需要提交所有電子檔儲存的資訊進行訴訟時。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 85124047c5bb894eb4eb4177fad0e0cfee53dfc3
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711767"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>對電子郵件中的內容進行電子檔探索Microsoft Teams

大型企業通常會受到高罰訴訟，要求提交所有電子 (ESI) 。 Microsoft Teams可在電子檔探索調查期間搜尋及使用內容。

## <a name="overview"></a>概觀

所有Microsoft Teams 1：1 或群組聊天會記錄到各個使用者的信箱。 所有標準頻道訊息會記錄到代表團隊的群組信箱。 在標準頻道中上傳的檔案會涵蓋在 SharePoint Online 和 商務用 OneDrive。

私人頻道中郵件和檔案的 [eDiscovery](private-channels.md) 運作方式與標準頻道不同。 若要深入瞭解，請參閱 [私人頻道的 eDiscovery](#ediscovery-of-private-and-shared-channels)。

並非所有Teams都是可電子檔探索的。 下表顯示您可以使用 Microsoft 電子檔探索工具搜尋的內容類型：

| 內容類型 | eDiscoverable | 注釋 |
|:--- | :--- |:--- |
|音訊錄製 | 否 | |
|卡片內容|是|請參閱 [搜尋卡片內容](#search-for-card-content) 以瞭解更多資訊。|
|聊天連結 | 是 | |
|聊天訊息 | 是 |這包括標準Teams頻道中的內容、1：1 聊天、1：N 群組聊天，以及與來賓使用者參與者的聊天。  |
|程式碼段 | 否 | |
|編輯的郵件 | 是 | 如果使用者保持保留狀態，也會保留先前版本的已編輯郵件。 |
|圖釋、GIF 和貼圖 | 是 | |
|提要通知 | 否 | |
|內嵌圖像 | 是 | |
|迴圈元件| 是|迴圈元件中的內容會儲存在 .fluid 檔案中，商務用 OneDrive傳送迴圈元件之使用者的帳戶。 這表示當您在迴圈元件中搜尋OneDrive時，您必須將內容包含為數據源。 |
|會議 IM 交談 | 是 | |
|會議中繼資料<sup>1</sup> | 是 |  |
|頻道名稱 | 是 | |
|私人和共用頻道聊天訊息 | 是 | |
|報價 | 是 | 可搜尋引用的內容。 不過，搜尋結果不會指出已引用內容。 |
|對 (反應，例如喜歡、心和其他反應)  | 否 | |
|主題 | 是 | |
|表 | 是 | |
||||

<sup>1</sup> 會議 (和) 中繼資料包括下列專案：

- 會議開始時間和結束時間，以及持續時間
- 每個參與者的會議加入和離開活動
- VOIP 加入/通話
- 匿名加入
- 聯合使用者加入
- 來賓使用者加入

以下是參與者在會議期間聊天交談的範例。

![會議參與者之間的Teams。](media/MeetingIMConversations.png)

[!div class="mx-imgBorder"]

以下是在電子檔探索工具中查看之相同聊天交談的合規性副本範例。

![eDiscovery 搜尋結果中參與者之間的交談。](media/MeetingImConversation2.png)

以下是會議中繼資料的範例。

  > [!div class="mx-imgBorder"]
  > ![合規性副本的會議中繼資料。](media/conversationOption3.png)

有關執行 eDiscovery 調查的資訊，請參閱開始使用[核心電子探索。](/microsoft-365/compliance/get-started-core-ediscovery)

Microsoft Teams電子檔探索匯出輸出中，Excel會顯示為 IM 或交談。 您可以在檔案中開啟 `.pst` Outlook以在匯出郵件後查看這些郵件。

檢視團隊的 .pst 檔案時，所有交談都位於 [交談記錄> 下的 [小組聊天> 資料夾中。 郵件的標題包含團隊名稱和頻道名稱。 例如，下圖顯示來自 Bob 的訊息，該訊息Project製造規格小組的 7 個標準通道。

![使用者信箱中的小組聊天資料夾螢幕擷取畫面Outlook。](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

使用者信箱中的私人聊天會儲存在交談記錄下的小組聊天資料夾中。

## <a name="ediscovery-of-private-and-shared-channels"></a>私人和共用頻道的 eDiscovery

私人和共用頻道中郵件的合規性複本會根據通道類型，送往不同的信箱。 這表示您必須根據使用者是其中一個成員的頻道類型來搜尋不同的信箱位置。

- **私人頻道**。 合規性複本會送到私人頻道成員所有成員的信箱。 這表示當您在私人頻道訊息中搜尋內容時，必須搜尋使用者信箱。

- **共用頻道**。 合規性複本會送到與父團隊相關聯的系統信箱。 由於 Teams 不支援以電子檔探索搜尋共用頻道的單一系統信箱，因此當您在共用頻道中搜尋郵件內容時，您必須選取小組信箱) 的名稱，以搜尋父團隊 (的信箱。

每個私人和共用頻道都有與SharePoint小組網站分開的網站。 這表示私人和共用頻道中的檔案會儲存在自己的網站中，並獨立于父團隊管理。 這表示在搜尋檔案和頻道郵件附件中的內容時，您必須識別並搜尋與頻道相關聯的特定網站。

請使用下列各節來協助識別要納入 eDiscovery 搜尋的私人或共用頻道。

### <a name="identifying-the-members-of-a-private-channel"></a>識別私人頻道的成員

使用本節中的程式來識別私人頻道的成員，以便您可以使用 eDiscovery 工具在成員信箱中搜尋私人頻道訊息中的內容。

執行這些步驟之前，請確定已安裝最新版本的[PowerShell 模組Teams PowerShell 模組](teams-powershell-overview.md)。

1. 執行下列命令以取得包含您想要搜尋之共用頻道的團隊群組識別碼。

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > 在沒有參數 **的情況下執行 Get-Team** Cmdlet，以顯示組織中Teams清單。 該清單包含每個團隊的群組識別碼和 DisplayName。

2. 執行下列命令以取得父團隊中的私人頻道清單。 使用您于步驟 1 中取得之團隊的群組識別碼。

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. 執行下列命令以取得特定私人頻道的私人頻道擁有者和成員清單。

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. 將私人頻道擁有者和成員的信箱納入核心電子檔探索的[eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery)搜尋查詢中，或在識別及收集 Advanced eDiscovery 中監護[者內容](/microsoft-365/compliance/add-custodians-to-case)時。

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>識別私人SharePoint頻道的網站

如先前所說明，在私人和共用頻道中共用的檔案 (附加至頻道訊息的檔案) 儲存在與頻道相關聯的網站集合中。 使用本節中的程式來識別與特定私人或共用頻道相關聯的網站的 URL。 然後，您可以使用 eDiscovery 工具來搜尋網站中的內容。

執行這些步驟之前，請[安裝 SharePoint管理命令殼並聯機至 SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

1. 或者，請執行下列操作，以取得與SharePoint團隊中共用頻道相關聯的所有網站集合清單。

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > 與私人和共用頻道相關聯的網站的 URL 命名慣例為 `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]` 。 例如，位於 Contoso 組織中「工程師小組」父團隊中的名為「合作夥伴共同合作」之共用頻道的 URL 為 `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration` 。

2. 執行下列 PowerShell 命令，以顯示組織中與私人SharePoint頻道相關聯的所有網站的 URL。 腳本的輸出也包含父團隊的組識別碼，您必須執行步驟 3 中的命令。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > SharePoint 2021 `"TEAMCHANNEL#0"` 年 6 月 28 日之前建立的私人頻道網站，請使用自訂範本識別碼的值。 若要顯示在此日期之後建立的私人頻道，請使用值 `"TEAMCHANNEL#1"` 執行前兩個腳本。 共用頻道只會使用 的值 `"TEAMCHANNEL#1"` 。

3. 針對每個父團隊，請執行下列 PowerShell 命令，以識別私人和共用頻道網站 `$groupID` ，其中是父團隊的組識別碼。

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. 將與私人或共用頻道相關聯的網站納入核心電子檔探索的[eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery)搜尋查詢中，或在識別及收集 Advanced eDiscovery 中監護[者Advanced eDiscovery](/microsoft-365/compliance/add-custodians-to-case)。

## <a name="search-for-content-for-guest-users"></a>搜尋來賓使用者的內容

您可以使用 eDiscovery 工具搜尋Teams來賓使用者的相關內容。 Teams與來賓使用者相關聯的聊天內容會保留在雲端儲存位置，而且可以使用 eDiscovery 搜尋。 這包括在 1：1 和 1：N 聊天交談中搜尋內容，其中來賓使用者是貴組織中其他使用者的參與者。 您也可以搜尋來賓使用者為參與者的私人頻道訊息，並搜尋來賓 *：來賓* 聊天交談中只有參與者為來賓使用者的內容。

若要搜尋來賓使用者的內容：

1. 連線 PowerShell Azure AD PowerShell。 有關指示，請參閱使用 PowerShell 連線 PowerShell Azure Active Directory>一連線Microsoft 365[>一節](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。 請務必完成上一個主題中的步驟 1 和步驟 2。

2. 成功連接到 PowerShell Azure AD之後，請執行下列命令，為貴組織的所有來賓使用者 (UPN) 使用者主體名稱。 當您在步驟 4 建立搜尋時，您必須使用來賓使用者的 UPN。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 您可以重新導向命令的輸出至文字檔，而不是在電腦畫面上顯示使用者主體名稱清單。 您可以附加至上一個 `> filename.txt` 命令，以執行此操作。 具有使用者主體名稱的文字檔會儲存到目前的資料夾。

3. 在不同的安全Windows PowerShell，請連接到安全性與合規性& PowerShell。 有關指示，[請參閱連線安全&中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。 您可以使用多重要素驗證進行連接，也可以不使用多重要素驗證。

4. 建立內容搜尋，以執行下列命令 (搜尋聊天訊息) 電子郵件訊息等所有內容。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   例如，若要搜尋與來賓使用者 Sara Davis 相關聯的內容，您可以執行下列命令。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    有關使用 PowerShell 建立內容搜尋的資訊，請參閱 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)。

5. 執行下列命令以開始在步驟 4 中建立的內容搜尋：

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 前往 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然後按一下 [**顯示所有**  >  **Content 搜尋**。

7. 在搜尋清單中，選取您于步驟 4 中建立搜尋以顯示飛出頁面。

8. 在飛出頁面上，您可以執行下列操作：

   - 按一下 **[查看結果** 以查看搜尋結果並預覽內容。

   - 按一下 [ **查詢欄位** 的旁邊 **編輯** 以編輯，然後重新執行搜尋。 例如，您可以新增搜尋查詢來縮小結果範圍。

   - 按一下 **[匯出結果** 以匯出並下載搜尋結果。

## <a name="search-for-card-content"></a>搜尋卡片內容

由應用程式在 Teams、1：1 聊天和 1xN 聊天中產生的卡片內容會儲存在信箱中，而且可以搜尋。 卡片 *是* 包含簡短內容的 UI 容器。 卡片可以有多個屬性和附件，而且可以包含可觸發卡片動作的按鈕。 詳細資訊，請參閱 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

與其他Teams內容一樣，卡片內容的儲存位置會依據卡片的使用位置。 在頻道中使用的卡片Teams內容會儲存在Teams信箱中。 1：1 和 1xN 聊天的卡片內容會儲存在聊天參與者的信箱中。

若要搜尋卡片內容，您可以使用 或 `kind:microsoftteams` 搜尋 `itemclass:IPM.SkypeTeams.Message` 條件。 在審查搜尋結果時，Teams頻道中的 Bot 產生的卡片內容具有寄件者 **/作者** 電子郵件屬性， `<appname>@teams.microsoft.com` `appname` 其中產生卡片內容的應用程式名稱在哪裡。 如果卡片內容是由使用者產生，寄件者 **/作者的值會** 識別使用者。

在內容搜尋結果中檢視卡片內容時，內容會顯示為郵件的附件。 附件會命名為 `appname.html` ，其中 `appname` 就是產生卡片內容的應用程式名稱。 下列螢幕擷取畫面顯示名為 Asana (應用程式卡片) 內容Teams顯示在搜尋結果中。

### <a name="card-content-in-teams"></a>卡片內容Teams

![頻道訊息Teams卡片內容。](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>搜尋結果中的卡片內容
  
![內容搜尋結果中的卡片內容相同。](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 若要在搜尋結果中顯示來自卡片內容的影像 (例如上一個螢幕擷取畫面) 中的核取方塊，您必須在您用於查看搜尋結果的同一個瀏覽器會話的不同索引點，于 Teams (https://teams.microsoft.com) 中登錄。 否則會顯示影像預留位置。

## <a name="related-topics"></a>相關主題

- [Microsoft 365電子探索解決方案](/microsoft-365/compliance/ediscovery)
- [開始使用核心電子探索](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams工作流程Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
