---
title: Microsoft Teams裝置使用方式報告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在系統管理中心Teams裝置使用方式Microsoft Teams，以查看貴組織的使用者如何Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478353"
---
# <a name="microsoft-teams-device-usage-report"></a><span data-ttu-id="01bda-103">Microsoft Teams裝置使用方式報告</span><span class="sxs-lookup"><span data-stu-id="01bda-103">Microsoft Teams device usage report</span></span>

<span data-ttu-id="01bda-104">系統Teams系統管理中心中的 Microsoft Teams 裝置使用方式報告會提供使用者如何連接到Teams。</span><span class="sxs-lookup"><span data-stu-id="01bda-104">The Teams device usage report in the Microsoft Teams admin center provides you with information about how users connect to Teams.</span></span> <span data-ttu-id="01bda-105">您可以使用報表來查看整個組織使用的裝置，包括Teams行動裝置使用多少裝置。</span><span class="sxs-lookup"><span data-stu-id="01bda-105">You can use the report to see the devices that are used across your organization, including how many use Teams from their mobile devices when on-the-go.</span></span>  

## <a name="view-the-device-usage-report"></a><span data-ttu-id="01bda-106">查看裝置使用方式報告</span><span class="sxs-lookup"><span data-stu-id="01bda-106">View the device usage report</span></span>

1. <span data-ttu-id="01bda-107">在系統管理中心的左側導Microsoft Teams，按一下 [分析&**報告**  >  **使用方式報告**。</span><span class="sxs-lookup"><span data-stu-id="01bda-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="01bda-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span><span class="sxs-lookup"><span data-stu-id="01bda-108">On the **View reports** tab, under **Report**, select **Teams device usage**.</span></span>
2. <span data-ttu-id="01bda-109">在 **[日期範圍**」 下，選取範圍，然後按一下 [ **執行報表**> 。</span><span class="sxs-lookup"><span data-stu-id="01bda-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

    <span data-ttu-id="01bda-110">![系統管理中心Teams裝置使用方式報表的螢幕擷取畫面Teams圖](../media/teams-reports-device-usage-with-callouts.png "系統管理中心Teams裝置使用方式報表的螢幕擷取畫面Teams圖")</span><span class="sxs-lookup"><span data-stu-id="01bda-110">![Screenshot of the Teams device usage report in the Teams admin center with callouts](../media/teams-reports-device-usage-with-callouts.png "Screenshot of the Teams device usage report in the Teams admin center  with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="01bda-111">解譯報表</span><span class="sxs-lookup"><span data-stu-id="01bda-111">Interpret the report</span></span>

|<span data-ttu-id="01bda-112">標注</span><span class="sxs-lookup"><span data-stu-id="01bda-112">Callout</span></span> |<span data-ttu-id="01bda-113">描述</span><span class="sxs-lookup"><span data-stu-id="01bda-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="01bda-114">**1**</span><span class="sxs-lookup"><span data-stu-id="01bda-114">**1**</span></span>   |<span data-ttu-id="01bda-115">您可以Teams裝置使用方式報告，查看過去 7 天或 30 天內的趨勢。</span><span class="sxs-lookup"><span data-stu-id="01bda-115">The Teams device usage report can be viewed for trends over the last 7 days or 30 days.</span></span>  |
|<span data-ttu-id="01bda-116">**2**</span><span class="sxs-lookup"><span data-stu-id="01bda-116">**2**</span></span>   |<span data-ttu-id="01bda-117">每個報表都有產生報表的日期。</span><span class="sxs-lookup"><span data-stu-id="01bda-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="01bda-118">報告通常會反映啟用時間 24 小時的延遲。</span><span class="sxs-lookup"><span data-stu-id="01bda-118">The reports usually reflect a 24 hour latency from time of activity.</span></span> |
|<span data-ttu-id="01bda-119">**3**</span><span class="sxs-lookup"><span data-stu-id="01bda-119">**3**</span></span>   |<ul><li><span data-ttu-id="01bda-120">圖表上的 X 軸代表用來 (Windows、Mac、Linux、iOS、Android \*\*\*\*\*\*電話、web\*\*) 用於Teams。    </span><span class="sxs-lookup"><span data-stu-id="01bda-120">The X axis on the chart represents the different devices (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) used to connect to Teams.</span></span> </li><li><span data-ttu-id="01bda-121">Y 軸是所選時段內使用裝置的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="01bda-121">The Y axis is the number of users using the device over the selected time period.</span></span></li> </ul><span data-ttu-id="01bda-122">將游標停留在代表裝置的長條上，以查看使用裝置連接到Teams。</span><span class="sxs-lookup"><span data-stu-id="01bda-122">Hover over the bar representing a device to see the number of users using the device to connect to Teams.</span></span>|
|<span data-ttu-id="01bda-123">**4**</span><span class="sxs-lookup"><span data-stu-id="01bda-123">**4**</span></span>   |<span data-ttu-id="01bda-124">下表提供使用者裝置使用量的明細。</span><span class="sxs-lookup"><span data-stu-id="01bda-124">The table gives you a breakdown of device usage by user.</span></span> <ul><li><span data-ttu-id="01bda-125">**使用者** 名稱是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="01bda-125">**Username** is the display name of the user.</span></span> <span data-ttu-id="01bda-126">您可以按一下顯示名稱，前往系統管理中心中的使用者Microsoft Teams頁面。</span><span class="sxs-lookup"><span data-stu-id="01bda-126">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li><li><span data-ttu-id="01bda-127">**Windows，** 如果使用者在以電腦為基礎的電腦Teams桌面用戶端中Windows，系統即會選取該選項。</span><span class="sxs-lookup"><span data-stu-id="01bda-127">**Windows** is selected if the user was active in the Teams desktop client on a Windows-based computer.</span></span></li><li><span data-ttu-id="01bda-128">**如果使用者在 macOS** 電腦上使用 Teams桌面用戶端，會選取 Mac。</span><span class="sxs-lookup"><span data-stu-id="01bda-128">**Mac** is selected if the user was active in the Teams desktop client on a macOS computer.</span></span> </li> <li><span data-ttu-id="01bda-129">**如果使用者** 在 Linux 電腦上使用Teams桌面用戶端，會選取 Linux。</span><span class="sxs-lookup"><span data-stu-id="01bda-129">**Linux** is selected if the user was active in the Teams desktop client on a Linux computer.</span></span> </li> <li><span data-ttu-id="01bda-130">**如果使用者在 iOS** 行動用戶端上Teams iOS，即會選取 iOS。</span><span class="sxs-lookup"><span data-stu-id="01bda-130">**iOS** is selected if the user was active on the Teams mobile client for iOS.</span></span></li><li><span data-ttu-id="01bda-131">**如果使用者使用** Android 行動Teams，系統即會選取 Android 手機。</span><span class="sxs-lookup"><span data-stu-id="01bda-131">**Android phone** is selected if the user was active on the Teams mobile client for Android.</span></span> <li><li><span data-ttu-id="01bda-132">**如果使用者** 在 Web 用戶端上Teams已選取 Web。</span><span class="sxs-lookup"><span data-stu-id="01bda-132">**Web** is selected if the user was active on the Teams web client.</span></span> <li><span data-ttu-id="01bda-133">**上次活動** 是使用者 (UTC) 最後一個Teams日期。</span><span class="sxs-lookup"><span data-stu-id="01bda-133">**Last activity** is the last date (UTC) that the user participated in a Teams activity.</span></span></li> </ul> <span data-ttu-id="01bda-134">請注意，如果 Azure AD 中不再有使用者帳戶，使用者名稱會顯示為 「--」于表格中。</span><span class="sxs-lookup"><span data-stu-id="01bda-134">Note that if a user account no longer exists in Azure AD, the user name is displayed as "--" in the table.</span></span> <br><br><span data-ttu-id="01bda-135">若要在表格中查看您想要的資訊，請務必新增欄至資料表。</span><span class="sxs-lookup"><span data-stu-id="01bda-135">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="01bda-136">**5**</span><span class="sxs-lookup"><span data-stu-id="01bda-136">**5**</span></span>   |<span data-ttu-id="01bda-137">選取 **編輯欄** 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="01bda-137">Select **Edit columns** to add or remove columns in the table.</span></span> |
|<span data-ttu-id="01bda-138">**6**</span><span class="sxs-lookup"><span data-stu-id="01bda-138">**6**</span></span>   |<span data-ttu-id="01bda-139">您可以將報表匯出至 CSV 檔案，進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="01bda-139">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="01bda-140">按一下 **[匯出Excel，** 然後在 [下載>選項卡上，按一下[下載以在報表準備就緒時下載報表。</span><span class="sxs-lookup"><span data-stu-id="01bda-140">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><br><span data-ttu-id="01bda-141">![顯示匯出報表的下載清單螢幕擷取畫面](../media/teams-reports-export-to-csv.png)</span><span class="sxs-lookup"><span data-stu-id="01bda-141">![Screenshot of the Downloads tab showing exported reports](../media/teams-reports-export-to-csv.png)</span></span>|


## <a name="make-the-user-specific-data-anonymous"></a><span data-ttu-id="01bda-142">將使用者特定資料匿名</span><span class="sxs-lookup"><span data-stu-id="01bda-142">Make the user specific data anonymous</span></span>

<span data-ttu-id="01bda-143">若要將裝置使用方式報告中Teams匿名，您必須是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="01bda-143">To make the data in Teams device usage report anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="01bda-144">這會隱藏可辨識的資訊，例如報表及其匯出中的顯示名稱、電子郵件和 AAD 識別碼。</span><span class="sxs-lookup"><span data-stu-id="01bda-144">This will hide identifiable information such as display name, email and AAD ID in report and their export.</span></span>

1. <span data-ttu-id="01bda-145">在 Microsoft 365系統管理中心中，前往 設定組織設定，然後選取在服務設定下 \> \*\*\*\*，選擇報告。</span><span class="sxs-lookup"><span data-stu-id="01bda-145">In Microsoft 365 admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="01bda-146">選取 **報表**，然後選擇顯示 **匿名識別碼**。</span><span class="sxs-lookup"><span data-stu-id="01bda-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="01bda-147">此設定會同時Microsoft 365系統管理中心的使用方式報告，Teams系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="01bda-147">This setting gets applied both to the usage reports in Microsoft 365 admin center as well as Teams admin center.</span></span>
  
3. <span data-ttu-id="01bda-148">選取 **儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="01bda-148">Select **Save changes**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="01bda-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="01bda-149">Related topics</span></span>

- [<span data-ttu-id="01bda-150">Teams分析與報告</span><span class="sxs-lookup"><span data-stu-id="01bda-150">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
