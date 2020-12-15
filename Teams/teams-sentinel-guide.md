---
title: Azure Sentinel 和 Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 適用於 IT 系統管理員的安全性建議和學習，以幫助他們使用 Sentinel 監視和搜捕 Teams 中可能出現的威脅。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6aa8e733aeb3828bb1815001ba0299a9ee1aaf78
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852144"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel 和 Microsoft Teams

Teams 可在 Microsoft 365 雲端的通訊和資料共用中扮演中心角色。 由於 Teams 服務涉及雲端中的許多基礎技術，因此在 *搜尋記錄* 和 *即時監控會議* 時，都可以從人工和自動化分析中受益。 Azure Sentinel 提供系統管理員以下解決方案。

> [!NOTE]
> 需要回顧 Azure Sentinel 的功能嗎？ [這篇文章](https://docs.microsoft.com/azure/sentinel/overview)就是您需要的。

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Azure Sentinel 和 Microsoft Teams

本文主要說明如何在 Azure Sentinel 中收集 Teams 活動記錄。 除了允許系統管理員將安全性管理放在單一窗格 (包括任何已選取的協力廠商裝置、Microsoft 威脅防護及其他 Microsoft 365 工作負載) 之下，Sentinel Workbook 和 Runbook 都能進行系統化的安全性監視。 此程序的第一步是收集所需的記錄進行分析。

> [!NOTE]
> 可以在同一個 Azure Sentinel 執行個體顯示多個 Microsoft 365 訂閱。 這樣就可以允許[即時監視](https://docs.microsoft.com/azure/sentinel/livestream)並在歷史記錄檔中尋找威脅。 系統管理員將能使用位於單一資源群組中的[跨資源查詢](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query)、跨資源群組或在其他訂閱中使用搜尋。

## <a name="step-1-collect-teams-logs"></a>步驟 1：收集 Teams 記錄

本節包含三個部分：

1. 在 **Microsoft 365** (M365) 中啟用審核記錄。
2. 在 **Microsoft Azure** 中註冊應用程式，以允許記錄收集的驗證和授權。
3. 註冊 API 訂閱，這將允許 **PowerShell**，透過 M365 API 收集記錄。

### <a name="enable-audit-logs-in-m365"></a>啟用 M365 中的稽核記錄

由於 Teams 會透過 M365 記錄活動，因此預設不會收集稽核記錄。 透過[以下步驟](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)開啟此功能。 Teams 資料會在 M365 稽核中的 *[Audit.General]* 下進行收集。

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>在 Microsoft Azure 中註冊應用程式以收集記錄

> [!TIP]
> 開始之前，您必須記錄 **應用程式識別碼/用戶端識別碼** 和您的 **租用戶識別碼**，以便日後使用。 當您進行以下的應用程式註冊步驟時，請務必記下這些資訊。 您會看到這兩個識別碼。
>- 應用程式建立之後，請按一下 [快速啟動] 側邊列上的 [應用程式註冊] > 尋找新應用程式的顯示名稱 > 複製應用程式 (用戶端) 識別碼。
>- 按一下 [快速啟動] 側邊列上的 [概觀]，> 複製目錄 (租用戶) 識別碼。

驗證並授權 Azure Active Directory (Azure AD) 應用程式，以從 API 收集記錄資料。

1. 瀏覽至 Azure 入口網站中 *[Azure AD]* 刀鋒視窗。
2. 在 [快速啟動] 側邊列中，按一下 *[應用程式註冊]*。
3. 選取 *[新增註冊]*。
4. 為您的 Teams 記錄收集應用程式命名，然後按一下 *[註冊]*。
5. 依以下路徑按一下：*[API 權限]* > *[新增權限]* > *[Office 365 管理 API]* > *[應用程式權限]*。
6. 展開 [活動] 摘要，然後查看 *[ActivityFeed.Read]*。
7. 在這裡選擇 *[授與系統管理同意]*。 出現提示時，請按一下 [是]。
8. 按一下側邊列中的 *[憑證和密碼]* > *[新增用戶端密碼]* 按鈕。
9. 在 [新增用戶端密碼] 視窗中，輸入新用戶端密碼的描述、確認在 [到期日] 中選擇 [永不]，然後按一下 *[新增]*。

> [!IMPORTANT]
> 請 **「務必」** 將新的用戶端密碼複製到位於新建立應用程式之名稱下的密碼管理器項目。 關閉 Azure 刀鋒視窗 (*「刀鋒視窗」* 是 Azure 用來表示視窗的詞彙) 之後，您將無法返回查看此密碼。

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>使用 PowerShell 註冊 API 來收集 Teams 記錄

設定的最後一個步驟是收集並註冊 API 訂閱，以便收集記錄資料。 這是透過 PowerShell REST 呼叫 M365 管理活動 API 來完成。

請在以下 PowerShell Cmdlet 中準備好提供 **[應用程式 (用戶端) 識別碼]**、新的 **[用戶端密碼]**、**[M365 的 URL 網域]** 和 **[目錄 (租用戶) 識別碼]** 的值。

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>步驟 2：部署 Sentinel Playbook 以擷取 Teams 記錄

Azure Sentinel Playbooks (又稱為邏輯應用程式) 將允許 Azure 擷取您收集的 Teams 資料。 邏輯應用程式會查詢 Office 365，以找出其寫入 Azure Sentinel 工作區的稽核資料。

使用[這個](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM 範本來部署您的 Sentinel Playbook。

注意事項：

1. 您需要逐步瀏覽 ARM 範本，並將某些值取代為適合您自己環境的值。
2. 記錄擷取與在 Azure Sentinel 查看結果的中間，需要一些時間。

   請等待 5 到 10 分鐘，並留意如果 5 分鐘之後沒有資料顯示，您會看到錯誤訊息。 檢查稽核記錄，並請留意，因為 Teams 資訊位於 Audit.General 事件中，其會收集多個 Teams 記錄，所以結果會在 5 到 10 分鐘內於使用的系統中顯示。 如果使用文字環境，請務必使用 Teams 來產生記錄。

![顯示邏輯應用程式類別的圖形。](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> 圖形中的動作說明： 
  </summary>

  • [週期] 是邏輯應用程式觸發器，可告知工作流程每小時執行一次。
  <p>
• [目前時間] 是相當基本動作，只是用來取得目前時間。
  <p>
• [初始化變數] 會建立稱為 NextPage 的變數，並將它設定為 1。 稍後會使用此動作來處理 O365 API 的分頁。
  <p>
• [初始化變數 2] 會建立稱為 Start Time 的空白變數。
  <p>
•[執行查詢] 和 [清單結果] 是 Azure 監視器動作，會針對從邏輯應用程式輸入的最後一個 O365 記錄查詢工作區。
  <p>
•[條件 4] 用於檢查 [執行查詢] 和 [清單結果] 查詢是否傳回任何資料。 這是為了檢查這個邏輯應用程式是否第一次使用。 如果沒有傳回資料，StartTime 變數會設定為 [現在 – 24 小時]。 如果傳回資料，StartTime 會設定為最後一筆記錄 TimeGenerated。 如此一來，查詢可以從 O365 API 的輪詢中的最後一個項目獲得到現在為止的資料；如果是第一次執行，則可以獲得最近 24 小時的資料。
  <p>
• [初始化變數 3] 會建立稱為 AvailableUri 的變數。 這是一個字串，其中 URL 分別使用 StartTime 和 CurrentTime 做為開始和結束時間來建立。
  <p>
• [Until 條件] 是一個迴圈，可讓邏輯應用程式持續輪詢 API，查看是否有更多的資料 (分頁)。 只要 NextPage 變數是1，迴圈就會繼續執行。 之後，如果沒有更多頁面可供擷取，將會更新此變數。
  <p>
•在 Until 迴圈內，第一個 HTTP 步驟會連線至 AvailableURI。 這個 URI 會傳回可用內容清單和每個內容的 URI。 您可以在以下 URL 深入了解運作方式：https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content。
  <p>
• 接下來會執行檢查，以確保資料傳回。 Condition 會檢查內文長度是否為 0。 如果為 0，表示沒有要寫入記錄分析的資料。 如果值大於 0，表示有要處理的資料。
  <p>
• 如果偵測到資料，必須緊接著處理。 剖析 JSON 會定義傳回資料的結構描述。 這可讓邏輯應用程式在後續步驟中使用經過剖析的資料做為動態內容。
  <p>
• 由於傳回的可用資料清單是陣列，因此會使用 For Each 動作迴圈可用內容清單。
  <p>
• 下一步是抓取內容。  會再次使用 HTTP 來取得 contentUri (由剖析 JSON 建立的動態屬性)，這是要檢索之資料的 URL。
  <p>
• 剖析 JSON 也用來剖析傳回的資料。 您可以在以下 URL 找到一些範例內容：https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content。
  <p>
• 傳回的資料也是陣列。 您也可以在這裡使用 For Each 迴圈。 在這個迴圈中，工作流程會取得目前的資料項目，並使用 [傳送資料] 動作，將資料寫入記錄分析。
  <p>
• 因為可能有多個可用內容頁面，所以條件會檢查 NextPageUri 是否不為 Null。 如果為 Null 或空白，NextPage 會設為 0，這會結束 Until 迴圈。 如果它包含 URL，AvaibleUri 變數會更新為該 URL。 如此一來，Until 迴圈的下次執行會使用下一個可用的 URL，而不是使用起始 URL。

  </details>

> [!TIP]
> 您可以選擇使用 *[Azure 函數]* 來擷取這些記錄，而如果您要這麼做，請依您的喜好而定，參閱 [這裡](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)或 [這裡](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp)的部署資訊。

若執行連接器 (無論您在上方選取哪個選項)，您應該會在 Azure Sentinel 工作區中看到一個名為 O365API_CL 的自訂資料表。 這裡會存放您的 Teams記錄。

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>步驟 3：使用 Sentinel 來監視 Microsoft Teams

對 Microsoft Teams 來說，身分識別是一個必須要監控的重要攻擊媒介。 由於 Azure Active Directory (Azure AD) 是 Microsoft 365 目錄的基礎 (包括 Teams)，因此收集和搜尋 Azure 記錄中有關驗證的威脅將有助捕獲跟身分識別有關的可疑行為。 您可以使用內建連接器將 Azure AD 資料拉入 Azure Sentinel，並使用這些[偵測](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs)和[搜尋](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs)查詢來尋找問題。

針對 Microsoft Teams 的特定攻擊 (例如，資料的威脅)，Azure Sentinel 也可讓您監視這些資料威脅並進行搜尋。

### <a name="create-a-parser-for-your-data"></a>為資料建立剖析程式

為了了解大量收集的資料，要做的第一件事是透過資料剖析使其具有意義。 會使用 Kusto查詢語言 (KQL) 函數來完成資料剖析，該函數可讓資料更易於使用。

> [!NOTE]
> KQL 函數是 KQL 查詢，但儲存為稱為「函數」的資料類型。 可在 Sentinel 中的查詢方塊輸入 KQL 函數的別名，以便再次快速執行查詢。 如需 KQL 函數以及如何建置剖析器函數的詳細資訊，請參閱[此技術社群文章](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381) (英文)。
 
 以下剖析器是可自訂的範例，目的在選取與 *[Teams]* 相關的 Office 365 管理 API 欄位的子集。 還有一個建議剖析器 [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)，但以下的剖析器可供修改，以符合不同的需求和喜好設定。

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 將剖析器儲存為 KQL 函數，其別名為 TeamsData。 它將用於後續查詢。 如需有關如何設定及使用 KQL 函數作為剖析器的詳細資訊，請參閱本[技術社群文章](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381) (英文)。

## <a name="helpful-hunting-kql-queries"></a>實用的搜捕 KQL 查詢

您可以使用這些查詢來熟悉您的 Teams 資料和 Teams 環境。 了解環境的外觀與運作方式是辨識可疑活動的最佳開端。 您可以在那裡擴展到威脅搜尋。

#### <a name="federated-external-users-query"></a>同盟外部使用者查詢

取得擁有同盟外部使用者的 Teams 網站清單。 這些使用者將會有一個網域名稱/UPN 尾碼，這個尾碼 *「並非」* 貴組織所有。 在此範例查詢中，組織擁有 contoso.com。

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> 若要深入了解 Teams 中的外部和來賓存取類型，請參閱 [本文](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)，或 [Teams 安全性指南](https://docs.microsoft.com/microsoftteams/teams-security-guide)中的 *參與者類型* 一節。

#### <a name="who-recently-joined--whose-role-changed"></a>最近加入/角色變更的人員

查詢特定使用者以檢查它們是否是過去 7 天內或一周內新增至 Teams 頻道：

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

過去 7 天內，團隊的使用者角色是否已變更：

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>來自未知或新組織的外部使用者

在 Teams 中，您可以將外部使用者新增至您的環境或頻道。 組織通常具有數量有限的關鍵合作夥伴，並會從這些合作夥伴中新增使用者。 此 KQL 會查看新增到團隊的外部使用者，這些使用者來自從未見過或未新增過的組織。

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a>過去新增然後移除的外部使用者

具有某種現有存取權層級的攻擊者可能會將一個新的外部帳戶新增到 Teams 以存取和竊取資料。 他們也可以快速移除該使用者，以隱藏他們所進行的存取。 此查詢會搜尋新增到 Teams 中並迅速刪除的外部帳戶，以幫助識別可疑行為。

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a>新增 Bot 或應用程式

Teams 可以將應用程式或 Bot 納入團隊中，以擴充功能集。 其中包括自訂應用程式和 Bot。 在某些情況下，您可以使用應用程式或 Bot 在 Teams 中建立持續性，不需要使用者帳戶，以及存取檔案和其他資料。 這個查詢會搜尋新增至 Teams 的應用程式或 Bot。

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>擁有大量 Teams 的使用者帳戶

當使用者通常圍繞特定主題建立和擁有少量 Teams 時，希望提升其權限的攻擊者可能會指派給自己大量不同 Teams 的擁有者權限。 此 KQL 查詢會尋找可疑行為。

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a>許多團隊遭單一使用者刪除

攻擊者可刪除多個團隊，進而造成中斷並危害專案和資料。 由於團隊通常是由個別擁有者來刪除，多個團隊被集中刪除可能會是問題的徵兆。 此 KQL 會尋找刪除多個團隊的使用者。

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a>擴大您的執行緒搜尋機會

您可以結合 Azure Active Directory (Azure AD) 等資源的查詢，或將其他 Office 365 工作負載與您的 Teams 查詢集合，來擴大您的搜尋範圍。 其中一個範例是結合 Azure AD SigninLogs 中的可疑模式偵測，並在搜尋團隊擁有者時使用該資訊。

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

另外，您可以使用以下方法為僅針對基於 Teams 的登入新增篩選器，進而對 Teams 進行 SigninLogs 偵測：

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

為了有助於進一步解釋如何使用 `where AppDisplayName starts with "Microsoft Teams"`，下面的 KQL 示範從一個 IP 位址成功登入而從另一個 IP 位址卻失敗的情況，但僅限於 Teams 登入：

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a>重要資訊和最新消息

**Pete Bryan、Nicholas DiCola 和 Matthew Lowe，感謝各位參與內容共同作業。** Pete Bryan 及與他共同作業的人員將繼續為 Teams 開發偵測查詢和搜尋查詢，因此請與此 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 存放庫保持聯繫，以取得最新消息。  追蹤本文所使用的[剖析器](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)和[邏輯應用程式](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)的更新。 您也可以加入並參與 [Azure Sentinel 社群](https://github.com/Azure/Azure-Sentinel/wiki)。 感謝您！ 祝您搜尋開心。

[在 Azure AD 中註冊您的應用程式](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[開啟或關閉稽核記錄搜尋](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[什麼是 Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)
