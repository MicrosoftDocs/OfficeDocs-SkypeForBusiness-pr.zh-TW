---
title: 通話品質儀表板中的資料和報表（CQD）
ms.author: lolaj
author: LolaJacobsen
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
description: 瞭解 Microsoft 通話品質儀表板（CQD）中提供的資料和報表。
ms.openlocfilehash: 02acff8cd423901c8959e94af664ffe4d43c0e51
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086002"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="8f905-103">通話品質儀表板中的資料和報表（CQD）</span><span class="sxs-lookup"><span data-stu-id="8f905-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="8f905-104">Microsoft 通話品質儀表板（CQD）使用近乎即時（NRT）的資料摘要。</span><span class="sxs-lookup"><span data-stu-id="8f905-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="8f905-105">通話記錄可在通話結束之30分鐘內的 CQD 中取得。</span><span class="sxs-lookup"><span data-stu-id="8f905-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="8f905-106">從資料集移除 NRT 管線中的記錄前，只能有幾個月提供給它。</span><span class="sxs-lookup"><span data-stu-id="8f905-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


> [!NOTE]
> <span data-ttu-id="8f905-107">[高級 CQD] （2019年11月的新功能）會從 [高級 CQD] 管線中的 NRT 資料，從較舊的 CQD 管線（讓通話記錄在大約24小時內提供）中合併資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-107">Advanced CQD (new in November 2019) merges data from the older CQD pipeline (which made call records available in about 24 hours) with NRT data from the Advanced CQD pipeline.</span></span> <span data-ttu-id="8f905-108">針對存檔週期中的資料，在舊版及高級入口網站上的查詢會產生相同的結果。</span><span class="sxs-lookup"><span data-stu-id="8f905-108">Queries on the older and Advanced portals for the data from the Archival period produce the same results.</span></span> <span data-ttu-id="8f905-109">針對 NRT 資料的任一入口網站上的查詢，以及 NRT 資料 + EUII 期間，會有所不同。</span><span class="sxs-lookup"><span data-stu-id="8f905-109">Queries on either portal for the NRT Data and NRT Data + EUII periods will be different.</span></span>

## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="8f905-110">許多存取 CQD 資料的方式</span><span class="sxs-lookup"><span data-stu-id="8f905-110">Many ways to access CQD data</span></span>

<span data-ttu-id="8f905-111">您可以透過幾種不同的途徑存取 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-111">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="8f905-112">挑選一個最符合您需求的專案：</span><span class="sxs-lookup"><span data-stu-id="8f905-112">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="8f905-113">團隊系統管理中心[（ https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8f905-113">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="8f905-114">CQD 資料包含在團隊系統管理中心的 [**使用者**] 頁面上，以易於閱讀的格式顯示最常需要的資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-114">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="8f905-115">您無法自訂您在 [**使用者**] 下找到的 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-115">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="8f905-116">CQD 入口[網站 https://cqd.teams.microsoft.com) （](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8f905-116">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="8f905-117">利用鑽取篩選功能，提供符合大部分需求的穩健摘要及詳細報告。</span><span class="sxs-lookup"><span data-stu-id="8f905-117">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="8f905-118">您也可以在 CQD 入口網站中自訂報表。</span><span class="sxs-lookup"><span data-stu-id="8f905-118">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="8f905-119">取得兩個[CQD 報表範本](#import-the-cqd-report-templates)，協助您分析 CQD 入口網站中的資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-119">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="8f905-120">Power BI</span><span class="sxs-lookup"><span data-stu-id="8f905-120">Power BI</span></span>     | <span data-ttu-id="8f905-121">使用直接查詢在 Power BI 中使用[可自訂的 POWER bi 範本](CQD-Power-BI-query-templates.md)來查看您的 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-121">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="8f905-122">[下載 POWER BI 查詢範本以進行 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="8f905-122">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="8f905-123">您也可以[使用 REST API 來透過 POWER BI 存取 CQD 資料](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api)。</span><span class="sxs-lookup"><span data-stu-id="8f905-123">You can also [use the REST API to access CQD data](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="8f905-124">如果您想要下載 CQD 資料以供離線使用，請使用這個方法。</span><span class="sxs-lookup"><span data-stu-id="8f905-124">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="8f905-125">使用這個方法的優點是取得較佳的效能，對於您線上時在 Power BI 中 bog 的大型資料集，特別有用。</span><span class="sxs-lookup"><span data-stu-id="8f905-125">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="8f905-126">圖形 API</span><span class="sxs-lookup"><span data-stu-id="8f905-126">Graph API</span></span>     | <span data-ttu-id="8f905-127">使用[圖形 API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)存取自己的通話品質資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-127">Access call quality data yourself using the [Graph API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="8f905-128">這是最複雜的方法，但它能在分析通話品質資料時提供最大的控制能力和靈活性。</span><span class="sxs-lookup"><span data-stu-id="8f905-128">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="8f905-129">例如，如果您需要將組織的其他資料加入其他資料，您可以使用圖形 API 來建立資料模型，並納入通話品質資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-129">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="8f905-130">匯入 CQD 報表範本</span><span class="sxs-lookup"><span data-stu-id="8f905-130">Import the CQD report templates</span></span>

<span data-ttu-id="8f905-131">下載[兩個策劃 CQD 報告範本](https://aka.ms/qertemplates)（所有網路和受管理的網路），協助您快速掌握 CQD。</span><span class="sxs-lookup"><span data-stu-id="8f905-131">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="8f905-132">[所有網路] 範本（雖然經過優化，可搭配建立資料檔案使用），但您可以在向 CQD 中進行收集及上傳資訊時使用，如下一節所述。</span><span class="sxs-lookup"><span data-stu-id="8f905-132">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="8f905-133">**若要匯入範本（。CQDX）轉換成 CQD**</span><span class="sxs-lookup"><span data-stu-id="8f905-133">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="8f905-134">在 CQD 中，從頁面頂端的功能表中選取 [**詳細報表**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-134">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="8f905-135">在左面板中，選取 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-135">In the left panel, select **Import**.</span></span> <span data-ttu-id="8f905-136">流覽至第一個 CQDX 範本，然後選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-136">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="8f905-137">在上傳範本之後，會出現一個快顯視窗，顯示「已成功匯入報告」訊息。</span><span class="sxs-lookup"><span data-stu-id="8f905-137">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="8f905-138">針對第二個 CQD 範本重複步驟2和3。</span><span class="sxs-lookup"><span data-stu-id="8f905-138">Repeat steps 2 and 3 for the second CQD template.</span></span>

> [!NOTE]
> <span data-ttu-id="8f905-139">每個使用者都必須將 CQD 範本匯入其 CQD 實例。</span><span class="sxs-lookup"><span data-stu-id="8f905-139">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="8f905-140">EUII 資料</span><span class="sxs-lookup"><span data-stu-id="8f905-140">EUII data</span></span>

<span data-ttu-id="8f905-141">出於合規性考慮，使用者可辨識的資訊（EUII）資料（也稱為個人身分資訊或 PII）只會保留30天。</span><span class="sxs-lookup"><span data-stu-id="8f905-141">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 30 days.</span></span> <span data-ttu-id="8f905-142">隨著 NRT 資料超過30日標記，包含 EUII 的欄位會被清除，從而產生 EUII 免費 NRT 資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-142">As NRT data crosses the 30-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="8f905-143">包含 EUII 資料的欄位如下：</span><span class="sxs-lookup"><span data-stu-id="8f905-143">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="8f905-144">完整 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8f905-144">Full IP address</span></span>
- <span data-ttu-id="8f905-145">媒體存取控制（MAC）位址</span><span class="sxs-lookup"><span data-stu-id="8f905-145">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="8f905-146">基本服務組識別元（BSSID）</span><span class="sxs-lookup"><span data-stu-id="8f905-146">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="8f905-147">會話初始通訊協定（SIP） URI （僅適用于商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="8f905-147">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="8f905-148">使用者主體名稱（UPN）</span><span class="sxs-lookup"><span data-stu-id="8f905-148">User Principal Name (UPN)</span></span>
- <span data-ttu-id="8f905-149">電腦端點名稱</span><span class="sxs-lookup"><span data-stu-id="8f905-149">Machine Endpoint Name</span></span>
- <span data-ttu-id="8f905-150">使用者逐字的意見反應</span><span class="sxs-lookup"><span data-stu-id="8f905-150">User Verbatim Feedback</span></span>
- <span data-ttu-id="8f905-151">物件識別碼（端點使用者的 Active Directory 物件識別碼）</span><span class="sxs-lookup"><span data-stu-id="8f905-151">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="8f905-152">擁有及不含 EUII 存取權的管理員角色</span><span class="sxs-lookup"><span data-stu-id="8f905-152">Admin roles with and without EUII access</span></span>

<span data-ttu-id="8f905-153">這些[RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview)角色**有**EUII 存取權：</span><span class="sxs-lookup"><span data-stu-id="8f905-153">These [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="8f905-154">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="8f905-154">Global Admin</span></span>
- <span data-ttu-id="8f905-155">團隊服務管理員</span><span class="sxs-lookup"><span data-stu-id="8f905-155">Teams Service Admin</span></span>
- <span data-ttu-id="8f905-156">團隊溝通系統管理員</span><span class="sxs-lookup"><span data-stu-id="8f905-156">Teams Communications Admin</span></span>
- <span data-ttu-id="8f905-157">Teams 通訊支援工程師</span><span class="sxs-lookup"><span data-stu-id="8f905-157">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="8f905-158">全域閱讀程式</span><span class="sxs-lookup"><span data-stu-id="8f905-158">Global Reader</span></span>
- <span data-ttu-id="8f905-159">商務用 Skype 系統管理員</span><span class="sxs-lookup"><span data-stu-id="8f905-159">Skype for Business Admin</span></span>

<span data-ttu-id="8f905-160">這些 RBAC 角色**沒有**EUII 存取權：</span><span class="sxs-lookup"><span data-stu-id="8f905-160">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="8f905-161">報表閱讀程式</span><span class="sxs-lookup"><span data-stu-id="8f905-161">Reports Reader</span></span>
- <span data-ttu-id="8f905-162">團隊溝通支援專家</span><span class="sxs-lookup"><span data-stu-id="8f905-162">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="8f905-163">日期控制項</span><span class="sxs-lookup"><span data-stu-id="8f905-163">Date controls</span></span>

<span data-ttu-id="8f905-164">CQD 支援下列滾動趨勢類型：</span><span class="sxs-lookup"><span data-stu-id="8f905-164">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="8f905-165">5天</span><span class="sxs-lookup"><span data-stu-id="8f905-165">5-day</span></span>
- <span data-ttu-id="8f905-166">7天</span><span class="sxs-lookup"><span data-stu-id="8f905-166">7-day</span></span>
- <span data-ttu-id="8f905-167">30天</span><span class="sxs-lookup"><span data-stu-id="8f905-167">30-day</span></span>
- <span data-ttu-id="8f905-168">60-日</span><span class="sxs-lookup"><span data-stu-id="8f905-168">60-day</span></span>
- <span data-ttu-id="8f905-169">90-日</span><span class="sxs-lookup"><span data-stu-id="8f905-169">90-day</span></span>

<span data-ttu-id="8f905-170">URL 日期參數會接受 Day 欄位。</span><span class="sxs-lookup"><span data-stu-id="8f905-170">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="8f905-171">[日常報告] 使用 YYYY MM 格式中指定的日期做為趨勢的最後一天。</span><span class="sxs-lookup"><span data-stu-id="8f905-171">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="8f905-172">URL 日期參數 "00" 代表 "today"。</span><span class="sxs-lookup"><span data-stu-id="8f905-172">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="8f905-173">網址</span><span class="sxs-lookup"><span data-stu-id="8f905-173">URL</span></span>| <span data-ttu-id="8f905-174">滾動日趨勢的結束日期</span><span class="sxs-lookup"><span data-stu-id="8f905-174">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="8f905-175"><span>HTTPs:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="8f905-175"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="8f905-176">2019年2月的目前日期</span><span class="sxs-lookup"><span data-stu-id="8f905-176">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="8f905-177"><span>HTTPs:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="8f905-177"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="8f905-178">2019年2月15日</span><span class="sxs-lookup"><span data-stu-id="8f905-178">Feb 15, 2019</span></span>|
|<span data-ttu-id="8f905-179"><span>HTTPs:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="8f905-179"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="8f905-180">當天</span><span class="sxs-lookup"><span data-stu-id="8f905-180">Current Day</span></span>|
|||

<span data-ttu-id="8f905-181">根據預設，月份的目前日期是作為滾動日期趨勢的最後一天。</span><span class="sxs-lookup"><span data-stu-id="8f905-181">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="8f905-182">CQD 報表中的可用資料</span><span class="sxs-lookup"><span data-stu-id="8f905-182">Data available in CQD reports</span></span>

<span data-ttu-id="8f905-183">預設摘要和詳細的 CQD 報表可能是您管理組織通話品質所需的全部。如有需要，您可以[建立自訂報表](#create-custom-detailed-reports)。</span><span class="sxs-lookup"><span data-stu-id="8f905-183">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="8f905-184">如果您想要使用 Power BI 來分析 CQD 資料，請參閱[使用 POWER bi 來分析團隊的 CQD 資料](CQD-Power-BI-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="8f905-184">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="8f905-185">功能</span><span class="sxs-lookup"><span data-stu-id="8f905-185">Feature</span></span>|<span data-ttu-id="8f905-186">摘要報告</span><span class="sxs-lookup"><span data-stu-id="8f905-186">Summary Reports</span></span>|<span data-ttu-id="8f905-187">詳細報告</span><span class="sxs-lookup"><span data-stu-id="8f905-187">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="8f905-188">應用程式共用躍點數</span><span class="sxs-lookup"><span data-stu-id="8f905-188">Application sharing metric</span></span> | <span data-ttu-id="8f905-189">否</span><span class="sxs-lookup"><span data-stu-id="8f905-189">No</span></span> | <span data-ttu-id="8f905-190">是</span><span class="sxs-lookup"><span data-stu-id="8f905-190">Yes</span></span> |
|<span data-ttu-id="8f905-191">客戶建立資訊支援</span><span class="sxs-lookup"><span data-stu-id="8f905-191">Customer building information support</span></span> | <span data-ttu-id="8f905-192">是</span><span class="sxs-lookup"><span data-stu-id="8f905-192">Yes</span></span> | <span data-ttu-id="8f905-193">是</span><span class="sxs-lookup"><span data-stu-id="8f905-193">Yes</span></span> |
|<span data-ttu-id="8f905-194">用戶端點資訊支援</span><span class="sxs-lookup"><span data-stu-id="8f905-194">Customer endpoint information support</span></span> | <span data-ttu-id="8f905-195">僅限 <span> cqd.teams.microsoft.com<span/></span><span class="sxs-lookup"><span data-stu-id="8f905-195">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="8f905-196">僅限 <span> cqd.teams.microsoft.com<span/></span><span class="sxs-lookup"><span data-stu-id="8f905-196">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="8f905-197">深化分析支援</span><span class="sxs-lookup"><span data-stu-id="8f905-197">Drill down analysis support</span></span>   | <span data-ttu-id="8f905-198">否</span><span class="sxs-lookup"><span data-stu-id="8f905-198">No</span></span>   | <span data-ttu-id="8f905-199">是</span><span class="sxs-lookup"><span data-stu-id="8f905-199">Yes</span></span>   |
|<span data-ttu-id="8f905-200">媒體可靠性度量單位</span><span class="sxs-lookup"><span data-stu-id="8f905-200">Media reliability metrics</span></span>   | <span data-ttu-id="8f905-201">否</span><span class="sxs-lookup"><span data-stu-id="8f905-201">No</span></span>   | <span data-ttu-id="8f905-202">是</span><span class="sxs-lookup"><span data-stu-id="8f905-202">Yes</span></span>   |
|<span data-ttu-id="8f905-203">外框報告</span><span class="sxs-lookup"><span data-stu-id="8f905-203">Out-of-the-box reports</span></span>   | <span data-ttu-id="8f905-204">是</span><span class="sxs-lookup"><span data-stu-id="8f905-204">Yes</span></span>   | <span data-ttu-id="8f905-205">是</span><span class="sxs-lookup"><span data-stu-id="8f905-205">Yes</span></span>   |
|<span data-ttu-id="8f905-206">[總覽] 報表</span><span class="sxs-lookup"><span data-stu-id="8f905-206">Overview reports</span></span>   | <span data-ttu-id="8f905-207">是</span><span class="sxs-lookup"><span data-stu-id="8f905-207">Yes</span></span>   | <span data-ttu-id="8f905-208">是</span><span class="sxs-lookup"><span data-stu-id="8f905-208">Yes</span></span>   |
|<span data-ttu-id="8f905-209">每個使用者的報表集</span><span class="sxs-lookup"><span data-stu-id="8f905-209">Per-user report set</span></span>   | <span data-ttu-id="8f905-210">否</span><span class="sxs-lookup"><span data-stu-id="8f905-210">No</span></span>   | <span data-ttu-id="8f905-211">是</span><span class="sxs-lookup"><span data-stu-id="8f905-211">Yes</span></span>   |
|<span data-ttu-id="8f905-212">報表集自訂（新增、刪除、修改報告）</span><span class="sxs-lookup"><span data-stu-id="8f905-212">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="8f905-213">否</span><span class="sxs-lookup"><span data-stu-id="8f905-213">No</span></span>   | <span data-ttu-id="8f905-214">是</span><span class="sxs-lookup"><span data-stu-id="8f905-214">Yes</span></span>   |
|<span data-ttu-id="8f905-215">以影片為基礎的畫面共用規格</span><span class="sxs-lookup"><span data-stu-id="8f905-215">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="8f905-216">否</span><span class="sxs-lookup"><span data-stu-id="8f905-216">No</span></span>   | <span data-ttu-id="8f905-217">是</span><span class="sxs-lookup"><span data-stu-id="8f905-217">Yes</span></span>   |
|<span data-ttu-id="8f905-218">影片度量單位</span><span class="sxs-lookup"><span data-stu-id="8f905-218">Video metrics</span></span>   | <span data-ttu-id="8f905-219">否</span><span class="sxs-lookup"><span data-stu-id="8f905-219">No</span></span>   | <span data-ttu-id="8f905-220">是</span><span class="sxs-lookup"><span data-stu-id="8f905-220">Yes</span></span>   |
|<span data-ttu-id="8f905-221">可用的資料量</span><span class="sxs-lookup"><span data-stu-id="8f905-221">Amount of data available</span></span>   | <span data-ttu-id="8f905-222">過去12個月</span><span class="sxs-lookup"><span data-stu-id="8f905-222">Last 12 months</span></span>   | <span data-ttu-id="8f905-223">過去12個月</span><span class="sxs-lookup"><span data-stu-id="8f905-223">Last 12 months</span></span>   |
|<span data-ttu-id="8f905-224">Microsoft 團隊資料</span><span class="sxs-lookup"><span data-stu-id="8f905-224">Microsoft Teams data</span></span>   | <span data-ttu-id="8f905-225">是</span><span class="sxs-lookup"><span data-stu-id="8f905-225">Yes</span></span>   | <span data-ttu-id="8f905-226">是</span><span class="sxs-lookup"><span data-stu-id="8f905-226">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="8f905-227">選取要在報表中查看的產品資料</span><span class="sxs-lookup"><span data-stu-id="8f905-227">Select product data to see in reports</span></span>

<span data-ttu-id="8f905-228">在摘要和位置增強的報表中，您可以使用 [**產品篩選**] 下拉式清單來顯示所有產品資料、只顯示 Microsoft 團隊資料，或只顯示商務用 Skype Online 資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-228">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![螢幕擷取畫面：顯示 [產品] 篩選控制項選項](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="8f905-230">在 [詳細報告] 中，您可以使用 [**成為團隊**維度] 來篩選資料至 Microsoft 團隊或商務用 Skype Online 資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-230">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="8f905-231">摘要報告</span><span class="sxs-lookup"><span data-stu-id="8f905-231">Summary Reports</span></span>

<span data-ttu-id="8f905-232">這些是您在第一次登入 CQD 時，在 CQD 儀表板上看到的報表。</span><span class="sxs-lookup"><span data-stu-id="8f905-232">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="8f905-233">它們能讓您一目了然，透過每天、每月和表格報告來查看品質趨勢，以協助識別品質較差的子網。</span><span class="sxs-lookup"><span data-stu-id="8f905-233">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

|<span data-ttu-id="8f905-234">Tab</span><span class="sxs-lookup"><span data-stu-id="8f905-234">Tab</span></span>  |  |
|---------|---------|
|<span data-ttu-id="8f905-235">整體通話品質</span><span class="sxs-lookup"><span data-stu-id="8f905-235">Overall Call Quality</span></span>     | <span data-ttu-id="8f905-236">[其他 3] 索引標籤的匯總</span><span class="sxs-lookup"><span data-stu-id="8f905-236">Aggregate of the other 3 tabs</span></span>        |
|<span data-ttu-id="8f905-237">伺服器-用戶端</span><span class="sxs-lookup"><span data-stu-id="8f905-237">Server—Client</span></span>     |<span data-ttu-id="8f905-238">伺服器與用戶端端點之間的資料流程詳細資料</span><span class="sxs-lookup"><span data-stu-id="8f905-238">Details of the streams between server and client endpoints</span></span>         |
|<span data-ttu-id="8f905-239">用戶端-用戶端</span><span class="sxs-lookup"><span data-stu-id="8f905-239">Client—Client</span></span>     |<span data-ttu-id="8f905-240">兩個用戶端端點之間的資料流程詳細資料</span><span class="sxs-lookup"><span data-stu-id="8f905-240">Details of the streams between two client endpoints</span></span>         |
|<span data-ttu-id="8f905-241">語音品質 SLA</span><span class="sxs-lookup"><span data-stu-id="8f905-241">Voice Quality SLA</span></span>     |<span data-ttu-id="8f905-242">商務用 Skype 語音品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)中包含的通話資訊</span><span class="sxs-lookup"><span data-stu-id="8f905-242">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)</span></span>         |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="8f905-243">[整體通話品質] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="8f905-243">Overall Call Quality tab</span></span>

<span data-ttu-id="8f905-244">使用此索引標籤上的資料來評估通話品質狀態，以及根據串流數與較差百分比的趨勢。</span><span class="sxs-lookup"><span data-stu-id="8f905-244">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="8f905-245">右上角的圖例會顯示哪些色彩和視覺元素代表這些度量單位。</span><span class="sxs-lookup"><span data-stu-id="8f905-245">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![螢幕擷取畫面：顯示 [通話品質] 索引標籤](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="8f905-247">串流分為三個群組： [完好]、[差] 和 [未分類]。</span><span class="sxs-lookup"><span data-stu-id="8f905-247">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="8f905-248">此外，也會計算出*較差的%* 值，可讓您將資料流程分類為不*佳*至總分類資料流程計數的比例。</span><span class="sxs-lookup"><span data-stu-id="8f905-248">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="8f905-249">由於*差% = 無法正常使用的資料流程/（資料流程 + 良好資料流程） \* 100*，*糟糕的%* 不會受到多個未*分類*資料流程的存在影響。</span><span class="sxs-lookup"><span data-stu-id="8f905-249">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="8f905-250">若要查看如何將串流分類為不良或良好，請參閱[通話品質儀表板中的資料流程分類](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="8f905-250">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="8f905-251">使用左邊的刻度來測量串流計數值。</span><span class="sxs-lookup"><span data-stu-id="8f905-251">Use the scale on the left to measure the stream count values.</span></span>
  
![螢幕擷取畫面：顯示資料流程計數值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="8f905-253">使用右側的刻度來測量較差的% 值。</span><span class="sxs-lookup"><span data-stu-id="8f905-253">Use the scale on the right to measure the Poor % values.</span></span>
  
![螢幕擷取畫面：顯示差% 的值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="8f905-255">您也可以將滑鼠游標停留在列上方，以取得實際數值。</span><span class="sxs-lookup"><span data-stu-id="8f905-255">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f905-256">下列範例是來自非常小的範例資料集，且這些值對於實際部署而言並不切合實際。</span><span class="sxs-lookup"><span data-stu-id="8f905-256">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![螢幕擷取畫面：顯示用來存取資料的滑鼠](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="8f905-258">整個串流大量可協助判斷計算出的低百分比。</span><span class="sxs-lookup"><span data-stu-id="8f905-258">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="8f905-259">總體資料流程的數量越小，報告的低百分比值就越不可靠。</span><span class="sxs-lookup"><span data-stu-id="8f905-259">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="8f905-260">[伺服器-用戶端] 索引標籤和用戶端用戶端索引標籤</span><span class="sxs-lookup"><span data-stu-id="8f905-260">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="8f905-261">這兩個索引標籤提供在其端點對端點案例中所發生之資料流程的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-261">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="8f905-262">[伺服器-用戶端] 索引標籤有四個可折迭的區段，分別代表媒體資料流程流向的四種案例。</span><span class="sxs-lookup"><span data-stu-id="8f905-262">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="8f905-263">有線內</span><span class="sxs-lookup"><span data-stu-id="8f905-263">Wired Inside</span></span>
- <span data-ttu-id="8f905-264">外有線</span><span class="sxs-lookup"><span data-stu-id="8f905-264">Wired Outside</span></span>
- <span data-ttu-id="8f905-265">內部 WiFi</span><span class="sxs-lookup"><span data-stu-id="8f905-265">WiFi Inside</span></span>
- <span data-ttu-id="8f905-266">WiFi 外</span><span class="sxs-lookup"><span data-stu-id="8f905-266">WiFi Outside</span></span>

<span data-ttu-id="8f905-267">同樣地，[用戶端-用戶端] 索引標籤有五個可折疊區段：</span><span class="sxs-lookup"><span data-stu-id="8f905-267">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="8f905-268">有線內-內側-有線</span><span class="sxs-lookup"><span data-stu-id="8f905-268">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="8f905-269">有線內-向外佈線</span><span class="sxs-lookup"><span data-stu-id="8f905-269">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="8f905-270">有線外-有線外側</span><span class="sxs-lookup"><span data-stu-id="8f905-270">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="8f905-271">內側無線內-WiFi 內側</span><span class="sxs-lookup"><span data-stu-id="8f905-271">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="8f905-272">內側無線-WiFi 外</span><span class="sxs-lookup"><span data-stu-id="8f905-272">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="8f905-273">內部與外部</span><span class="sxs-lookup"><span data-stu-id="8f905-273">Inside versus Outside</span></span>

<span data-ttu-id="8f905-274">CQD 使用建築物資訊（如果有的話）將串流分類為*內部*或*外部*。</span><span class="sxs-lookup"><span data-stu-id="8f905-274">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="8f905-275">每個串流的端點都會與子網位址產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8f905-275">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="8f905-276">如果子網位於已上傳的建築物資訊中標示為 InsideCorp 的子網清單中，則會被視為*內部*。</span><span class="sxs-lookup"><span data-stu-id="8f905-276">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="8f905-277">如果建築物資訊尚未上傳，請在測試中永遠將串流分類為*外部*。</span><span class="sxs-lookup"><span data-stu-id="8f905-277">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="8f905-278">伺服器用戶端案例的內部測試只會考慮用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="8f905-278">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="8f905-279">因為伺服器永遠都不是從使用者的角度來看，所以在測試中並不考慮。</span><span class="sxs-lookup"><span data-stu-id="8f905-279">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="8f905-280">有線與 WiFi</span><span class="sxs-lookup"><span data-stu-id="8f905-280">Wired versus WiFi</span></span>

<span data-ttu-id="8f905-281">如名稱所指出，分類準則是以用戶端連線的類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="8f905-281">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="8f905-282">伺服器一直是有線的，不會包含在計算中。</span><span class="sxs-lookup"><span data-stu-id="8f905-282">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="8f905-283">在指定的資料流程中，如果兩個端點中有一個連接至 WiFi 網路，則 CQD 會將它分類為 WiFi。</span><span class="sxs-lookup"><span data-stu-id="8f905-283">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>
> [!NOTE]
> <span data-ttu-id="8f905-284">如果有一個資料流程，如果兩個端點中有一個連接至 WiFi 網路，則會在 CQD 中分類為 WiFi。</span><span class="sxs-lookup"><span data-stu-id="8f905-284">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="8f905-285">租使用者資料資訊</span><span class="sxs-lookup"><span data-stu-id="8f905-285">Tenant Data information</span></span>

<span data-ttu-id="8f905-286">CQD 摘要報告儀表板包含**租使用者資料上傳**頁面，方法是從右上角的 [設定] 功能表中選取 [**租使用者資料上傳**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-286">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="8f905-287">此頁面可供系統管理員上傳自己的資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="8f905-287">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="8f905-288">IP 位址與地理位置資訊的地圖</span><span class="sxs-lookup"><span data-stu-id="8f905-288">A map of IP address and geographical information</span></span>
- <span data-ttu-id="8f905-289">每個無線 AP 及其 MAC 位址的地圖</span><span class="sxs-lookup"><span data-stu-id="8f905-289">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="8f905-290">端點和模型/類型等的端點地圖。</span><span class="sxs-lookup"><span data-stu-id="8f905-290">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="8f905-291">我們建議您上傳您的租使用者、組建及位置資料，好讓 CQD 可在報表中包含這項資訊。</span><span class="sxs-lookup"><span data-stu-id="8f905-291">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="8f905-292">如果您尚未上傳這些資料，請閱讀[上傳租使用者及組建資料](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="8f905-292">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="8f905-293">詳細報告</span><span class="sxs-lookup"><span data-stu-id="8f905-293">Detailed reports</span></span>

|<span data-ttu-id="8f905-294">名稱</span><span class="sxs-lookup"><span data-stu-id="8f905-294">Name</span></span>  |  |
|---------|---------|
|<span data-ttu-id="8f905-295">位置改進的報表</span><span class="sxs-lookup"><span data-stu-id="8f905-295">Location-Enhanced Reports</span></span>     |<span data-ttu-id="8f905-296">根據位置資訊顯示品質趨勢。</span><span class="sxs-lookup"><span data-stu-id="8f905-296">Shows quality trends based on location information.</span></span> <span data-ttu-id="8f905-297">只有在您[上傳租使用者資料](CQD-upload-tenant-building-data.md)後，才會顯示此報告。</span><span class="sxs-lookup"><span data-stu-id="8f905-297">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="8f905-298">可靠性報告</span><span class="sxs-lookup"><span data-stu-id="8f905-298">Reliability Reports</span></span>     |<span data-ttu-id="8f905-299">包括音訊、影片、影片畫面共用（VBSS），以及應用程式共用報告</span><span class="sxs-lookup"><span data-stu-id="8f905-299">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports</span></span>         |
|<span data-ttu-id="8f905-300">經驗品質報告</span><span class="sxs-lookup"><span data-stu-id="8f905-300">Quality of Experience Reports</span></span>     |<span data-ttu-id="8f905-301">所有用戶端和裝置的音訊品質與可靠性，包括會議室。</span><span class="sxs-lookup"><span data-stu-id="8f905-301">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="8f905-302">這些報告是一種「slimmed」的可下載[CQD 範本](https://aka.ms/QERtemplates)版本，側重在分析音訊品質與可靠性的重要區域上。</span><span class="sxs-lookup"><span data-stu-id="8f905-302">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="8f905-303">品質深入分析報表</span><span class="sxs-lookup"><span data-stu-id="8f905-303">Quality Drill Down Reports</span></span>     | <span data-ttu-id="8f905-304">深化：依地區、位置、子網、小時與使用者的日期</span><span class="sxs-lookup"><span data-stu-id="8f905-304">Drill downs: Date by region, locations, subnets, hour, and users</span></span>         |
|<span data-ttu-id="8f905-305">深入分析報表</span><span class="sxs-lookup"><span data-stu-id="8f905-305">Failure Drill Down Reports</span></span>     | <span data-ttu-id="8f905-306">深化：依地區、位置、子網、小時與使用者的日期</span><span class="sxs-lookup"><span data-stu-id="8f905-306">Drill downs: Date by region, locations, subnets, hour, and users</span></span>        |
|<span data-ttu-id="8f905-307">評價我的通話報告</span><span class="sxs-lookup"><span data-stu-id="8f905-307">Rate My Call Reports</span></span>     |<span data-ttu-id="8f905-308">依地區、位置或使用者分析使用者通話評等。</span><span class="sxs-lookup"><span data-stu-id="8f905-308">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="8f905-309">包括原義的意見反應。</span><span class="sxs-lookup"><span data-stu-id="8f905-309">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="8f905-310">技術支援中心報告</span><span class="sxs-lookup"><span data-stu-id="8f905-310">Help Desk Reports</span></span>     |<span data-ttu-id="8f905-311">問訊台報告：針對個別使用者、使用者群組或每個人，查看通話與會議資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-311">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="8f905-312">這些報告結合了建立與 EUII 資料，可協助根據網路位置、會議詳細資料、裝置或固件來識別可能的系統問題。</span><span class="sxs-lookup"><span data-stu-id="8f905-312">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="8f905-313">用戶端版本報告</span><span class="sxs-lookup"><span data-stu-id="8f905-313">Client Version Reports</span></span>     |<span data-ttu-id="8f905-314">用戶端版本摘要：針對每個用戶端 app 版本，查看會話與使用者計數</span><span class="sxs-lookup"><span data-stu-id="8f905-314">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="8f905-315">用戶端版本（依使用者）：查看每個用戶端 app 版本的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="8f905-315">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="8f905-316">針對產品和用戶端類型預先建立的篩選，可協助將版本集中到特定的用戶端。</span><span class="sxs-lookup"><span data-stu-id="8f905-316">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="8f905-317">端點報告</span><span class="sxs-lookup"><span data-stu-id="8f905-317">Endpoint Reports</span></span>     |<span data-ttu-id="8f905-318">依電腦端點（電腦品牌與模型）顯示通話品質。</span><span class="sxs-lookup"><span data-stu-id="8f905-318">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="8f905-319">這些報表包括建立資料（如果您已上傳）。</span><span class="sxs-lookup"><span data-stu-id="8f905-319">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="8f905-320">建立自訂的詳細報告</span><span class="sxs-lookup"><span data-stu-id="8f905-320">Create custom detailed reports</span></span>

<span data-ttu-id="8f905-321">如果預設的 CQD 報表不符合您的需求，請使用這些指示來建立自訂報表。</span><span class="sxs-lookup"><span data-stu-id="8f905-321">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="8f905-322">或者（從2020年1月起）[請改為使用 POWER BI 來 CQD 報告](cqd-power-bi-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="8f905-322">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="8f905-323">從 [登入摘要報告] 畫面所顯示之畫面頂端的 [報告] 下拉式清單中， \( **Summary Reports** \) 選取 [**詳細報告**]，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-323">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="8f905-324">按一下報表中的 [**編輯**]，即可查看 [查詢編輯器]。</span><span class="sxs-lookup"><span data-stu-id="8f905-324">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="8f905-325">每個報告都會以查詢的方式支援到立方體中。</span><span class="sxs-lookup"><span data-stu-id="8f905-325">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="8f905-326">報表是其查詢所傳回資料的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="8f905-326">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="8f905-327">[查詢編輯器] 可協助您編輯這些查詢和報表的顯示選項。</span><span class="sxs-lookup"><span data-stu-id="8f905-327">The Query Editor helps you edit these queries and the display options of the report.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="8f905-328">網路範圍可用來代表 supernet （多個子網與單一路由前置詞的組合）。</span><span class="sxs-lookup"><span data-stu-id="8f905-328">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="8f905-329">所有新的建築物上傳都會被檢查，以取得任何重迭的範圍。</span><span class="sxs-lookup"><span data-stu-id="8f905-329">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="8f905-330">如果您先前上傳的是組建檔案，您應該下載目前的檔案，然後重新上傳以找出任何重疊，並修正問題，然後再重新上傳。</span><span class="sxs-lookup"><span data-stu-id="8f905-330">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="8f905-331">先前上傳的檔案中的任何交疊，可能會導致無法正確地將子網對應至報表中的建築物。</span><span class="sxs-lookup"><span data-stu-id="8f905-331">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="8f905-332">某些 VPN 實現不會精確地報告子網資訊。</span><span class="sxs-lookup"><span data-stu-id="8f905-332">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="8f905-333">建議將 VPN 子網新增至組建檔案，而不是子網的一個專案時，會針對 VPN 子網中的每個位址，為個別的32位網路新增個別專案。</span><span class="sxs-lookup"><span data-stu-id="8f905-333">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="8f905-334">每個資料列都可以有相同的建築物中繼資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-334">Each row can have the same building metadata.</span></span> <span data-ttu-id="8f905-335">例如，172.16.18.0/24 不只一列，您應該有256列，每個位址都有一個資料列，其中每個位址都在 172.16.18.0/32 和 172.16.18.255/32 之間（含）。</span><span class="sxs-lookup"><span data-stu-id="8f905-335">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="8f905-336">[VPN] 欄是選擇性的，預設為0。</span><span class="sxs-lookup"><span data-stu-id="8f905-336">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="8f905-337">如果 VPN 欄的值設為1，則該資料列所代表的子網將會完全展開，以符合子網中的所有 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8f905-337">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="8f905-338">請謹慎使用這個方式，然後只針對 VPN 子網，因為完全擴充這些子網會對涉及建立資料之查詢的查詢時間造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="8f905-338">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="8f905-339">指向報表中的 [橫條圖] 和 [趨勢線]，以顯示詳細值。</span><span class="sxs-lookup"><span data-stu-id="8f905-339">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="8f905-340">具有焦點的報表會顯示 [動作] 功能表： [**編輯**]、[**克隆**]、[**刪除**]、[**下載**] 和 [**匯出] 報表樹**。</span><span class="sxs-lookup"><span data-stu-id="8f905-340">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="8f905-341">查詢篩選</span><span class="sxs-lookup"><span data-stu-id="8f905-341">Query filters</span></span>

<span data-ttu-id="8f905-342">查詢篩選是透過使用 CQD 中的 [查詢編輯器] 來實現。</span><span class="sxs-lookup"><span data-stu-id="8f905-342">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="8f905-343">這些篩選可用來減少 CQD 傳回的記錄數，從而將報表的整體大小和查詢時間降至最低。</span><span class="sxs-lookup"><span data-stu-id="8f905-343">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="8f905-344">這對於篩選掉未受管理的網路特別有用。</span><span class="sxs-lookup"><span data-stu-id="8f905-344">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="8f905-345">下表所列的篩選使用正則運算式（RegEx）。</span><span class="sxs-lookup"><span data-stu-id="8f905-345">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="8f905-346">Filter</span><span class="sxs-lookup"><span data-stu-id="8f905-346">Filter</span></span>         | <span data-ttu-id="8f905-347">描述</span><span class="sxs-lookup"><span data-stu-id="8f905-347">Description</span></span>          | <span data-ttu-id="8f905-348">CQD 查詢篩選範例</span><span class="sxs-lookup"><span data-stu-id="8f905-348">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="8f905-349">沒有空白值</span><span class="sxs-lookup"><span data-stu-id="8f905-349">No blank values</span></span>   | <span data-ttu-id="8f905-350">有些篩選沒有選項可篩選空白值。</span><span class="sxs-lookup"><span data-stu-id="8f905-350">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="8f905-351">若要手動篩選空白值，請根據您的需求，使用空白運算式，並將篩選設定為 [等於] 或 [不等於]。</span><span class="sxs-lookup"><span data-stu-id="8f905-351">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="8f905-352">第二個建築物名稱 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="8f905-352">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="8f905-353">排除常見子網</span><span class="sxs-lookup"><span data-stu-id="8f905-353">Exclude common subnets</span></span> | <span data-ttu-id="8f905-354">若沒有有效的組建檔案，無法從非託管網路個別管理，就會將 [家用網路] 包含在報告中。</span><span class="sxs-lookup"><span data-stu-id="8f905-354">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="8f905-355">這些 home 子網不在其控制範圍內，而且可以從報表中快速排除。</span><span class="sxs-lookup"><span data-stu-id="8f905-355">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="8f905-356">在本指南中定義的常見子網是10.0.0.0、192.168.1.0 和192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="8f905-356">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="8f905-357">第二個子網 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1。0</span><span class="sxs-lookup"><span data-stu-id="8f905-357">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="8f905-358">僅限內部查看</span><span class="sxs-lookup"><span data-stu-id="8f905-358">View inside only</span></span>  | <span data-ttu-id="8f905-359">用來篩選受管理（內部）或非託管（外部）的報表。</span><span class="sxs-lookup"><span data-stu-id="8f905-359">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="8f905-360">受管理的 CQD 範本已預先設定了這些篩選器。</span><span class="sxs-lookup"><span data-stu-id="8f905-360">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="8f905-361">Corp = 內部的秒數</span><span class="sxs-lookup"><span data-stu-id="8f905-361">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="8f905-362">報表篩選</span><span class="sxs-lookup"><span data-stu-id="8f905-362">Report filters</span></span>

<span data-ttu-id="8f905-363">使用 CQD 報表篩選來縮小調查的重點。</span><span class="sxs-lookup"><span data-stu-id="8f905-363">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="8f905-364">您可以在 [查詢編輯器] 或直接在報表中，將篩選新增至所轉譯的報表中，以使用報表篩選。</span><span class="sxs-lookup"><span data-stu-id="8f905-364">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="8f905-365">下列報表篩選是在整個[CQD 範本](https://aka.ms/QERtemplates)中使用。</span><span class="sxs-lookup"><span data-stu-id="8f905-365">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="8f905-366">Filter</span><span class="sxs-lookup"><span data-stu-id="8f905-366">Filter</span></span>     | <span data-ttu-id="8f905-367">描述</span><span class="sxs-lookup"><span data-stu-id="8f905-367">Description</span></span>                            | <span data-ttu-id="8f905-368">CQD 報表篩選範例</span><span class="sxs-lookup"><span data-stu-id="8f905-368">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="8f905-369">月</span><span class="sxs-lookup"><span data-stu-id="8f905-369">Month</span></span>      | <span data-ttu-id="8f905-370">首先從年份開始，然後從月份開始。</span><span class="sxs-lookup"><span data-stu-id="8f905-370">Start with the year first, then month.</span></span> | <span data-ttu-id="8f905-371">2017-10</span><span class="sxs-lookup"><span data-stu-id="8f905-371">2017-10</span></span>                           |
| <span data-ttu-id="8f905-372">字母</span><span class="sxs-lookup"><span data-stu-id="8f905-372">Alphabetic</span></span> | <span data-ttu-id="8f905-373">篩選任何字母字元。</span><span class="sxs-lookup"><span data-stu-id="8f905-373">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="8f905-374">[a-z]</span><span class="sxs-lookup"><span data-stu-id="8f905-374">[a-z]</span></span>                             |
| <span data-ttu-id="8f905-375">小數</span><span class="sxs-lookup"><span data-stu-id="8f905-375">Numeric</span></span>    | <span data-ttu-id="8f905-376">篩選任何數位字元。</span><span class="sxs-lookup"><span data-stu-id="8f905-376">Filters for any numeric characters.</span></span>    | <span data-ttu-id="8f905-377">[0-9]</span><span class="sxs-lookup"><span data-stu-id="8f905-377">[0-9]</span></span>                             |
| <span data-ttu-id="8f905-378">百分</span><span class="sxs-lookup"><span data-stu-id="8f905-378">Percentage</span></span> | <span data-ttu-id="8f905-379">篩選百分比。</span><span class="sxs-lookup"><span data-stu-id="8f905-379">Filters for a percentage.</span></span>              | <span data-ttu-id="8f905-380">（[3-9] \\ 。） \|（[3-9]） \|（[1-9] [0-9]）</span><span class="sxs-lookup"><span data-stu-id="8f905-380">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="8f905-381">深化篩選</span><span class="sxs-lookup"><span data-stu-id="8f905-381">Drill-down filters</span></span>

<span data-ttu-id="8f905-382">CQD 報表功能有數個向下切入篩選，這些篩選是可縮小通話品質調查焦點的強大工具。</span><span class="sxs-lookup"><span data-stu-id="8f905-382">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="8f905-383">如果您選取 [向下切入] 欄位，報告會自動開啟適當的索引標籤，並篩選選取的值。</span><span class="sxs-lookup"><span data-stu-id="8f905-383">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="8f905-384">如果該索引標籤有自己的向下切入欄位，而其中一個是選取的，則會套用這兩組篩選，並逐漸縮小產生的資料集。</span><span class="sxs-lookup"><span data-stu-id="8f905-384">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![闡釋向下切入報表流程的圖表](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="8f905-386">新增及編輯向下切入欄位</span><span class="sxs-lookup"><span data-stu-id="8f905-386">Adding and editing drill-down fields</span></span>

<span data-ttu-id="8f905-387">編輯報表時，您可以選擇使用 [查詢編輯器] 來指定您自己的深化欄位。</span><span class="sxs-lookup"><span data-stu-id="8f905-387">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="8f905-388">首先按一下 **...**</span><span class="sxs-lookup"><span data-stu-id="8f905-388">Start by clicking **…**</span></span> <span data-ttu-id="8f905-389">針對您要編輯的報表，然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-389">for the report you want to edit, then select **Edit**.</span></span>

![編輯深化欄位的螢幕擷取畫面](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="8f905-391">從 [查詢編輯器] 左側的清單中選取維度。</span><span class="sxs-lookup"><span data-stu-id="8f905-391">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="8f905-392">然後按一下 [**流覽至**標籤] 底下的下拉式清單，然後選取您要該尺寸向下切入至其中的索引標籤和展開器群組。</span><span class="sxs-lookup"><span data-stu-id="8f905-392">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="8f905-393">注意：目前只有流覽至不同的索引標籤，才能使用 [深化] 功能。</span><span class="sxs-lookup"><span data-stu-id="8f905-393">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="8f905-394">稍後會新增對特定展開器進行鑽取的支援。</span><span class="sxs-lookup"><span data-stu-id="8f905-394">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="8f905-395">最後，按一下 [**關閉**]，儲存您對維度所做的變更，然後按一下 [**儲存**] 以儲存並關閉 [查詢編輯器]。</span><span class="sxs-lookup"><span data-stu-id="8f905-395">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![在 [查詢編輯器] 中選取維度的螢幕擷取畫面](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="8f905-397">多重選取篩選</span><span class="sxs-lookup"><span data-stu-id="8f905-397">Multi-select filters</span></span>

<span data-ttu-id="8f905-398">除了向下切入功能之外，CQD 也支援指定含多個值的篩選（或篩選）。</span><span class="sxs-lookup"><span data-stu-id="8f905-398">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="8f905-399">若要選取多個篩選值，請先將新篩選新增至報表。</span><span class="sxs-lookup"><span data-stu-id="8f905-399">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="8f905-400">按一下 **+** [**篩選**] 標籤旁的 [輸入您要使用的維度名稱]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-400">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![新增多重選取篩選的螢幕擷取畫面](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="8f905-402">接著，按一下 [**搜尋**] （新濾鏡旁的放大鏡圖示）。</span><span class="sxs-lookup"><span data-stu-id="8f905-402">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="8f905-403">您會看到一個 [文字] 欄位及許多選項，包括 [**全選**] 和 [**反相**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-403">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="8f905-404">輸入一個值，然後按一下該欄位旁邊的 [**搜尋**] 進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="8f905-404">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="8f905-405">或者，將 [文字] 欄位保留空白，然後按一下 [**搜尋**] 以查看前100個選項。</span><span class="sxs-lookup"><span data-stu-id="8f905-405">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="8f905-406">範例</span><span class="sxs-lookup"><span data-stu-id="8f905-406">Example:</span></span>  

![新增查詢篩選的螢幕擷取畫面](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="8f905-408">儀表板層級篩選</span><span class="sxs-lookup"><span data-stu-id="8f905-408">Dashboard level filters</span></span>
<span data-ttu-id="8f905-409">某些 CQD 報表會將儀表板層級篩選新增到其中，讓您可以輕鬆地依一般參數進行篩選。</span><span class="sxs-lookup"><span data-stu-id="8f905-409">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="8f905-410">這些篩選會出現在一般報表索引標籤之外，且直接位於 [產品] 篩選器下方，且適用于儀表板中的所有篩選器。</span><span class="sxs-lookup"><span data-stu-id="8f905-410">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![儀表板篩選的螢幕擷取畫面](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="8f905-412">URL 篩選</span><span class="sxs-lookup"><span data-stu-id="8f905-412">URL filters</span></span>

<span data-ttu-id="8f905-413">CQD 支援將篩選新增至 URL。</span><span class="sxs-lookup"><span data-stu-id="8f905-413">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="8f905-414">這可讓您輕鬆共用或為 CQD 查詢加上書簽。</span><span class="sxs-lookup"><span data-stu-id="8f905-414">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="8f905-415">您可以在 URL 中定義參數，例如 [趨勢月份]、[租使用者識別碼] 或 [語言]。</span><span class="sxs-lookup"><span data-stu-id="8f905-415">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="8f905-416">您也可以將產品或儀表板層級篩選新增至 URL。</span><span class="sxs-lookup"><span data-stu-id="8f905-416">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="8f905-417">如果您要修正受管理的建築物或網路（其中的同盟端點可能會影響您的報表），則從 CQD 報告排除同盟資料就很有用。</span><span class="sxs-lookup"><span data-stu-id="8f905-417">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="8f905-418">若要新增篩選，請將下列專案附加到 URL 的結尾：</span><span class="sxs-lookup"><span data-stu-id="8f905-418">To add a filter, append the following to the end of the URL:</span></span>

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="8f905-419">範例</span><span class="sxs-lookup"><span data-stu-id="8f905-419">Example:</span></span>  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

<span data-ttu-id="8f905-420">若要將儀表板層級篩選新增至 URL，該篩選必須以 [產品] 或 [儀表板層級] 篩選器存在於 CQD 中。</span><span class="sxs-lookup"><span data-stu-id="8f905-420">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="8f905-421">在趨勢月份之後及 URL 參數之前，將這些篩選新增至 URL：</span><span class="sxs-lookup"><span data-stu-id="8f905-421">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

```filter/DATA_MODEL_NAME|VALUE```

<span data-ttu-id="8f905-422">例如，若要套用 Microsoft 團隊的產品篩選值，您必須加入下列專案：</span><span class="sxs-lookup"><span data-stu-id="8f905-422">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

```filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="8f905-423">整個 URL 看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="8f905-423">Your entire URL would look something like this:</span></span>

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="8f905-424">若要套用含多重選取值的 URL 篩選，請使用管道（|）字元來分隔每個值。</span><span class="sxs-lookup"><span data-stu-id="8f905-424">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="8f905-425">例如：</span><span class="sxs-lookup"><span data-stu-id="8f905-425">For example:</span></span>

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

<span data-ttu-id="8f905-426">如果您指定不正確名稱或值，就不會套用 URL 篩選。</span><span class="sxs-lookup"><span data-stu-id="8f905-426">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="8f905-427">您可以使用 URL 篩選來篩選特定維度的每個報表。</span><span class="sxs-lookup"><span data-stu-id="8f905-427">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="8f905-428">最常見的 URL 篩選是用來篩選報告，以排除同盟參與者遙測，或只將焦點集中在團隊或商務用 Skype Online 上。</span><span class="sxs-lookup"><span data-stu-id="8f905-428">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="8f905-429">如果您要修正受管理的建築物或網路（其中的同盟端點可能會影響您的報表），則從 CQD 報告排除同盟資料就很有用。</span><span class="sxs-lookup"><span data-stu-id="8f905-429">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="8f905-430">Filter</span><span class="sxs-lookup"><span data-stu-id="8f905-430">Filter</span></span>         | <span data-ttu-id="8f905-431">描述</span><span class="sxs-lookup"><span data-stu-id="8f905-431">Description</span></span>          | <span data-ttu-id="8f905-432">CQD 查詢篩選範例</span><span class="sxs-lookup"><span data-stu-id="8f905-432">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="8f905-433">沒有空白值</span><span class="sxs-lookup"><span data-stu-id="8f905-433">No blank values</span></span>   | <span data-ttu-id="8f905-434">有些篩選沒有選項可篩選空白值。</span><span class="sxs-lookup"><span data-stu-id="8f905-434">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="8f905-435">若要手動篩選空白值，請根據您的需求，使用空白運算式，並將篩選設定為 [等於] 或 [不等於]。</span><span class="sxs-lookup"><span data-stu-id="8f905-435">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="8f905-436">第二個建築物名稱 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="8f905-436">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="8f905-437">排除常見子網</span><span class="sxs-lookup"><span data-stu-id="8f905-437">Exclude common subnets</span></span> | <span data-ttu-id="8f905-438">若沒有有效的組建檔案，無法從非託管網路個別管理，就會將 [家用網路] 包含在報告中。</span><span class="sxs-lookup"><span data-stu-id="8f905-438">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="8f905-439">這些 home 子網不在其控制範圍內，而且可以從報表中快速排除。</span><span class="sxs-lookup"><span data-stu-id="8f905-439">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="8f905-440">如本文所定義，常見的子網是10.0.0.0、192.168.1.0 和192.168.0.0。</span><span class="sxs-lookup"><span data-stu-id="8f905-440">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="8f905-441">第二個子網 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1。0</span><span class="sxs-lookup"><span data-stu-id="8f905-441">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="8f905-442">僅限內部查看</span><span class="sxs-lookup"><span data-stu-id="8f905-442">View inside only</span></span>  | <span data-ttu-id="8f905-443">用來篩選受管理（內部）或非託管（外部）的報表。</span><span class="sxs-lookup"><span data-stu-id="8f905-443">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="8f905-444">受管理的 CQD 範本已預先設定了這些篩選器。</span><span class="sxs-lookup"><span data-stu-id="8f905-444">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="8f905-445">Corp = 內部的秒數</span><span class="sxs-lookup"><span data-stu-id="8f905-445">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="8f905-446">如何尋找您的租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="8f905-446">How to find your tenant ID</span></span>

<span data-ttu-id="8f905-447">CQD 中的租使用者識別碼會對應到 Azure 中的目錄 ID。</span><span class="sxs-lookup"><span data-stu-id="8f905-447">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="8f905-448">如果您不知道您的目錄識別碼，您可以在 Azure 入口網站中找到：</span><span class="sxs-lookup"><span data-stu-id="8f905-448">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="8f905-449">登入 Microsoft Azure 入口網站：<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="8f905-449">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="8f905-450">選取 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-450">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="8f905-451">在 [**管理**] 底下，選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-451">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="8f905-452">您的租使用者識別碼位於 [**目錄識別碼**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="8f905-452">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="8f905-453">您也可以使用 PowerShell 來尋找您的租使用者識別碼：</span><span class="sxs-lookup"><span data-stu-id="8f905-453">You can also find your tenant ID by using PowerShell:</span></span> 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="8f905-454">比較團隊與商務用 Skype CQD 資料</span><span class="sxs-lookup"><span data-stu-id="8f905-454">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="8f905-455">即使是在最新的 CQD （cqd.teams.microsoft.com）中，您也會看到團隊和商務用 Skype 之間資料的差異。</span><span class="sxs-lookup"><span data-stu-id="8f905-455">Even within the latest CQD (cqd.teams.microsoft.com), you'll see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="8f905-456">原因如下：</span><span class="sxs-lookup"><span data-stu-id="8f905-456">Some reasons:</span></span>
- <span data-ttu-id="8f905-457">確保效能與可靠性的機制差異</span><span class="sxs-lookup"><span data-stu-id="8f905-457">Differences in the mechanisms for ensuring performance and reliability</span></span>
  - <span data-ttu-id="8f905-458">團隊已自動重新連線並快速漫遊。</span><span class="sxs-lookup"><span data-stu-id="8f905-458">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="8f905-459">商務用 Skype 不會。</span><span class="sxs-lookup"><span data-stu-id="8f905-459">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="8f905-460">團隊有動態頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="8f905-460">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="8f905-461">商務用 Skype 不會。</span><span class="sxs-lookup"><span data-stu-id="8f905-461">Skype for Business doesn't.</span></span>
- <span data-ttu-id="8f905-462">團隊與商務用 Skype 之間[IP 位址範圍](Office-365-URLs-IP-address-ranges.md)的差異。</span><span class="sxs-lookup"><span data-stu-id="8f905-462">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="8f905-463">團隊 IP 範圍較新，可能會導致防火牆出現連線問題。</span><span class="sxs-lookup"><span data-stu-id="8f905-463">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a><span data-ttu-id="8f905-464">從商務用 Skype 傳統版入口網站開啟 CQD</span><span class="sxs-lookup"><span data-stu-id="8f905-464">Open CQD from the Skype for Business legacy portal</span></span>

<span data-ttu-id="8f905-465">![](media/sfb-logo-30x30.png)**使用商務用 skype 傳統版入口網站**的商務用 skype 標誌圖示</span><span class="sxs-lookup"><span data-stu-id="8f905-465">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="8f905-466">使用系統管理員帳戶登入您的 Office 365 組織，然後選取 [系統**管理**] 磚以開啟系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="8f905-466">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="8f905-467">在左窗格中的 [系統**管理中心**] 底下，選取 [ **Microsoft 團隊**] 以開啟團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="8f905-467">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Teams admin center.</span></span>
3. <span data-ttu-id="8f905-468">在團隊管理中心中，選取左窗格中的 [**舊版入口網站**]，選取 [**工具**]，然後選取 [**商務用 Skype Online 通話品質儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="8f905-468">In the Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![螢幕擷取畫面：選取 [通話品質] 儀表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="8f905-470">在開啟的頁面上，使用您的全域系統管理員帳戶登入，然後在出現提示時提供該帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="8f905-470">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="8f905-471">第一次登入時，CQD 會開始收集及處理資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-471">After the first time you sign in, CQD will begin collecting and processing data.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8f905-472">從2019年12月之後，您仍然可以存取舊版的 CQD （cqd.lync.com），不過舊版入口網站提供最新 CQD （cqd.teams.microsoft.com）的連結。</span><span class="sxs-lookup"><span data-stu-id="8f905-472">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="8f905-473">最後，將會解除舊版的 CQD。</span><span class="sxs-lookup"><span data-stu-id="8f905-473">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="8f905-474">從2020年7月1日起，較舊版本的 CQD 會從新的 CQD 存取資料（ https://CQD.teams.microsoft.com) ，而且您不能再匯出建立及報告資料。</span><span class="sxs-lookup"><span data-stu-id="8f905-474">As of July 1, 2020, the older version of CQD accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="8f905-475">在後期2020中，我們會關閉舊的 CQD，您將無法再存取它。</span><span class="sxs-lookup"><span data-stu-id="8f905-475">Sometime in late 2020, we'll turn off the old CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8f905-476">相關主題</span><span class="sxs-lookup"><span data-stu-id="8f905-476">Related topics</span></span>

[<span data-ttu-id="8f905-477">改善及監視團隊的通話品質</span><span class="sxs-lookup"><span data-stu-id="8f905-477">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="8f905-478">什麼是 CQD？</span><span class="sxs-lookup"><span data-stu-id="8f905-478">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="8f905-479">設定通話品質儀表板（CQD）</span><span class="sxs-lookup"><span data-stu-id="8f905-479">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="8f905-480">上傳租使用者及組建資料</span><span class="sxs-lookup"><span data-stu-id="8f905-480">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="8f905-481">使用 CQD 管理通話與會議品質</span><span class="sxs-lookup"><span data-stu-id="8f905-481">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="8f905-482">CQD 中可用的維度與量值</span><span class="sxs-lookup"><span data-stu-id="8f905-482">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="8f905-483">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="8f905-483">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="8f905-484">使用 Power BI 來分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="8f905-484">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
