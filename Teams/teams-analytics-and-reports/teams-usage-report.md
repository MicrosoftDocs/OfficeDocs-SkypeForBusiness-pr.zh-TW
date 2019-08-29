---
title: Microsoft 團隊使用量報告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 瞭解如何使用 Microsoft 團隊系統管理中心中的 [團隊使用量] 報告, 以取得貴組織中的小組活動的概覽。
appliesto:
- Microsoft Teams
ms.openlocfilehash: d530ba8009cd113354a511b61589b409958ec276
ms.sourcegitcommit: a5cde2df1aceed9d919ef53281dd0d75f1f5e183
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2019
ms.locfileid: "36667086"
---
# <a name="microsoft-teams-usage-report"></a><span data-ttu-id="3dc80-103">Microsoft 團隊使用量報告</span><span class="sxs-lookup"><span data-stu-id="3dc80-103">Microsoft Teams usage report</span></span>

<span data-ttu-id="3dc80-104">Microsoft 團隊系統管理中心中的 [團隊使用量] 報告可讓您大致瞭解團隊中的使用狀況活動, 包括作用中使用者和頻道的數量, 讓您可以快速查看貴組織中的使用者數是使用團隊進行通訊, 以及整合.</span><span class="sxs-lookup"><span data-stu-id="3dc80-104">The Teams usage report in the Microsoft Teams admin center gives you an overview of the usage activity in Teams, including the number of active users and channels, so you can quickly see how many users across your organization are using Teams to communicate and collaborate.</span></span> <span data-ttu-id="3dc80-105">您可以查看小組的使用方式資訊, 包括每個小組中的作用中使用者數與頻道、來賓和訊息。</span><span class="sxs-lookup"><span data-stu-id="3dc80-105">You can view usage information for  teams, including the number of active users and channels, guests, and messages in each team.</span></span>

## <a name="view-the-report"></a><span data-ttu-id="3dc80-106">查看報表</span><span class="sxs-lookup"><span data-stu-id="3dc80-106">View the report</span></span>

1. <span data-ttu-id="3dc80-107">在 Microsoft [團隊管理中心] 的左導覽中, 按一下 [**分析] & 報表**], 然後在 [**報表**] 底下, 選取 [**團隊使用方式**]。</span><span class="sxs-lookup"><span data-stu-id="3dc80-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports**, and then under **Report**, select **Teams usage**.</span></span>
2. <span data-ttu-id="3dc80-108">在 [**日期範圍**] 底下, 選取一個範圍, 然後按一下 [**執行報表**]。</span><span class="sxs-lookup"><span data-stu-id="3dc80-108">Under **Date range**, select a range, and then click **Run report**.</span></span>

<span data-ttu-id="3dc80-109">[![團隊系統管理中心] 中的 [團隊使用方式] 報告螢幕擷取畫面 (含標注])[(../media/teams-reports-teams-usage-with-callouts.png "團隊系統管理中心] 中的 [團隊使用方式] 報告螢幕擷取畫面 (含標注"))</span><span class="sxs-lookup"><span data-stu-id="3dc80-109">![Screen shot of the Teams usage report in the Teams admin center with callouts](../media/teams-reports-teams-usage-with-callouts.png "Screen shot of the Teams usage report in the Teams admin center with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="3dc80-110">解讀報表</span><span class="sxs-lookup"><span data-stu-id="3dc80-110">Interpret the report</span></span>

|<span data-ttu-id="3dc80-111">圖說文字</span><span class="sxs-lookup"><span data-stu-id="3dc80-111">Callout</span></span> |<span data-ttu-id="3dc80-112">說明</span><span class="sxs-lookup"><span data-stu-id="3dc80-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="3dc80-113">**sr-1**</span><span class="sxs-lookup"><span data-stu-id="3dc80-113">**1**</span></span>   |<span data-ttu-id="3dc80-114">您可以針對過去7天或28天的趨勢, 查看 [團隊使用狀況] 活動報告。</span><span class="sxs-lookup"><span data-stu-id="3dc80-114">The Teams usage activity report can be viewed for trends over the last 7 days or 28 days.</span></span> |
|<span data-ttu-id="3dc80-115">**pplx-2**</span><span class="sxs-lookup"><span data-stu-id="3dc80-115">**2**</span></span>   |<span data-ttu-id="3dc80-116">每個報告都有產生此報告的日期。</span><span class="sxs-lookup"><span data-stu-id="3dc80-116">Each report has a date for when this report was generated.</span></span> <span data-ttu-id="3dc80-117">報告通常會反映來自啟用時間的24到48小時延遲時間。</span><span class="sxs-lookup"><span data-stu-id="3dc80-117">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="3dc80-118">**3**</span><span class="sxs-lookup"><span data-stu-id="3dc80-118">**3**</span></span>   |<ul><li><span data-ttu-id="3dc80-119">圖表上的 X 軸是報表所選取的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="3dc80-119">The X axis on the chart is the selected date range for the report.</span></span></li> <li> <span data-ttu-id="3dc80-120">Y 軸是作用中專案或活動的計數。</span><span class="sxs-lookup"><span data-stu-id="3dc80-120">The Y axis is the count of active items or activity.</span></span></li> </ul><span data-ttu-id="3dc80-121">將游標暫留在代表指定日期的專案或活動點上, 即可查看該專案或該日期的活動實例數。</span><span class="sxs-lookup"><span data-stu-id="3dc80-121">Hover over the dot representing an item or activity on a given date to see the number of instances of that item or activity on that given date.</span></span>|
|<span data-ttu-id="3dc80-122">**4**</span><span class="sxs-lookup"><span data-stu-id="3dc80-122">**4**</span></span>   |<span data-ttu-id="3dc80-123">您可以按一下圖例中的專案, 篩選您在圖表上看到的內容。</span><span class="sxs-lookup"><span data-stu-id="3dc80-123">You can filter what you see on the chart by clicking an item in the legend.</span></span> <span data-ttu-id="3dc80-124">例如, 按一下 [**總**作用中的使用者]、[**團隊] & [頻道**作用中的使用者]、[作用中**通道**] 或 [**郵件**], 只會看到與每個資訊相關</span><span class="sxs-lookup"><span data-stu-id="3dc80-124">For example, click  **Total active users**, **Teams & Channels active users**,  **Active channels**, or **Messages** to see only the info related to each one.</span></span> <span data-ttu-id="3dc80-125">變更此選取範圍不會變更表格中的資訊。</span><span class="sxs-lookup"><span data-stu-id="3dc80-125">Changing this selection doesn’t change the information in the table.</span></span> |
|<span data-ttu-id="3dc80-126">**500**</span><span class="sxs-lookup"><span data-stu-id="3dc80-126">**5**</span></span>   |<span data-ttu-id="3dc80-127">此表格提供依團隊進行的使用方式細分。</span><span class="sxs-lookup"><span data-stu-id="3dc80-127">The table gives you a breakdown of usage by team.</span></span> <ul><li><span data-ttu-id="3dc80-128">[**團隊名稱**] 是團隊的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="3dc80-128">**Team name** is the display name of the team.</span></span> <span data-ttu-id="3dc80-129">您可以按一下團隊名稱, 移至 Microsoft 團隊系統管理中心的小組 [設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3dc80-129">You can click the team name to go to the team's settings page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="3dc80-130">**隱私權**指的是私人小組或公用小組。</span><span class="sxs-lookup"><span data-stu-id="3dc80-130">**Privacy** refers to whether the team is a private team or public team.</span></span></li> <li><span data-ttu-id="3dc80-131">[作用中的**使用者**] 是團隊中在指定時段內作用中的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="3dc80-131">**Active users** is the number of active users in the team in the specified time period.</span></span></li><li><span data-ttu-id="3dc80-132">[**來賓**] 是團隊中指定時間內的來賓人數。</span><span class="sxs-lookup"><span data-stu-id="3dc80-132">**Guests** is the number of guests in the team in the specified time period.</span></span></li> </li> </ul><span data-ttu-id="3dc80-133">請注意, 如果使用者帳戶已不存在於 Azure AD 中, 則使用者名稱會在資料表中顯示為 "--"。</span><span class="sxs-lookup"><span data-stu-id="3dc80-133">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="3dc80-134">若要在表格中查看您想要的資訊, 請務必將資料行新增至資料表。</span><span class="sxs-lookup"><span data-stu-id="3dc80-134">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="3dc80-135">**6**</span><span class="sxs-lookup"><span data-stu-id="3dc80-135">**6**</span></span>   |<span data-ttu-id="3dc80-136">選取 [**編輯欄**] 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="3dc80-136">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="3dc80-137">**utf-7**</span><span class="sxs-lookup"><span data-stu-id="3dc80-137">**7**</span></span>   |<span data-ttu-id="3dc80-138">您可以將報表匯出為 CSV 檔案, 以便進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="3dc80-138">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="3dc80-139">按一下 [**匯出至 Excel**], 然後在 [**下載**] 索引標籤上, 按一下 [**下載**] 以在準備好時下載報告。</span><span class="sxs-lookup"><span data-stu-id="3dc80-139">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="3dc80-140">![[下載] 索引標籤的螢幕擷取畫面, 顯示已匯出的報告供下載](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="3dc80-140">![Screen shot of the Downloads tab showing exported reports to download](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="3dc80-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="3dc80-141">Related topics</span></span>

- [<span data-ttu-id="3dc80-142">團隊分析和報告</span><span class="sxs-lookup"><span data-stu-id="3dc80-142">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
