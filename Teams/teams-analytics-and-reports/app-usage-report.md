---
title: Microsoft Teams App 使用方式報告
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Microsoft Teams 系統管理中心使用 Teams App 使用方式報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29e51e91cdc42000350a48dd0d83225e7791aea6
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460593"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="0790c-103">Microsoft Teams App 使用方式報告</span><span class="sxs-lookup"><span data-stu-id="0790c-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="0790c-104">Microsoft Teams 系統管理中心的 Teams 應用程式使用方式報告會提供使用者在 Teams 中使用哪些應用程式的資訊。</span><span class="sxs-lookup"><span data-stu-id="0790c-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="0790c-105">查看應用程式使用量報告</span><span class="sxs-lookup"><span data-stu-id="0790c-105">View the App Usage report</span></span>

1.  <span data-ttu-id="0790c-106">在系統管理中心的左側流覽位置，按一下 <https://admin.teams.microsoft.com> **[分析&報告** \> **使用方式報告**。</span><span class="sxs-lookup"><span data-stu-id="0790c-106">In the left navigation of the admin center at <https://admin.teams.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="0790c-107">在顯示 **報表的顯示** 方式中 **，選取在** 報表下的 **應用程式使用量**。</span><span class="sxs-lookup"><span data-stu-id="0790c-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text="使用方式報告功能表項目的螢幕擷取畫面":::

2.  <span data-ttu-id="0790c-109">在 **[日期範圍** 中，選取範圍，然後按一下 [ **執行報表**。</span><span class="sxs-lookup"><span data-stu-id="0790c-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text="應用程式使用量報告的螢幕擷取畫面":::

## <a name="interpret-the-report"></a><span data-ttu-id="0790c-111">解讀報表</span><span class="sxs-lookup"><span data-stu-id="0790c-111">Interpret the report</span></span>

|<span data-ttu-id="0790c-112">標注</span><span class="sxs-lookup"><span data-stu-id="0790c-112">Callout</span></span> |<span data-ttu-id="0790c-113">說明</span><span class="sxs-lookup"><span data-stu-id="0790c-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="0790c-114">**1**</span><span class="sxs-lookup"><span data-stu-id="0790c-114">**1**</span></span>   |<span data-ttu-id="0790c-115">您可以針對過去 7、30 或 90 天內的趨勢來查看 Teams 應用程式使用量報告。</span><span class="sxs-lookup"><span data-stu-id="0790c-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="0790c-116">**2**</span><span class="sxs-lookup"><span data-stu-id="0790c-116">**2**</span></span>   |<span data-ttu-id="0790c-117">每個報表都有產生報表的日期。</span><span class="sxs-lookup"><span data-stu-id="0790c-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="0790c-118">報告通常會反映出從應用程式開啟起 24 小時的延遲。</span><span class="sxs-lookup"><span data-stu-id="0790c-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![顯示日期範圍之應用程式使用量報表的螢幕擷取畫面](media/app-usage-report3.png)|
|<span data-ttu-id="0790c-120">**3**</span><span class="sxs-lookup"><span data-stu-id="0790c-120">**3**</span></span>    | <ul><li><span data-ttu-id="0790c-121">圖表上的 X 軸是特定報表的選取日期範圍。</span><span class="sxs-lookup"><span data-stu-id="0790c-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="0790c-122">Y 軸是將游標暫停于圖表中之日期的使用者數目，這些使用者已開啟應用程式至少一次，如此一來，就視為使用中使用者，並計入滑鼠暫停時看到的總數量。</span><span class="sxs-lookup"><span data-stu-id="0790c-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="0790c-123">**4**</span><span class="sxs-lookup"><span data-stu-id="0790c-123">**4**</span></span>   |<span data-ttu-id="0790c-124">將游標停留在代表給定日期之應用程式使用量的點上，以查看該 App 在該日期的總使用中使用者數目。</span><span class="sxs-lookup"><span data-stu-id="0790c-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="0790c-125">**5**</span><span class="sxs-lookup"><span data-stu-id="0790c-125">**5**</span></span>   |<span data-ttu-id="0790c-126">所有應用程式都會包含在內，但選擇篩選圖示，即可使用其他篩選。</span><span class="sxs-lookup"><span data-stu-id="0790c-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="0790c-127">**6**</span><span class="sxs-lookup"><span data-stu-id="0790c-127">**6**</span></span>   |<span data-ttu-id="0790c-128">表格提供使用中使用者和團隊的 App 名稱明細。</span><span class="sxs-lookup"><span data-stu-id="0790c-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="0790c-129">**應用程式名稱** 是 Teams 中所使用的應用程式的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="0790c-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="0790c-130">**使用中** 使用者是在指定的時段內至少開啟應用程式一次的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="0790c-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="0790c-131">**應用程式類型** 是「Microsoft」或「協力廠商」的靜態值。</span><span class="sxs-lookup"><span data-stu-id="0790c-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="0790c-132">**使用中的** 團隊是團隊中至少有一個成員在指定的時段內開啟應用程式的團隊數目。</span><span class="sxs-lookup"><span data-stu-id="0790c-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="0790c-133">**Publisher** 是 App 的軟體發行者。</span><span class="sxs-lookup"><span data-stu-id="0790c-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="0790c-134">**版本** 是應用程式發行者所提供 App 的軟體版本。</span><span class="sxs-lookup"><span data-stu-id="0790c-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><span data-ttu-id="0790c-135"><b> 注意：</b> 目前，只有頻道中使用的應用程式會計算使用中使用者和使用中團隊。</span><span class="sxs-lookup"><span data-stu-id="0790c-135"><b> Note :</b> Currently, 'Active users' and 'Active teams' are calculated for apps used in channels only.</span></span>     

<br><span data-ttu-id="0790c-136">![應用程式使用量報表的 ](media/app-usage-report4.png)  螢幕擷取畫面 **| |7 |**  選取 **編輯欄** 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="0790c-136">![Screenshot of an Apps Usage report](media/app-usage-report4.png)  | |**7**  |Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="0790c-137">![編輯欄頁面的 ](media/app-usage-report5.png)  螢幕擷取畫面 **| |8 |**  您可以將報表匯出為 CSV 檔案，進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="0790c-137">![Screenshot of the Edit columns page](media/app-usage-report5.png)  | |**8**  |You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="0790c-138">按一下 **[匯出至 Excel，** 再按一下 [下載資料標籤上，下載時下載報表已就緒。</span><span class="sxs-lookup"><span data-stu-id="0790c-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="0790c-139">![下載頁面的螢幕擷取畫面| | ](media/app-usage-report7.png) **9 |**   當您在 Excel 中查看報表時，也會看到代表應用程式識別碼的 **識別碼** 欄。</span><span class="sxs-lookup"><span data-stu-id="0790c-139">![Screenshot of Downloads page](media/app-usage-report7.png)  | |**9**   |When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="0790c-140">團隊識別碼通常是一個 Alphanumer 字串。</span><span class="sxs-lookup"><span data-stu-id="0790c-140">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="0790c-141">如果 **識別碼** 欄顯示為 \**\n*{，這表示使用者要求刪除其資訊。</span><span class="sxs-lookup"><span data-stu-id="0790c-141">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="0790c-142">![下載的 Excel 報表螢幕擷取畫面](media/app-usage-report8.png)  |</span><span class="sxs-lookup"><span data-stu-id="0790c-142">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)  |</span></span>

## <a name="related-topics"></a><span data-ttu-id="0790c-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="0790c-143">Related topics</span></span>

- [<span data-ttu-id="0790c-144">Teams 分析和報告</span><span class="sxs-lookup"><span data-stu-id="0790c-144">Teams analytics and reporting</span></span>](teams-reporting-reference.md)