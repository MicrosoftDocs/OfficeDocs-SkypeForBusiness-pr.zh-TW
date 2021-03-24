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
ms.openlocfilehash: 3990b96981a65bb4d706cc3141abee10102c0839
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094053"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft Teams 中對內容進行電子檔探索調查

大型企業通常會遭受高罰訴訟，要求提交所有電子 (ESI) 。 您可以在電子檔探索調查期間搜尋及使用 Microsoft Teams 內容。

## <a name="overview"></a>概觀

所有 Microsoft Teams 1：1 或群組聊天會記錄到各個使用者的信箱。 所有標準頻道訊息會記錄到代表團隊的群組信箱。 在標準頻道上傳的檔案會涵蓋 SharePoint Online 和商務用 OneDrive 的 eDiscovery 功能。

私人頻道中郵件和檔案的 [eDiscovery](private-channels.md) 運作方式與標準頻道不同。 若要深入瞭解，請參閱 [私人頻道的 eDiscovery](#ediscovery-of-private-channels)。

並非所有 Teams 內容都是可電子檔探索的。 下表顯示您可以使用 Microsoft 電子檔探索工具搜尋的內容類型：

| 內容類型 | eDiscoverable | 注釋 |
|:--- | :--- |:--- |
|音訊錄製 | 否 | |
|卡片內容|是|請參閱 [搜尋卡片內容](#search-for-card-content) 以瞭解更多資訊。|
|聊天連結 | 是 | |
|聊天訊息 | 是 |這包括 Teams 頻道中的內容、1：1 聊天、1：N 群組聊天，以及與來賓使用者參與者的聊天。  |
|程式碼段 | 否 | |
|編輯的郵件 | 是 | 如果使用者保持保留狀態，也會保留先前版本的已編輯郵件。 |
|圖釋、GIF 和貼圖 | 是 | |
|內嵌圖像 | 是 | |
|會議 IM 交談 | 是 | |
|會議中繼資料<sup>1</sup> | 是 |  |
|頻道名稱 | 否 | |
|私人頻道訊息 | 是 | |
|報價 | 是 | 可搜尋引用的內容。 不過，搜尋結果不會指出已引用內容。 |
|對 (反應，例如喜歡、心和其他反應)  | 否 | |
|主題 | 是 | |
|表 | 是 | |
|||

<sup>1</sup> 會議 (和) 中繼資料包括下列專案：

- 會議開始時間和結束時間，以及持續時間
- 每個參與者的會議加入和離開活動
- VOIP 加入/通話
- 匿名加入
- 聯合使用者加入
- 來賓使用者加入

  影像顯示會議中繼資料的範例。

  > [!div class="mx-imgBorder"]
  > ![影像是 CVR 記錄會議中繼資料的影像。](media/conversationOption3.png)

以下是參與者在會議期間進行 IM 交談的範例。

![Teams 中參與者之間的交談。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![eDiscovery 搜尋結果中參與者之間的交談。](media/MeetingImConversation2.png)

有關執行 eDiscovery 調查的資訊，請參閱開始使用 [Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)。

Microsoft Teams 資料在 Excel 電子檔探索匯出輸出中會顯示為 IM 或交談。 您可以在 Outlook `.pst` 中開啟檔案，以在匯出郵件後查看這些郵件。

檢視小組的 .pst 檔案時，所有交談會保留在 [交談記錄> 下的 [小組聊天> 資料夾中。 郵件的標題包含團隊名稱和頻道名稱。 例如，下圖顯示一則來自 Bob 的訊息，該訊息是給製造規格小組的 Project 7 標準通道發郵件。

![Outlook 中使用者信箱中的小組聊天資料夾螢幕擷取畫面](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

使用者信箱中的私人聊天會儲存在交談記錄下的小組聊天資料夾中。

## <a name="ediscovery-of-private-channels"></a>私人頻道的 eDiscovery

在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。 記錄的標題會有格式設定，指出寄自哪一個私人頻道。

由於每個私人頻道都有自己的 SharePoint 網站，與父小組網站分開，因此私人頻道中的檔案會不受父團隊管理。

Teams 不支援小組內單一頻道的 eDiscovery 搜尋，因此必須搜尋整個團隊。 若要在私人頻道中執行 eDiscovery 內容搜尋，請搜尋整個小組、與私人頻道關聯的網站集合 (以包含檔案) ，以及私人頻道成員的信箱 (以包含郵件) 。

請使用下列步驟來識別私人頻道中的檔案和訊息，以納入您的電子檔探索搜尋。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在電子檔探索搜尋中納入私人頻道檔案

執行這些步驟之前，請安裝 [SharePoint Online 管理命令殼並聯機至 SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

1. 執行下列操作，以取得與團隊中私人頻道相關聯的所有 SharePoint 網站集合清單。

    ```PowerShell
    Get-SPOSite
    ```

2. 執行下列 PowerShell 腳本，以取得與小組中私人頻道相關聯的所有 SharePoint 網站集合 URL 清單，以及父團隊群組識別碼。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. 針對每個小組或群組識別碼，執行下列 PowerShell 腳本，以識別所有相關的私人頻道網站，$groupID是團隊的組識別碼。

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>在 eDiscovery 搜尋中納入私人頻道訊息

執行這些步驟之前，請確定您已安裝 [最新版本的 Teams PowerShell 模組](teams-powershell-overview.md) 。

1. 執行下列命令以取得團隊中的私人頻道清單。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 執行下列命令以取得私人頻道成員的清單。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 在 [eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery)搜尋查詢中，包含團隊中每個私人頻道中所有成員的信箱。

## <a name="search-for-content-for-guest-users"></a>搜尋來賓使用者的內容

您可以使用 eDiscovery 工具來搜尋與貴組織中來賓使用者相關的 Teams 內容。 與來賓使用者相關聯的 Teams 聊天內容會保留在雲端儲存位置，而且可以使用 eDiscovery 搜尋。 這包括在 1：1 和 1：N 聊天交談中搜尋內容，其中來賓使用者是貴組織中其他使用者的參與者。 您也可以搜尋來賓使用者為參與者的私人頻道訊息，並搜尋來賓 *：來賓* 聊天交談中只有參與者為來賓使用者的內容。

若要搜尋來賓使用者的內容：

1. 連接到 Azure AD PowerShell。 有關指示，請參閱使用 PowerShell 連接到 [Microsoft 365](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)中的「使用 Azure Active Directory PowerShell 連接」一節。 請務必完成上一個主題中的步驟 1 和步驟 2。

2. 成功連接到 Azure AD PowerShell 之後，請執行下列命令，為貴組織的所有來賓使用者 (UPN) 使用者主體名稱。 當您在步驟 4 建立搜尋時，您必須使用來賓使用者的 UPN。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 您可以重新導向命令的輸出至文字檔，而不是在電腦畫面上顯示使用者主體名稱清單。 您可以附加至上一個命令 `> filename.txt` ，以執行此操作。 具有使用者主體名稱的文字檔會儲存到目前的資料夾。

3. 在不同的 Windows PowerShell 視窗中，連接到安全性與合規性& PowerShell。 有關指示，請參閱連接至 [安全性與合規性&中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。 您可以使用多重要素驗證進行連接，也可以不使用多重要素驗證。

4. 建立內容搜尋，以執行下列命令 (搜尋所有內容，例如聊天訊息) 電子郵件訊息。其中指定的來賓使用者是參與者。

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

6. 前往 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然後按一下 [**顯示所有**  >  **內容搜尋**> 。

7. 在搜尋清單中，選取您于步驟 4 中建立搜尋以顯示飛出頁面。

8. 在飛出頁面上，您可以執行下列操作：

   - 按一下 **[查看結果** 以查看搜尋結果並預覽內容。

   - 按一下 [ **查詢欄位** 的旁邊 **編輯** 以編輯，然後重新執行搜尋。 例如，您可以新增搜尋查詢來縮小結果範圍。

   - 按一下 **[匯出結果** 以匯出並下載搜尋結果。

## <a name="search-for-card-content"></a>搜尋卡片內容

Teams 頻道、1：1 聊天和 1xN 聊天中應用程式產生的卡片內容會儲存在信箱中，而且可以搜尋。 卡片 *是* 包含簡短內容的 UI 容器。 卡片可以有多個屬性和附件，而且可以包含可觸發卡片動作的按鈕。 詳細資訊，請參閱 [卡片](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

與其他 Teams 內容一樣，卡片內容的儲存位置會依據卡片的使用位置。 Teams 頻道中使用的卡片內容會儲存在 Teams 群組信箱中。 1：1 和 1xN 聊天的卡片內容會儲存在聊天參與者的信箱中。

若要搜尋卡片內容，您可以使用 或 `kind:microsoftteams` `itemclass:IPM.SkypeTeams.Message` 搜尋條件。 在審查搜尋結果時，Teams 頻道中 Bot 產生的卡片內容具有寄件者 **/作者** 電子郵件屬性，其中產生卡片內容的應用程式 `<appname>@teams.microsoft.com` `appname` 名稱為 。 如果卡片內容是由使用者產生，寄件者 **/作者的值會** 識別使用者。

在內容搜尋結果中檢視卡片內容時，內容會顯示為郵件的附件。 附件會命名為 `appname.html` ，其中就是產生卡片 `appname` 內容的應用程式名稱。 下列螢幕擷取畫面顯示名為 Asana (App 的卡片內容) 在 Teams 中顯示，以及搜尋結果。

**Teams 中的卡片內容**

![Teams 頻道訊息中的卡片內容](media/CardContentTeams.png)

**搜尋結果中的卡片內容**
  
![內容搜尋結果中的卡片內容相同](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 若要在搜尋結果中顯示來自卡片內容的影像 (例如上一個螢幕擷取畫面) 中的核取方塊，您必須在您用於查看搜尋結果的同一個瀏覽器會話的不同索引點，于另一個索引標上登錄 Teams (。 https://teams.microsoft.com) 否則會顯示影像預留位置。

## <a name="advanced-ediscovery"></a>進一版電子資料探索

您也可以使用進一步電子檔探索工作流程來搜尋及保留部分 [Microsoft Teams 內容](/microsoft-365/compliance/overview-ediscovery-20)。 雖然 eDiscovery 提供一系列的搜尋、保留和匯出功能，但進一步電子檔探索提供合規性系統管理員更多工具來識別資料來源及分析其內容。

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Teams 內容的進一步電子檔探索監護工作流程

監護者可能是各種團隊的成員。 您可以捕獲與這些監護者相關的 Teams 內容。 有關監護工作流程的指示，請參閱在進一步 [電子資料](/microsoft-365/compliance/add-custodians-to-case)探索案例新增監護者。

新增保管人之後，按一下 **[下** 一步> 按鈕，然後按一下 [ **新增>** 按鈕。 隨後會顯示一個視窗，提示您選取其他位置，這會顯示保管人的所有成員資格，以及其資料對應的 SharePoint 網站位置。 您可以從所有這些資料來源和團隊中，選擇您想要用於 eDiscovery 的內容，然後將該使用者和您識別的所有資料來源保留。

您可以選取是否要包含他們的 Exchange 內容、其 OneDrive 內容或兩者。 Exchange 內容包含使用者信箱中所有的應用程式內容，例如其電子郵件、儲存在其信箱中的 Teams 內容等等。 OneDrive 內容不僅包括使用者的內容，也包含儲存在 OneDrive 中的所有 Teams 內容，例如 1：1 聊天、1：N 聊天，以及聊天中共用的檔案。

您也可以選擇將監護者是其中一員的任何團隊進行關聯，以便包含監護者可存取的頻道聊天訊息和檔案。 此外，任何其他團隊都可以與監護者相關聯。

> [!NOTE]
> 私人頻道中郵件和檔案的 [eDiscovery](private-channels.md) 運作方式與標準頻道不同。 若要深入瞭解，請參閱 [私人頻道的 eDiscovery](#ediscovery-of-private-channels)。

### <a name="placing-a-data-source-on-hold"></a>保留資料來源

如果沒有任何特定使用者要指定為監管人，您可以將整個資料來源保留。 有關保留詳細資訊，請參閱在進一版 [電子資料](/microsoft-365/compliance/managing-holds)探索中管理保留。

為 Teams 內容建立保留時，您可以選擇要納入保留的所有位置。 即使使用者刪除或變更內容，保留也會保留該內容的所有先前版本複本。

您也可以使用選擇性查詢，根據關鍵字、日期範圍、作者和許多其他準則來設定保留的條件。 如果您未指定關鍵字，則來自該資料來源的所有專案都會受到保留。

### <a name="advanced-ediscovery-searches"></a>進一版電子探索搜尋

您也可以搜尋 Teams 內容。 有關搜尋的資訊，請參閱在 Advanced [eDiscovery](/microsoft-365/compliance/collecting-data-for-ediscovery)中收集案例的資料。 即使有一封郵件符合搜尋查詢，搜尋也會返回整個交談。

建立搜尋查詢時，您可以選擇監護者，以便搜尋所有已選取的來源。 您也可以搜尋非監護來源，例如未對應到使用者的 Teams 網站。 也可以選取查詢來縮小 Teams 內容中的搜尋範圍。

建立並選取搜尋之後，視窗會顯示其他詳細資料，以及您可以在選取的搜尋上執行的動作。 如果您按一下 [統計資料> 按鈕，就可以查看搜尋的統計資料，包括根據位置類型細分、內容的原始來源，以及內容是否位於群組信箱、個別使用者信箱或 SharePoint 網站。 因此，您可以查看哪些來源對搜尋結果有説明。 您也可以使用 **查詢** 視圖，以便查看哪些個別關鍵字對結果有影響。

完成搜尋之後，您可以按一下 [新增結果 **以審查** 設定按鈕並新增到評論集。 有關評論集詳細資訊，請參閱本文稍後在進一步 [eDiscovery](/microsoft-365/compliance/managing-review-sets) 和 [Review 集工作流程](#review-sets-workflow) 中管理審查集。

#### <a name="normal-review-sets-and-conversation-review-sets"></a>一般評論集和交談評論集

新增搜尋至評論集時，您可以選擇一般評論集或交談評論集。

一般評論集與匯出類似;它提供 Teams `.msg` 內容的個別檔案，並且以基本視圖呈現內容。 當您打算稍後使用其他軟體工具來重新處理檔案時，通常會使用一般評論集。

交談評論集提供交談的更直覺、討論執行緒的視圖;它會以適當的順序一起顯示相關郵件。

> [!div class="mx-imgBorder"]
> ![交談評論集的螢幕擷取畫面](media/conversationOptions2.png)

兩種類型的校閱集都提供編校等功能。 有關評論集詳細資訊，請參閱在進一版 [eDiscovery 中審查交談](/microsoft-365/compliance/conversation-review-sets)。

#### <a name="collection-options"></a>集合選項

新增到評論集時，視窗的收藏選項區段下有幾個選項可用做為核取方塊，包括交談 **取回選項** 和 **Teams 交談**。 如果您啟用這些選項，屬於您審查集的任何個別 Teams 郵件也會顯示周圍其他訊息，以便查看內容。 例如，如果您的查詢是特定的，因此只會返回一封郵件，啟用這些選項也會在符合查詢的郵件前和之後，返回數封郵件。

許多邏輯準則會用來判斷其他郵件是否提供符合您查詢的郵件內容。 例如，針對 Teams 內容，啟用這些選項會因為郵件的執行緒方式，來取回父郵件和所有子郵件。

也會檢查郵件時間戳記。 如果郵件符合您的查詢，則 4 小時內在其前或 4 小時內追蹤該郵件的相鄰郵件會視為交談的一部分，也會包含在結果中。

如果您必須確定哪些上下文相關郵件會與搜尋查詢的符合專案一起返回，則不需要使用這些選項。 您可以收集所有內容，也可以擴大搜尋的日期範圍，讓查詢的結果會退回更多郵件。

### <a name="review-sets-workflow"></a>審查集工作流程

您可以按一下檢查集，來查看現有的評論集或建立新 **評論** 集。有關評論集詳細資訊，請參閱在進一版電子資料探索中管理 [評論集](/microsoft-365/compliance/managing-review-sets)。

除了檔之外，您還可以在評論集新增電子郵件、Teams 訊息、Yammer 訊息及其他內容。 您也可以在評論集內執行許多可在其他上下文執行相同的作業，例如搜尋內容和建立自訂查詢。 這些作業僅適用于已新加入審查集的專案。

管理 **審查集** 按鈕提供其他選項，例如分析、摘要報告、已新增的載入集數等等。

若要存取資料的視覺效果和圖表，請按一下右上角的 [個別 **結果** 搜尋 \> 設定檔視圖。 您可以按一下這些圖表中的圓形圖，以互動式方式選取您想要查詢的內容類型。 例如，您可以選擇只查詢 Teams 內容。 您也可以儲存這些查詢，就像儲存手動撰寫的查詢一樣。

#### <a name="summary-view-text-view-and-annotate-view"></a>摘要視圖、文字視圖和批註視圖

如果您按一下評論集的 Teams 交談，它會顯示 [摘要視圖」，其中將整個 Teams 交談顯示為您可以個別互動的訊息清單。 按一下郵件右邊的向下箭箭，以顯示操作功能表，可讓您查看郵件詳細資料或下載個別 `.msg` 檔案。 按一下郵件詳細資料會顯示中繼資料摘要或郵件的完整中繼資料。

若要下載 PDF，請按一下摘要視圖右上角的下載按鈕。

按一下 [ **文字視圖>** 選項卡以顯示 Teams 交談摘要文字的純文字視圖。 此純文字內容適合匯出，而且您可以使用其他軟體工具輕鬆處理。

按一下 [ **批註視圖>** 選項卡以存取注釋功能。 此選項卡會以類似 Teams 交談的格式顯示內容，但也提供其他編輯選項。 您可以使用鉛筆工具做筆記、在郵件上繪圖，或執行細細微性的刮擦，以用於編校用途。 您也可以使用 **區域密** 文工具來繪製一個矩形，將區域黑色化，並標記為「已重新編輯」。

以下是使用者之間對話對話的已修訂檔案範例。

> [!div class="mx-imgBorder"]
> ![已修訂檔案的螢幕擷取畫面](media/RedactedFileExample.png)

At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel. 您可以在此面板中將標記適用于 Teams 交談內的所有郵件。 您可以將交談標示為回應性或非回應式、有許可權或不具有許可權、是否包含「有趣專案」、是否要包含在匯出中，以及是否需要進一步審查。 您也可以管理並應用其他可自訂的標記。

#### <a name="action-menu"></a>動作功能表

在評論集視窗中，您可以按一下動作匯出來 **匯出** \> **內容**。 匯出時有許多可用的選項。

若要匯出包含所有 Teams 郵件之所有中繼資料的檔案，請按一下以選取 [ **載入檔案>** 核取方塊。 若要在檔案中納入任何您已對內容所申請的標記，請按一下以選取 [ **標記>** 核取方塊。

使用 **原生檔案** 選項以原生格式匯出檔案。 您可以選擇將交談匯出為個別檔案中的一個檔案或所有個別聊天訊息。

文字檔 **選項** 可讓您儲存純文字版本的內容。 有關如何在評論集取得 Teams 交談純文字視圖之詳細資訊，請參閱上方的摘要視圖、文字視圖和 [批註](#summary-view-text-view-and-annotate-view) 視圖。

如果您如上節的摘要視圖、文字視圖和批註視圖區 [](#summary-view-text-view-and-annotate-view)段所述，對內容應用任何編目，您可以選取以轉換 **PDF** 取代已編輯的原生檔選項，以 PDF 中的轉換複本取代原生檔案。

您可以選擇匯出至 Microsoft 提供的 Azure Blob 儲存容器，或提供您自己的 Azure Blob 儲存容器。

當您準備好開始匯出程式時，請按一下 [ **匯出>** 按鈕。 請參閱 [下載匯出工作](/microsoft-365/compliance/download-export-jobs) ，以取得如何存取 Azure Blob 儲存容器，以及匯出完成後下載匯出內容之詳細資訊。

> [!NOTE]
> 匯出可能需要一段長的時間。 若要追蹤匯出程式的狀態，請離開 [檢查集>**選項卡，** 然後按一下 [**匯出> Tab。**

## <a name="related-topics"></a>相關主題

- [Microsoft 365 中的電子探索](/microsoft-365/compliance/ediscovery)
- [Teams PowerShell 概觀](teams-powershell-overview.md)