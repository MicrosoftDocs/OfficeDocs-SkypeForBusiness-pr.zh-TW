---
title: 從 Slack 移轉到 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- NOCSH
description: 從 Slack 移轉到 Microsoft Teams 的完全指引。
ms.openlocfilehash: 8b4fc90cde4bb438eee421459cf2c26672555b09
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030639"
---
# <a name="migrate-from-slack-to-microsoft-teams"></a><span data-ttu-id="65836-103">從 Slack 移轉到 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65836-103">Migrate from Slack to Microsoft Teams</span></span>

<span data-ttu-id="65836-104">本文將逐步引導您從 Slack 移轉到 Microsoft Teams 的過程。</span><span class="sxs-lookup"><span data-stu-id="65836-104">This article walks you through the journey of moving to Microsoft Teams from Slack.</span></span>

<span data-ttu-id="65836-105">為組織規劃從 Slack 移轉到 Teams 時，您必須先決定要保留的項目 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="65836-105">When planning your organization’s move to Teams from Slack, it's important to decide what you need to keep (if anything).</span></span> <span data-ttu-id="65836-106">我們一開始先說明可以轉移的資料類型，然後逐步引導您如何評估需求、規劃移轉，然後執行移轉。</span><span class="sxs-lookup"><span data-stu-id="65836-106">We'll start off by describing what types of data can be migrated and then walk you through how to assess your needs, plan your move, and then make the move.</span></span>

<span data-ttu-id="65836-107">下列圖表顯示了高等級 Slack 架構。</span><span class="sxs-lookup"><span data-stu-id="65836-107">The diagram below shows the Slack architecture at a high level.</span></span>

![減緩高等級 Slack 架構的影像](media/migrate-slack-to-teams-image1.png)

## <a name="plan-your-migration-from-slack"></a><span data-ttu-id="65836-109">規劃從 Slack 的移轉</span><span class="sxs-lookup"><span data-stu-id="65836-109">Plan your migration from Slack</span></span>
### <a name="what-you-can-and-cant-migrate"></a><span data-ttu-id="65836-110">可以或不可移轉的項目</span><span class="sxs-lookup"><span data-stu-id="65836-110">What you can and can’t migrate</span></span>
<span data-ttu-id="65836-111">您的 Slack 服務方案將決定您可以或無法移轉的項目。</span><span class="sxs-lookup"><span data-stu-id="65836-111">Your Slack service plan will determine what you can and can’t migrate.</span></span> <span data-ttu-id="65836-112">例如，某些 Slack 服務方案只允許您匯出公用頻道的歷程記錄和檔案，而其他的則需要 DocuSign 要求，以包含私人頻道和直接訊息。</span><span class="sxs-lookup"><span data-stu-id="65836-112">For example, some Slack service plans only let you export public channels history and files, other require a DocuSign request to include Private Channels and Direct Messages.</span></span> 

<span data-ttu-id="65836-113">若要決定您的 Slack 工作區服務等級，請登入 Slack 並記下在 **[關於此工作區]** 頁面上的的方案類型。</span><span class="sxs-lookup"><span data-stu-id="65836-113">To determine your Slack Workspace service level, log into Slack and note your plan type on the **About this Workspace** page.</span></span>

<span data-ttu-id="65836-114">若要深入了解 Slack 的匯出選項，請移至 Slack 網站：https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="65836-114">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

<span data-ttu-id="65836-115">下列圖表提供了在本文中我們將涵蓋之 Slack 移轉狀況的高等級看法。</span><span class="sxs-lookup"><span data-stu-id="65836-115">The diagram below gives you a high-level look at the Slack migration landscape that we’ll cover in this article.</span></span> 

![顯示 Slack 匯出狀況的圖表。](media/migrate-slack-to-teams-image2.png)

<span data-ttu-id="65836-117">完成本章節後，您應能了解：</span><span class="sxs-lookup"><span data-stu-id="65836-117">When you're done with this section, you should understand:</span></span>
- <span data-ttu-id="65836-118">Slack 工作區的服務等級</span><span class="sxs-lookup"><span data-stu-id="65836-118">The service level of your Slack Workspaces</span></span>
- <span data-ttu-id="65836-119">可以或無法匯出的項目</span><span class="sxs-lookup"><span data-stu-id="65836-119">What can and can't be exported</span></span>
- <span data-ttu-id="65836-120">匯出的一般方法</span><span class="sxs-lookup"><span data-stu-id="65836-120">Common approaches to exporting</span></span>

### <a name="assess-your-slack-workspaces"></a><span data-ttu-id="65836-121">評估您的 Slack 工作區</span><span class="sxs-lookup"><span data-stu-id="65836-121">Assess your Slack workspaces</span></span>
<span data-ttu-id="65836-122">在可規劃組織的移轉方案之前，您必須先集結一些與 Slack 工作區相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="65836-122">Before you can plan your organization’s migration plan, you need to pull together some information about your Slack workspaces.</span></span> <span data-ttu-id="65836-123">了解您 Slack 工作區的使用方式將幫助您決定移轉的範圍。</span><span class="sxs-lookup"><span data-stu-id="65836-123">Understanding how your Slack workspaces are being used helps you determine the scope of your migration.</span></span> <span data-ttu-id="65836-124">例如，要移轉多少工作區？</span><span class="sxs-lookup"><span data-stu-id="65836-124">For example, how many workspaces are being moved?</span></span> <span data-ttu-id="65836-125">是由某個特定部門、許多部門，還是由整個組織使用？</span><span class="sxs-lookup"><span data-stu-id="65836-125">Are they used by a specific department, many, or in use by an entire organization?</span></span>

<span data-ttu-id="65836-126">如果您屬於打算移轉之 Slack 工作區的成員之一，您可以前往 *<your Slack workspace>.slack.com/stats* 來自行分析使用方式。查看 [頻道] 和 [成員] 索引標籤以尋找使用模式。</span><span class="sxs-lookup"><span data-stu-id="65836-126">If you’re a member of the Slack Workspaces you want to migrate, you can analyze the usage yourself by going to *<your Slack workspace>.slack.com/stats*. Review the Channels and Members tabs to look for usage patterns.</span></span> <span data-ttu-id="65836-127">決定要移轉何種工作區 (以及要留下哪些工作區)。</span><span class="sxs-lookup"><span data-stu-id="65836-127">Decide which workspaces you want to migrate (and which ones you want to leave behind).</span></span> 

> [!NOTE]
> <span data-ttu-id="65836-128">如果您沒有統計資料頁面的存取權，您就不是系統管理員或擁有者。</span><span class="sxs-lookup"><span data-stu-id="65836-128">If you don’t have access to the stats page, you’re not an admin or owner.</span></span> 

### <a name="export-channels"></a><span data-ttu-id="65836-129">匯出頻道</span><span class="sxs-lookup"><span data-stu-id="65836-129">Export Channels</span></span>

<span data-ttu-id="65836-130">在 Slack 中，使用者會加入屬於 Slack 工作區的頻道，然而 Teams 使用者則是加入頻道集合的團隊。</span><span class="sxs-lookup"><span data-stu-id="65836-130">In Slack, users join a channel which is part of a Slack Workspace, whereas in Teams users join a team which is a collection of channels.</span></span> <span data-ttu-id="65836-131">我們建議您使用 Slack 分析，查看每個頻道發生活動的次數，以幫助您決定要移轉的頻道。</span><span class="sxs-lookup"><span data-stu-id="65836-131">We recommend that you use Slack analytics to see how much activity happens in each channel to help you decide which channels to move.</span></span> <span data-ttu-id="65836-132">您將使用結果清單找出如何將 Slack 頻道分組至 Teams 中的團隊，以及每個團隊應具有的成員。</span><span class="sxs-lookup"><span data-stu-id="65836-132">You’ll use the resulting list to figure out how to group your Slack channels into teams in Teams as well as who should be members of each team.</span></span>

<span data-ttu-id="65836-133">如果您有付費的 Slack 服務方案 (除了免費以外)，您可以使用 Slack 分析 (<your Slack workspace>.slack.com/admin/stats#channels) 來查看頻道的使用程度、上次使用時間和成員人數。</span><span class="sxs-lookup"><span data-stu-id="65836-133">If you have a paid Slack service plan (anything other than Free), you can use Slack’s analytics (<your Slack workspace>.slack.com/admin/stats#channels) to see how active a channel is, when it was last used, and how many people are members.</span></span> <span data-ttu-id="65836-134">這可協助您決定是否要移轉頻道。</span><span class="sxs-lookup"><span data-stu-id="65836-134">This can help you decide whether to migrate the channel.</span></span> <span data-ttu-id="65836-135">根據預設，可以匯出公用頻道內容(訊息與檔案)。</span><span class="sxs-lookup"><span data-stu-id="65836-135">By default, public channels content (messages and files) can be exported.</span></span> <span data-ttu-id="65836-136">根據您的 Slack 服務方案，以及您是否已從 Slack 要求私人頻道和從直接訊息，這些都可以匯出。</span><span class="sxs-lookup"><span data-stu-id="65836-136">Depending on your Slack service plan and whether you’ve requested Private Channels and Direct Messages from Slack, those can be exported.</span></span>

<span data-ttu-id="65836-137">若要深入了解 Slack 的匯出選項，請移至 Slack 網站：https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="65836-137">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="65836-138">檢查組織對頻道資料的隱私權與合規性需求。</span><span class="sxs-lookup"><span data-stu-id="65836-138">Check your organization’s privacy and compliance requirements around channel data.</span></span> <span data-ttu-id="65836-139">除了遵守終端可識別內容t (EUII) 的生命週期外，您的組織還可能在操作、儲存和處理此資料方面有合規性要求。</span><span class="sxs-lookup"><span data-stu-id="65836-139">Your organization may have compliance requirements around the handling, storage, and processing of this data, in addition to complying with the lifecycle of end-user identifiable content (EUII).</span></span>

### <a name="export-direct-messages"></a><span data-ttu-id="65836-140">匯出直接訊息</span><span class="sxs-lookup"><span data-stu-id="65836-140">Export Direct Messages</span></span>
<span data-ttu-id="65836-141">直接訊息與 Teams 中的聊天相同，也就是1:1 或一對多非頻道交談。</span><span class="sxs-lookup"><span data-stu-id="65836-141">Direct Messages are the same as chats in Teams, which are 1:1 or 1-to-many non-channel conversations.</span></span> <span data-ttu-id="65836-142">匯出能力取決於您的 Slack 服務方案，以及您是否已要求將直接訊息包含在 [Slack 匯出] 中。</span><span class="sxs-lookup"><span data-stu-id="65836-142">Export-ability depends on your Slack service plan and if you’ve requested Direct Messages to be included in your Slack Export.</span></span> <span data-ttu-id="65836-143">Teams 目前不支援匯入直接訊息。</span><span class="sxs-lookup"><span data-stu-id="65836-143">Teams doesn’t support importing Direct messages currently.</span></span> <span data-ttu-id="65836-144">請諮詢 Microsoft 合作夥伴，以了解可探索之將直接訊息內容匯入 Teams 的協力廠商相關解決方案。</span><span class="sxs-lookup"><span data-stu-id="65836-144">Consult a Microsoft partner to learn about third-party solutions you can explore that bring Direct Messages content into Teams.</span></span>

<span data-ttu-id="65836-145">若要匯出直接訊息，請查看 Slack 應用程式市集中的工具 (例如 [匯出])。</span><span class="sxs-lookup"><span data-stu-id="65836-145">For exporting Direct Messages, check out tools, such as Export, in the Slack App Store.</span></span>

### <a name="apps-and-custom-integrations"></a><span data-ttu-id="65836-146">應用程式和自訂整合</span><span class="sxs-lookup"><span data-stu-id="65836-146">Apps and custom integrations</span></span>

<span data-ttu-id="65836-147">Slack 中的應用程式就如同 Teams 中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="65836-147">Apps in Slack are like apps in Teams.</span></span> <span data-ttu-id="65836-148">當您在工作區中擁有應用程式及其設定清單後，您可以在 Teams 應用程式市集中搜尋，以查看它們是否可用於 Teams\*。</span><span class="sxs-lookup"><span data-stu-id="65836-148">Once you have a list of apps and their configurations in the Workspace, you can search in the Teams App store to see if they’re available for Teams\*.</span></span> 

<span data-ttu-id="65836-149">前往 <your Slack workspace>.slack.com/apps/manage 以取得應用程式和自訂整合清單。</span><span class="sxs-lookup"><span data-stu-id="65836-149">Go to <your Slack workspace>.slack.com/apps/manage to get a list of Apps and Custom Integrations.</span></span> <span data-ttu-id="65836-150">此頁面也會顯示每個應用程式使用中的設定數量。</span><span class="sxs-lookup"><span data-stu-id="65836-150">This page also shows you the number of configurations where each app is in use.</span></span> <span data-ttu-id="65836-151">自訂整合按照「移轉能力」而有所不同。</span><span class="sxs-lookup"><span data-stu-id="65836-151">Custom Integrations vary in their “migrate-ability.”</span></span> <span data-ttu-id="65836-152">如果是 Web Hook，您通常可以將其傳送到 Microsoft 365 或 Office 365 連接器，以將工作流程轉換至 Teams。</span><span class="sxs-lookup"><span data-stu-id="65836-152">If it’s a Web Hook, you can usually send it to a Microsoft 365 or Office 365 Connector to shift the workflow into Teams.</span></span> <span data-ttu-id="65836-153">視情況評估 Bot 和其他應用程式，以規劃將其移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="65836-153">Assess bots and other apps on a case-by-case basis to plan for moving them to Teams.</span></span>

<span data-ttu-id="65836-154">\* 如果您的系統管理員已限制應用程式使用，您可能不會看到可用應用程式的完整清單。</span><span class="sxs-lookup"><span data-stu-id="65836-154">\* If your administrator has restricted apps usage, you may not be looking at the full list of available apps.</span></span>

### <a name="users"></a><span data-ttu-id="65836-155">使用者</span><span class="sxs-lookup"><span data-stu-id="65836-155">Users</span></span>
<span data-ttu-id="65836-156">您在 Slack 中使用的身分識別模式，可能不會直接對應到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="65836-156">The identity schemes you used in Slack might not map directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="65836-157">例如，您的 Slack 使用者電子郵件地址可能不會對應到 Microsoft 365 或 Office 365 的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="65836-157">For example, the email addresses of your Slack users may not map to Microsoft 365 or Office 365 work or school accounts.</span></span> <span data-ttu-id="65836-158">開始規劃 Teams 推出前，您應先建立使用者識別碼對應。</span><span class="sxs-lookup"><span data-stu-id="65836-158">You should create a user-ID map before you start planning your Teams rollout.</span></span>

<span data-ttu-id="65836-159">如果您使用付費的 Slack 服務方案，您可以移至 *<your Slack workspace>.slack.com/admin/stats#members* 以取得成員詳細資料，例如每位使用者的電子郵件地址和帳戶類型 (如單一與多頻道來賓)。</span><span class="sxs-lookup"><span data-stu-id="65836-159">If you’re on a paid Slack service plan, you can go to *<your Slack workspace>.slack.com/admin/stats#members* to get member details such as email address and account type for each user (for example, single vs. multi-channel guest).</span></span>

<span data-ttu-id="65836-160">以下是您可以用來比較來自 Slack 匯出和 Azure AD 電子郵件地址的指令碼，以協助解決名稱模稜兩可的情形。</span><span class="sxs-lookup"><span data-stu-id="65836-160">Here’s a script you can use to compare email addresses from a Slack export against Azure AD to help solve for name ambiguity.</span></span> <span data-ttu-id="65836-161">如果啟用 Teams 時也會報告。</span><span class="sxs-lookup"><span data-stu-id="65836-161">It’ll also report if the user is enabled for Teams.</span></span> <span data-ttu-id="65836-162">如果您需要 PowerShell 的說明，請參閱[開始使用 Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps)。</span><span class="sxs-lookup"><span data-stu-id="65836-162">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

```azurepowershell
Connect-AzureAD
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class User {
    [ValidateNotNullOrEmpty()] $ID
    [ValidateNotNullOrEmpty()] $FullName
    [string] $Email
    [string] $UPN
    [ValidateNotNullOrEmpty()][bool] $ExistsAzureAD
    [ValidateNotNullOrEmpty()][bool] $TeamsEnabled
}

$output = New-Object -type System.Collections.ObjectModel.Collection["User"]

$users = Get-Content -Raw -Path .\slackHistory\users.json | ConvertFrom-Json

Write-Host -ForegroundColor Green "$(Get-Timestamp) User Count: " $users.Count

$i=1
Write-Host "$(Get-Timestamp) Attempting direct email match.. `n"
foreach ($slackUser in $users) {
    $user = New-Object User
    $user.id = $slackUser.id
    $user.FullName = $slackUser.name
    try {
        if ($null -ne $slackUser.profile.email) {
            $user.email = $slackUser.profile.email
            $emailSplit = $slackUser.profile.email.Split('@')
            $mailNickName = $emailSplit[0]
            $result = Get-AzureADUser -Filter "MailNickName eq '$($mailNickName)' or UserPrincipalName eq '$($slackUser.profile.email)' or proxyAddresses/any(c:c eq 'smtp:$($slackUser.profile.email)')"
            if ($null -ne $result) {
                $user.ExistsAzureAD = $true
                $user.UPN = $result.UserPrincipalName
                $assignedPlans = $result.assignedPlans
                foreach ($plan in $assignedPlans) {
                    if ($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") {
                        if ($plan.CapabilityStatus -eq "Enabled") {
                            $user.TeamsEnabled = $true
                        }
                        else {
                            $user.TeamsEnabled = $false
                        }
                    }
                }
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - AzureAD object found:" $result.MailNickName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - Teams Enabled:" $user.TeamsEnabled
            }
            else {
                $user.ExistsAzureAD = $false
                Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: " $slackUser.profile.email
            }
        }
        $i++
    }   
    catch
    {
        $user.ExistsAzureAD = $false
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: $($i)" $user.profile.email
        $i++
    }
    $output.Add($user)
}

$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
```

<span data-ttu-id="65836-163">完成本章節後，您應已具有：</span><span class="sxs-lookup"><span data-stu-id="65836-163">When you’re done with this section, you should have:</span></span>
- <span data-ttu-id="65836-164">含有使用方式統計資料之每個工作區的頻道清單。</span><span class="sxs-lookup"><span data-stu-id="65836-164">A list of Channels per Workspace with usage statistics.</span></span>
- <span data-ttu-id="65836-165">具有每個頻道設定的 Slack 應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="65836-165">A list of Slack Apps with configurations per channel.</span></span>
- <span data-ttu-id="65836-166">已決定您要匯出 Slack 訊息歷程記錄的類型 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="65836-166">Determined what type of Slack message history you want to export (if any).</span></span>
- <span data-ttu-id="65836-167">Slack 帳戶對應至 Microsoft 工作或學校帳戶的使用者清單，以及其擁有的 Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="65836-167">A list of users whose Slack accounts map to Microsoft work or school accounts and which Teams license they have.</span></span>

## <a name="plan-your-teams-deployment"></a><span data-ttu-id="65836-168">規劃 Teams 部署</span><span class="sxs-lookup"><span data-stu-id="65836-168">Plan your Teams deployment</span></span>
<span data-ttu-id="65836-169">您已由 Slack 匯出所需的項目 (並留下不需要的任何項目)。</span><span class="sxs-lookup"><span data-stu-id="65836-169">You’ve exported what you need from Slack (and left behind anything you don’t need).</span></span> <span data-ttu-id="65836-170">現在可以規劃推出 Teams 的方式並匯入您的 Slack 資料。</span><span class="sxs-lookup"><span data-stu-id="65836-170">Now it’s time to plan how you’ll roll out Teams and import your Slack data.</span></span> <span data-ttu-id="65836-171">這是一個根據使用方式評估何者適合團隊的好機會，並將這些元素包含至您的 Teams 部署方案。</span><span class="sxs-lookup"><span data-stu-id="65836-171">This is a great opportunity to assess what's worked well for the team based on usage and include those elements in your Teams deployment plan.</span></span> <span data-ttu-id="65836-172">在本章節的結尾，您將具有您的 Teams 使用者、頻道和應用程式的藍圖。</span><span class="sxs-lookup"><span data-stu-id="65836-172">At the end of this section, you’ll have a blueprint for your Teams users, channels, and apps.</span></span> 

<span data-ttu-id="65836-173">下列圖表將提供在 Teams 部署中您將解決事項的高等級大綱。</span><span class="sxs-lookup"><span data-stu-id="65836-173">The diagram below gives you a high-level outline of the things you’ll address in your Teams deployment.</span></span>

:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="從 Slack 規劃 Teams 部署的高等級大綱。":::

### <a name="team-and-channel-structure"></a><span data-ttu-id="65836-175">Team 和頻道結構</span><span class="sxs-lookup"><span data-stu-id="65836-175">Team and channel structure</span></span>

<span data-ttu-id="65836-176">Slack 工作區可以代表單一團隊、多個團隊或整個組織。</span><span class="sxs-lookup"><span data-stu-id="65836-176">A Slack Workspace may represent a single team, multiple teams or an entire organization.</span></span> <span data-ttu-id="65836-177">當您決定結構時，了解工作區的範圍至關重要。</span><span class="sxs-lookup"><span data-stu-id="65836-177">It’s important to understand the scope of the Workspaces as you determine the structure.</span></span> <span data-ttu-id="65836-178">與 Slack 中 Teams 團隊最接近的關係是工作區，而其中包含頻道集合。</span><span class="sxs-lookup"><span data-stu-id="65836-178">The closest relationship to a Teams team in Slack is the Workspace, which contains a collection of channels.</span></span> <span data-ttu-id="65836-179">下列圖表證明 3 種不同的 Slack 到 Teams 的對應，以及為每個工作區挑選正確對應的指引。</span><span class="sxs-lookup"><span data-stu-id="65836-179">The diagram below demonstrates 3 different Slack-to-Teams mappings, and guidance for picking the right one for each Workspace.</span></span>


|<span data-ttu-id="65836-180">Slack 到 Teams 的對應</span><span class="sxs-lookup"><span data-stu-id="65836-180">Slack-to-Teams mapping</span></span> |  |
|---------|---------|
|<span data-ttu-id="65836-181">1 個 Slack 工作區：箭號_右側：1 個團隊</span><span class="sxs-lookup"><span data-stu-id="65836-181">1 Slack Workspace :arrow_right: 1 team</span></span>   | <span data-ttu-id="65836-182">針對需要少於 200 個頻道的較小型 Slack 工作區</span><span class="sxs-lookup"><span data-stu-id="65836-182">For smaller Slack workspaces that need fewer than 200 channels</span></span><br><span data-ttu-id="65836-183">包含成長和私人頻道規劃的緩衝區</span><span class="sxs-lookup"><span data-stu-id="65836-183">Include a buffer for growth and private channel planning</span></span>  |
|<span data-ttu-id="65836-184">1 個 Slack 工作區：箭號_右側：多個團隊</span><span class="sxs-lookup"><span data-stu-id="65836-184">1 Slack Workspace :arrow_right: multiple teams</span></span>     | <span data-ttu-id="65836-185">使用您的 Slack 工作區分析資料來建立邏輯頻道群組，其會成為成為您團隊的基礎。</span><span class="sxs-lookup"><span data-stu-id="65836-185">Use your Slack Workspace analytics data to create logical channel groupings, which become the basis of your teams</span></span>        |
|<span data-ttu-id="65836-186">2 個以上 Slack 工作區：箭號_右側：多個團隊</span><span class="sxs-lookup"><span data-stu-id="65836-186">2+ Slack Workspaces :arrow_right: multiple teams</span></span>     | <span data-ttu-id="65836-187">使用您的 Slack 工作區分析資料來建立邏輯團隊和頻道群組，其會成為成為您團隊的基礎。</span><span class="sxs-lookup"><span data-stu-id="65836-187">Use your Slack Workspace analytics data to create logical team and channel groupings, which become the basis of your teams</span></span>        |

<span data-ttu-id="65836-188">協力廠商解決方案具有使用統計資料，可協助您評估頻道作用狀況和貼文的數量。</span><span class="sxs-lookup"><span data-stu-id="65836-188">Third-party solutions have usage statistics to help you assess how active the channel is and how many posts there are.</span></span> <span data-ttu-id="65836-189">通常經常使用的頻道會成為包含於團隊規劃中的候選頻道。</span><span class="sxs-lookup"><span data-stu-id="65836-189">Typically, channels that are frequently used would be candidates to include in your team planning.</span></span>

> [!TIP]
> <span data-ttu-id="65836-190">僅保留方法中所必須的項目，以決定要在 Teams 中重新建立哪些頻道。</span><span class="sxs-lookup"><span data-stu-id="65836-190">Retain only what is required in your approach to determine which channels to recreate in Teams.</span></span> <span data-ttu-id="65836-191">若要深入了解，請參閱[團隊和頻道概觀](teams-channels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="65836-191">To learn more, read [Overview of teams and channels](teams-channels-overview.md).</span></span> 

#### <a name="team-planning"></a><span data-ttu-id="65836-192">團隊規劃</span><span class="sxs-lookup"><span data-stu-id="65836-192">Team Planning</span></span>
<span data-ttu-id="65836-193">使用您在上述 [規劃] 章節中所編譯的 [頻道庫存]，與您的 Slack 擁有者和系統管理員合作，以找出哪些頻道應成為團隊，以及哪些頻道應成為團隊中的頻道。</span><span class="sxs-lookup"><span data-stu-id="65836-193">Using the Channel inventory you compiled in the Planning section above, work with your Slack owners and admins to figure out which channels should become teams and which ones should become channels in a team.</span></span> <span data-ttu-id="65836-194">使用 Excel 或 PowerBI 來協助本次分析 - 兩種都可以提供額外的深入資訊，以幫助推動有關保留哪些頻道的討論。</span><span class="sxs-lookup"><span data-stu-id="65836-194">Use either Excel or PowerBI to help with this analysis - both can provide additional insights to help drive these discussions on which channels to retain.</span></span>

> [!TIP]
> <span data-ttu-id="65836-195">Teams 目前每個團隊有 200 個頻道的限制。</span><span class="sxs-lookup"><span data-stu-id="65836-195">Teams currently has a 200-channel limit per team.</span></span> <span data-ttu-id="65836-196">如果您的頻道清單正接近該限制，請找出將其分割成兩個個別團隊的方法。</span><span class="sxs-lookup"><span data-stu-id="65836-196">If your list of channels is getting close to that limit, you should figure out a way to split them into two separate teams.</span></span>

### <a name="channel-history"></a><span data-ttu-id="65836-197">頻道歷程記錄</span><span class="sxs-lookup"><span data-stu-id="65836-197">Channel History</span></span>

<span data-ttu-id="65836-198">您可以根據貴組織保留公用和私人通道歷程記錄的需求，使用 GitHub 的免費解決方案和付費方案。</span><span class="sxs-lookup"><span data-stu-id="65836-198">There are both free solutions on GitHub and paid solutions you can use, depending on your organization’s requirements to retain Channel History of Public and Private channels.</span></span> <span data-ttu-id="65836-199">此外，也可將其執行指令為 Teams。</span><span class="sxs-lookup"><span data-stu-id="65836-199">Additionally, this could be scripted into Teams.</span></span>

<span data-ttu-id="65836-200">一旦在 Teams 中設定好新的團隊和頻道結構，您可以將匯出的檔案複製到 Teams 頻道中適當的文件庫。</span><span class="sxs-lookup"><span data-stu-id="65836-200">Once you’ve set up your new team and channel structure in Teams, you can copy the exported files into the appropriate document libraries in your Teams channels.</span></span>

<span data-ttu-id="65836-201">若要自動匯入您的內容，有幾種可以考慮的方法。</span><span class="sxs-lookup"><span data-stu-id="65836-201">To automate the importing of your content, there are several approaches you can consider.</span></span> <span data-ttu-id="65836-202">GitHub 上的免費解決方案 ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) 或 [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) 和合作夥伴解決方案。</span><span class="sxs-lookup"><span data-stu-id="65836-202">There are  free solutions on GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) or [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) and partner solutions.</span></span> <span data-ttu-id="65836-203">根據您組織的需求選擇解決方案。</span><span class="sxs-lookup"><span data-stu-id="65836-203">Choose a solution based on your organization’s needs.</span></span> 

### <a name="channel-files"></a><span data-ttu-id="65836-204">頻道檔案</span><span class="sxs-lookup"><span data-stu-id="65836-204">Channel Files</span></span>

<span data-ttu-id="65836-205">大部分解決方案都會匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="65836-205">Most solutions will export files.</span></span> <span data-ttu-id="65836-206">然而它們通常都以 [頻道歷程記錄] 中連結的方式提供，需要 API 金鑰才能以程式設計的方式擷取。</span><span class="sxs-lookup"><span data-stu-id="65836-206">However, they’re typically provided as links in the Channel History that require an API key to programmatically retrieve.</span></span>

<span data-ttu-id="65836-207">針對儲存在 Slack 中的檔案，一旦您設定好 Teams 中的團隊和頻道，可以以程式設計的方式由 Slack 將其複製到目標的 Teams 頻道。</span><span class="sxs-lookup"><span data-stu-id="65836-207">For files stored in Slack, once you’ve set up your teams and channels in Teams, you can programmatically copy them from Slack into the target Teams channel.</span></span>

<span data-ttu-id="65836-208">以下指令碼從 Slack 擷取檔案。</span><span class="sxs-lookup"><span data-stu-id="65836-208">The following script retrieves files from Slack.</span></span> <span data-ttu-id="65836-209">它會在您的電腦上搜尋特定的 Slack 匯出，在每個目標頻道中建立資料夾，並將所有檔案下載到該位置。</span><span class="sxs-lookup"><span data-stu-id="65836-209">It searches the specified Slack export on your computer, creates a folder in each target channel, and downloads all of the files to that location.</span></span> <span data-ttu-id="65836-210">現有協力廠商解決方案可以解壓縮資料。</span><span class="sxs-lookup"><span data-stu-id="65836-210">Third-party solutions exist that can extract data.</span></span> <span data-ttu-id="65836-211">如果您需要 PowerShell 的說明，請參閱[開始使用 Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps)。</span><span class="sxs-lookup"><span data-stu-id="65836-211">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>



```azurepowershell
$ExportPath = ".\slackHistory"
$ExportContents = Get-ChildItem -path $ExportPath -Recurse
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class File {
    [string] $Name
    [string] $Title
    [string] $Channel
    [string] $DownloadURL
    [string] $MimeType
    [double] $Size
    [string] $ParentPath
    [string] $Time
}

$channelList = Get-Content -Raw -Path .\slackHistory\channels.json | ConvertFrom-Json
$Files = New-Object -TypeName System.Collections.ObjectModel.Collection["File"]

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting Step 1 (processing channel export for files) of 2. Total Channel Count: $($channelList.Count)"
#Iterate through each Channel listed in the Archive
foreach ($channel in $channelList) {
    #Iterate through Channel folders from the Export
    foreach ($folder in $ExportContents)
    {
        #If Channel Name matches..
        if ($channel.name -eq $folder){
            $channelJsons = Get-ChildItem -Path $folder.FullName -File
            Write-Host -ForegroundColor White "$(Get-TimeStamp) Info: Starting to process $($channelJsons.Count) days of content for #$($channel.name)."
            #Start processing the daily JSON for files
            foreach ($json in $channelJsons){
                $currentJson = Get-Content -Raw -Path $json.FullName | ConvertFrom-Json
                #Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Info: Processing $($json.Name) in #$($channel.name).."
                #Iterate through every action
                foreach ($entry in $currentJson){
                    #If the action contained file(s)..
                    if($null -ne $entry.files){
                        #Iterate through each file and add it to the List of Files to download
                        foreach ($item in $entry.Files) {
                        $file = New-Object -TypeName File
                            if ($null -ne $item.url_private_download){
                                $file.Name = $item.name
                                $file.Title = $item.Title
                                $file.Channel = $channel.name
                                $file.DownloadURL = $item.url_private_download
                                $file.MimeType = $item.mimetype
                                $file.Size = $item.size
                                $file.ParentPath = $folder.FullName
                                $file.Time = $item.created
                                $files.Add($file)
                            }
                        }
                    }
                }
            }
        }
    }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 1 of 2 complete. `n"

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting step 2 (creating folders and downloading files) of 2."
#Determine which Files folders need to be created
$FoldersToMake = New-Object System.Collections.ObjectModel.Collection["string"]
foreach ($file in $files){
    if ($FoldersToMake -notcontains $file.Channel){
        $FoldersToMake.Add($file.Channel)
    }
}

#Create Folders
foreach ($folder in $FoldersToMake){
    #$fullFolderPath = $file.ParentPath + "\Files"
    $fullFolderPath = $ExportPath +"\$($folder)"
    $fullFilesPath = $ExportPath +"\$($folder)\Files"
    if (-not (Test-Path $fullFilesPath)){
        New-Item -Path $fullFolderPath  -Name "Files" -ItemType "directory"
    }
}

#Downloading Files
foreach ($file in $files)
{
    Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Downloading $($file.Name)."
    $fullFilePath = $file.ParentPath + "\Files\" + $file.Name
        if (-not (Test-Path $fullFilePath)){
            try{
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
        else {
            try{
                $extensionPosition = $file.name.LastIndexOf('.')
                $splitFileName = $file.name.Substring(0,$extensionPosition)
                $splitFileExtention = $file.name.Substring($extensionPosition)
                $newFileName = $splitFileName + $file.Time + $splitFileExtention
                $fullFilePath = $file.ParentPath + "\Files\" + $newFileName
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 2 of 2 complete. `n"
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Exiting.."
```


### <a name="apps-and-custom-integrations"></a><span data-ttu-id="65836-212">應用程式和自訂整合</span><span class="sxs-lookup"><span data-stu-id="65836-212">Apps and Custom Integrations</span></span>
<span data-ttu-id="65836-213">檢視您的 Slack 應用程式和自訂整合清單 (含設定)，並決定要將哪些移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="65836-213">Review your list of Slack apps and custom integrations (with configurations) and decide which ones you want to move to Teams.</span></span> <span data-ttu-id="65836-214">檢查 Teams Marketplace 以查看是否有可用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="65836-214">Check the Teams Marketplace to see if an app is available.</span></span> <span data-ttu-id="65836-215">如果沒有，可能會有替代方案。</span><span class="sxs-lookup"><span data-stu-id="65836-215">If not, there are likely alternatives.</span></span> 

<span data-ttu-id="65836-216">若要判斷要新增至 Teams 的應用程式，請務必了解應用程式的使用方式。</span><span class="sxs-lookup"><span data-stu-id="65836-216">To figure out which apps to add to Teams, it’s important to understand how the app is being used.</span></span> <span data-ttu-id="65836-217">透過詢問「應用程式提供給此頻道的功能為何？」，將會了解該應用程式所傳遞的成果。</span><span class="sxs-lookup"><span data-stu-id="65836-217">By asking the question "what functionality is the app providing to this channel?", you'll learn about the outcome the app is delivering.</span></span> 

<span data-ttu-id="65836-218">在許多情況下，應用程式主要由外部服務接收事件驅動的資料 (如監視系統)，並將訊息推入 Slack。</span><span class="sxs-lookup"><span data-stu-id="65836-218">In many cases, apps primarily receive event-driven data from an external service (for example, monitoring system) and push a message into Slack.</span></span> <span data-ttu-id="65836-219">您可以使用 Microsoft 365 連接器來取得相同的結果，同樣可以根據根據事件將訊息推入 Slack。</span><span class="sxs-lookup"><span data-stu-id="65836-219">You can achieve the same outcome by using a Microsoft 365 Connector that can push messages into Teams based on events.</span></span>

<span data-ttu-id="65836-220">以下是 Teams 中使用 Microsoft 365 連接器整合的 Slack 解決方案範例。</span><span class="sxs-lookup"><span data-stu-id="65836-220">Below are examples of Slack solutions where a Microsoft 365 Connector was used in Teams for integration.</span></span>
- <span data-ttu-id="65836-221">Ansible</span><span class="sxs-lookup"><span data-stu-id="65836-221">Ansible</span></span>
  - <span data-ttu-id="65836-222">可透過 [Ansible webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook) 將警示傳送到 Teams</span><span class="sxs-lookup"><span data-stu-id="65836-222">Alerts can be sent to Teams via [Ansible webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span></span>
- <span data-ttu-id="65836-223">New Relic</span><span class="sxs-lookup"><span data-stu-id="65836-223">New Relic</span></span>
  - <span data-ttu-id="65836-224">查看[傳送 New Relic 警示到 Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3) 的使用者解決方案</span><span class="sxs-lookup"><span data-stu-id="65836-224">Check out this user solution for [sending New Relic alerts to Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span></span>
- <span data-ttu-id="65836-225">Nagios</span><span class="sxs-lookup"><span data-stu-id="65836-225">Nagios</span></span>
  - <span data-ttu-id="65836-226">可透過 [連接器] 立即整合警示。</span><span class="sxs-lookup"><span data-stu-id="65836-226">Alerts can be integrated today via Connectors.</span></span> <span data-ttu-id="65836-227">https://github.com/isaac-galvan/nagios-teams-notify</span><span class="sxs-lookup"><span data-stu-id="65836-227">https://github.com/isaac-galvan/nagios-teams-notify</span></span>
- <span data-ttu-id="65836-228">Zendesk</span><span class="sxs-lookup"><span data-stu-id="65836-228">ZenDesk</span></span>
  - <span data-ttu-id="65836-229">可在 Teams Store 找到應用程式</span><span class="sxs-lookup"><span data-stu-id="65836-229">App exists in Teams Store</span></span>
- <span data-ttu-id="65836-230">Jenkins</span><span class="sxs-lookup"><span data-stu-id="65836-230">Jenkins</span></span>
  - <span data-ttu-id="65836-231">可使用 [Jenkins’s Office 365 連接器](https://plugins.jenkins.io/Office-365-Connector)傳送警示到 Teams</span><span class="sxs-lookup"><span data-stu-id="65836-231">Alerts can be sent to Teams using [Jenkins’s Office 365 Connector](https://plugins.jenkins.io/Office-365-Connector)</span></span>


### <a name="user-readiness-and-adoption-plan"></a><span data-ttu-id="65836-232">使用者整備和採用方案</span><span class="sxs-lookup"><span data-stu-id="65836-232">User readiness and adoption plan</span></span>
<span data-ttu-id="65836-233">任何成功的軟體部署基石，取決於使用者為變更所做的準備。</span><span class="sxs-lookup"><span data-stu-id="65836-233">The cornerstone of any successful software deployment hinges on how prepared users are for the change.</span></span> <span data-ttu-id="65836-234">貴組織中使用 Slack 的使用者可輕鬆了解 Teams 概念，但仍需要訓練以協助他們平順的轉換。</span><span class="sxs-lookup"><span data-stu-id="65836-234">Users in your organization using Slack will easily understand Teams concepts, but training is still needed to help them make a smooth transition.</span></span> <span data-ttu-id="65836-235">如需全方位的 Teams 採用資源集合，請移至 [Teams 採用adoption 中心](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="65836-235">For a comprehensive set of Teams adoption resources, go to the [Teams adoption hub](adopt-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="65836-236">例如，兩者都是產品功能頻道，但在每個產品中都以不同方式使用。</span><span class="sxs-lookup"><span data-stu-id="65836-236">For example, both products feature channels, but they’re used differently in each product.</span></span> <span data-ttu-id="65836-237">例如，Slack 頻道通常像在 Teams 中的聊天一樣，用於短期的交易式交談。</span><span class="sxs-lookup"><span data-stu-id="65836-237">For example, often a Channel in Slack is used like a chat in Teams for short-term, transactional conversations.</span></span> <span data-ttu-id="65836-238">其他明顯的差異則在於往來/非往來談，和調整通知設定。</span><span class="sxs-lookup"><span data-stu-id="65836-238">Other notable differences are around threaded/non-threaded conversations and tuning notification settings.</span></span>

<span data-ttu-id="65836-239">查看我們豐富的[使用者 Teams 視訊訓練](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)文件庫。</span><span class="sxs-lookup"><span data-stu-id="65836-239">Check out our rich library of [End-user Teams video training](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7).</span></span> 

## <a name="move-to-teams"></a><span data-ttu-id="65836-240">移轉至 Teams</span><span class="sxs-lookup"><span data-stu-id="65836-240">Move to Teams</span></span> 
<span data-ttu-id="65836-241">既然已定義好您的轉換計畫，您可以開始建立 Teams 中的團隊和頻道。</span><span class="sxs-lookup"><span data-stu-id="65836-241">Now that your transition plan is defined, you can begin creating your teams and channels in Teams.</span></span> 

<span data-ttu-id="65836-242">一旦建立好團隊和頻道之後，開始將檔案從 Slack 頻道複製到 Teams，並設定您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="65836-242">Once you’ve created your teams & channels, begin copying files from Slack channels into Teams and configuring your apps.</span></span> <span data-ttu-id="65836-243">如果您使用解決方案來保留歷程記錄，也可以立即設定。</span><span class="sxs-lookup"><span data-stu-id="65836-243">If you’re using a solution to retain history, that can be configured now as well.</span></span> <span data-ttu-id="65836-244">然後您可以開始授權使用者 (如果他們尚未取得授權)，並將他們新增至適當的團隊。</span><span class="sxs-lookup"><span data-stu-id="65836-244">Then you’re ready to start licensing users (if they aren’t licensed already) and adding them to the appropriate teams.</span></span> <span data-ttu-id="65836-245">若要減少額外匯出和檔案複製的需求，請考慮在每個使用者加入團隊同時的商定日期移除 Slack 存取權。</span><span class="sxs-lookup"><span data-stu-id="65836-245">To reduce the need for additional exports and file copies, consider removing Slack access at an agreed-upon date that coincides with each user’s addition to the team.</span></span> <span data-ttu-id="65836-246">這樣就可避免檔案和歷程記錄上之重新匯出和匯入的差異變更。</span><span class="sxs-lookup"><span data-stu-id="65836-246">This avoids needing to re-export and import delta changes on files and history.</span></span>

<span data-ttu-id="65836-247">按照下列圖表中的步驟在貴組織中推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="65836-247">Follow the steps in the diagram below to roll out Teams in your organization.</span></span> <span data-ttu-id="65836-248">如需詳細資訊，請參閱[如何推出 Teams](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="65836-248">For more information, check out [How to roll out Teams](How-to-roll-out-teams.md).</span></span>


:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="圖表列出了從 Slack 移至 Teams 的步驟。":::
