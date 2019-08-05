---
title: Microsoft 團隊裝置使用量報告
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/24/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 瞭解如何使用 Microsoft 團隊系統管理中心中的 [團隊裝置使用量] 報告, 以瞭解貴組織中的使用者如何連線至團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86d8e2dc145aa8538326b42f5110de69542e8453
ms.sourcegitcommit: 5791b98589e64df2e2bcd96f05fd2f869a65861f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36184605"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="33e3d-103">Microsoft 團隊裝置使用量報告</span><span class="sxs-lookup"><span data-stu-id="33e3d-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="33e3d-104">Microsoft 團隊系統管理中心的 [小組裝置使用量] 報告可提供使用者連線至團隊之方式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="33e3d-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="33e3d-105">您可以使用報告來查看貴組織所使用的裝置, 包括在行動裝置上使用的小組數。</span><span class="sxs-lookup"><span data-stu-id="33e3d-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

<span data-ttu-id="33e3d-106">![管理中心的 [小組裝置使用量] 報告螢幕擷取畫面](../media/teams-reports-device-usage.png "Microsoft 團隊系統管理中心的 [小組裝置使用量] 報告螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="33e3d-106">![Screen shot of the Teams device usage report in the admin center](../media/teams-reports-device-usage.png "Screen shot of the Teams device usage report in the Microsoft Teams admin center")</span></span>

## <a name="view-the-report"></a><span data-ttu-id="33e3d-107">查看報表</span><span class="sxs-lookup"><span data-stu-id="33e3d-107">View the report</span></span>

1. <span data-ttu-id="33e3d-108">移至 [Microsoft 團隊系統管理中心], 在左側導覽中, 按一下 [**分析] & 報表**], 然後在 [**報表**] 底下, 選取 [**團隊裝置使用方式**]。</span><span class="sxs-lookup"><span data-stu-id="33e3d-108">Go to the Microsoft Teams admin center, in the left navigation, click **Analytics & reports**, and then under **Report**, select **Teams device usage**.</span></span> 
2. <span data-ttu-id="33e3d-109">在 [**日期範圍**] 底下, 選取一個範圍, 然後按一下 [**執行報表**]。</span><span class="sxs-lookup"><span data-stu-id="33e3d-109">Under **Date range**, select a range, and then click **Run report**.</span></span> 

## <a name="interpret-the-report"></a><span data-ttu-id="33e3d-110">解讀報表</span><span class="sxs-lookup"><span data-stu-id="33e3d-110">Interpret the report</span></span>

<span data-ttu-id="33e3d-111">![管理中心的 [小組裝置使用量] 報告螢幕擷取畫面](../media/teams-reports-device-usage-with-callouts.png "Microsoft 團隊系統管理中心中使用編號標注的小組裝置使用方式報告螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="33e3d-111">![Screen shot of the Teams device usage report in the admin center](../media/teams-reports-device-usage-with-callouts.png "Screen shot of the Teams device usage report in the Microsoft Teams admin center with numbered callouts")</span></span>

|<span data-ttu-id="33e3d-112">圖說文字</span><span class="sxs-lookup"><span data-stu-id="33e3d-112">Callout</span></span> |<span data-ttu-id="33e3d-113">說明</span><span class="sxs-lookup"><span data-stu-id="33e3d-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="33e3d-114">**sr-1**</span><span class="sxs-lookup"><span data-stu-id="33e3d-114">**1**</span></span>   |<span data-ttu-id="33e3d-115">您可以在過去7天或28天的趨勢中查看小組裝置使用方式報告。</span><span class="sxs-lookup"><span data-stu-id="33e3d-115">The Teams device usage report can be viewed for trends over the last 7 days or 28 days.</span></span>  |
|<span data-ttu-id="33e3d-116">**pplx-2**</span><span class="sxs-lookup"><span data-stu-id="33e3d-116">**2**</span></span>   |<span data-ttu-id="33e3d-117">每個報告都有產生報告的日期。</span><span class="sxs-lookup"><span data-stu-id="33e3d-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="33e3d-118">報告通常會反映來自啟用時間的24到48小時延遲時間。</span><span class="sxs-lookup"><span data-stu-id="33e3d-118">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="33e3d-119">**3**</span><span class="sxs-lookup"><span data-stu-id="33e3d-119">**3**</span></span>   |<ul><li><span data-ttu-id="33e3d-120">圖表上的 X 軸代表用來連接至團隊的不同裝置 (**Windows**、 **Mac**、 **iOS**、 **Android 手機**)。</span><span class="sxs-lookup"><span data-stu-id="33e3d-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **iOS**, **Android Phone**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="33e3d-121">Y 軸是在所選時間範圍內使用裝置的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="33e3d-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="33e3d-122">將游標暫留在代表裝置的列上, 即可查看使用裝置連接至團隊的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="33e3d-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="33e3d-123">**4**</span><span class="sxs-lookup"><span data-stu-id="33e3d-123">**4**</span></span>   |<span data-ttu-id="33e3d-124">此表格可讓您細分使用者的裝置使用量。</span><span class="sxs-lookup"><span data-stu-id="33e3d-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="33e3d-125">[**顯示名稱**] 是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="33e3d-125">**Display name** is the display name of the user.</span></span> <span data-ttu-id="33e3d-126">您可以按一下顯示名稱, 移至 Microsoft 團隊系統管理中心的 [使用者設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="33e3d-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="33e3d-127">如果使用者是在 Windows 電腦上的小組桌面用戶端中使用中, 則會選取 [ **Windows** ]。</span><span class="sxs-lookup"><span data-stu-id="33e3d-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="33e3d-128">如果使用者在 macOS 電腦上的小組桌面用戶端中處於作用中, 則會選取**Mac** 。</span><span class="sxs-lookup"><span data-stu-id="33e3d-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="33e3d-129">如果使用者在 iOS 的 [小組行動用戶端] 上是作用中的, 就會選取**ios** 。</span><span class="sxs-lookup"><span data-stu-id="33e3d-129">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="33e3d-130">如果使用者在 Android 版團隊行動用戶端上是作用中的, 則會選取 [ **android 手機**]。</span><span class="sxs-lookup"><span data-stu-id="33e3d-130">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><span data-ttu-id="33e3d-131">[**上一個活動**] 是使用者參與團隊活動的最後一個日期 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="33e3d-131">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="33e3d-132">請注意, 如果使用者帳戶已不存在於 Azure AD 中, 則使用者名稱會在資料表中顯示為 "--"。</span><span class="sxs-lookup"><span data-stu-id="33e3d-132">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="33e3d-133">若要在表格中查看您想要的資訊, 請務必將資料行新增至資料表。</span><span class="sxs-lookup"><span data-stu-id="33e3d-133">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="33e3d-134">**500**</span><span class="sxs-lookup"><span data-stu-id="33e3d-134">**5**</span></span>   |<span data-ttu-id="33e3d-135">選取 [**編輯欄**] 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="33e3d-135">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="33e3d-136">**6**</span><span class="sxs-lookup"><span data-stu-id="33e3d-136">**6**</span></span>   |<span data-ttu-id="33e3d-137">您可以將報表匯出為 CSV 檔案, 以便進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="33e3d-137">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="33e3d-138">按一下 [**匯出至 Excel**], 然後在 [**下載**] 索引標籤上, 按一下 [**下載**] 以在準備好時下載報告。</span><span class="sxs-lookup"><span data-stu-id="33e3d-138">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="33e3d-139">![[下載] 索引標籤上顯示匯出報表的螢幕擷取畫面](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="33e3d-139">![Screen shot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|

## <a name="related-topics"></a><span data-ttu-id="33e3d-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="33e3d-140">Related topics</span></span>
- [<span data-ttu-id="33e3d-141">團隊分析和報告</span><span class="sxs-lookup"><span data-stu-id="33e3d-141">Teams analytics and reporting</span></span>](teams-reporting-reference.md)