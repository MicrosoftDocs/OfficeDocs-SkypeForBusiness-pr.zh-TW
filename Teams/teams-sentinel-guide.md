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
ms.localizationpriority: high
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
ms.openlocfilehash: 745500dd0ac30d717e37ec9287618342554b26c9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627025"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel 和 Microsoft Teams

> [!IMPORTANT]
> Azure Sentinel 現在具有整合式連接器。 如需詳細資訊，請參閱[將 Office 365 記錄連線至 Azure Sentinel](/azure/sentinel/connect-office-365)。 這是收集這些記錄的建議路由，並取代下列所述的收集方法。

Teams 可在 Microsoft 365 雲端的通訊和資料共用中扮演中心角色。 由於 Teams 涉及雲端中的許多技術，因此可以從人工和自動化分析獲益。 這同時適用 *在記錄中搜捕* 及 *即時監視會議*。 Azure Sentinel 提供系統管理員以下解決方案。

> [!NOTE]
> 需要回顧 Azure Sentinel 的功能嗎？ [這篇文章](/azure/sentinel/overview)就是您需要的。

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Azure Sentinel 和 Microsoft Teams

本文主要說明如何在 Azure Sentinel 中收集 Teams 活動記錄。

Sentinel 可讓系統管理員在單一位置中執行安全性管理。這包括管理：

- 協力廠商裝置
- Microsoft 威脅防護
- Microsoft 365 工作負載

Sentinel 活頁簿和 Runbook 可以使得安全性監視 *系統化*。 此程序的第一步是收集分析所需的記錄。

> [!NOTE]
> 可以在同一個 Azure Sentinel 執行個體顯示多個 Microsoft 365 訂閱。 這樣就可以允許[即時監視](/azure/sentinel/livestream)，並在歷史記錄檔中搜捕威脅。 系統管理員將能使用位於單一資源群組內、跨資源群組或在其他訂閱中的[跨資源查詢](/azure/azure-monitor/log-query/cross-workspace-query)進行搜捕。

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>步驟 1：收集 Teams 記錄：在 Microsoft 365 中啟用稽核記錄

因為 Teams 會透過 Microsoft 365 記錄活動，因此預設不會收集稽核記錄。 使用[這些步驟](/microsoft-365/compliance/turn-audit-log-search-on-or-off)開啟此功能。 Teams 資料會收集在 Microsoft 365 稽核中的 *Audit.General* 下。

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>步驟 2：將 Office 365 記錄連線至 Azure Sentinel

Azure Sentinel 為 Office 365 記錄提供內建的連接器，可讓您將 Teams 資料與其他 Office 365 資料一起擷取至 Azure Sentinel。
 
在 Azure Sentinel 中，啟用 Office 365 資料連接器。 如需詳細資訊，請參閱 [Azure Sentinel 文件](/azure/sentinel/connect-office-365)。

## <a name="helpful-hunting-kql-queries"></a>實用的搜捕 KQL 查詢

您可以使用這些查詢來熟悉您的 Teams 資料和 Teams 環境。 了解環境的外觀與運作方式是辨識可疑活動的最佳開端。 您可以在那裡擴展到威脅搜尋。

### <a name="federated-external-users-query"></a>同盟外部使用者查詢

取得擁有同盟外部使用者的 Teams 網站清單。 這些使用者有一個網域名稱和/或 UPN 尾碼，其並非由組織所擁有。

在此範例查詢中，組織擁有 contoso.com。

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> 若要深入了解 Teams 中的外部和來賓存取類型，請參閱[與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)或《Teams 安全性指南》中的[參與者類型](teams-security-guide.md#participant-types)一節。

### <a name="who-recently-joined--whose-role-changed"></a>最近加入/角色變更的人員

查詢特定使用者，以檢查他們是否為過去七天或一週內新增至 Teams 頻道：

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

查詢團隊中使用者的角色是否於過去七天內變更：

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>來自未知或新組織的外部使用者

在 Teams 中，您可以將外部使用者新增至您的環境或頻道。 組織通常具有數量有限的關鍵合作夥伴，並會從這些合作夥伴中新增使用者。 此 KQL 會查看新增到團隊的外部使用者，這些使用者來自從未見過或未新增過的組織。

如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml) 中的查詢。

### <a name="external-users-who-were-added-and-then-removed"></a>過去新增然後移除的外部使用者

具有某種現有存取權層級的攻擊者可能會將一個新的外部帳戶新增到 Teams 以存取和竊取資料。 他們也可以快速移除該使用者，以隱藏他們所進行的存取。 此查詢會搜尋新增到 Teams 中並迅速刪除的外部帳戶，以幫助識別可疑行為。

如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml) 中的查詢。

### <a name="new-bot-or-application-added"></a>加入了新 Bot 或應用程式

Teams 可以在團隊中納入應用程式或 Bot，以延伸功能集 (包括自訂應用程式和 Bot)。 在某些情況下，可以為了 *持續性* 而在 Teams 中使用應用程式或 Bot，而不需要使用者帳戶，而且可以存取檔案和其他資料。 此查詢會搜捕對 Teams 而言為新項目的應用程式或 Bot。

如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml) 中的查詢。

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>為大量 Teams 擁有者的使用者帳戶

尋求提升其權限的攻擊者可能會為自己指派大量不同團隊的擁有者權限。 *一般來說*，使用者會建立並擁有與特定主題相關的一些團隊。 此 KQL 查詢會尋找可疑行為。

如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml) 中的查詢。

### <a name="many-team-deletions-by-a-single-user"></a>許多團隊遭單一使用者刪除

攻擊者可刪除多個團隊，進而造成中斷並危害專案和資料。 由於團隊通常是由個別擁有者來刪除，多個團隊被集中刪除可能會是問題的徵兆。 此 KQL 會尋找刪除多個團隊的單一使用者。

如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml) 中的查詢。

### <a name="expanding-your-threat-hunting-opportunities"></a>擴大您的威脅搜捕機會

結合來自 Azure Active Directory (Azure AD) 之類的資源或其他 Office 365 工作負載的查詢，可以與 Teams 查詢一起使用。 例如，結合 Azure AD SigninLogs 中可疑模式的偵測，並在搜捕團隊擁有者時使用該輸出。

```Kusto
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
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

另外，您可以使用以下方法為僅針對基於 Teams 的登入新增篩選器，進而對 Teams 進行 SigninLogs 偵測：

```Kusto
| where AppDisplayName has 'Teams'
```

為協助進一步說明使用 *where AppDisplayName has Teams*，下面的 KQL 將示範從一個 IP 位址成功登入而從另一個 IP 位址卻失敗的情況，但 *僅限* 於 Teams 登入：

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
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

**Pete Bryan、Nicholas DiCola 和 Matthew Lowe，感謝各位參與內容共同作業。** Pete Bryan 以及與他共同合作的人，會持續開發 Teams 的偵測和搜捕查詢。

保持追蹤此 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 存放庫以取得更新。

注意本文所使用的[剖析器](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)和[邏輯應用程式](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)的更新。

您也應該加入 (並貢獻) [Azure Sentinel 社群](https://github.com/Azure/Azure-Sentinel/wiki)。 我們正積極尋求對本文的意見反應，因此請使用下方的意見反應選項。 感謝您並祝您快樂搜捕。

[在 Azure AD 中註冊您的應用程式](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[開啟或關閉稽核記錄搜尋](/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[什麼是 Azure Sentinel？](/azure/sentinel/overview)
