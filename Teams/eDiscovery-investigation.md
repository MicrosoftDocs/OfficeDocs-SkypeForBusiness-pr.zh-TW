---
title: 對內容進行 eDiscovery 調查
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
description: 瞭解當您需要執行 eDiscovery 時要採取的動作，例如當您需要提交所有以電子形式儲存的法律訴訟資訊時。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 25729dea68d2d8ea75fae894387316dfbcd1975a
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49661908"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft 團隊中進行 eDiscovery 調查內容

大型企業通常會面臨大量的法律訴訟，要求提交所有以電子方式儲存的資訊 (ESI) 。 Microsoft 團隊內容可以在 eDiscovery 調查期間進行搜尋和使用。

## <a name="overview"></a>概觀

所有 Microsoft 團隊1:1 或群組聊天都會在各個使用者的信箱中進行日記。 所有標準通道訊息都會在代表小組的群組信箱中進行歸檔。 在標準頻道中上傳的檔案涵蓋在 SharePoint Online 和商務用 OneDrive 的 eDiscovery 功能底下。

電子檔探索 [私人通道](private-channels.md) 中的訊息和檔案，與在標準通道中的運作方式不同。 若要深入瞭解，請參閱電子檔探索（ [私人頻道](#ediscovery-of-private-channels)）。

並非所有團隊內容都是 eDiscoverable。 下表顯示可透過 eDiscovery 找到的內容類型。

| 內容類型 | eDiscoverable | 注釋 |
|:--- | --- |:--- |
| 小組聊天訊息 | 是 |  |
| 私人通道訊息 | 是 | |
| 頻道名稱 | 否 | |
| 會議 IM 交談 | 是 | |
| 會議中繼資料<sup>1</sup> | 是 |  |
| 已編輯的郵件 | 是 | 如果使用者已保留，則會保留先前版本的已編輯郵件。 |
| Emoji、Gif、不乾膠標籤 | 是 | |
| 程式碼片段 | 否 | |
| 聊天連結 | 是 | |
|  (贊、紅心大戰等) 的反應 | 否 | |
| 內嵌圖像 | 是 | |
| 該表 | 是 | |
| 主題 | 是 | |
| 引述 | 是 | 已報價的內容可供搜尋。 不過，搜尋結果不會指出內容已加上引號。 |
| 音訊錄製 | 否 | |

<sup>1</sup> 會議 (並呼叫) 中繼資料包括下列各項：

- 會議開始和結束時間，以及持續時間
- 會議加入與離開每位參與者的活動
- VOIP 連接/通話
- 匿名加入
- 聯盟使用者加入
- 來賓使用者加入

影像會顯示中繼資料的範例。

> [!div class="mx-imgBorder"]
> ![Image 是 CVR 記錄會議中繼資料。](media/conversationOption3.png)

以下是會議期間參與者之間的 IM 交談範例。

![團隊參與者之間的交談。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![EDiscovery 搜尋結果中的參與者之間的交談。](media/MeetingImConversation2.png)

如需有關進行 eDiscovery 調查的詳細資訊，請參閱 [核心 EDiscovery 快速](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)入門。

Microsoft 團隊資料將在 Excel eDiscovery 匯出輸出中顯示為 IM 或交談。 您可以 `.pst` 在 Outlook 中開啟檔案，以在匯出後查看這些郵件。

針對小組查看 .pst 檔案時，所有交談都會保留在 [交談歷程記錄] 底下的 [小組聊天] 資料夾中。 郵件標題包含團隊名稱和頻道名稱。 例如，下圖顯示的是來自王俊元的訊息，其中 messaged 製造規範小組的專案7標準頻道。

![Outlook 中使用者信箱的小組聊天資料夾螢幕擷取畫面](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

使用者信箱中的私人聊天儲存在 [交談歷程記錄] 底下的 [小組聊天] 資料夾中。

## <a name="ediscovery-of-private-channels"></a>電子檔探索（私人頻道）

在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。 記錄的標題會有格式設定，指出寄自哪一個私人頻道。

因為每個私人通道都有自己的 SharePoint 網站，與父小組網站分開，所以專用通道中的檔案會獨立于父團隊進行管理。

小組不支援小組內單一頻道的 eDiscovery 搜尋，所以必須搜尋整個小組。 若要在私人頻道中執行電子檔探索搜尋，請在整個小組中搜尋與私人頻道 (相關聯的網站集合，以包含) 的檔案，以及私人頻道成員的信箱 (，以包含) 的郵件。

使用下列步驟來識別您在 eDiscovery 搜尋中包含的私人頻道中的檔案和訊息。

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>在 eDiscovery 搜尋中包含私人通道檔案

在執行這些步驟之前，請先安裝 [Sharepoint Online 管理命令介面並聯機至 SharePoint online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

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

在執行這些步驟之前，請確定您已安裝 [最新版本的團隊 PowerShell 模組](teams-powershell-overview.md) 。

1. 執行下列命令，以取得小組中的私人頻道清單。

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 執行下列命令以取得私人頻道成員的清單。

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. 從小組中的每個私人頻道包含所有成員的信箱，成為 [eDiscovery 搜尋查詢](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)的一部分。

## <a name="search-for-content-for-guest-users"></a>搜尋來賓使用者的內容

您可以使用 eDiscovery 工具來搜尋與您組織中的來賓使用者相關的小組內容。 團隊聊天與來賓使用者相關聯的內容會保留在雲端式儲存位置，而且可以使用 eDiscovery 搜尋。 這包括搜尋1:1 和1： N 聊天交談中的內容，來賓使用者是您組織中其他使用者的參與者。 您也可以搜尋來賓使用者是參與者的私人通道訊息，並在來賓中搜尋內容 *：* 只有來賓聊天的參與者是來賓使用者。

若要搜尋來賓使用者的內容：

1. [連線至 Azure AD PowerShell]。 如需相關指示，請參閱 [使用 PowerShell 連線至 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)中的 [與 Azure Active Directory PowerShell 連線] 區段。 請務必完成上一個主題中的步驟1和步驟2。

2. 成功連線至 Azure AD PowerShell 之後，請執行下列命令，以顯示貴組織中所有來賓使用者的使用者主要名稱 (UPN) 。 當您在步驟4中建立搜尋時，您必須使用來賓使用者的 UPN。

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 您可以將命令的輸出重新導向到文字檔，而不是在電腦螢幕上顯示使用者主要名稱清單。 您可以透過附加 `> filename.txt` 至前一個命令來執行此動作。 含有使用者主要名稱的文字檔會儲存至目前的資料夾。

3. 在不同的 Windows PowerShell 視窗中，連線至安全性 & 合規性中心 PowerShell]。 如需相關指示，請參閱連線 [到安全性 & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。 您可以使用或不使用多重要素驗證來連接。

4. 您可以執行下列命令，來建立搜尋內容搜尋，以搜尋所有內容 (例如交談訊息和電子郵件訊息) 。

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   例如，若要搜尋與來賓使用者 Sara Davis 相關聯的內容，您可以執行下列命令。

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    如需使用 PowerShell 建立內容搜尋的詳細資訊，請參閱 [新 ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)。

5. 執行下列命令以啟動您在步驟4中建立的內容搜尋：

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [**顯示所有**  >  **內容搜尋**]。

7. 在搜尋清單中，選取您在步驟4中建立的搜尋，以顯示飛出頁面。

8. 在飛出頁面上，您可以執行下列動作：

   - 按一下 [ **查看結果** ]，查看搜尋結果並預覽內容。

   - 在 **查詢** 欄位旁邊，按一下 [ **編輯** ] 以編輯，然後重新執行搜尋。 例如，您可以新增搜尋查詢來縮小結果範圍。

   - 按一下 [ **匯出結果** ]，匯出並下載搜尋結果。

## <a name="advanced-ediscovery"></a>高級 eDiscovery

您也可以使用 [ [高級 eDiscovery 工作流程](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)] 來搜尋及保留部分 Microsoft 團隊內容。 雖然 eDiscovery 提供一系列的搜尋、保留和匯出功能，但高級 eDiscovery 則提供合規性管理員更多工具來識別資料來源並分析其內容。

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>小組內容的高級 eDiscovery 保管人工作流程

保管人可能是各種團隊的成員。 您可以捕獲與這些保管人相關的小組內容。 如需保管人工作流程的指示，請參閱 [將保管人新增至高級 eDiscovery 案例](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。

在新增保管人之後，按一下 [ **下一步]** 按鈕，然後按一下 [ **新增** ] 按鈕。 接著會顯示一個視窗，提示您選取其他位置，這會顯示所有保管人的成員資格以及其資料對應的 SharePoint 網站位置。 從所有這些資料來源和小組中，您可以選擇您想要用於 eDiscovery 的內容，然後將該使用者及您已識別的所有資料來源保留。

您可以選取是否要包括其 Exchange 內容、其 OneDrive 內容，或同時包含兩者。 Exchange 內容包括使用者信箱中的所有應用程式內容，例如他們的電子郵件、儲存在其信箱中的小組內容等。 OneDrive 內容不僅包括使用者的內容，還包含儲存在 OneDrive 中的所有小組內容，例如1:1 聊天、1： N 聊天，以及在聊天中共用的檔案。

您也可以選擇將保管人中的任何小組相關聯，讓保管人擁有存取權的通道交談訊息和檔案都包含在其中。 此外，任何其他團隊都可以與保管人建立關聯。

> [!NOTE]
> 電子檔探索 [私人通道](private-channels.md) 中的訊息和檔案，與在標準通道中的運作方式不同。 若要深入瞭解，請參閱電子檔探索（ [私人頻道](#ediscovery-of-private-channels)）。

### <a name="placing-a-data-source-on-hold"></a>保留資料來源

如果沒有指派給保管人的特定使用者，您可以保留整個資料來源。 如需保留的詳細資訊，請參閱 [在高級 eDiscovery 中管理保留](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。

建立小組內容的保留時間時，您可以選擇要在保留中包含的所有位置。 即使使用者正在刪除或變更內容，保留也會維持該內容所有先前版本的複本。

您也可以使用選擇性查詢，根據關鍵字、日期範圍、作者及許多其他準則來設定保留條件。 如果您沒有指定關鍵字，則來自該資料來源的所有內容都會受到保留。

### <a name="advanced-ediscovery-searches"></a>[高級 eDiscovery 搜尋]

您也可以搜尋小組內容。 如需搜尋的詳細資訊，請參閱 [在 [高級 eDiscovery] 中收集案例的資料](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。 如果即使一封郵件符合搜尋查詢，搜尋將會傳回整個交談。

建立搜尋查詢時，您可以選擇 [保管人]，讓您已選取的所有來源都經過搜尋。 您也可以搜尋非 custodial 來源，例如未對應至使用者的小組網站。 您也可以在小組內容中縮小搜尋範圍，提供選用的查詢。

在您建立並選取搜尋後，會顯示一個視窗，其中包含您可以在選取的搜尋上執行的其他詳細資料和動作。 如果您按一下 [ **統計資料]** 按鈕，您可以查看有關搜尋的統計資料，包括根據位置類型、內容的原始來源，以及內容是否位於群組信箱、個別使用者信箱或 SharePoint 網站中。 因此，您可以在搜尋結果中看到哪些來源的明細。 您也可以使用 [ **查詢** ] 視圖，查看哪些個別關鍵字對您的結果有影響。

完成搜尋之後，您可以按一下 [ **新增結果至審閱設定** ] 按鈕，然後將其新增至審閱集。 如需有關審閱集的詳細資訊，請參閱本文稍後的管理高級 eDiscovery 和[審閱集合工作流程](#review-sets-workflow)[中的審閱集合](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。

#### <a name="normal-review-sets-and-conversation-review-sets"></a>標準的審閱集和交談審查集合

在將搜尋新增至審閱集合時，您可以從一般的審閱集或交談審查集合中進行選擇。

標準的審閱集與匯出類似;它提供小組內容的個別檔案 `.msg` ，並在 [基本視圖] 中呈現內容。 您通常會在規劃使用其他軟體工具以稍後重新處理檔案時，使用一般的審閱集。

交談審查集合提供更直觀、更具執行緒的交談視圖;它會以正確的順序來顯示相關的郵件。

> [!div class="mx-imgBorder"]
> ![交談審查設定的螢幕擷取畫面](media/conversationOptions2.png)

在兩種類型的審閱集中都提供密文等功能。 如需有關審閱集的詳細資訊，請參閱 [在高級 eDiscovery 中查看交談](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。

#### <a name="collection-options"></a>收集選項

新增至審閱集合時，視窗的 [ **收集選項** ] 區段下有幾個選項可供使用，包括 **交談檢索選項** 和 **團隊交談**。 如果您啟用這些選項，任何屬於您的審閱集中的個別團隊訊息，也會顯示在其周圍有其他訊息，以供內容使用。 例如，如果您的查詢是特定的，且只傳回一封郵件，則啟用這些選項也會傳回數個郵件，並追蹤符合您查詢的訊息。

許多邏輯準則是用來判斷其他訊息是否提供與您查詢相符之訊息的內容。 例如，針對小組內容，啟用這些選項將會因郵件進行執行緒化的方式來檢索上層訊息和所有子郵件。

也會檢查郵件的時間戳記。 如果郵件符合您的查詢，在4小時內，或在4個小時內追蹤的相鄰訊息，就會被視為交談的一部分，也會包含在結果中。

如果您必須確定哪些上下文訊息會傳回與您的搜尋查詢相符的內容，您就不需要使用這些選項。 您可以收集所有內容，或者您可以放寬搜尋的日期範圍，以便讓您查詢的結果傳回更多的郵件。

### <a name="review-sets-workflow"></a>審閱集合工作流程

您可以按一下 [ **審閱集** ] 索引標籤，查看現有的審閱集或建立新的評論。如需有關審閱集的詳細資訊，請參閱 [在高級 eDiscovery 中管理審閱集合](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。

除了檔之外，您還可以將電子郵件、團隊訊息、Yammer 郵件及其他內容新增到您的審閱集中。 在審閱集中，您也可以執行許多您可以在其他上下文中執行的相同作業，例如搜尋內容和建立自訂查詢。 這些操作只適用于已新增至審閱集的專案。

[ **管理審閱設定** ] 按鈕可提供其他選項，例如 [分析]、[摘要報告]、已新增多少個載入組等等。

若要存取資料的視覺效果與圖表，請按一下右上角的 [ **個別結果** \> **搜尋設定檔] 視圖** 。 您可以按一下這些圖表中的 [楔形]，以互動方式選取您要查詢的內容類型。 例如，您可以選擇只查詢團隊內容。 您也可以儲存這些查詢，就像儲存您手動撰寫的查詢一樣。

#### <a name="summary-view-text-view-and-annotate-view"></a>[摘要] 視圖、[文字視圖] 和 [批註] 視圖

如果您按一下 [審查] 集中的 [小組交談]，就會顯示 [ **摘要] 視圖**，將整個小組交談顯示為您可以個別互動的訊息清單。 按一下訊息右邊的向下箭號，以顯示操作功能表，可讓您查看訊息詳細資料或下載個別檔案 `.msg` 。 按一下 [郵件詳細資料]，就會顯示該郵件的中繼資料或完整中繼資料摘要。

若要下載 PDF，請按一下 [摘要] 視圖右上方的 [下載] 按鈕。

按一下 [ **文字視圖** ] 索引標籤，以顯示已提取的小組交談文字的純文字視圖。 此純文字內容適合匯出，您可以使用其他軟體工具輕鬆處理。

按一下 [批註] [ **查看** ] 索引標籤，即可存取 [批註] 功能。 這個索引標籤會以類似團隊交談的格式來顯示內容，但是還有其他編輯選項。 您可以使用鉛筆工具來製作筆記、在郵件上繪圖，或進行精細的 scratching 以進行密文。 您也可以使用「 **區域密文** 」工具來繪製黑色外框，並將它標示為「Redacted」的矩形。

以下是在使用者之間進行執行緒交談的 redacted 檔案範例。

> [!div class="mx-imgBorder"]
> ![Redacted 檔案的螢幕擷取畫面](media/RedactedFileExample.png)

[ **批註視圖** ] 索引標籤底部是 [ **標記檔** ] 按鈕，會顯示 [標記] 面板。 在此面板中，您可以將標記套用至團隊交談中的所有訊息。 您可以將交談標記為「回應」或「無回應」、[無論是否包含有趣的專案] （無論是否應包含在匯出中），以及是否需要進一步審查。 您也可以管理並套用其他可自訂的標記。

#### <a name="action-menu"></a>[動作] 功能表

您可以在 [審閱集合] 視窗中按一下 [ **動作** 匯出] 來匯出內容 \> ****。 匯出時有許多選項可供使用。

若要匯出包含所有小組郵件之所有中繼資料的檔案，請按一下以選取 [ **載入** 檔案] 核取方塊。 若要在檔案中包含任何您已套用至內容的標記，請按一下以選取 **[卷** 標] 核取方塊。

使用 [ **原生** 檔案] 選項，以其原生格式匯出檔案。 您可以選擇將交談匯出為單一檔案，或是將所有個別聊天訊息匯出為自己的個別檔案。

[ **文字檔** ] 選項可讓您儲存純文字版本的內容。 如需如何在審閱集中取得小組交談的純文字視圖的詳細資訊，請參閱上方的 [ [摘要視圖]、[文字視圖] 和 [批註] 視圖](#summary-view-text-view-and-annotate-view) 。

如果您對內容套用任何密文，如上面的 [ [摘要視圖]、[文字視圖] 和 [批註](#summary-view-text-view-and-annotate-view) ] 區段所述，您可以選取 [ **使用轉換過的 pdf 取代 redacted natives** ] 選項，以 PDF 中的已轉換複本來取代原生檔案。

您可以選擇匯出至 Microsoft 提供的 Azure blob 儲存體容器，或提供您自己的 Azure Blob 儲存體容器。

當您準備好要開始匯出程式時，請按一下 [ **匯出** ] 按鈕。 如需如何存取 Azure blob 儲存體容器，以及在匯出完成後下載匯出內容的詳細資訊，請參閱 [下載匯出作業](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 。

> [!NOTE]
> 匯出可能需要較長的時間。 若要追蹤匯出程式的狀態，請結束 [ **審閱集** ] 索引標籤，然後按一下 [ **匯出** ] 索引標籤。

## <a name="related-topics"></a>相關主題

- [Microsoft 365 中的 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [團隊 PowerShell 概覽](teams-powershell-overview.md)
