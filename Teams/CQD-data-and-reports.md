---
title: '通話品質儀表板和 CQD (中的資料和) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 瞭解 Microsoft 通話品質儀表板和 CQD (中) 。
ms.openlocfilehash: 2d36787a5341db016c18a30977cb086b0b6d7afc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111539"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="2f6db-103">通話品質儀表板和 CQD (中的資料和) </span><span class="sxs-lookup"><span data-stu-id="2f6db-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="2f6db-104">Microsoft 通話品質儀表板 (CQD) 使用接近即時的 NRT (NRT) 資料來源。</span><span class="sxs-lookup"><span data-stu-id="2f6db-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="2f6db-105">通話記錄可在通話結束的 30 分鐘內在 CQD 中提供。</span><span class="sxs-lookup"><span data-stu-id="2f6db-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="2f6db-106">NRT 管道的通話記錄只能在從資料集中移除前幾個月使用。</span><span class="sxs-lookup"><span data-stu-id="2f6db-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="2f6db-107">存取 CQD 資料的多種方式</span><span class="sxs-lookup"><span data-stu-id="2f6db-107">Many ways to access CQD data</span></span>

<span data-ttu-id="2f6db-108">您可以用數種不同的方式存取 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-108">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="2f6db-109">挑選最符合您需求的產品：</span><span class="sxs-lookup"><span data-stu-id="2f6db-109">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="2f6db-110">Teams 系統管理[中心 (https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="2f6db-110">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="2f6db-111">CQD 資料會包含在Teams 系統管理中心的使用者頁面上，以易於閱讀的格式顯示您所需的最常見資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-111">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="2f6db-112">您無法自訂在 使用者 下找到的 CQD **資料**。</span><span class="sxs-lookup"><span data-stu-id="2f6db-112">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="2f6db-113">CQD[入口網站 (https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="2f6db-113">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="2f6db-114">使用深入篩選功能，提供符合大多數需求的強大的摘要和詳細報表。</span><span class="sxs-lookup"><span data-stu-id="2f6db-114">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="2f6db-115">您也可以在 CQD 入口網站中自訂報表。</span><span class="sxs-lookup"><span data-stu-id="2f6db-115">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="2f6db-116">取得 [兩個 CQD 報表範本](#import-the-cqd-report-templates) ，可協助您分析 CQD 入口網站的資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-116">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="2f6db-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="2f6db-117">Power BI</span></span>     | <span data-ttu-id="2f6db-118">使用直接查詢在 Power BI 中使用可自訂的 Power BI 範本來查看您的 [CQD 資料](CQD-Power-BI-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-118">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="2f6db-119">[下載適用于 CQD 的 Power BI 查詢範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-119">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="2f6db-120">您也可以使用 REST API 透過 Power BI [存取 CQD](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) 資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-120">You can also [use the REST API to access CQD data](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="2f6db-121">如果您想要下載 CQD 資料，以便離線處理，請使用此方法。</span><span class="sxs-lookup"><span data-stu-id="2f6db-121">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="2f6db-122">使用此方法的好處是提升性能，尤其適用于在連線時在 Power BI 中當做為問題的大型資料集。</span><span class="sxs-lookup"><span data-stu-id="2f6db-122">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="2f6db-123">Graph API</span><span class="sxs-lookup"><span data-stu-id="2f6db-123">Graph API</span></span>     | <span data-ttu-id="2f6db-124">使用 Graph API 自己存取 [通話品質資料](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-124">Access call quality data yourself using the [Graph API](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="2f6db-125">這是最複雜的方法，但能讓您在分析通話品質資料時擁有最大的控制權與彈性。</span><span class="sxs-lookup"><span data-stu-id="2f6db-125">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="2f6db-126">例如，如果您需要將其與貴組織的其他資料聯在一起，您可以使用 Graph API 建立資料模型併合並通話品質資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-126">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="2f6db-127">輸入 CQD 報表範本</span><span class="sxs-lookup"><span data-stu-id="2f6db-127">Import the CQD report templates</span></span>

<span data-ttu-id="2f6db-128">在所有網路和受管理 (下載兩個已策劃的 [CQD](https://aka.ms/qertemplates) 報表範本) 可協助您快速使用 CQD 快速上手。</span><span class="sxs-lookup"><span data-stu-id="2f6db-128">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="2f6db-129">所有網路範本雖然已優化處理建築物資料檔案，但可在您收集建築物資訊並上傳至 CQD 時使用，如下一節所述。</span><span class="sxs-lookup"><span data-stu-id="2f6db-129">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="2f6db-130">**若要將範本 (。CQDX) into CQD**</span><span class="sxs-lookup"><span data-stu-id="2f6db-130">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="2f6db-131">在 CQD 中， **從** 頁面頂端的功能表選取詳細報告。</span><span class="sxs-lookup"><span data-stu-id="2f6db-131">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="2f6db-132">在左側面板中 **，選取**</span><span class="sxs-lookup"><span data-stu-id="2f6db-132">In the left panel, select **Import**.</span></span> <span data-ttu-id="2f6db-133">流覽至第一個 CQDX 範本， **然後選取** 開啟 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-133">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="2f6db-134">範本上傳後，快顯視窗會顯示「報表成功輸入」訊息。</span><span class="sxs-lookup"><span data-stu-id="2f6db-134">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="2f6db-135">針對第二個 CQD 範本重複步驟 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="2f6db-135">Repeat steps 2 and 3 for the second CQD template.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2f6db-136">每個使用者都必須將 CQD 範本導入其 CQD 實例。</span><span class="sxs-lookup"><span data-stu-id="2f6db-136">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="2f6db-137">EUII 資料</span><span class="sxs-lookup"><span data-stu-id="2f6db-137">EUII data</span></span>

<span data-ttu-id="2f6db-138">基於合規性考慮，使用者標識資訊 (EUII) 資料 (也稱為個人識別資訊或 PII) 只會保留 28 天。</span><span class="sxs-lookup"><span data-stu-id="2f6db-138">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 28 days.</span></span> <span data-ttu-id="2f6db-139">當 NRT 資料跨過 28 天標記時，會清除包含 EUII 的欄位，產生不含 EUII 的 NRT 資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-139">As NRT data crosses the 28-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="2f6db-140">包含 EUII 資料的欄位為：</span><span class="sxs-lookup"><span data-stu-id="2f6db-140">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="2f6db-141">完整 IP 位址</span><span class="sxs-lookup"><span data-stu-id="2f6db-141">Full IP address</span></span>
- <span data-ttu-id="2f6db-142">MAC (媒體存取控制) 位址</span><span class="sxs-lookup"><span data-stu-id="2f6db-142">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="2f6db-143">基本服務組識別元 (BSSID) </span><span class="sxs-lookup"><span data-stu-id="2f6db-143">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="2f6db-144">只有商務用 Skype (SIP) URI (會話初始通訊協定) </span><span class="sxs-lookup"><span data-stu-id="2f6db-144">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="2f6db-145">使用者主體名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="2f6db-145">User Principal Name (UPN)</span></span>
- <span data-ttu-id="2f6db-146">電腦端點名稱</span><span class="sxs-lookup"><span data-stu-id="2f6db-146">Machine Endpoint Name</span></span>
- <span data-ttu-id="2f6db-147">使用者逐字記錄意見</span><span class="sxs-lookup"><span data-stu-id="2f6db-147">User Verbatim Feedback</span></span>
- <span data-ttu-id="2f6db-148">物件識別碼 (端點使用者識別碼的 Active Directory 物件識別碼) </span><span class="sxs-lookup"><span data-stu-id="2f6db-148">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="2f6db-149">具有或不含 EUII 存取的系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="2f6db-149">Admin roles with and without EUII access</span></span>

<span data-ttu-id="2f6db-150">這些 [RBAC](/azure/role-based-access-control/overview) 角色 **DO** 具有 EUII 存取權：</span><span class="sxs-lookup"><span data-stu-id="2f6db-150">These [RBAC](/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="2f6db-151">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="2f6db-151">Global Admin</span></span>
- <span data-ttu-id="2f6db-152">Teams 服務系統管理員</span><span class="sxs-lookup"><span data-stu-id="2f6db-152">Teams Service Admin</span></span>
- <span data-ttu-id="2f6db-153">Teams Communications 系統管理員</span><span class="sxs-lookup"><span data-stu-id="2f6db-153">Teams Communications Admin</span></span>
- <span data-ttu-id="2f6db-154">Teams 通訊支援工程師</span><span class="sxs-lookup"><span data-stu-id="2f6db-154">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="2f6db-155">全域閱讀程式</span><span class="sxs-lookup"><span data-stu-id="2f6db-155">Global Reader</span></span>
- <span data-ttu-id="2f6db-156">商務用 Skype 系統管理員</span><span class="sxs-lookup"><span data-stu-id="2f6db-156">Skype for Business Admin</span></span>

<span data-ttu-id="2f6db-157">這些 RBAC **角色沒有** EUII 存取權：</span><span class="sxs-lookup"><span data-stu-id="2f6db-157">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="2f6db-158">報表閱讀程式</span><span class="sxs-lookup"><span data-stu-id="2f6db-158">Reports Reader</span></span>
- <span data-ttu-id="2f6db-159">Teams Communications 支援專員</span><span class="sxs-lookup"><span data-stu-id="2f6db-159">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="2f6db-160">日期控制項</span><span class="sxs-lookup"><span data-stu-id="2f6db-160">Date controls</span></span>

<span data-ttu-id="2f6db-161">CQD 支援下列滾動趨勢類型：</span><span class="sxs-lookup"><span data-stu-id="2f6db-161">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="2f6db-162">5 天</span><span class="sxs-lookup"><span data-stu-id="2f6db-162">5-day</span></span>
- <span data-ttu-id="2f6db-163">7 天</span><span class="sxs-lookup"><span data-stu-id="2f6db-163">7-day</span></span>
- <span data-ttu-id="2f6db-164">30 天</span><span class="sxs-lookup"><span data-stu-id="2f6db-164">30-day</span></span>
- <span data-ttu-id="2f6db-165">60 天</span><span class="sxs-lookup"><span data-stu-id="2f6db-165">60-day</span></span>
- <span data-ttu-id="2f6db-166">90 天</span><span class="sxs-lookup"><span data-stu-id="2f6db-166">90-day</span></span>

<span data-ttu-id="2f6db-167">URL Date 參數接受 Day 欄位。</span><span class="sxs-lookup"><span data-stu-id="2f6db-167">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="2f6db-168">滾動日報表使用以 YYYY-MM-DD 格式指定的日期做為趨勢的最後一天。</span><span class="sxs-lookup"><span data-stu-id="2f6db-168">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="2f6db-169">URL Date 參數 "00" 表示 「今天」。</span><span class="sxs-lookup"><span data-stu-id="2f6db-169">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="2f6db-170">Url</span><span class="sxs-lookup"><span data-stu-id="2f6db-170">URL</span></span>| <span data-ttu-id="2f6db-171">捲動日趨勢的結束日期</span><span class="sxs-lookup"><span data-stu-id="2f6db-171">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="2f6db-172"><span>HTTPs:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="2f6db-172"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="2f6db-173">2019 年 2 月目前的一天</span><span class="sxs-lookup"><span data-stu-id="2f6db-173">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="2f6db-174"><span>HTTPs:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="2f6db-174"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="2f6db-175">2019 年 2 月 15 日</span><span class="sxs-lookup"><span data-stu-id="2f6db-175">Feb 15, 2019</span></span>|
|<span data-ttu-id="2f6db-176"><span>HTTPs:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="2f6db-176"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="2f6db-177">目前日</span><span class="sxs-lookup"><span data-stu-id="2f6db-177">Current Day</span></span>|
|||

<span data-ttu-id="2f6db-178">根據預設，當月中的目前天會做為捲動日趨勢的最後一天。</span><span class="sxs-lookup"><span data-stu-id="2f6db-178">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="2f6db-179">CQD 報告中提供的資料</span><span class="sxs-lookup"><span data-stu-id="2f6db-179">Data available in CQD reports</span></span>

<span data-ttu-id="2f6db-180">您只需要預設摘要和詳細的 CQD 報告，就只需要管理貴組織通話品質。如果需要，您可以建立 [自訂報表](#create-custom-detailed-reports)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-180">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="2f6db-181">如果您想要使用 Power BI 分析您的 CQD 資料，請參閱使用 [Power BI 分析 Teams 的 CQD 資料](CQD-Power-BI-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-181">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="2f6db-182">功能</span><span class="sxs-lookup"><span data-stu-id="2f6db-182">Feature</span></span>|<span data-ttu-id="2f6db-183">摘要報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-183">Summary Reports</span></span>|<span data-ttu-id="2f6db-184">詳細報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-184">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="2f6db-185">應用程式共用度量</span><span class="sxs-lookup"><span data-stu-id="2f6db-185">Application sharing metric</span></span> | <span data-ttu-id="2f6db-186">否</span><span class="sxs-lookup"><span data-stu-id="2f6db-186">No</span></span> | <span data-ttu-id="2f6db-187">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-187">Yes</span></span> |
|<span data-ttu-id="2f6db-188">客戶建立資訊支援</span><span class="sxs-lookup"><span data-stu-id="2f6db-188">Customer building information support</span></span> | <span data-ttu-id="2f6db-189">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-189">Yes</span></span> | <span data-ttu-id="2f6db-190">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-190">Yes</span></span> |
|<span data-ttu-id="2f6db-191">用戶端點資訊支援</span><span class="sxs-lookup"><span data-stu-id="2f6db-191">Customer endpoint information support</span></span> | <span data-ttu-id="2f6db-192">只有在 <span> cqd.teams.microsoft.com<span/></span><span class="sxs-lookup"><span data-stu-id="2f6db-192">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="2f6db-193">只有在 <span> cqd.teams.microsoft.com<span/></span><span class="sxs-lookup"><span data-stu-id="2f6db-193">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="2f6db-194">向下切入分析支援</span><span class="sxs-lookup"><span data-stu-id="2f6db-194">Drill down analysis support</span></span>   | <span data-ttu-id="2f6db-195">否</span><span class="sxs-lookup"><span data-stu-id="2f6db-195">No</span></span>   | <span data-ttu-id="2f6db-196">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-196">Yes</span></span>   |
|<span data-ttu-id="2f6db-197">媒體可靠性度量</span><span class="sxs-lookup"><span data-stu-id="2f6db-197">Media reliability metrics</span></span>   | <span data-ttu-id="2f6db-198">否</span><span class="sxs-lookup"><span data-stu-id="2f6db-198">No</span></span>   | <span data-ttu-id="2f6db-199">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-199">Yes</span></span>   |
|<span data-ttu-id="2f6db-200">開箱就地報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-200">Out-of-the-box reports</span></span>   | <span data-ttu-id="2f6db-201">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-201">Yes</span></span>   | <span data-ttu-id="2f6db-202">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-202">Yes</span></span>   |
|<span data-ttu-id="2f6db-203">概觀報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-203">Overview reports</span></span>   | <span data-ttu-id="2f6db-204">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-204">Yes</span></span>   | <span data-ttu-id="2f6db-205">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-205">Yes</span></span>   |
|<span data-ttu-id="2f6db-206">每個使用者報表集</span><span class="sxs-lookup"><span data-stu-id="2f6db-206">Per-user report set</span></span>   | <span data-ttu-id="2f6db-207">否</span><span class="sxs-lookup"><span data-stu-id="2f6db-207">No</span></span>   | <span data-ttu-id="2f6db-208">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-208">Yes</span></span>   |
|<span data-ttu-id="2f6db-209">報表集自訂 (新增、刪除、修改報告) </span><span class="sxs-lookup"><span data-stu-id="2f6db-209">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="2f6db-210">否</span><span class="sxs-lookup"><span data-stu-id="2f6db-210">No</span></span>   | <span data-ttu-id="2f6db-211">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-211">Yes</span></span>   |
|<span data-ttu-id="2f6db-212">影片型螢幕共用量值</span><span class="sxs-lookup"><span data-stu-id="2f6db-212">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="2f6db-213">否</span><span class="sxs-lookup"><span data-stu-id="2f6db-213">No</span></span>   | <span data-ttu-id="2f6db-214">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-214">Yes</span></span>   |
|<span data-ttu-id="2f6db-215">影片度量</span><span class="sxs-lookup"><span data-stu-id="2f6db-215">Video metrics</span></span>   | <span data-ttu-id="2f6db-216">否</span><span class="sxs-lookup"><span data-stu-id="2f6db-216">No</span></span>   | <span data-ttu-id="2f6db-217">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-217">Yes</span></span>   |
|<span data-ttu-id="2f6db-218">可用的資料量</span><span class="sxs-lookup"><span data-stu-id="2f6db-218">Amount of data available</span></span>   | <span data-ttu-id="2f6db-219">過去 12 個月</span><span class="sxs-lookup"><span data-stu-id="2f6db-219">Last 12 months</span></span>   | <span data-ttu-id="2f6db-220">過去 12 個月</span><span class="sxs-lookup"><span data-stu-id="2f6db-220">Last 12 months</span></span>   |
|<span data-ttu-id="2f6db-221">Microsoft Teams 資料</span><span class="sxs-lookup"><span data-stu-id="2f6db-221">Microsoft Teams data</span></span>   | <span data-ttu-id="2f6db-222">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-222">Yes</span></span>   | <span data-ttu-id="2f6db-223">是</span><span class="sxs-lookup"><span data-stu-id="2f6db-223">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="2f6db-224">選取產品資料以在報告中查看</span><span class="sxs-lookup"><span data-stu-id="2f6db-224">Select product data to see in reports</span></span>

<span data-ttu-id="2f6db-225">在摘要與Location-Enhanced中，您可以使用產品篩選下拉式清單來顯示所有產品資料、只有 Microsoft Teams 資料，或只顯示商務用 Skype Online 資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-225">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![螢幕擷取畫面：顯示產品篩選控制項選項](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="2f6db-227">在詳細報告中，您可以使用 Is **Teams** 維度將資料篩選至 Microsoft Teams 或商務用 Skype Online 資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-227">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="2f6db-228">摘要報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-228">Summary Reports</span></span>

<span data-ttu-id="2f6db-229">這些是當您第一次登錄 CQD 時，在 CQD 儀表板上會看到的報告。</span><span class="sxs-lookup"><span data-stu-id="2f6db-229">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="2f6db-230">它們提供您每日、每月和表格報表的品質趨勢概覽，以協助識別品質不佳的子網。</span><span class="sxs-lookup"><span data-stu-id="2f6db-230">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

| <span data-ttu-id="2f6db-231">選項 卡</span><span class="sxs-lookup"><span data-stu-id="2f6db-231">Tab</span></span> | <span data-ttu-id="2f6db-232">說明</span><span class="sxs-lookup"><span data-stu-id="2f6db-232">Description</span></span> |
|---------|---------|
|<span data-ttu-id="2f6db-233">整體通話品質</span><span class="sxs-lookup"><span data-stu-id="2f6db-233">Overall Call Quality</span></span>     | <span data-ttu-id="2f6db-234">其他 3 個定位停駐點的匯總。</span><span class="sxs-lookup"><span data-stu-id="2f6db-234">Aggregate of the other 3 tabs.</span></span>       |
|<span data-ttu-id="2f6db-235">伺服器 —用戶端</span><span class="sxs-lookup"><span data-stu-id="2f6db-235">Server—Client</span></span>     |<span data-ttu-id="2f6db-236">伺服器與用戶端端點之間的資料流程詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-236">Details of the streams between server and client endpoints.</span></span>        |
|<span data-ttu-id="2f6db-237">用戶端 -用戶端</span><span class="sxs-lookup"><span data-stu-id="2f6db-237">Client—Client</span></span>     |<span data-ttu-id="2f6db-238">兩個用戶端端點之間的資料流程詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-238">Details of the streams between two client endpoints.</span></span>        |
|<span data-ttu-id="2f6db-239">語音品質 SLA</span><span class="sxs-lookup"><span data-stu-id="2f6db-239">Voice Quality SLA</span></span>     |<span data-ttu-id="2f6db-240">商務用 Skype 語音品質 SLA 中包含的通話 [資訊](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-240">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>        |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="2f6db-241">整體通話品質 Tab</span><span class="sxs-lookup"><span data-stu-id="2f6db-241">Overall Call Quality tab</span></span>

<span data-ttu-id="2f6db-242">使用此選項卡上的資料，根據串流計數和不佳的百分比來評估通話品質狀態和趨勢。</span><span class="sxs-lookup"><span data-stu-id="2f6db-242">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="2f6db-243">右上角的圖例顯示哪些色彩和視覺元素代表這些度量。</span><span class="sxs-lookup"><span data-stu-id="2f6db-243">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![螢幕擷取畫面：顯示通話品質選項卡](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="2f6db-245">資料流程分為三個群組：良好、差和未分類。</span><span class="sxs-lookup"><span data-stu-id="2f6db-245">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="2f6db-246">此外，還有計算 *結果的 Poor %* 值，提供分類為"差" 的資料流程與總分類串流計數的比例。</span><span class="sxs-lookup"><span data-stu-id="2f6db-246">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="2f6db-247">由於 Poor % = (資料流程+ 良好資料流程 *) \* 100，* 因此 Poor *%*  不會受到多個未分類 *資料流程的目前*  狀態影響。</span><span class="sxs-lookup"><span data-stu-id="2f6db-247">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="2f6db-248">若要瞭解將資料流程分類為不佳或良好，請參閱通話品質儀表板 [中的](stream-classification-in-call-quality-dashboard.md)[串流分類> 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-248">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="2f6db-249">使用左側的縮放比例來測量串流計數值。</span><span class="sxs-lookup"><span data-stu-id="2f6db-249">Use the scale on the left to measure the stream count values.</span></span>
  
![螢幕擷取畫面：顯示串流計數值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="2f6db-251">使用右邊的刻度來測量差 % 值。</span><span class="sxs-lookup"><span data-stu-id="2f6db-251">Use the scale on the right to measure the Poor % values.</span></span>
  
![螢幕擷取畫面：顯示差 % 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="2f6db-253">您也可以將滑鼠游標移到長條上，以取得實際的數值。</span><span class="sxs-lookup"><span data-stu-id="2f6db-253">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f6db-254">下列範例來自非常小的範例資料集，而值在實際部署中並不實際。</span><span class="sxs-lookup"><span data-stu-id="2f6db-254">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![螢幕擷取畫面：顯示用來存取資料的滑鼠](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="2f6db-256">整體串流音量可協助判斷計算得的差百分比相關性。</span><span class="sxs-lookup"><span data-stu-id="2f6db-256">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="2f6db-257">整體資料流程的音量越小，報告的差百分比值越不可靠。</span><span class="sxs-lookup"><span data-stu-id="2f6db-257">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="2f6db-258">Server-Client和Client-Client欄</span><span class="sxs-lookup"><span data-stu-id="2f6db-258">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="2f6db-259">這兩個選項卡提供其端點到端點案例的資料流程詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-259">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="2f6db-260">該Server-Client有四個可壓縮的區段，代表四個媒體資料流程在哪個情況下會流動。</span><span class="sxs-lookup"><span data-stu-id="2f6db-260">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="2f6db-261">內線</span><span class="sxs-lookup"><span data-stu-id="2f6db-261">Wired Inside</span></span>
- <span data-ttu-id="2f6db-262">有線外部</span><span class="sxs-lookup"><span data-stu-id="2f6db-262">Wired Outside</span></span>
- <span data-ttu-id="2f6db-263">內部 WiFi</span><span class="sxs-lookup"><span data-stu-id="2f6db-263">WiFi Inside</span></span>
- <span data-ttu-id="2f6db-264">WiFi 外部</span><span class="sxs-lookup"><span data-stu-id="2f6db-264">WiFi Outside</span></span>

<span data-ttu-id="2f6db-265">同樣地，Client-Client有五個可折疊的節：</span><span class="sxs-lookup"><span data-stu-id="2f6db-265">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="2f6db-266">內部有線 - 內接</span><span class="sxs-lookup"><span data-stu-id="2f6db-266">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="2f6db-267">內部有線 - 外部有線</span><span class="sxs-lookup"><span data-stu-id="2f6db-267">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="2f6db-268">外部有線 - 外部有線</span><span class="sxs-lookup"><span data-stu-id="2f6db-268">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="2f6db-269">內部有線 - 內部 WiFi</span><span class="sxs-lookup"><span data-stu-id="2f6db-269">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="2f6db-270">內部有線 - 外部 WiFi</span><span class="sxs-lookup"><span data-stu-id="2f6db-270">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="2f6db-271">內部與外部</span><span class="sxs-lookup"><span data-stu-id="2f6db-271">Inside versus Outside</span></span>

<span data-ttu-id="2f6db-272">CQD 會使用建築物資訊將串流分類為 [內部」 或 [外部資料串流若存在的話）。</span><span class="sxs-lookup"><span data-stu-id="2f6db-272">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="2f6db-273">每個資料流程的端點都與子網位址相關聯。</span><span class="sxs-lookup"><span data-stu-id="2f6db-273">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="2f6db-274">如果子網位於上傳的建築物資訊中標示為 InsideCorp 的子網清單中，則它視為 *內部 。*</span><span class="sxs-lookup"><span data-stu-id="2f6db-274">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="2f6db-275">如果尚未上傳 [建房資訊>，則內部測試會一直將資料流程分類為 *[外部*）。</span><span class="sxs-lookup"><span data-stu-id="2f6db-275">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="2f6db-276">此案例的Server-Client測試只會考慮用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="2f6db-276">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="2f6db-277">由於伺服器從使用者的角度而言一直位於外部，因此在測試中不會說明這一點。</span><span class="sxs-lookup"><span data-stu-id="2f6db-277">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="2f6db-278">有線與 WiFi</span><span class="sxs-lookup"><span data-stu-id="2f6db-278">Wired versus WiFi</span></span>

<span data-ttu-id="2f6db-279">如名稱所指出，分類準則是以用戶端連線類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="2f6db-279">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="2f6db-280">伺服器一直是有線的，而且不會包含在計算中。</span><span class="sxs-lookup"><span data-stu-id="2f6db-280">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="2f6db-281">在給定的資料流程中，如果兩個端點之一已連接到 WiFi 網路，則 CQD 會分類為 WiFi。</span><span class="sxs-lookup"><span data-stu-id="2f6db-281">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>

> [!NOTE]
> <span data-ttu-id="2f6db-282">如果兩個端點之一已連接到 WiFi 網路，則串流會分類為 CQD 中的 WiFi。</span><span class="sxs-lookup"><span data-stu-id="2f6db-282">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="2f6db-283">租使用者資料資訊</span><span class="sxs-lookup"><span data-stu-id="2f6db-283">Tenant Data information</span></span>

<span data-ttu-id="2f6db-284">CQD 摘要報表儀表板包含租使用者資料 **上傳頁面，** 從右上角的設定功能表中選取租使用者資料上傳來存取。</span><span class="sxs-lookup"><span data-stu-id="2f6db-284">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="2f6db-285">此頁面供系統管理員用來上傳自己的資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="2f6db-285">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="2f6db-286">IP 位址和地理資訊的地圖。</span><span class="sxs-lookup"><span data-stu-id="2f6db-286">A map of IP address and geographical information.</span></span>
- <span data-ttu-id="2f6db-287">每個無線 AP 及其 MAC 位址的地圖。</span><span class="sxs-lookup"><span data-stu-id="2f6db-287">A map of each wireless AP and its MAC address.</span></span>
- <span data-ttu-id="2f6db-288">端點到端點製作/模型/類型等的地圖。</span><span class="sxs-lookup"><span data-stu-id="2f6db-288">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="2f6db-289">我們建議您上傳租使用者、建築物和位置資料，讓 CQD 將這項資訊納入您的報告中。</span><span class="sxs-lookup"><span data-stu-id="2f6db-289">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="2f6db-290">如果您尚未上傳此資料，請閱讀上傳租使用者 [和建房資料](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-290">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="2f6db-291">詳細報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-291">Detailed reports</span></span>

| <span data-ttu-id="2f6db-292">名稱</span><span class="sxs-lookup"><span data-stu-id="2f6db-292">Name</span></span> | <span data-ttu-id="2f6db-293">說明</span><span class="sxs-lookup"><span data-stu-id="2f6db-293">Description</span></span> |
|---------|---------|
|<span data-ttu-id="2f6db-294">Location-Enhanced報表</span><span class="sxs-lookup"><span data-stu-id="2f6db-294">Location-Enhanced Reports</span></span>     |<span data-ttu-id="2f6db-295">根據位置資訊顯示品質趨勢。</span><span class="sxs-lookup"><span data-stu-id="2f6db-295">Shows quality trends based on location information.</span></span> <span data-ttu-id="2f6db-296">只有在您上傳租使用者資料時，才能 [顯示此報表](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-296">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="2f6db-297">可靠性報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-297">Reliability Reports</span></span>     |<span data-ttu-id="2f6db-298">包含音訊、視視、視 (VBSS) ，以及應用程式共用報告。</span><span class="sxs-lookup"><span data-stu-id="2f6db-298">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports.</span></span>        |
|<span data-ttu-id="2f6db-299">體驗品質報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-299">Quality of Experience Reports</span></span>     |<span data-ttu-id="2f6db-300">所有用戶端和裝置的音訊品質和可靠性，包括會議室。</span><span class="sxs-lookup"><span data-stu-id="2f6db-300">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="2f6db-301">這些報告是可下載 [CQD](https://aka.ms/QERtemplates)範本的「精簡」版本，著重于分析音訊品質和可靠性的重要區域。</span><span class="sxs-lookup"><span data-stu-id="2f6db-301">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="2f6db-302">品質向下切入報表</span><span class="sxs-lookup"><span data-stu-id="2f6db-302">Quality Drill Down Reports</span></span>     | <span data-ttu-id="2f6db-303">向下向下切入：按地區、位置、子網、小時和使用者的日期。</span><span class="sxs-lookup"><span data-stu-id="2f6db-303">Drill downs: Date by region, locations, subnets, hour, and users.</span></span>        |
|<span data-ttu-id="2f6db-304">失敗向下切入報表</span><span class="sxs-lookup"><span data-stu-id="2f6db-304">Failure Drill Down Reports</span></span>     | <span data-ttu-id="2f6db-305">向下向下切入：按地區、位置、子網、小時和使用者的日期。</span><span class="sxs-lookup"><span data-stu-id="2f6db-305">Drill downs: Date by region, locations, subnets, hour, and users.</span></span>        |
|<span data-ttu-id="2f6db-306">為我的通話報告評分</span><span class="sxs-lookup"><span data-stu-id="2f6db-306">Rate My Call Reports</span></span>     |<span data-ttu-id="2f6db-307">根據地區、位置或使用者來分析使用者通話分級。</span><span class="sxs-lookup"><span data-stu-id="2f6db-307">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="2f6db-308">包含逐字意見回饋。</span><span class="sxs-lookup"><span data-stu-id="2f6db-308">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="2f6db-309">技術支援台報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-309">Help Desk Reports</span></span>     |<span data-ttu-id="2f6db-310">服務台報告會查看個別使用者、使用者群組或所有人的通話和會議資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-310">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="2f6db-311">這些報告結合建築物和 EUII 資料，可依據網路位置、會議詳細資料、裝置或固件，協助找出可能的系統問題。</span><span class="sxs-lookup"><span data-stu-id="2f6db-311">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="2f6db-312">用戶端版本報告</span><span class="sxs-lookup"><span data-stu-id="2f6db-312">Client Version Reports</span></span>     |<span data-ttu-id="2f6db-313">用戶端版本摘要：查看每個用戶端應用程式版本的會話和使用者計數</span><span class="sxs-lookup"><span data-stu-id="2f6db-313">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="2f6db-314">使用者用戶端版本：查看每個用戶端應用程式版本的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="2f6db-314">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="2f6db-315">針對產品與用戶端類型預先建立篩選有助於將版本焦點放在特定用戶端。</span><span class="sxs-lookup"><span data-stu-id="2f6db-315">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="2f6db-316">端點報表</span><span class="sxs-lookup"><span data-stu-id="2f6db-316">Endpoint Reports</span></span>     |<span data-ttu-id="2f6db-317">顯示電腦端點與電腦 (通話品質) 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-317">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="2f6db-318">這些報表包含建建資料 ，如果您已經上傳資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-318">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="2f6db-319">建立自訂的詳細報表</span><span class="sxs-lookup"><span data-stu-id="2f6db-319">Create custom detailed reports</span></span>

<span data-ttu-id="2f6db-320">如果預設的 CQD 報表不符合您的需求，請使用這些指示來建立自訂報表。</span><span class="sxs-lookup"><span data-stu-id="2f6db-320">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="2f6db-321">或者 (2020 年 1 月) [Power BI for CQD 報表 ](cqd-power-bi-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-321">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="2f6db-322">從登入時顯示于畫面頂端的報表下拉式清單中，選取摘要 \( 報表畫面選取詳細報表 \) ，然後選取 **新報表**。</span><span class="sxs-lookup"><span data-stu-id="2f6db-322">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="2f6db-323">按一下 **報告中** 的 [編輯>，查看查詢編輯器。</span><span class="sxs-lookup"><span data-stu-id="2f6db-323">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="2f6db-324">每個報表都由查詢備份到 Cube 中。</span><span class="sxs-lookup"><span data-stu-id="2f6db-324">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="2f6db-325">報表是查詢所返回資料的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="2f6db-325">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="2f6db-326">查詢編輯器可協助編輯這些查詢和報表的顯示選項。</span><span class="sxs-lookup"><span data-stu-id="2f6db-326">The Query Editor helps you edit these queries and the display options of the report.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f6db-327">網路範圍可用來代表一個超網路， (多個子網的組合，以及單一路由首碼) 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-327">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="2f6db-328">所有新建築物上傳都會檢查任何重迭範圍。</span><span class="sxs-lookup"><span data-stu-id="2f6db-328">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="2f6db-329">如果您先前上傳過建置檔案，您應該先下載目前的檔案，然後重新上傳，找出任何重迭之處並修正問題，然後再重新上傳。</span><span class="sxs-lookup"><span data-stu-id="2f6db-329">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="2f6db-330">先前上傳檔案的任何重迭都可能會導致報告中子網與建築物的相互比對錯誤。</span><span class="sxs-lookup"><span data-stu-id="2f6db-330">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="2f6db-331">某些 VPN 的實現無法正確報告子網資訊。</span><span class="sxs-lookup"><span data-stu-id="2f6db-331">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="2f6db-332">建議在建築物檔案中新增 VPN 子網時，不要為子網新增一個專案，而是將 VPN 子網中每個位址的個別專案新增為個別的 32 位網路。</span><span class="sxs-lookup"><span data-stu-id="2f6db-332">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="2f6db-333">每一列都可以有相同的建築物中繼資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-333">Each row can have the same building metadata.</span></span> <span data-ttu-id="2f6db-334">例如，您應該有 256 列，而不是 172.16.18.0/24 的一列，每個位址在 172.16.18.0/32 和 172.16.18.255/32 之間各有一列，包括。</span><span class="sxs-lookup"><span data-stu-id="2f6db-334">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="2f6db-335">VPN 欄為選擇性，預設為 0。</span><span class="sxs-lookup"><span data-stu-id="2f6db-335">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="2f6db-336">如果 VPN 欄的值設為 1，該列所代表的子網將會完全展開，以符合子網內的所有 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2f6db-336">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="2f6db-337">請謹慎且僅適用于 VPN 子網，因為完全展開這些子網會對建立資料之查詢的查詢時間造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="2f6db-337">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="2f6db-338">指向報告中的橫條圖和趨勢線以顯示詳細值。</span><span class="sxs-lookup"><span data-stu-id="2f6db-338">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="2f6db-339">焦點報表會顯示動作功能表：編輯、複製、**刪除**、**下載** 及 **匯出報表樹**。 </span><span class="sxs-lookup"><span data-stu-id="2f6db-339">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="2f6db-340">查詢篩選</span><span class="sxs-lookup"><span data-stu-id="2f6db-340">Query filters</span></span>

<span data-ttu-id="2f6db-341">查詢篩選是使用 CQD 中的查詢編輯器來執行的。</span><span class="sxs-lookup"><span data-stu-id="2f6db-341">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="2f6db-342">這些篩選是用來減少 CQD 所返回的記錄數目，因此將報表的整體大小和查詢時間最小化。</span><span class="sxs-lookup"><span data-stu-id="2f6db-342">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="2f6db-343">這項功能對於篩選出未管理的網路特別有用。</span><span class="sxs-lookup"><span data-stu-id="2f6db-343">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="2f6db-344">下表所列的篩選會使用正則運算式 (RegEx) 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-344">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="2f6db-345">Filter</span><span class="sxs-lookup"><span data-stu-id="2f6db-345">Filter</span></span>         | <span data-ttu-id="2f6db-346">說明</span><span class="sxs-lookup"><span data-stu-id="2f6db-346">Description</span></span>          | <span data-ttu-id="2f6db-347">CQD 查詢篩選範例</span><span class="sxs-lookup"><span data-stu-id="2f6db-347">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="2f6db-348">無空白值</span><span class="sxs-lookup"><span data-stu-id="2f6db-348">No blank values</span></span>   | <span data-ttu-id="2f6db-349">有些篩選沒有篩選空白值的選項。</span><span class="sxs-lookup"><span data-stu-id="2f6db-349">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="2f6db-350">若要手動篩選空白值，請使用空白運算式，並視您的需求將篩選設定為等於或不等於。</span><span class="sxs-lookup"><span data-stu-id="2f6db-350">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="2f6db-351">第二個建築物 \<\> \^ \\ 名稱 s\*\$</span><span class="sxs-lookup"><span data-stu-id="2f6db-351">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="2f6db-352">排除一般子網</span><span class="sxs-lookup"><span data-stu-id="2f6db-352">Exclude common subnets</span></span> | <span data-ttu-id="2f6db-353">若沒有有效的建築物檔案，無法與未管理的網路分開管理，則報告會包含家用網路。</span><span class="sxs-lookup"><span data-stu-id="2f6db-353">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="2f6db-354">這些家用子網不在 IT 控制範圍內，而且可以快速排除在報表之外。</span><span class="sxs-lookup"><span data-stu-id="2f6db-354">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="2f6db-355">本指南定義的常見子網為 10.0.0.0、192.168.1.0 和 192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="2f6db-355">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="2f6db-356">第二子網 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="2f6db-356">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="2f6db-357">僅內部查看</span><span class="sxs-lookup"><span data-stu-id="2f6db-357">View inside only</span></span>  | <span data-ttu-id="2f6db-358">用來篩選報表， (外部) 管理 (管理) 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-358">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="2f6db-359">受管理的 CQD 範本已預配置這些篩選。</span><span class="sxs-lookup"><span data-stu-id="2f6db-359">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="2f6db-360">第二個內部公司 = 內部</span><span class="sxs-lookup"><span data-stu-id="2f6db-360">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="2f6db-361">報表篩選</span><span class="sxs-lookup"><span data-stu-id="2f6db-361">Report filters</span></span>

<span data-ttu-id="2f6db-362">使用 CQD 報表篩選來縮小調查的焦點。</span><span class="sxs-lookup"><span data-stu-id="2f6db-362">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="2f6db-363">在查詢編輯器或直接在報表的呈現報表新增篩選，以使用報表篩選。</span><span class="sxs-lookup"><span data-stu-id="2f6db-363">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="2f6db-364">下列報表篩選會用於 [整個 CQD 範本](https://aka.ms/QERtemplates)。</span><span class="sxs-lookup"><span data-stu-id="2f6db-364">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="2f6db-365">Filter</span><span class="sxs-lookup"><span data-stu-id="2f6db-365">Filter</span></span>     | <span data-ttu-id="2f6db-366">說明</span><span class="sxs-lookup"><span data-stu-id="2f6db-366">Description</span></span>                            | <span data-ttu-id="2f6db-367">CQD 報表篩選範例</span><span class="sxs-lookup"><span data-stu-id="2f6db-367">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="2f6db-368">月</span><span class="sxs-lookup"><span data-stu-id="2f6db-368">Month</span></span>      | <span data-ttu-id="2f6db-369">首先從年份開始，然後從月份開始。</span><span class="sxs-lookup"><span data-stu-id="2f6db-369">Start with the year first, then month.</span></span> | <span data-ttu-id="2f6db-370">2017-10</span><span class="sxs-lookup"><span data-stu-id="2f6db-370">2017-10</span></span>                           |
| <span data-ttu-id="2f6db-371">字母</span><span class="sxs-lookup"><span data-stu-id="2f6db-371">Alphabetic</span></span> | <span data-ttu-id="2f6db-372">篩選任何字母字元。</span><span class="sxs-lookup"><span data-stu-id="2f6db-372">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="2f6db-373">[a-z]</span><span class="sxs-lookup"><span data-stu-id="2f6db-373">[a-z]</span></span>                             |
| <span data-ttu-id="2f6db-374">數位</span><span class="sxs-lookup"><span data-stu-id="2f6db-374">Numeric</span></span>    | <span data-ttu-id="2f6db-375">篩選任何數值字元。</span><span class="sxs-lookup"><span data-stu-id="2f6db-375">Filters for any numeric characters.</span></span>    | <span data-ttu-id="2f6db-376">[0-9]</span><span class="sxs-lookup"><span data-stu-id="2f6db-376">[0-9]</span></span>                             |
| <span data-ttu-id="2f6db-377">百分比</span><span class="sxs-lookup"><span data-stu-id="2f6db-377">Percentage</span></span> | <span data-ttu-id="2f6db-378">篩選百分比。</span><span class="sxs-lookup"><span data-stu-id="2f6db-378">Filters for a percentage.</span></span>              | <span data-ttu-id="2f6db-379"> ([3-9] \\ \| .)  ([3-9])  ([1-9][0-9]) \|</span><span class="sxs-lookup"><span data-stu-id="2f6db-379">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="2f6db-380">向下拉式篩選</span><span class="sxs-lookup"><span data-stu-id="2f6db-380">Drill-down filters</span></span>

<span data-ttu-id="2f6db-381">CQD 報告具有數種向下切取篩選，是縮小通話品質調查焦點的強大工具。</span><span class="sxs-lookup"><span data-stu-id="2f6db-381">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="2f6db-382">如果您選取向下切取欄位，報表會自動開啟適當的定位停駐點，並篩選選取的值。</span><span class="sxs-lookup"><span data-stu-id="2f6db-382">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="2f6db-383">如果該定位停駐點有它自己的向下切入欄位，而且已選取其中一個欄位，則兩組篩選會套用，逐漸縮小產生的資料集。</span><span class="sxs-lookup"><span data-stu-id="2f6db-383">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![說明向下拉式報表流程的圖表](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="2f6db-385">新增和編輯向下拉式欄位</span><span class="sxs-lookup"><span data-stu-id="2f6db-385">Adding and editing drill-down fields</span></span>

<span data-ttu-id="2f6db-386">編輯報表時，您可以選擇使用查詢編輯器指定您自己的向下切入欄位。</span><span class="sxs-lookup"><span data-stu-id="2f6db-386">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="2f6db-387">首先按一下 **...**</span><span class="sxs-lookup"><span data-stu-id="2f6db-387">Start by clicking **…**</span></span> <span data-ttu-id="2f6db-388">針對您想要編輯的報告，然後選取 **編輯**。</span><span class="sxs-lookup"><span data-stu-id="2f6db-388">for the report you want to edit, then select **Edit**.</span></span>

![編輯向下拉式欄位的螢幕擷取畫面](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="2f6db-390">從查詢編輯器左側的清單選取維度。</span><span class="sxs-lookup"><span data-stu-id="2f6db-390">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="2f6db-391">接著，按一下 [流覽至卷標」 下方的下拉式清單，然後選取您希望該維度向下切入的定位點和展開器群組。</span><span class="sxs-lookup"><span data-stu-id="2f6db-391">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="2f6db-392">注意：目前，向下向下拉式功能只能流覽至不同的定位點。</span><span class="sxs-lookup"><span data-stu-id="2f6db-392">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="2f6db-393">稍後會新增深入到特定展開器的支援。</span><span class="sxs-lookup"><span data-stu-id="2f6db-393">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="2f6db-394">最後，按一下 **[關閉** 以將變更儲存至維度，然後按一下 [ **儲存** 並關閉查詢編輯器。</span><span class="sxs-lookup"><span data-stu-id="2f6db-394">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![在查詢編輯器中選取維度的螢幕擷取畫面](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="2f6db-396">多重選取篩選</span><span class="sxs-lookup"><span data-stu-id="2f6db-396">Multi-select filters</span></span>

<span data-ttu-id="2f6db-397">除了向下切取功能之外，CQD 也支援指定具有多個值的篩選 (或篩選) 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-397">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="2f6db-398">若要選取多個篩選值，首先請新增篩選至報表。</span><span class="sxs-lookup"><span data-stu-id="2f6db-398">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="2f6db-399">按一下 [篩選標籤的旁邊，輸入您想要使用的尺寸名稱， **+** 然後按一下 [**新增**> 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-399">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![新增多重選取篩選的螢幕擷取畫面](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="2f6db-401">接著，按一下 [ **搜尋** (新篩選清單旁的放大鏡) 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-401">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="2f6db-402">您會看到一個文字欄位，以及一些選項，包括 **選取全部** 和 **反相**。</span><span class="sxs-lookup"><span data-stu-id="2f6db-402">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="2f6db-403">輸入值，然後按一下 **該欄位旁的** [搜尋以搜尋。</span><span class="sxs-lookup"><span data-stu-id="2f6db-403">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="2f6db-404">或者，將文字欄位保留空白，然後按一下 [ **搜尋** 以查看最多前 100 個選項。</span><span class="sxs-lookup"><span data-stu-id="2f6db-404">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="2f6db-405">範例：</span><span class="sxs-lookup"><span data-stu-id="2f6db-405">Example:</span></span>  

![新增查詢篩選的螢幕擷取畫面](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="2f6db-407">儀表板層級篩選</span><span class="sxs-lookup"><span data-stu-id="2f6db-407">Dashboard level filters</span></span>
<span data-ttu-id="2f6db-408">某些 CQD 報表會新增儀表板層級篩選，方便您根據一般參數進行篩選。</span><span class="sxs-lookup"><span data-stu-id="2f6db-408">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="2f6db-409">這些篩選會出現在一般報表選項卡外，且直接在產品篩選下方，並適用于儀表板中的所有篩選。</span><span class="sxs-lookup"><span data-stu-id="2f6db-409">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![儀表板篩選的螢幕擷取畫面](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="2f6db-411">URL 篩選</span><span class="sxs-lookup"><span data-stu-id="2f6db-411">URL filters</span></span>

<span data-ttu-id="2f6db-412">CQD 支援新增篩選至 URL。</span><span class="sxs-lookup"><span data-stu-id="2f6db-412">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="2f6db-413">這可輕鬆地共用 CQD 查詢或將查詢加入書簽。</span><span class="sxs-lookup"><span data-stu-id="2f6db-413">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="2f6db-414">您可以在 URL 中定義參數，例如趨勢月、租使用者識別碼或語言。</span><span class="sxs-lookup"><span data-stu-id="2f6db-414">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="2f6db-415">您也可以在 URL 中新增產品或儀表板層級篩選。</span><span class="sxs-lookup"><span data-stu-id="2f6db-415">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="2f6db-416">當您補救受管理的建築物或網路時，從 CQD 報表排除聯合資料會很有用，因為聯合端點可能會影響報表。</span><span class="sxs-lookup"><span data-stu-id="2f6db-416">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="2f6db-417">若要新增篩選，請附加下列內容至 URL 結尾：</span><span class="sxs-lookup"><span data-stu-id="2f6db-417">To add a filter, append the following to the end of the URL:</span></span>

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="2f6db-418">範例：</span><span class="sxs-lookup"><span data-stu-id="2f6db-418">Example:</span></span>  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

<span data-ttu-id="2f6db-419">若要新增儀表板層級篩選至 URL，該篩選必須存在於 CQD 中，做為產品或儀表板層級篩選。</span><span class="sxs-lookup"><span data-stu-id="2f6db-419">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="2f6db-420">在熱門月份之後，以及 URL 參數之前，將這些篩選新增到 URL：</span><span class="sxs-lookup"><span data-stu-id="2f6db-420">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

`filter/DATA_MODEL_NAME|VALUE`

<span data-ttu-id="2f6db-421">例如，若要使用 Microsoft Teams 的產品篩選值，您可以新增下列專案：</span><span class="sxs-lookup"><span data-stu-id="2f6db-421">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

`filter/[AllStreams].[Is%20Teams]|[True]`

<span data-ttu-id="2f6db-422">您的整個 URL 看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="2f6db-422">Your entire URL would look something like this:</span></span>

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

<span data-ttu-id="2f6db-423">若要使用多重選取值來申請 URL 篩選，請以管道或管道分隔 ( |) 字元。</span><span class="sxs-lookup"><span data-stu-id="2f6db-423">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="2f6db-424">例如：</span><span class="sxs-lookup"><span data-stu-id="2f6db-424">For example:</span></span>

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

<span data-ttu-id="2f6db-425">如果您指定不正確名稱或值，將不會使用 URL 篩選。</span><span class="sxs-lookup"><span data-stu-id="2f6db-425">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="2f6db-426">您可以使用 URL 篩選來篩選特定維度的每一個報表。</span><span class="sxs-lookup"><span data-stu-id="2f6db-426">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="2f6db-427">最常見的 URL 篩選是用來篩選報表以排除聯合參與者遙測，或只專注于 Teams 或商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="2f6db-427">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="2f6db-428">當您補救受管理的建築物或網路時，從 CQD 報表排除聯合資料會很有用，因為聯合端點可能會影響報表。</span><span class="sxs-lookup"><span data-stu-id="2f6db-428">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="2f6db-429">Filter</span><span class="sxs-lookup"><span data-stu-id="2f6db-429">Filter</span></span>         | <span data-ttu-id="2f6db-430">說明</span><span class="sxs-lookup"><span data-stu-id="2f6db-430">Description</span></span>          | <span data-ttu-id="2f6db-431">CQD 查詢篩選範例</span><span class="sxs-lookup"><span data-stu-id="2f6db-431">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="2f6db-432">無空白值</span><span class="sxs-lookup"><span data-stu-id="2f6db-432">No blank values</span></span>   | <span data-ttu-id="2f6db-433">有些篩選沒有篩選空白值的選項。</span><span class="sxs-lookup"><span data-stu-id="2f6db-433">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="2f6db-434">若要手動篩選空白值，請使用空白運算式，並視您的需求將篩選設定為等於或不等於。</span><span class="sxs-lookup"><span data-stu-id="2f6db-434">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="2f6db-435">第二個建築物 \<\> \^ \\ 名稱 s\*\$</span><span class="sxs-lookup"><span data-stu-id="2f6db-435">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="2f6db-436">排除一般子網</span><span class="sxs-lookup"><span data-stu-id="2f6db-436">Exclude common subnets</span></span> | <span data-ttu-id="2f6db-437">若沒有有效的建築物檔案，無法與未管理的網路分開管理，則報告會包含家用網路。</span><span class="sxs-lookup"><span data-stu-id="2f6db-437">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="2f6db-438">這些家用子網不在 IT 控制範圍內，而且可以快速排除在報表之外。</span><span class="sxs-lookup"><span data-stu-id="2f6db-438">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="2f6db-439">本文定義的常見子網為 10.0.0.0、192.168.1.0 和 192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="2f6db-439">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="2f6db-440">第二子網 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="2f6db-440">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="2f6db-441">僅內部查看</span><span class="sxs-lookup"><span data-stu-id="2f6db-441">View inside only</span></span>  | <span data-ttu-id="2f6db-442">用來篩選報表， (外部) 管理 (管理) 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-442">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="2f6db-443">受管理的 CQD 範本已預配置這些篩選。</span><span class="sxs-lookup"><span data-stu-id="2f6db-443">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="2f6db-444">第二個內部公司 = 內部</span><span class="sxs-lookup"><span data-stu-id="2f6db-444">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="2f6db-445">如何尋找您的租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="2f6db-445">How to find your tenant ID</span></span>

<span data-ttu-id="2f6db-446">CQD 中的租使用者識別碼會對應到 Azure 中的目錄識別碼。</span><span class="sxs-lookup"><span data-stu-id="2f6db-446">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="2f6db-447">如果您不知道您的目錄識別碼，您可以在 Azure 入口網站找到它：</span><span class="sxs-lookup"><span data-stu-id="2f6db-447">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="2f6db-448">請登錄 Microsoft Azure 入口網站： <https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="2f6db-448">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="2f6db-449">選取 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="2f6db-449">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="2f6db-450">在 **管理下**，選取 **屬性**。</span><span class="sxs-lookup"><span data-stu-id="2f6db-450">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="2f6db-451">您的租使用者識別碼位於 **目錄識別碼** 方塊中。</span><span class="sxs-lookup"><span data-stu-id="2f6db-451">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="2f6db-452">您也可以使用 PowerShell 尋找租使用者識別碼：</span><span class="sxs-lookup"><span data-stu-id="2f6db-452">You can also find your tenant ID by using PowerShell:</span></span> 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="2f6db-453">比較 Teams 和商務用 Skype CQD 資料</span><span class="sxs-lookup"><span data-stu-id="2f6db-453">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="2f6db-454">即使在最新的 CQD (cqd.teams.microsoft.com) ，您也會看到 Teams 與商務用 Skype 之間的資料差異。</span><span class="sxs-lookup"><span data-stu-id="2f6db-454">Even within the latest CQD (cqd.teams.microsoft.com), you'll see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="2f6db-455">原因如下：</span><span class="sxs-lookup"><span data-stu-id="2f6db-455">Some reasons:</span></span>
- <span data-ttu-id="2f6db-456">確保績效和可靠性機制的差異：</span><span class="sxs-lookup"><span data-stu-id="2f6db-456">Differences in the mechanisms for ensuring performance and reliability:</span></span>
  - <span data-ttu-id="2f6db-457">Teams 具有自動重新連接和快速漫遊功能。</span><span class="sxs-lookup"><span data-stu-id="2f6db-457">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="2f6db-458">商務用 Skype 不會。</span><span class="sxs-lookup"><span data-stu-id="2f6db-458">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="2f6db-459">Teams 具有動態頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="2f6db-459">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="2f6db-460">商務用 Skype 不會。</span><span class="sxs-lookup"><span data-stu-id="2f6db-460">Skype for Business doesn't.</span></span>
- <span data-ttu-id="2f6db-461">Teams 與 [商務](Office-365-URLs-IP-address-ranges.md) 用 Skype 之間 IP 位址的差異範圍。</span><span class="sxs-lookup"><span data-stu-id="2f6db-461">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="2f6db-462">Teams IP 範圍較新，可能會導致防火牆的連接問題。</span><span class="sxs-lookup"><span data-stu-id="2f6db-462">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a><span data-ttu-id="2f6db-463">從商務用 Skype 舊版入口網站開啟 CQD</span><span class="sxs-lookup"><span data-stu-id="2f6db-463">Open CQD from the Skype for Business legacy portal</span></span>

<span data-ttu-id="2f6db-464">![使用商務用 Skype 舊版入口網站 ](media/sfb-logo-30x30.png) **之商務用 Skype 標誌的圖示**</span><span class="sxs-lookup"><span data-stu-id="2f6db-464">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="2f6db-465">使用系統管理員帳戶來登錄您的 Office 365 組織，然後選取系統管理磚以開啟系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="2f6db-465">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>

2. <span data-ttu-id="2f6db-466">在左窗格中的系統 **管理中心** 下，選取 **Microsoft Teams** 以開啟 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="2f6db-466">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Teams admin center.</span></span>

3. <span data-ttu-id="2f6db-467">在 Teams 系統管理中心 **，選取左** 窗格中的舊版入口網站，選取工具，然後選取商務用 **Skype Online 通話品質儀表板**。</span><span class="sxs-lookup"><span data-stu-id="2f6db-467">In the Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

   ![螢幕擷取畫面：選取通話品質儀表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="2f6db-469">在開啟的頁面上，使用全域系統管理員帳戶進行登錄，然後在系統提示時提供帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="2f6db-469">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="2f6db-470">在您第一次登錄之後，CQD 會開始收集和處理資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-470">After the first time you sign in, CQD will begin collecting and processing data.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2f6db-471">自 2019 年 12 月起，您仍可存取舊版 CQD (cqd.lync.com) ，雖然舊版入口網站提供您最新 CQD (cqd.teams.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="2f6db-471">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="2f6db-472">最後，較舊版本的 CQD 將會解除授權。</span><span class="sxs-lookup"><span data-stu-id="2f6db-472">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="2f6db-473">自 2020 年 7 月 1 日起，舊版 CQD 會從新的 CQD (存取資料，而且您無法再匯出建築物和 https://CQD.teams.microsoft.com) 報表資料。</span><span class="sxs-lookup"><span data-stu-id="2f6db-473">As of July 1, 2020, the older version of CQD accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="2f6db-474">在 2020 年底的某個時候，我們會關閉舊的 CQD，而您無法再存取它。</span><span class="sxs-lookup"><span data-stu-id="2f6db-474">Sometime in late 2020, we'll turn off the old CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="2f6db-475">相關主題</span><span class="sxs-lookup"><span data-stu-id="2f6db-475">Related topics</span></span>

[<span data-ttu-id="2f6db-476">改善及監控 Teams 的通話品質</span><span class="sxs-lookup"><span data-stu-id="2f6db-476">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="2f6db-477">什麼是 CQD？</span><span class="sxs-lookup"><span data-stu-id="2f6db-477">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="2f6db-478">設定通話品質儀表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="2f6db-478">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="2f6db-479">上傳租使用者和建築物資料</span><span class="sxs-lookup"><span data-stu-id="2f6db-479">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="2f6db-480">使用 CQD 管理通話和會議品質</span><span class="sxs-lookup"><span data-stu-id="2f6db-480">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="2f6db-481">CQD 中可用的維度和度量</span><span class="sxs-lookup"><span data-stu-id="2f6db-481">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="2f6db-482">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="2f6db-482">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="2f6db-483">使用 Power BI 分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="2f6db-483">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)