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
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712765"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="6a3d8-103">Azure Sentinel 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a3d8-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a3d8-104">Azure Sentinel 現在具有整合式連接器。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="6a3d8-105">如需詳細資訊，請參閱[將 Office 365 記錄連線至 Azure Sentinel](/azure/sentinel/connect-office-365)。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="6a3d8-106">這是收集這些記錄的建議路由，並取代下列所述的收集方法。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="6a3d8-107">Teams 可在 Microsoft 365 雲端的通訊和資料共用中扮演中心角色。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="6a3d8-108">由於 Teams 涉及雲端中的許多技術，因此可以從人工和自動化分析獲益。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="6a3d8-109">這同時適用 *在記錄中搜捕* 及 *即時監視會議*。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="6a3d8-110">Azure Sentinel 提供系統管理員以下解決方案。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="6a3d8-111">需要回顧 Azure Sentinel 的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="6a3d8-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="6a3d8-112">[這篇文章](/azure/sentinel/overview)就是您需要的。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="6a3d8-113">Azure Sentinel 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a3d8-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="6a3d8-114">本文主要說明如何在 Azure Sentinel 中收集 Teams 活動記錄。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="6a3d8-115">Sentinel 可讓系統管理員在單一位置中執行安全性管理。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="6a3d8-116">這包括管理：</span><span class="sxs-lookup"><span data-stu-id="6a3d8-116">This includes managing:</span></span>

- <span data-ttu-id="6a3d8-117">協力廠商裝置</span><span class="sxs-lookup"><span data-stu-id="6a3d8-117">Third-party devices</span></span>
- <span data-ttu-id="6a3d8-118">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="6a3d8-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="6a3d8-119">Microsoft 365 工作負載</span><span class="sxs-lookup"><span data-stu-id="6a3d8-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="6a3d8-120">Sentinel 活頁簿和 Runbook 可以使得安全性監視 *系統化*。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="6a3d8-121">此程序的第一步是收集分析所需的記錄。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="6a3d8-122">可以在同一個 Azure Sentinel 執行個體顯示多個 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="6a3d8-123">這樣就可以允許[即時監視](/azure/sentinel/livestream)，並在歷史記錄檔中搜捕威脅。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="6a3d8-124">系統管理員將能使用位於單一資源群組內、跨資源群組或在其他訂閱中的[跨資源查詢](/azure/azure-monitor/log-query/cross-workspace-query)進行搜捕。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="6a3d8-125">步驟 1：收集 Teams 記錄：在 Microsoft 365 中啟用稽核記錄</span><span class="sxs-lookup"><span data-stu-id="6a3d8-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="6a3d8-126">因為 Teams 會透過 Microsoft 365 記錄活動，因此預設不會收集稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="6a3d8-127">使用[這些步驟](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="6a3d8-128">Teams 資料會收集在 Microsoft 365 稽核中的 *Audit.General* 下。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="6a3d8-129">步驟 2：將 Office 365 記錄連線至 Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="6a3d8-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="6a3d8-130">Azure Sentinel 為 Office 365 記錄提供內建的連接器，可讓您將 Teams 資料與其他 Office 365 資料一起擷取至 Azure Sentinel。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="6a3d8-131">在 Azure Sentinel 中，啟用 Office 365 資料連接器。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="6a3d8-132">如需詳細資訊，請參閱 [Azure Sentinel 文件](/azure/sentinel/connect-office-365)。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="6a3d8-133">實用的搜捕 KQL 查詢</span><span class="sxs-lookup"><span data-stu-id="6a3d8-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="6a3d8-134">您可以使用這些查詢來熟悉您的 Teams 資料和 Teams 環境。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="6a3d8-135">了解環境的外觀與運作方式是辨識可疑活動的最佳開端。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="6a3d8-136">您可以在那裡擴展到威脅搜尋。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="6a3d8-137">同盟外部使用者查詢</span><span class="sxs-lookup"><span data-stu-id="6a3d8-137">Federated external users query</span></span>

<span data-ttu-id="6a3d8-138">取得擁有同盟外部使用者的 Teams 網站清單。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="6a3d8-139">這些使用者有一個網域名稱和/或 UPN 尾碼，其並非由組織所擁有。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="6a3d8-140">在此範例查詢中，組織擁有 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-140">In this example query, the organization owns contoso.com.</span></span>

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
> <span data-ttu-id="6a3d8-141">若要深入了解 Teams 中的外部和來賓存取類型，請參閱[與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)或《Teams 安全性指南》中的[參與者類型](teams-security-guide.md#participant-types)一節。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="6a3d8-142">最近加入/角色變更的人員</span><span class="sxs-lookup"><span data-stu-id="6a3d8-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="6a3d8-143">查詢特定使用者，以檢查他們是否為過去七天或一週內新增至 Teams 頻道：</span><span class="sxs-lookup"><span data-stu-id="6a3d8-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="6a3d8-144">查詢團隊中使用者的角色是否於過去七天內變更：</span><span class="sxs-lookup"><span data-stu-id="6a3d8-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="6a3d8-145">來自未知或新組織的外部使用者</span><span class="sxs-lookup"><span data-stu-id="6a3d8-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="6a3d8-146">在 Teams 中，您可以將外部使用者新增至您的環境或頻道。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="6a3d8-147">組織通常具有數量有限的關鍵合作夥伴，並會從這些合作夥伴中新增使用者。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="6a3d8-148">此 KQL 會查看新增到團隊的外部使用者，這些使用者來自從未見過或未新增過的組織。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="6a3d8-149">如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml) 中的查詢。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="6a3d8-150">過去新增然後移除的外部使用者</span><span class="sxs-lookup"><span data-stu-id="6a3d8-150">External users who were added and then removed</span></span>

<span data-ttu-id="6a3d8-151">具有某種現有存取權層級的攻擊者可能會將一個新的外部帳戶新增到 Teams 以存取和竊取資料。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="6a3d8-152">他們也可以快速移除該使用者，以隱藏他們所進行的存取。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="6a3d8-153">此查詢會搜尋新增到 Teams 中並迅速刪除的外部帳戶，以幫助識別可疑行為。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="6a3d8-154">如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml) 中的查詢。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="6a3d8-155">加入了新 Bot 或應用程式</span><span class="sxs-lookup"><span data-stu-id="6a3d8-155">New bot or application added</span></span>

<span data-ttu-id="6a3d8-156">Teams 可以在團隊中納入應用程式或 Bot，以延伸功能集 (包括自訂應用程式和 Bot)。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="6a3d8-157">在某些情況下，可以為了 *持續性* 而在 Teams 中使用應用程式或 Bot，而不需要使用者帳戶，而且可以存取檔案和其他資料。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="6a3d8-158">此查詢會搜捕對 Teams 而言為新項目的應用程式或 Bot。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="6a3d8-159">如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml) 中的查詢。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="6a3d8-160">為大量 Teams 擁有者的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="6a3d8-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="6a3d8-161">尋求提升其權限的攻擊者可能會為自己指派大量不同團隊的擁有者權限。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="6a3d8-162">*一般來說*，使用者會建立並擁有與特定主題相關的一些團隊。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="6a3d8-163">此 KQL 查詢會尋找可疑行為。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="6a3d8-164">如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml) 中的查詢。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="6a3d8-165">許多團隊遭單一使用者刪除</span><span class="sxs-lookup"><span data-stu-id="6a3d8-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="6a3d8-166">攻擊者可刪除多個團隊，進而造成中斷並危害專案和資料。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="6a3d8-167">由於團隊通常是由個別擁有者來刪除，多個團隊被集中刪除可能會是問題的徵兆。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="6a3d8-168">此 KQL 會尋找刪除多個團隊的單一使用者。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="6a3d8-169">如需詳細資訊，請參閱 [Azure Sentinel 社群 GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml) 中的查詢。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="6a3d8-170">擴大您的威脅搜捕機會</span><span class="sxs-lookup"><span data-stu-id="6a3d8-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="6a3d8-171">結合來自 Azure Active Directory (Azure AD) 之類的資源或其他 Office 365 工作負載的查詢，可以與 Teams 查詢一起使用。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="6a3d8-172">例如，結合 Azure AD SigninLogs 中可疑模式的偵測，並在搜捕團隊擁有者時使用該輸出。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

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

<span data-ttu-id="6a3d8-173">另外，您可以使用以下方法為僅針對基於 Teams 的登入新增篩選器，進而對 Teams 進行 SigninLogs 偵測：</span><span class="sxs-lookup"><span data-stu-id="6a3d8-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="6a3d8-174">為協助進一步說明使用 *where AppDisplayName has Teams*，下面的 KQL 將示範從一個 IP 位址成功登入而從另一個 IP 位址卻失敗的情況，但 *僅限* 於 Teams 登入：</span><span class="sxs-lookup"><span data-stu-id="6a3d8-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

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

## <a name="important-information-and-updates"></a><span data-ttu-id="6a3d8-175">重要資訊和最新消息</span><span class="sxs-lookup"><span data-stu-id="6a3d8-175">Important information and updates</span></span>

<span data-ttu-id="6a3d8-176">**Pete Bryan、Nicholas DiCola 和 Matthew Lowe，感謝各位參與內容共同作業。**</span><span class="sxs-lookup"><span data-stu-id="6a3d8-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="6a3d8-177">Pete Bryan 以及與他共同合作的人，會持續開發 Teams 的偵測和搜捕查詢。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="6a3d8-178">保持追蹤此 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 存放庫以取得更新。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="6a3d8-179">注意本文所使用的[剖析器](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)和[邏輯應用程式](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)的更新。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="6a3d8-180">您也應該加入 (並貢獻) [Azure Sentinel 社群](https://github.com/Azure/Azure-Sentinel/wiki)。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="6a3d8-181">我們正積極尋求對本文的意見反應，因此請使用下方的意見反應選項。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="6a3d8-182">感謝您並祝您快樂搜捕。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-182">Thank you & Happy hunting.</span></span>

[<span data-ttu-id="6a3d8-183">在 Azure AD 中註冊您的應用程式</span><span class="sxs-lookup"><span data-stu-id="6a3d8-183">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="6a3d8-184">開啟或關閉稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="6a3d8-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="6a3d8-185">什麼是 Azure Sentinel？</span><span class="sxs-lookup"><span data-stu-id="6a3d8-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
