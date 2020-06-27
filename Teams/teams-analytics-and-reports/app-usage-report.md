---
title: Microsoft 團隊 app 使用方式報告
author: LolaJacobsen
ms.author: lolaj
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
description: 瞭解如何在 Microsoft 團隊系統管理中心使用團隊 app 使用方式報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a5d5c1bdb5b5bbe58ecdb90721ce24bd0081a65
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902311"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="bd3c4-103">Microsoft 團隊 app 使用方式報告</span><span class="sxs-lookup"><span data-stu-id="bd3c4-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="bd3c4-104">Microsoft [小組] 系統管理中心中的 [小組 app 使用量] 報告，可讓您在小組中提供使用者使用哪些 app 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="bd3c4-105">查看應用程式使用量報告</span><span class="sxs-lookup"><span data-stu-id="bd3c4-105">View the App Usage report</span></span>

1.  <span data-ttu-id="bd3c4-106">在系統管理中心的左側導覽中 <https://teams.admin.microsoft.com> ，按一下 [**分析] & 報告** \> **使用方式報告**。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-106">In the left navigation of the admin center at <https://teams.admin.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="bd3c4-107">在 [**查看報表**] 索引標籤的 [**報表**] 底下，選取 [ **app 使用方式**]。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text="[使用狀況報告] 功能表項目的螢幕擷取畫面":::

2.  <span data-ttu-id="bd3c4-109">在 [**日期範圍**] 底下，選取一個範圍，然後按一下 [**執行報表**]。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text="[應用程式使用量] 報告的螢幕擷取畫面":::

## <a name="interpret-the-report"></a><span data-ttu-id="bd3c4-111">解讀報表</span><span class="sxs-lookup"><span data-stu-id="bd3c4-111">Interpret the report</span></span>

|<span data-ttu-id="bd3c4-112">圖說文字</span><span class="sxs-lookup"><span data-stu-id="bd3c4-112">Callout</span></span> |<span data-ttu-id="bd3c4-113">說明</span><span class="sxs-lookup"><span data-stu-id="bd3c4-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="bd3c4-114">**1**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-114">**1**</span></span>   |<span data-ttu-id="bd3c4-115">您可以針對過去7、30或90天的趨勢，查看團隊 App 使用方式報告。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="bd3c4-116">**2**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-116">**2**</span></span>   |<span data-ttu-id="bd3c4-117">每個報告都有產生報告的日期。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="bd3c4-118">報告通常會反映來自開啟 app 時間的24小時延遲時間。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![顯示日期範圍之 [應用程式使用量] 報告的螢幕擷取畫面](media/app-usage-report3.png)|
|<span data-ttu-id="bd3c4-120">**3**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-120">**3**</span></span>    | <ul><li><span data-ttu-id="bd3c4-121">圖表上的 X 軸是特定報表的已選取日期範圍。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="bd3c4-122">Y 軸是在圖表中停留在指定日期的使用者數目，這些使用者至少已開啟一次 app，而且這樣做會被視為作用中的使用者，並計入滑鼠暫留上所看到的總數。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="bd3c4-123">**4**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-123">**4**</span></span>   |<span data-ttu-id="bd3c4-124">將游標暫留在代表指定日期應用程式使用量的點上，即可查看該應用程式在該日期的總作用中使用者的實例數。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="bd3c4-125">**500**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-125">**5**</span></span>   |<span data-ttu-id="bd3c4-126">所有 App 都將包含，但在選擇 [篩選] 圖示之後，就可以使用其他篩選器。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="bd3c4-127">**6**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-127">**6**</span></span>   |<span data-ttu-id="bd3c4-128">表格會依 App 名稱提供作用中使用者和小組的明細。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="bd3c4-129">[**應用程式名稱**] 是在 [團隊] 中使用之應用程式的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="bd3c4-130">[作用中的**使用者**] 是指在指定的時段內至少開啟過一次 app 的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="bd3c4-131">**應用程式類型**是「Microsoft」或「協力廠商」的靜態值。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="bd3c4-132">[作用中的**團隊**] 是由團隊中至少一個成員以及在指定的時段內開啟 App 的團隊數目。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="bd3c4-133">**Publisher**是 app 的軟體發行者。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="bd3c4-134">**版本**是應用程式的軟體版本（來自 app 發行者）。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><br><span data-ttu-id="bd3c4-135">![App 使用方式報告的螢幕擷取畫面](media/app-usage-report4.png)</span><span class="sxs-lookup"><span data-stu-id="bd3c4-135">![Screenshot of an Apps Usage report](media/app-usage-report4.png)</span></span>  |
|<span data-ttu-id="bd3c4-136">**utf-7**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-136">**7**</span></span>  |<span data-ttu-id="bd3c4-137">選取 [**編輯欄**] 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-137">Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="bd3c4-138">![[編輯欄] 頁面的螢幕擷取畫面](media/app-usage-report5.png)</span><span class="sxs-lookup"><span data-stu-id="bd3c4-138">![Screenshot of the Edit columns page](media/app-usage-report5.png)</span></span>  |
|<span data-ttu-id="bd3c4-139">**型**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-139">**8**</span></span>  |<span data-ttu-id="bd3c4-140">您可以將報表匯出為 CSV 檔案，以便進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-140">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="bd3c4-141">按一下 [**匯出至 Excel**]，然後在 [**下載**] 索引標籤上，按一下 [**下載**] 以在準備好時下載報告。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-141">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="bd3c4-142">![[下載] 頁面的螢幕擷取畫面](media/app-usage-report7.png)</span><span class="sxs-lookup"><span data-stu-id="bd3c4-142">![Screenshot of Downloads page](media/app-usage-report7.png)</span></span>  |
|<span data-ttu-id="bd3c4-143">**9**</span><span class="sxs-lookup"><span data-stu-id="bd3c4-143">**9**</span></span>   |<span data-ttu-id="bd3c4-144">當您在 Excel 中查看報表時，您也會看到 [**識別碼**] 欄，代表 [應用程式識別碼]。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-144">When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="bd3c4-145">團隊識別碼通常是一個字母數位字串。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-145">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="bd3c4-146">如果 [**識別碼**] 欄顯示為 \* \* \n \* \* \* \*，這表示使用者要求刪除其資訊。</span><span class="sxs-lookup"><span data-stu-id="bd3c4-146">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="bd3c4-147">![下載的 Excel 報表螢幕擷取畫面](media/app-usage-report8.png)</span><span class="sxs-lookup"><span data-stu-id="bd3c4-147">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="bd3c4-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="bd3c4-148">Related topics</span></span>

- [<span data-ttu-id="bd3c4-149">團隊分析和報告</span><span class="sxs-lookup"><span data-stu-id="bd3c4-149">Teams analytics and reporting</span></span>](teams-reporting-reference.md)