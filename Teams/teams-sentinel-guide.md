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
ms.openlocfilehash: 1075a2c345bd866266b175a4b62432e9f819b330
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598522"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="1c6c3-103">Azure Sentinel 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c6c3-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c6c3-104">Azure Sentinel 現在具有整合式連接器。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="1c6c3-105">如需詳細資訊，請參閱[將 Office 365 記錄連線至 Azure Sentinel](/azure/sentinel/connect-office-365)。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="1c6c3-106">這是收集這些記錄的建議路由，並取代下列所述的收集方法。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="1c6c3-107">Teams 可在 Microsoft 365 雲端的通訊和資料共用中扮演中心角色。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-107">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="1c6c3-108">由於 Teams 服務涉及雲端中的許多基礎技術，因此在 *搜尋記錄* 和 *即時監控會議* 時，都可以從人工和自動化分析中受益。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-108">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="1c6c3-109">Azure Sentinel 提供系統管理員以下解決方案。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-109">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="1c6c3-110">需要回顧 Azure Sentinel 的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="1c6c3-110">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="1c6c3-111">[這篇文章](/azure/sentinel/overview)就是您需要的。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-111">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="1c6c3-112">Azure Sentinel 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c6c3-112">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="1c6c3-113">本文主要說明如何在 Azure Sentinel 中收集 Teams 活動記錄。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-113">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="1c6c3-114">除了允許系統管理員將安全性管理放在單一窗格 (包括任何已選取的協力廠商裝置、Microsoft 威脅防護及其他 Microsoft 365 工作負載) 之下，Sentinel Workbook 和 Runbook 都能進行系統化的安全性監視。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-114">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="1c6c3-115">此程序的第一步是收集所需的記錄進行分析。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-115">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="1c6c3-116">可以在同一個 Azure Sentinel 執行個體顯示多個 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-116">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="1c6c3-117">這樣就可以允許[即時監視](/azure/sentinel/livestream)並在歷史記錄檔中尋找威脅。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-117">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="1c6c3-118">系統管理員將能使用位於單一資源群組中的[跨資源查詢](/azure/azure-monitor/log-query/cross-workspace-query)、跨資源群組或在其他訂閱中使用搜尋。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-118">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="1c6c3-119">步驟 1：收集 Teams 記錄</span><span class="sxs-lookup"><span data-stu-id="1c6c3-119">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="1c6c3-120">本節包含三個部分：</span><span class="sxs-lookup"><span data-stu-id="1c6c3-120">This section has three parts:</span></span>

1. <span data-ttu-id="1c6c3-121">在 **Microsoft 365** 中啟用稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-121">Enabling Audit Logs in **Microsoft 365**.</span></span>
2. <span data-ttu-id="1c6c3-122">在 **Microsoft Azure** 中註冊應用程式，以允許記錄收集的驗證和授權。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-122">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="1c6c3-123">註冊 API 訂閱，這將允許 **PowerShell**，透過 Microsoft 365 API 收集記錄。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-123">Registering the API subscription that will allow log collection via Microsoft 365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="1c6c3-124">在 Microsoft 365 中啟用稽核記錄</span><span class="sxs-lookup"><span data-stu-id="1c6c3-124">Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="1c6c3-125">因為 Teams 會透過 Microsoft 365 記錄活動，因此預設不會收集稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-125">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="1c6c3-126">透過[以下步驟](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0)開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-126">Turn on this feature via [these steps](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span></span> <span data-ttu-id="1c6c3-127">Teams 資料會在 Microsoft 365 稽核中的 *[Audit.General]* 下進行收集。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-127">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="1c6c3-128">在 Microsoft Azure 中註冊應用程式以收集記錄</span><span class="sxs-lookup"><span data-stu-id="1c6c3-128">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="1c6c3-129">開始之前，您必須記錄 **應用程式識別碼/用戶端識別碼** 和您的 **租用戶識別碼**，以便日後使用。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-129">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="1c6c3-130">當您進行以下的應用程式註冊步驟時，請務必記下這些資訊。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-130">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="1c6c3-131">您會看到這兩個識別碼。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-131">You will see both IDs.</span></span>
>- <span data-ttu-id="1c6c3-132">應用程式建立之後，請按一下 [快速啟動] 側邊列上的 [應用程式註冊] > 尋找新應用程式的顯示名稱 > 複製應用程式 (用戶端) 識別碼。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-132">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="1c6c3-133">按一下 [快速啟動] 側邊列上的 [概觀]，> 複製目錄 (租用戶) 識別碼。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-133">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="1c6c3-134">驗證並授權 Azure Active Directory (Azure AD) 應用程式，以從 API 收集記錄資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-134">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="1c6c3-135">瀏覽至 Azure 入口網站中 *[Azure AD]* 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-135">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="1c6c3-136">在 [快速啟動] 側邊列中，按一下 *[應用程式註冊]*。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-136">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="1c6c3-137">選取 *[新增註冊]*。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-137">Select *New registration*.</span></span>
4. <span data-ttu-id="1c6c3-138">為您的 Teams 記錄收集應用程式命名，然後按一下 *[註冊]*。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-138">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="1c6c3-139">依以下路徑按一下：*[API 權限]* > *[新增權限]* > *[Office 365 管理 API]* > *[應用程式權限]*。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-139">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="1c6c3-140">展開 [活動] 摘要，然後查看 *[ActivityFeed.Read]*。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-140">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="1c6c3-141">在這裡選擇 *[授與系統管理同意]*。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-141">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="1c6c3-142">出現提示時，請按一下 [是]。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-142">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="1c6c3-143">按一下側邊列中的 *[憑證和密碼]* > *[新增用戶端密碼]* 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-143">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="1c6c3-144">在 [新增用戶端密碼] 視窗中，輸入新用戶端密碼的描述、確認在 [到期日] 中選擇 [永不]，然後按一下 *[新增]*。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-144">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c6c3-145">請 **「務必」** 將新的用戶端密碼複製到位於新建立應用程式之名稱下的密碼管理器項目。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-145">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="1c6c3-146">關閉 Azure 刀鋒視窗 (*「刀鋒視窗」* 是 Azure 用來表示視窗的詞彙) 之後，您將無法返回查看此密碼。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-146">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="1c6c3-147">使用 PowerShell 註冊 API 來收集 Teams 記錄</span><span class="sxs-lookup"><span data-stu-id="1c6c3-147">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="1c6c3-148">設定的最後一個步驟是收集並註冊 API 訂閱，以便收集記錄資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-148">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="1c6c3-149">這會透過 PowerShell REST 呼叫 Microsoft 365 管理活動 API 來完成。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-149">This is done via PowerShell REST calls to the Microsoft 365 Management Activity API.</span></span>

<span data-ttu-id="1c6c3-150">請在以下 PowerShell Cmdlet 中準備好提供 **[應用程式 (用戶端) 識別碼]**、新的 **[用戶端密碼]**、**[M365 的 URL 網域]** 和 **[目錄 (租用戶) 識別碼]** 的值。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-150">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

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

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="1c6c3-151">步驟 2：部署 Sentinel Playbook 以擷取 Teams 記錄</span><span class="sxs-lookup"><span data-stu-id="1c6c3-151">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="1c6c3-152">Azure Sentinel Playbooks (又稱為邏輯應用程式) 將允許 Azure 擷取您收集的 Teams 資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-152">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="1c6c3-153">邏輯應用程式會查詢 Office 365，以找出其寫入 Azure Sentinel 工作區的稽核資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-153">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="1c6c3-154">使用[這個](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM 範本來部署您的 Sentinel Playbook。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-154">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="1c6c3-155">注意事項：</span><span class="sxs-lookup"><span data-stu-id="1c6c3-155">Things to remember:</span></span>

1. <span data-ttu-id="1c6c3-156">您需要逐步瀏覽 ARM 範本，並將某些值取代為適合您自己環境的值。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-156">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="1c6c3-157">記錄擷取與在 Azure Sentinel 查看結果的中間，需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-157">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="1c6c3-158">請等待 5 到 10 分鐘，並留意如果 5 分鐘之後沒有資料顯示，您會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-158">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="1c6c3-159">檢查稽核記錄，並請留意，因為 Teams 資訊位於 Audit.General 事件中，其會收集多個 Teams 記錄，所以結果會在 5 到 10 分鐘內於使用的系統中顯示。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-159">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="1c6c3-160">如果使用文字環境，請務必使用 Teams 來產生記錄。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-160">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![顯示邏輯應用程式類別的圖形。](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="1c6c3-162">圖形中的動作說明：</span><span class="sxs-lookup"><span data-stu-id="1c6c3-162">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="1c6c3-163">• [週期] 是邏輯應用程式觸發器，可告知工作流程每小時執行一次。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-163">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="1c6c3-164">• [目前時間] 是相當基本動作，只是用來取得目前時間。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-164">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="1c6c3-165">• [初始化變數] 會建立稱為 NextPage 的變數，並將它設定為 1。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-165">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="1c6c3-166">稍後會使用此動作來處理 O365 API 的分頁。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-166">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="1c6c3-167">• [初始化變數 2] 會建立稱為 Start Time 的空白變數。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-167">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="1c6c3-168">•[執行查詢] 和 [清單結果] 是 Azure 監視器動作，會針對從邏輯應用程式輸入的最後一個 O365 記錄查詢工作區。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-168">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="1c6c3-169">•[條件 4] 用於檢查 [執行查詢] 和 [清單結果] 查詢是否傳回任何資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-169">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="1c6c3-170">這是為了檢查這個邏輯應用程式是否第一次使用。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-170">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="1c6c3-171">如果沒有傳回資料，StartTime 變數會設定為 [現在 – 24 小時]。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-171">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="1c6c3-172">如果傳回資料，StartTime 會設定為最後一筆記錄 TimeGenerated。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-172">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="1c6c3-173">如此一來，查詢可以從 O365 API 的輪詢中的最後一個項目獲得到現在為止的資料；如果是第一次執行，則可以獲得最近 24 小時的資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-173">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="1c6c3-174">• [初始化變數 3] 會建立稱為 AvailableUri 的變數。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-174">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="1c6c3-175">這是一個字串，其中 URL 分別使用 StartTime 和 CurrentTime 做為開始和結束時間來建立。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-175">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="1c6c3-176">• [Until 條件] 是一個迴圈，可讓邏輯應用程式持續輪詢 API，查看是否有更多的資料 (分頁)。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-176">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="1c6c3-177">只要 NextPage 變數是1，迴圈就會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-177">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="1c6c3-178">之後，如果沒有更多頁面可供擷取，將會更新此變數。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-178">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="1c6c3-179">•在 Until 迴圈內，第一個 HTTP 步驟會連線至 AvailableURI。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-179">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="1c6c3-180">這個 URI 會傳回可用內容清單和每個內容的 URI。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-180">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="1c6c3-181">您可以在以下 URL 深入了解運作方式：https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-181">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="1c6c3-182">• 接下來會執行檢查，以確保資料傳回。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-182">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="1c6c3-183">Condition 會檢查內文長度是否為 0。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-183">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="1c6c3-184">如果為 0，表示沒有要寫入記錄分析的資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-184">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="1c6c3-185">如果值大於 0，表示有要處理的資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-185">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="1c6c3-186">• 如果偵測到資料，必須緊接著處理。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-186">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="1c6c3-187">剖析 JSON 會定義傳回資料的結構描述。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-187">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="1c6c3-188">這可讓邏輯應用程式在後續步驟中使用經過剖析的資料做為動態內容。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-188">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="1c6c3-189">• 由於傳回的可用資料清單是陣列，因此會使用 For Each 動作迴圈可用內容清單。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-189">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="1c6c3-190">• 下一步是抓取內容。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-190">• Next is grabbing the content.</span></span>  <span data-ttu-id="1c6c3-191">會再次使用 HTTP 來取得 contentUri (由剖析 JSON 建立的動態屬性)，這是要檢索之資料的 URL。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-191">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="1c6c3-192">• 剖析 JSON 也用來剖析傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-192">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="1c6c3-193">您可以在以下 URL 找到一些範例內容：https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-193">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="1c6c3-194">• 傳回的資料也是陣列。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-194">• The data returned is also an array.</span></span> <span data-ttu-id="1c6c3-195">您也可以在這裡使用 For Each 迴圈。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-195">A For Each loop can be used here as well.</span></span> <span data-ttu-id="1c6c3-196">在這個迴圈中，工作流程會取得目前的資料項目，並使用 [傳送資料] 動作，將資料寫入記錄分析。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-196">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="1c6c3-197">• 因為可能有多個可用內容頁面，所以條件會檢查 NextPageUri 是否不為 Null。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-197">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="1c6c3-198">如果為 Null 或空白，NextPage 會設為 0，這會結束 Until 迴圈。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-198">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="1c6c3-199">如果它包含 URL，AvaibleUri 變數會更新為該 URL。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-199">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="1c6c3-200">如此一來，Until 迴圈的下次執行會使用下一個可用的 URL，而不是使用起始 URL。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-200">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="1c6c3-201">您可以選擇使用 *[Azure 函數]* 來擷取這些記錄，而如果您要這麼做，請依您的喜好而定，參閱 [這裡](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)或 [這裡](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp)的部署資訊。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-201">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="1c6c3-202">若執行連接器 (無論您在上方選取哪個選項)，您應該會在 Azure Sentinel 工作區中看到一個名為 O365API_CL 的自訂資料表。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-202">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="1c6c3-203">這裡會存放您的 Teams記錄。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-203">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="1c6c3-204">步驟 3：使用 Sentinel 來監視 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c6c3-204">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="1c6c3-205">對 Microsoft Teams 來說，身分識別是一個必須要監控的重要攻擊媒介。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-205">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="1c6c3-206">由於 Azure Active Directory (Azure AD) 是 Microsoft 365 目錄的基礎 (包括 Teams)，因此收集和搜尋 Azure 記錄中有關驗證的威脅將有助捕獲跟身分識別有關的可疑行為。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-206">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="1c6c3-207">您可以使用內建連接器將 Azure AD 資料拉入 Azure Sentinel，並使用這些[偵測](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs)和[搜尋](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs)查詢來尋找問題。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-207">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="1c6c3-208">針對 Microsoft Teams 的特定攻擊 (例如，資料的威脅)，Azure Sentinel 也可讓您監視這些資料威脅並進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-208">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="1c6c3-209">為資料建立剖析程式</span><span class="sxs-lookup"><span data-stu-id="1c6c3-209">Create a parser for your data</span></span>

<span data-ttu-id="1c6c3-210">為了了解大量收集的資料，要做的第一件事是透過資料剖析使其具有意義。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-210">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="1c6c3-211">會使用 Kusto查詢語言 (KQL) 函數來完成資料剖析，該函數可讓資料更易於使用。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-211">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="1c6c3-212">KQL 函數是 KQL 查詢，但儲存為稱為「函數」的資料類型。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-212">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="1c6c3-213">可在 Sentinel 中的查詢方塊輸入 KQL 函數的別名，以便再次快速執行查詢。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-213">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="1c6c3-214">如需 KQL 函數以及如何建置剖析器函數的詳細資訊，請參閱[此技術社群文章](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-214">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="1c6c3-215">以下剖析器是可自訂的範例，目的在選取與 *[Teams]* 相關的 Office 365 管理 API 欄位的子集。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-215">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="1c6c3-216">還有一個建議剖析器 [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)，但以下的剖析器可供修改，以符合不同的需求和喜好設定。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-216">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

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
 <span data-ttu-id="1c6c3-217">將剖析器儲存為 KQL 函數，其別名為 TeamsData。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-217">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="1c6c3-218">它將用於後續查詢。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-218">It will be used for the queries to follow.</span></span> <span data-ttu-id="1c6c3-219">如需有關如何設定及使用 KQL 函數作為剖析器的詳細資訊，請參閱本[技術社群文章](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-219">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="1c6c3-220">實用的搜捕 KQL 查詢</span><span class="sxs-lookup"><span data-stu-id="1c6c3-220">Helpful hunting KQL queries</span></span>

<span data-ttu-id="1c6c3-221">您可以使用這些查詢來熟悉您的 Teams 資料和 Teams 環境。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-221">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="1c6c3-222">了解環境的外觀與運作方式是辨識可疑活動的最佳開端。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-222">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="1c6c3-223">您可以在那裡擴展到威脅搜尋。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-223">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="1c6c3-224">同盟外部使用者查詢</span><span class="sxs-lookup"><span data-stu-id="1c6c3-224">Federated external users query</span></span>

<span data-ttu-id="1c6c3-225">取得擁有同盟外部使用者的 Teams 網站清單。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-225">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="1c6c3-226">這些使用者將會有一個網域名稱/UPN 尾碼，這個尾碼 *「並非」* 貴組織所有。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-226">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="1c6c3-227">在此範例查詢中，組織擁有 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-227">In this example query, the organization owns contoso.com.</span></span>

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
> <span data-ttu-id="1c6c3-228">若要深入了解 Teams 中的外部和來賓存取類型，請參閱 [本文](./communicate-with-users-from-other-organizations.md)，或 [Teams 安全性指南](./teams-security-guide.md)中的 *參與者類型* 一節。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-228">To learn more about External and Guest access types in Teams see [this article](./communicate-with-users-from-other-organizations.md), or the *Participant Types* section in the [Teams Security Guide](./teams-security-guide.md).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="1c6c3-229">最近加入/角色變更的人員</span><span class="sxs-lookup"><span data-stu-id="1c6c3-229">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="1c6c3-230">查詢特定使用者以檢查它們是否是過去 7 天內或一周內新增至 Teams 頻道：</span><span class="sxs-lookup"><span data-stu-id="1c6c3-230">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="1c6c3-231">過去 7 天內，團隊的使用者角色是否已變更：</span><span class="sxs-lookup"><span data-stu-id="1c6c3-231">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="1c6c3-232">來自未知或新組織的外部使用者</span><span class="sxs-lookup"><span data-stu-id="1c6c3-232">External users from unknown or new organizations</span></span>

<span data-ttu-id="1c6c3-233">在 Teams 中，您可以將外部使用者新增至您的環境或頻道。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-233">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="1c6c3-234">組織通常具有數量有限的關鍵合作夥伴，並會從這些合作夥伴中新增使用者。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-234">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="1c6c3-235">此 KQL 會查看新增到團隊的外部使用者，這些使用者來自從未見過或未新增過的組織。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-235">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

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

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="1c6c3-236">過去新增然後移除的外部使用者</span><span class="sxs-lookup"><span data-stu-id="1c6c3-236">External users who were added and then removed</span></span>

<span data-ttu-id="1c6c3-237">具有某種現有存取權層級的攻擊者可能會將一個新的外部帳戶新增到 Teams 以存取和竊取資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-237">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="1c6c3-238">他們也可以快速移除該使用者，以隱藏他們所進行的存取。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-238">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="1c6c3-239">此查詢會搜尋新增到 Teams 中並迅速刪除的外部帳戶，以幫助識別可疑行為。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-239">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

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

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="1c6c3-240">新增 Bot 或應用程式</span><span class="sxs-lookup"><span data-stu-id="1c6c3-240">New bot or application added</span></span>

<span data-ttu-id="1c6c3-241">Teams 可以將應用程式或 Bot 納入團隊中，以擴充功能集。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-241">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="1c6c3-242">其中包括自訂應用程式和 Bot。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-242">This includes custom apps and bots.</span></span> <span data-ttu-id="1c6c3-243">在某些情況下，您可以使用應用程式或 Bot 在 Teams 中建立持續性，不需要使用者帳戶，以及存取檔案和其他資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-243">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="1c6c3-244">這個查詢會搜尋新增至 Teams 的應用程式或 Bot。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-244">This query hunts for apps or bots that are new to Teams.</span></span>

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

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="1c6c3-245">擁有大量 Teams 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="1c6c3-245">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="1c6c3-246">當使用者通常圍繞特定主題建立和擁有少量團隊時，希望提升其權限的攻擊者可能會指派給自己大量不同團隊的擁有者權限。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-246">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="1c6c3-247">此 KQL 查詢會尋找可疑行為。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-247">This KQL query looks for suspicious behavior.</span></span>

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

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="1c6c3-248">許多團隊遭單一使用者刪除</span><span class="sxs-lookup"><span data-stu-id="1c6c3-248">Many Team deletions by a single user</span></span>

<span data-ttu-id="1c6c3-249">攻擊者可刪除多個團隊，進而造成中斷並危害專案和資料。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-249">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="1c6c3-250">由於團隊通常是由個別擁有者來刪除，多個團隊被集中刪除可能會是問題的徵兆。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-250">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="1c6c3-251">此 KQL 會尋找刪除多個團隊的使用者。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-251">This KQL looks for single users who delete multiple teams.</span></span>

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

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="1c6c3-252">擴大您的執行緒搜尋機會</span><span class="sxs-lookup"><span data-stu-id="1c6c3-252">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="1c6c3-253">您可以結合 Azure Active Directory (Azure AD) 等資源的查詢，或將其他 Office 365 工作負載與您的 Teams 查詢集合，來擴大您的搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-253">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="1c6c3-254">其中一個範例是結合 Azure AD SigninLogs 中的可疑模式偵測，並在搜尋團隊擁有者時使用該資訊。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-254">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

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

<span data-ttu-id="1c6c3-255">另外，您可以使用以下方法為僅針對基於 Teams 的登入新增篩選器，進而對 Teams 進行 SigninLogs 偵測：</span><span class="sxs-lookup"><span data-stu-id="1c6c3-255">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="1c6c3-256">為了有助於進一步解釋如何使用 `where AppDisplayName starts with "Microsoft Teams"`，下面的 KQL 示範從一個 IP 位址成功登入而從另一個 IP 位址卻失敗的情況，但僅限於 Teams 登入：</span><span class="sxs-lookup"><span data-stu-id="1c6c3-256">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

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

## <a name="important-information-and-updates"></a><span data-ttu-id="1c6c3-257">重要資訊和最新消息</span><span class="sxs-lookup"><span data-stu-id="1c6c3-257">Important information and updates</span></span>

<span data-ttu-id="1c6c3-258">**Pete Bryan、Nicholas DiCola 和 Matthew Lowe，感謝各位參與內容共同作業。**</span><span class="sxs-lookup"><span data-stu-id="1c6c3-258">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="1c6c3-259">Pete Bryan 及與他共同作業的人員將繼續為 Teams 開發偵測查詢和搜尋查詢，因此請與此 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 存放庫保持聯繫，以取得最新消息。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-259">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="1c6c3-260">追蹤本文所使用的[剖析器](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)和[邏輯應用程式](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)的更新。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-260">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="1c6c3-261">您也可以加入並參與 [Azure Sentinel 社群](https://github.com/Azure/Azure-Sentinel/wiki)。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-261">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="1c6c3-262">感謝您！</span><span class="sxs-lookup"><span data-stu-id="1c6c3-262">Thank you!</span></span> <span data-ttu-id="1c6c3-263">祝您搜尋開心。</span><span class="sxs-lookup"><span data-stu-id="1c6c3-263">Happy hunting.</span></span>

[<span data-ttu-id="1c6c3-264">在 Azure AD 中註冊您的應用程式</span><span class="sxs-lookup"><span data-stu-id="1c6c3-264">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="1c6c3-265">開啟或關閉稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="1c6c3-265">Turn audit log search on or off</span></span>](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0)

[<span data-ttu-id="1c6c3-266">什麼是 Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="1c6c3-266">What is Azure Sentinel</span></span>](/azure/sentinel/overview)
