---
title: 使用 Power BI 來分析 Microsoft 團隊的 CQD 資料
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 Power BI 來分析 Microsoft 團隊的 CQD 資料。
ms.openlocfilehash: a288376192af375660107b79e93ec8613f46163d
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918672"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a><span data-ttu-id="931e9-103">使用 Power BI 來分析 Microsoft 團隊的 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="931e9-103">Use Power BI to analyze CQD data for Microsoft Teams</span></span>

<span data-ttu-id="931e9-104">2020年1月[的新功能：下載 POWER BI 查詢範本以進行 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="931e9-104">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="931e9-105">可自訂的 Power BI 範本，您可以用來分析及報告您的 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="931e9-105">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="931e9-106">針對團隊中的 CQD 報表，如果您想要使用 Power BI 查詢及報告資料，請下載我們的 CQD Power BI 範本。</span><span class="sxs-lookup"><span data-stu-id="931e9-106">For CQD reports in Teams, if you'd rather use Power BI to query and report your data, download our CQD Power BI templates.</span></span> <span data-ttu-id="931e9-107">當您在 Power BI 中開啟範本時，系統會提示您使用 CQD 管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="931e9-107">When you open the templates in Power BI, you'll be prompted to sign in with your CQD admin credentials.</span></span> <span data-ttu-id="931e9-108">您可以自訂這些查詢範本，並將它們發佈給貴組織中擁有 Power BI 授權及 CQD 系統管理員許可權的任何人。</span><span class="sxs-lookup"><span data-stu-id="931e9-108">You can customize these query templates and distribute them to anyone in your organization who has a Power BI license and CQD admin permissions.</span></span>

<span data-ttu-id="931e9-109">在您可以使用這些 PBIT 檔案之前，您必須使用[下載](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中包含的*MicrosoftCallQuality Pqx*檔案，[安裝 Microsoft CQD 的 Power BI 連接器](CQD-Power-BI-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="931e9-109">Before you can use these PBIT files, you'll need to [Install the Power BI Connector for Microsoft CQD](CQD-Power-BI-connector.md) using the *MicrosoftCallQuality.pqx* file included in the [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


|  |  |
|---------|---------|
|<span data-ttu-id="931e9-110">CQD 支援人員報告。 pbit</span><span class="sxs-lookup"><span data-stu-id="931e9-110">CQD Helpdesk Report.pbit</span></span>     |<span data-ttu-id="931e9-111">整合建立與 EUII 資料時，此報告的設計目的是讓您從單一使用者向上切入，找出該使用者的通話品質差的上游根本原因（例如，使用者在遇到網路問題的建築物中）。</span><span class="sxs-lookup"><span data-stu-id="931e9-111">Integrating building and EUII data, this report is designed to let you drill up from a single user to find the upstream root cause of poor call quality for that user (for example, the user is in a building that's experiencing network problems).</span></span>         |
|<span data-ttu-id="931e9-112">CQD 位置增強的報表。 pbit</span><span class="sxs-lookup"><span data-stu-id="931e9-112">CQD Location Enhanced Report.pbit</span></span>     | <span data-ttu-id="931e9-113">重新 imagining CQD 的 SPD 位置報告。</span><span class="sxs-lookup"><span data-stu-id="931e9-113">Re-imagining CQD SPD location reports.</span></span> <span data-ttu-id="931e9-114">包括9個報告、提供通話品質、建立 WiFi、可靠性，以及透過透過建立或使用者進行額外的 thrus 來評價我的通話（RMC）資訊。</span><span class="sxs-lookup"><span data-stu-id="931e9-114">Includes 9 reports, providing Call Quality, Building WiFi, Reliability, and Rate My Call (RMC) information with additional drill-thrus by Building or by User.</span></span>  <span data-ttu-id="931e9-115">請確定您上傳的是組建資料，以最大化您的報表體驗。</span><span class="sxs-lookup"><span data-stu-id="931e9-115">Make sure you upload the building data to maximize your reporting experience.</span></span>        |
|<span data-ttu-id="931e9-116">CQD 行動裝置報告。 pbit</span><span class="sxs-lookup"><span data-stu-id="931e9-116">CQD Mobile Device Report.pbit</span></span>     | <span data-ttu-id="931e9-117">提供專門針對行動裝置使用者進行調整的深入資訊，包括通話品質、可靠性及評級我的通話。</span><span class="sxs-lookup"><span data-stu-id="931e9-117">Provides insights specifically tuned towards mobile device users, including Call Quality, Reliability, and Rate My Call.</span></span> <span data-ttu-id="931e9-118">查看行動網路、WiFi 網路及行動作業系統報告（Android、iOS）。</span><span class="sxs-lookup"><span data-stu-id="931e9-118">View mobile network, WiFi network, and mobile operating system reports (Android, iOS).</span></span>        |
|<span data-ttu-id="931e9-119">CQD PSTN 直向路由報告。 pbit</span><span class="sxs-lookup"><span data-stu-id="931e9-119">CQD PSTN Direct Routing Report.pbit</span></span>     |<span data-ttu-id="931e9-120">提供穿過直接路由的 PSTN 呼叫的深入見解。</span><span class="sxs-lookup"><span data-stu-id="931e9-120">Provides insights specific for PSTN calls that go through Direct Routing.</span></span> <span data-ttu-id="931e9-121">若要深入瞭解，請[使用 CQD PSTN Direct 路由報告](CQD-PSTN-report.md)進行閱讀。</span><span class="sxs-lookup"><span data-stu-id="931e9-121">To learn more, read [Using the CQD PSTN Direct Routing Report](CQD-PSTN-report.md).</span></span>         |
|<span data-ttu-id="931e9-122">CQD 摘要報表。 pbit</span><span class="sxs-lookup"><span data-stu-id="931e9-122">CQD Summary Report.pbit</span></span>     |<span data-ttu-id="931e9-123">更好的視覺效果、改良的簡報、增加的資訊密度，以及滾動日期。</span><span class="sxs-lookup"><span data-stu-id="931e9-123">Better visualizations, improved presentation, increased information density, and rolling dates.</span></span> <span data-ttu-id="931e9-124">這些報告可讓識別碼的離群更容易。</span><span class="sxs-lookup"><span data-stu-id="931e9-124">These reports make it easier to identifier outliers.</span></span> <span data-ttu-id="931e9-125">使用便於使用的互動式地圖，透過位置深化通話品質。</span><span class="sxs-lookup"><span data-stu-id="931e9-125">Drill into call quality by location with an easy-to-use interactive map.</span></span> <span data-ttu-id="931e9-126">9個新的報表：</span><span class="sxs-lookup"><span data-stu-id="931e9-126">9 new reports:</span></span></p><span data-ttu-id="931e9-127">整體品質</span><span class="sxs-lookup"><span data-stu-id="931e9-127">- Quality Overall</span></span><br><span data-ttu-id="931e9-128">-整體可靠性</span><span class="sxs-lookup"><span data-stu-id="931e9-128">- Reliability Overall</span></span><br><span data-ttu-id="931e9-129">-RMC （費率通話）整體</span><span class="sxs-lookup"><span data-stu-id="931e9-129">- RMC (Rate My Call) Overall</span></span><br><span data-ttu-id="931e9-130">-會議品質</span><span class="sxs-lookup"><span data-stu-id="931e9-130">- Conference Quality</span></span><br><span data-ttu-id="931e9-131">-P2P 品質</span><span class="sxs-lookup"><span data-stu-id="931e9-131">- P2P Quality</span></span><br><span data-ttu-id="931e9-132">-會議可靠性</span><span class="sxs-lookup"><span data-stu-id="931e9-132">- Conference Reliability</span></span><br><span data-ttu-id="931e9-133">-P2P 可靠性</span><span class="sxs-lookup"><span data-stu-id="931e9-133">- P2P Reliability</span></span><br><span data-ttu-id="931e9-134">-會議 RMC</span><span class="sxs-lookup"><span data-stu-id="931e9-134">- Conference RMC</span></span><br><span data-ttu-id="931e9-135">-P2P RMC</span><span class="sxs-lookup"><span data-stu-id="931e9-135">- P2P RMC</span></span>         |
|<span data-ttu-id="931e9-136"><strong>（新增！）</strong>CQD [團隊利用率] 報表。 pbit</span><span class="sxs-lookup"><span data-stu-id="931e9-136"><strong>(New!)</strong> CQD Teams Utilization Report.pbit</span></span>     | <span data-ttu-id="931e9-137">顯示貴組織中的使用者如何使用團隊以及多少。</span><span class="sxs-lookup"><span data-stu-id="931e9-137">Shows how users in your organization are using Teams and how much.</span></span> <span data-ttu-id="931e9-138">請確定您上傳的是組建資料，以最大化您的報表體驗。</span><span class="sxs-lookup"><span data-stu-id="931e9-138">Make sure you upload the building data to maximize your reporting experience.</span></span> <span data-ttu-id="931e9-139">若要深入瞭解，請參閱[使用 CQD POWER BI 報表來查看 Microsoft 團隊的利用率](CQD-teams-utilization-report.md)。</span><span class="sxs-lookup"><span data-stu-id="931e9-139">To learn more, read [Use CQD Power BI report to view Microsoft Teams utilization](CQD-teams-utilization-report.md).</span></span>        |
|<span data-ttu-id="931e9-140">CQD 使用者意見反應（評級我的通話）報告。 pbit</span><span class="sxs-lookup"><span data-stu-id="931e9-140">CQD User Feedback (Rate My Call) Report.pbit</span></span>     | <span data-ttu-id="931e9-141">顯示使用您可以輕鬆地協助支援您組織通話的方式，為我的通話資料打分。</span><span class="sxs-lookup"><span data-stu-id="931e9-141">Shows Rate My Call data in a way that you can easily use to help support calling for your organization.</span></span> <span data-ttu-id="931e9-142">與 verbatims 進行交叉參照，以找出使用者的教育機會。</span><span class="sxs-lookup"><span data-stu-id="931e9-142">Cross reference with verbatims to identify end user education opportunities.</span></span>        |

> [!TIP]
> <span data-ttu-id="931e9-143">在您設定 Power BI 報表以取得 CQD 資料後，請將其新增為頻道的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="931e9-143">Once you've set up your Power BI reports for CQD data, add them as a tab to a channel.</span></span> <span data-ttu-id="931e9-144">選取**+** 頻道之後，請選取 [ **Power BI** ]，然後尋找您的報表。</span><span class="sxs-lookup"><span data-stu-id="931e9-144">After you select **+** in a channel, select **Power BI** and then find your report.</span></span> <span data-ttu-id="931e9-145">若要深入瞭解，請參閱[使用 [POWER BI] 索引標籤針對團隊的內嵌報表](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="931e9-145">To learn more, read [Embed report with the Power BI tab for Teams](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams).</span></span> <span data-ttu-id="931e9-146">請記住，只有具備 Power BI 授權及 CQD 管理員認證的人員才能存取這些報告。</span><span class="sxs-lookup"><span data-stu-id="931e9-146">Remember, only people with a Power BI license and CQD admin credentials can access these reports.</span></span>


## <a name="related-topics"></a><span data-ttu-id="931e9-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="931e9-147">Related topics</span></span>

[<span data-ttu-id="931e9-148">通話品質儀表板中提供的維度和量值</span><span class="sxs-lookup"><span data-stu-id="931e9-148">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="931e9-149">通話品質儀表板中的資料流分類</span><span class="sxs-lookup"><span data-stu-id="931e9-149">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="931e9-150">設定商務用 Skype 通話分析</span><span class="sxs-lookup"><span data-stu-id="931e9-150">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="931e9-151">使用通話分析來疑難排解不良通話品質</span><span class="sxs-lookup"><span data-stu-id="931e9-151">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="931e9-152">通話分析和通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="931e9-152">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 
