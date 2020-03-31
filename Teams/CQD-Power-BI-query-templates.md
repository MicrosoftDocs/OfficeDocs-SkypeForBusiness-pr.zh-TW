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
ms.openlocfilehash: 374f0da0342e5fbd50a7a27b9dde49acf605a23d
ms.sourcegitcommit: f96d66d08a9d6993edbb9554738dc8236d901933
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053506"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a><span data-ttu-id="f1e07-103">使用 Power BI 來分析 Microsoft 團隊的 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="f1e07-103">Use Power BI to analyze CQD data for Microsoft Teams</span></span>

<span data-ttu-id="f1e07-104">2020年1月[的新功能：下載 POWER BI 查詢範本以進行 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="f1e07-104">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="f1e07-105">可自訂的 Power BI 範本，您可以用來分析及報告您的 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="f1e07-105">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="f1e07-106">針對團隊中的 CQD 報表，如果您想要使用 Power BI 查詢及報告資料，請下載我們的 CQD Power BI 範本。</span><span class="sxs-lookup"><span data-stu-id="f1e07-106">For CQD reports in Teams, if you'd rather use Power BI to query and report your data, download our CQD Power BI templates.</span></span> <span data-ttu-id="f1e07-107">當您在 Power BI 中開啟範本時，系統會提示您使用 CQD 管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="f1e07-107">When you open the templates in Power BI, you'll be prompted to sign in with your CQD admin credentials.</span></span> <span data-ttu-id="f1e07-108">您可以自訂這些查詢範本，並將它們發佈給貴組織中擁有 Power BI 授權及 CQD 系統管理員許可權的任何人。</span><span class="sxs-lookup"><span data-stu-id="f1e07-108">You can customize these query templates and distribute them to anyone in your organization who has a Power BI license and CQD admin permissions.</span></span>

<span data-ttu-id="f1e07-109">在您可以使用這些 .PBIX 檔案之前，您必須使用[下載](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中包含的*MicrosoftCallQuality Pqx*檔案，[安裝 Microsoft CQD 的 Power BI 連接器](CQD-Power-BI-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="f1e07-109">Before you can use these PBIX files, you'll need to [Install the Power BI Connector for Microsoft CQD](CQD-Power-BI-connector.md) using the *MicrosoftCallQuality.pqx* file included in the [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


|  |  |
|---------|---------|
|<span data-ttu-id="f1e07-110">CQD 支援人員報告 .pbix</span><span class="sxs-lookup"><span data-stu-id="f1e07-110">CQD Helpdesk Report.pbix</span></span>     |<span data-ttu-id="f1e07-111">整合建立與 EUII 資料時，此報告的設計目的是讓您從單一使用者向上切入，找出該使用者的通話品質差的上游根本原因（例如，使用者在遇到網路問題的建築物中）。</span><span class="sxs-lookup"><span data-stu-id="f1e07-111">Integrating building and EUII data, this report is designed to let you drill up from a single user to find the upstream root cause of poor call quality for that user (for example, the user is in a building that's experiencing network problems).</span></span>         |
|<span data-ttu-id="f1e07-112">CQD 位置增強的報表 .pbix</span><span class="sxs-lookup"><span data-stu-id="f1e07-112">CQD Location Enhanced Report.pbix</span></span>     | <span data-ttu-id="f1e07-113">重新 imagining CQD 的 SPD 位置報告。</span><span class="sxs-lookup"><span data-stu-id="f1e07-113">Re-imagining CQD SPD location reports.</span></span> <span data-ttu-id="f1e07-114">包括9個報告、提供通話品質、建立 WiFi、可靠性，以及透過透過建立或使用者進行額外的 thrus 來評價我的通話（RMC）資訊。</span><span class="sxs-lookup"><span data-stu-id="f1e07-114">Includes 9 reports, providing Call Quality, Building WiFi, Reliability, and Rate My Call (RMC) information with additional drill-thrus by Building or by User.</span></span>        |
|<span data-ttu-id="f1e07-115">CQD 行動裝置報表 .pbix</span><span class="sxs-lookup"><span data-stu-id="f1e07-115">CQD Mobile Device Report.pbix</span></span>     | <span data-ttu-id="f1e07-116">提供專門針對行動裝置使用者進行調整的深入資訊，包括通話品質、可靠性及評級我的通話。</span><span class="sxs-lookup"><span data-stu-id="f1e07-116">Provides insights specifically tuned towards mobile device users, including Call Quality, Reliability, and Rate My Call.</span></span> <span data-ttu-id="f1e07-117">查看行動網路、WiFi 網路及行動作業系統報告（Android、iOS）。</span><span class="sxs-lookup"><span data-stu-id="f1e07-117">View mobile network, WiFi network, and mobile operating system reports (Android, iOS).</span></span>        |
|<span data-ttu-id="f1e07-118">CQD PSTN 直向路由報告 .pbix</span><span class="sxs-lookup"><span data-stu-id="f1e07-118">CQD PSTN Direct Routing Report.pbix</span></span>     |<span data-ttu-id="f1e07-119">提供穿過直接路由的 PSTN 呼叫的深入見解。</span><span class="sxs-lookup"><span data-stu-id="f1e07-119">Provides insights specific for PSTN calls that go through Direct Routing.</span></span> <span data-ttu-id="f1e07-120">若要深入瞭解，請[使用 CQD PSTN Direct 路由報告](CQD-PSTN-report.md)進行閱讀。</span><span class="sxs-lookup"><span data-stu-id="f1e07-120">To learn more, read [Using the CQD PSTN Direct Routing Report](CQD-PSTN-report.md).</span></span>         |
|<span data-ttu-id="f1e07-121">CQD 摘要報表 .pbix</span><span class="sxs-lookup"><span data-stu-id="f1e07-121">CQD Summary Report.pbix</span></span>     |<span data-ttu-id="f1e07-122">更好的視覺效果、改良的簡報、增加的資訊密度，以及滾動日期。</span><span class="sxs-lookup"><span data-stu-id="f1e07-122">Better visualizations, improved presentation, increased information density, and rolling dates.</span></span> <span data-ttu-id="f1e07-123">這些報告可讓識別碼的離群更容易。</span><span class="sxs-lookup"><span data-stu-id="f1e07-123">These reports make it easier to identifier outliers.</span></span> <span data-ttu-id="f1e07-124">使用便於使用的互動式地圖，透過位置深化通話品質。</span><span class="sxs-lookup"><span data-stu-id="f1e07-124">Drill into call quality by location with an easy-to-use interactive map.</span></span> <span data-ttu-id="f1e07-125">9個新的報表：</span><span class="sxs-lookup"><span data-stu-id="f1e07-125">9 new reports:</span></span></p><span data-ttu-id="f1e07-126">整體品質</span><span class="sxs-lookup"><span data-stu-id="f1e07-126">- Quality Overall</span></span><br><span data-ttu-id="f1e07-127">-整體可靠性</span><span class="sxs-lookup"><span data-stu-id="f1e07-127">- Reliability Overall</span></span><br><span data-ttu-id="f1e07-128">-RMC （費率通話）整體</span><span class="sxs-lookup"><span data-stu-id="f1e07-128">- RMC (Rate My Call) Overall</span></span><br><span data-ttu-id="f1e07-129">-會議品質</span><span class="sxs-lookup"><span data-stu-id="f1e07-129">- Conference Quality</span></span><br><span data-ttu-id="f1e07-130">-P2P 品質</span><span class="sxs-lookup"><span data-stu-id="f1e07-130">- P2P Quality</span></span><br><span data-ttu-id="f1e07-131">-會議可靠性</span><span class="sxs-lookup"><span data-stu-id="f1e07-131">- Conference Reliability</span></span><br><span data-ttu-id="f1e07-132">-P2P 可靠性</span><span class="sxs-lookup"><span data-stu-id="f1e07-132">- P2P Reliability</span></span><br><span data-ttu-id="f1e07-133">-會議 RMC</span><span class="sxs-lookup"><span data-stu-id="f1e07-133">- Conference RMC</span></span><br><span data-ttu-id="f1e07-134">-P2P RMC</span><span class="sxs-lookup"><span data-stu-id="f1e07-134">- P2P RMC</span></span>         |
|<span data-ttu-id="f1e07-135"><strong>（新增！）</strong>CQD 團隊使用方式報表 .pbix</span><span class="sxs-lookup"><span data-stu-id="f1e07-135"><strong>(New!)</strong> CQD Teams Utilization Report.pbix</span></span>     | <span data-ttu-id="f1e07-136">顯示貴組織中的使用者如何使用團隊以及多少。</span><span class="sxs-lookup"><span data-stu-id="f1e07-136">Shows how users in your organization are using Teams and how much.</span></span> <span data-ttu-id="f1e07-137">若要深入瞭解，請參閱[使用 CQD POWER BI 報表來查看 Microsoft 團隊的利用率](CQD-teams-utilization-report.md)。</span><span class="sxs-lookup"><span data-stu-id="f1e07-137">To learn more, read [Use CQD Power BI report to view Microsoft Teams utilization](CQD-teams-utilization-report.md).</span></span>        |
|<span data-ttu-id="f1e07-138">CQD 使用者意見反應（比率我的通話）報表 .pbix</span><span class="sxs-lookup"><span data-stu-id="f1e07-138">CQD User Feedback (Rate My Call) Report.pbix</span></span>     | <span data-ttu-id="f1e07-139">顯示使用您可以輕鬆地協助支援您組織通話的方式，為我的通話資料打分。</span><span class="sxs-lookup"><span data-stu-id="f1e07-139">Shows Rate My Call data in a way that you can easily use to help support calling for your organization.</span></span> <span data-ttu-id="f1e07-140">與 verbatims 進行交叉參照，以找出使用者的教育機會。</span><span class="sxs-lookup"><span data-stu-id="f1e07-140">Cross reference with verbatims to identify end user education opportunities.</span></span>        |

> [!TIP]
> <span data-ttu-id="f1e07-141">在您設定 Power BI 報表以取得 CQD 資料後，請將其新增為頻道的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f1e07-141">Once you've set up your Power BI reports for CQD data, add them as a tab to a channel.</span></span> <span data-ttu-id="f1e07-142">選取**+** 頻道之後，請選取 [ **Power BI** ]，然後尋找您的報表。</span><span class="sxs-lookup"><span data-stu-id="f1e07-142">After you select **+** in a channel, select **Power BI** and then find your report.</span></span> <span data-ttu-id="f1e07-143">請記住，只有具備 Power BI 授權及 CQD 管理員認證的人員才能存取這些報告。</span><span class="sxs-lookup"><span data-stu-id="f1e07-143">Remember, only people with a Power BI license and CQD admin credentials can access these reports.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f1e07-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="f1e07-144">Related topics</span></span>

[<span data-ttu-id="f1e07-145">通話品質儀表板中提供的維度和量值</span><span class="sxs-lookup"><span data-stu-id="f1e07-145">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="f1e07-146">通話品質儀表板中的資料流分類</span><span class="sxs-lookup"><span data-stu-id="f1e07-146">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="f1e07-147">設定商務用 Skype 通話分析</span><span class="sxs-lookup"><span data-stu-id="f1e07-147">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="f1e07-148">使用通話分析來疑難排解不良通話品質</span><span class="sxs-lookup"><span data-stu-id="f1e07-148">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="f1e07-149">通話分析和通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="f1e07-149">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 