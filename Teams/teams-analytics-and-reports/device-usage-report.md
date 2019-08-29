---
title: Microsoft 團隊裝置使用量報告
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
description: 瞭解如何使用 Microsoft 團隊系統管理中心中的 [團隊裝置使用量] 報告, 以瞭解貴組織中的使用者如何連線至團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfe8b11d633a8848d73e87c8fe0b4ecc8854062f
ms.sourcegitcommit: a5cde2df1aceed9d919ef53281dd0d75f1f5e183
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2019
ms.locfileid: "36667099"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="69c6b-103">Microsoft 團隊裝置使用量報告</span><span class="sxs-lookup"><span data-stu-id="69c6b-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="69c6b-104">Microsoft 團隊系統管理中心的 [小組裝置使用量] 報告可提供使用者連線至團隊之方式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="69c6b-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="69c6b-105">您可以使用報告來查看貴組織所使用的裝置, 包括在行動裝置上使用的小組數。</span><span class="sxs-lookup"><span data-stu-id="69c6b-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-report"></a><span data-ttu-id="69c6b-106">查看報表</span><span class="sxs-lookup"><span data-stu-id="69c6b-106">View the report</span></span>

1. <span data-ttu-id="69c6b-107">在 Microsoft [團隊管理中心] 的左導覽中, 按一下 [**分析] & 報表**], 然後在 [**報表**] 底下, 選取 [**團隊裝置使用方式**]。</span><span class="sxs-lookup"><span data-stu-id="69c6b-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports**, and then under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="69c6b-108">在 [**日期範圍**] 底下, 選取一個範圍, 然後按一下 [**執行報表**]。</span><span class="sxs-lookup"><span data-stu-id="69c6b-108">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="69c6b-109">小組系統![管理中心的 [小組裝置使用方式] 報告螢幕擷取畫面 (含標注])小組系統(../media/teams-reports-device-usage-with-callouts.png "管理中心的 [小組裝置使用方式] 報告螢幕擷取畫面 (含標注"))</span><span class="sxs-lookup"><span data-stu-id="69c6b-109">![Screen shot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screen shot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="69c6b-110">解讀報表</span><span class="sxs-lookup"><span data-stu-id="69c6b-110">Interpret the report</span></span>

|<span data-ttu-id="69c6b-111">圖說文字</span><span class="sxs-lookup"><span data-stu-id="69c6b-111">Callout</span></span> |<span data-ttu-id="69c6b-112">說明</span><span class="sxs-lookup"><span data-stu-id="69c6b-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="69c6b-113">**sr-1**</span><span class="sxs-lookup"><span data-stu-id="69c6b-113">**1**</span></span>   |<span data-ttu-id="69c6b-114">您可以在過去7天或28天的趨勢中查看小組裝置使用方式報告。</span><span class="sxs-lookup"><span data-stu-id="69c6b-114">The Teams device usage report can be viewed for trends over the last 7 days or 28 days.</span></span>  |
|<span data-ttu-id="69c6b-115">**pplx-2**</span><span class="sxs-lookup"><span data-stu-id="69c6b-115">**2**</span></span>   |<span data-ttu-id="69c6b-116">每個報告都有產生報告的日期。</span><span class="sxs-lookup"><span data-stu-id="69c6b-116">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="69c6b-117">報告通常會反映來自啟用時間的24到48小時延遲時間。</span><span class="sxs-lookup"><span data-stu-id="69c6b-117">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="69c6b-118">**3**</span><span class="sxs-lookup"><span data-stu-id="69c6b-118">**3**</span></span>   |<ul><li><span data-ttu-id="69c6b-119">圖表上的 X 軸代表用來連接至團隊的不同裝置 (**Windows**、 **Mac**、 **iOS**、 **Android 手機**)。</span><span class="sxs-lookup"><span data-stu-id="69c6b-119">The X axis on the chart represents the different devices (**Windows**, **Mac**, **iOS**, **Android Phone**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="69c6b-120">Y 軸是在所選時間範圍內使用裝置的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="69c6b-120">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="69c6b-121">將游標暫留在代表裝置的列上, 即可查看使用裝置連接至團隊的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="69c6b-121">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="69c6b-122">**4**</span><span class="sxs-lookup"><span data-stu-id="69c6b-122">**4**</span></span>   |<span data-ttu-id="69c6b-123">此表格可讓您細分使用者的裝置使用量。</span><span class="sxs-lookup"><span data-stu-id="69c6b-123">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="69c6b-124">[**顯示名稱**] 是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="69c6b-124">**Display name** is the display name of the user.</span></span> <span data-ttu-id="69c6b-125">您可以按一下顯示名稱, 移至 Microsoft 團隊系統管理中心的 [使用者設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="69c6b-125">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="69c6b-126">如果使用者是在 Windows 電腦上的小組桌面用戶端中使用中, 則會選取 [ **Windows** ]。</span><span class="sxs-lookup"><span data-stu-id="69c6b-126">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="69c6b-127">如果使用者在 macOS 電腦上的小組桌面用戶端中處於作用中, 則會選取**Mac** 。</span><span class="sxs-lookup"><span data-stu-id="69c6b-127">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="69c6b-128">如果使用者在 iOS 的 [小組行動用戶端] 上是作用中的, 就會選取**ios** 。</span><span class="sxs-lookup"><span data-stu-id="69c6b-128">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="69c6b-129">如果使用者在 Android 版團隊行動用戶端上是作用中的, 則會選取 [ **android 手機**]。</span><span class="sxs-lookup"><span data-stu-id="69c6b-129">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><span data-ttu-id="69c6b-130">[**上一個活動**] 是使用者參與團隊活動的最後一個日期 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="69c6b-130">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="69c6b-131">請注意, 如果使用者帳戶已不存在於 Azure AD 中, 則使用者名稱會在資料表中顯示為 "--"。</span><span class="sxs-lookup"><span data-stu-id="69c6b-131">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="69c6b-132">若要在表格中查看您想要的資訊, 請務必將資料行新增至資料表。</span><span class="sxs-lookup"><span data-stu-id="69c6b-132">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="69c6b-133">**500**</span><span class="sxs-lookup"><span data-stu-id="69c6b-133">**5**</span></span>   |<span data-ttu-id="69c6b-134">選取 [**編輯欄**] 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="69c6b-134">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="69c6b-135">**6**</span><span class="sxs-lookup"><span data-stu-id="69c6b-135">**6**</span></span>   |<span data-ttu-id="69c6b-136">您可以將報表匯出為 CSV 檔案, 以便進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="69c6b-136">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="69c6b-137">按一下 [**匯出至 Excel**], 然後在 [**下載**] 索引標籤上, 按一下 [**下載**] 以在準備好時下載報告。</span><span class="sxs-lookup"><span data-stu-id="69c6b-137">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="69c6b-138">![[下載] 索引標籤上顯示匯出報表的螢幕擷取畫面](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="69c6b-138">![Screen shot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="69c6b-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="69c6b-139">Related topics</span></span>

- [<span data-ttu-id="69c6b-140">團隊分析和報告</span><span class="sxs-lookup"><span data-stu-id="69c6b-140">Teams analytics and reporting</span></span>](teams-reporting-reference.md)