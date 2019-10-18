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
- M365-collaboration
description: 瞭解如何使用 Microsoft 團隊系統管理中心中的 [團隊裝置使用量] 報告，以瞭解貴組織中的使用者如何連線至團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c961b6c5897d0c494d0461a3533cae63fa613d41
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568394"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="3e0d5-103">Microsoft 團隊裝置使用量報告</span><span class="sxs-lookup"><span data-stu-id="3e0d5-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="3e0d5-104">Microsoft 團隊系統管理中心的 [小組裝置使用量] 報告可提供使用者連線至團隊之方式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="3e0d5-105">您可以使用報告來查看貴組織所使用的裝置，包括在行動裝置上使用的小組數。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-report"></a><span data-ttu-id="3e0d5-106">查看報表</span><span class="sxs-lookup"><span data-stu-id="3e0d5-106">View the report</span></span>

1. <span data-ttu-id="3e0d5-107">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**分析] & 報告** > **使用方式報告**。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="3e0d5-108">在 [**查看報表**] 索引標籤的 [**報表**] 底下，選取 [**團隊裝置使用方式**]。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="3e0d5-109">在 [**日期範圍**] 底下，選取一個範圍，然後按一下 [**執行報表**]。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="3e0d5-110">![[小組系統管理中心] 的 [小組裝置使用方式] 報告螢幕擷取畫面（含標注）](../media/teams-reports-device-usage-with-callouts.png "[小組系統管理中心] 的 [小組裝置使用方式] 報告螢幕擷取畫面（含標注）")</span><span class="sxs-lookup"><span data-stu-id="3e0d5-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="3e0d5-111">解讀報表</span><span class="sxs-lookup"><span data-stu-id="3e0d5-111">Interpret the report</span></span>

|<span data-ttu-id="3e0d5-112">圖說文字</span><span class="sxs-lookup"><span data-stu-id="3e0d5-112">Callout</span></span> |<span data-ttu-id="3e0d5-113">說明</span><span class="sxs-lookup"><span data-stu-id="3e0d5-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="3e0d5-114">**sr-1**</span><span class="sxs-lookup"><span data-stu-id="3e0d5-114">**1**</span></span>   |<span data-ttu-id="3e0d5-115">您可以在過去7天或28天的趨勢中查看小組裝置使用方式報告。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-115">The Teams device usage report can be viewed for trends over the last 7 days or 28 days.</span></span>  |
|<span data-ttu-id="3e0d5-116">**pplx-2**</span><span class="sxs-lookup"><span data-stu-id="3e0d5-116">**2**</span></span>   |<span data-ttu-id="3e0d5-117">每個報告都有產生報告的日期。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="3e0d5-118">報告通常會反映來自啟用時間的24到48小時延遲時間。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-118">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="3e0d5-119">**3**</span><span class="sxs-lookup"><span data-stu-id="3e0d5-119">**3**</span></span>   |<ul><li><span data-ttu-id="3e0d5-120">圖表上的 X 軸代表用來連接至團隊的不同裝置（**Windows**、 **Mac**、 **iOS**、 **Android 手機**）。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **iOS**, **Android Phone**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="3e0d5-121">Y 軸是在所選時間範圍內使用裝置的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="3e0d5-122">將游標暫留在代表裝置的列上，即可查看使用裝置連接至團隊的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="3e0d5-123">**4**</span><span class="sxs-lookup"><span data-stu-id="3e0d5-123">**4**</span></span>   |<span data-ttu-id="3e0d5-124">此表格可讓您細分使用者的裝置使用量。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="3e0d5-125">[**顯示名稱**] 是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-125">**Display name** is the display name of the user.</span></span> <span data-ttu-id="3e0d5-126">您可以按一下顯示名稱，移至 Microsoft 團隊系統管理中心的 [使用者設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="3e0d5-127">如果使用者是在 Windows 電腦上的小組桌面用戶端中使用中，則會選取 [ **Windows** ]。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="3e0d5-128">如果使用者在 macOS 電腦上的小組桌面用戶端中處於作用中，則會選取**Mac** 。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="3e0d5-129">如果使用者在 iOS 的 [小組行動用戶端] 上是作用中的，就會選取**ios** 。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-129">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="3e0d5-130">如果使用者在 Android 版團隊行動用戶端上是作用中的，則會選取 [ **android 手機**]。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-130">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><span data-ttu-id="3e0d5-131">[**上一個活動**] 是使用者參與團隊活動的最後一個日期（UTC）。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-131">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="3e0d5-132">請注意，如果使用者帳戶已不存在於 Azure AD 中，則使用者名稱會在資料表中顯示為 "--"。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-132">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="3e0d5-133">若要在表格中查看您想要的資訊，請務必將資料行新增至資料表。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-133">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="3e0d5-134">**500**</span><span class="sxs-lookup"><span data-stu-id="3e0d5-134">**5**</span></span>   |<span data-ttu-id="3e0d5-135">選取 [**編輯欄**] 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-135">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="3e0d5-136">**6**</span><span class="sxs-lookup"><span data-stu-id="3e0d5-136">**6**</span></span>   |<span data-ttu-id="3e0d5-137">您可以將報表匯出為 CSV 檔案，以便進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-137">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="3e0d5-138">按一下 [**匯出至 Excel**]，然後在 [**下載**] 索引標籤上，按一下 [**下載**] 以在準備好時下載報告。</span><span class="sxs-lookup"><span data-stu-id="3e0d5-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="3e0d5-139">![[下載] 索引標籤上顯示已匯出報表的螢幕擷取畫面](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="3e0d5-139">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="3e0d5-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="3e0d5-140">Related topics</span></span>

- [<span data-ttu-id="3e0d5-141">團隊分析和報告</span><span class="sxs-lookup"><span data-stu-id="3e0d5-141">Teams analytics and reporting</span></span>](teams-reporting-reference.md)