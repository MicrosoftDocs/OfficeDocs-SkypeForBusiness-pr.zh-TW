---
title: Microsoft Teams資訊保護授權報告
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: 瞭解如何在系統管理中心Teams資訊保護授權報告Microsoft Teams查看貴組織中應用程式如何使用變更通知事件訂閱 API。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f5652ee503d6810a11f1b152dc0ea2dad23cf4df
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096877"
---
# <a name="microsoft-teams-information-protection-license-report"></a><span data-ttu-id="38fc1-103">Microsoft Teams資訊保護授權報告</span><span class="sxs-lookup"><span data-stu-id="38fc1-103">Microsoft Teams information protection license report</span></span>

<span data-ttu-id="38fc1-104">Teams 資訊保護授權報告提供訂閱變更通知事件以聆聽租使用者[](/graph/api/resources/subscription?view=graph-rest-1.0)層級 ([](/graph/api/resources/webhooks?view=graph-rest-1.0)即/teams/getAllMessage 或 /chats/getAllMessages) 之通知事件的深入資訊。</span><span class="sxs-lookup"><span data-stu-id="38fc1-104">The Teams information protection license report gives insight into apps that have [subscribed](/graph/api/resources/subscription?view=graph-rest-1.0) to [change notification](/graph/api/resources/webhooks?view=graph-rest-1.0) events to listen to created, updated, or deleted messages at tenant level (that is, /teams/getAllMessage or /chats/getAllMessages).</span></span> <span data-ttu-id="38fc1-105">只有在使用者擁有所需授權時，才成功送出與郵件對應的 [變更通知](/graph/teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="38fc1-105">A change notification corresponding to the message is sent successfully only when the user has the [required license](/graph/teams-licenses).</span></span>  <span data-ttu-id="38fc1-106">您可以查看特定使用者觸發的變更通知數。</span><span class="sxs-lookup"><span data-stu-id="38fc1-106">You can see how many change notifications was triggered by a given user.</span></span>


## <a name="view-the-information-protection-license-report"></a><span data-ttu-id="38fc1-107">查看資訊保護授權報告</span><span class="sxs-lookup"><span data-stu-id="38fc1-107">View the information protection license report</span></span>

<span data-ttu-id="38fc1-108">您必須是 Teams 服務系統管理員才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="38fc1-108">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="38fc1-109">請參閱[使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)，以了解取得系統管理員角色和權限。</span><span class="sxs-lookup"><span data-stu-id="38fc1-109">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="38fc1-110">在系統管理中心的左側導Microsoft Teams，選取分析&**報告**  >  **使用方式報告**。</span><span class="sxs-lookup"><span data-stu-id="38fc1-110">In the left navigation of the Microsoft Teams admin center, select **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="38fc1-111">On the **View reports** tab, under **Report**, select **Information Protection License**.</span><span class="sxs-lookup"><span data-stu-id="38fc1-111">On the **View reports** tab, under **Report**, select **Information Protection License**.</span></span>
2. <span data-ttu-id="38fc1-112">在 **日期範圍下**，選取範圍。</span><span class="sxs-lookup"><span data-stu-id="38fc1-112">Under **Date range**, select a range.</span></span>
3. <span data-ttu-id="38fc1-113">在 **應用程式下**，選取應用程式，然後選取執行 **報表**。</span><span class="sxs-lookup"><span data-stu-id="38fc1-113">Under **Apps**, select an app and then select **Run report**.</span></span>

    <span data-ttu-id="38fc1-114">![系統管理中心Teams資訊保護授權報告的螢幕擷取畫面Teams圖](../media/teams-info-protection-license-report-with-callouts.png "系統管理中心Teams資訊保護授權報告的螢幕擷取畫面Teams圖")</span><span class="sxs-lookup"><span data-stu-id="38fc1-114">![Screenshot of the Teams information protection license report in the Teams admin center with callouts](../media/teams-info-protection-license-report-with-callouts.png "Screenshot of the Teams information protection license report in the Teams admin center with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="38fc1-115">解譯報表</span><span class="sxs-lookup"><span data-stu-id="38fc1-115">Interpret the report</span></span>

|<span data-ttu-id="38fc1-116">標注</span><span class="sxs-lookup"><span data-stu-id="38fc1-116">Callout</span></span> |<span data-ttu-id="38fc1-117">說明</span><span class="sxs-lookup"><span data-stu-id="38fc1-117">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="38fc1-118">**1**</span><span class="sxs-lookup"><span data-stu-id="38fc1-118">**1**</span></span>   |<span data-ttu-id="38fc1-119">您可以針對過去 7 天、30 天或 90 天內的趨勢來查看資訊保護授權報告。</span><span class="sxs-lookup"><span data-stu-id="38fc1-119">The information protection license report can be viewed for trends over the last 7 days, 30, or 90 days.</span></span> |
|<span data-ttu-id="38fc1-120">**2**</span><span class="sxs-lookup"><span data-stu-id="38fc1-120">**2**</span></span>   |<span data-ttu-id="38fc1-121">應用程式名稱會顯示所有已訂閱以變更過去 n 天內郵件通知事件的應用程式清單，如日期範圍中選取的。</span><span class="sxs-lookup"><span data-stu-id="38fc1-121">App name will display a list of all apps that have subscribed to change notification events of messages in the last n days as selected in the date range.</span></span> |
|<span data-ttu-id="38fc1-122">**3**</span><span class="sxs-lookup"><span data-stu-id="38fc1-122">**3**</span></span>   |<span data-ttu-id="38fc1-123">下表提供所選 App 每個使用者的使用狀況明細。</span><span class="sxs-lookup"><span data-stu-id="38fc1-123">The table gives you a breakdown of usage per user for the selected app.</span></span><ul><li><span data-ttu-id="38fc1-124">**顯示名稱** 是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="38fc1-124">**Display name** is the display name of the user.</span></span> <span data-ttu-id="38fc1-125">選取顯示名稱，以前往系統管理中心中的使用者詳細Microsoft Teams頁面。</span><span class="sxs-lookup"><span data-stu-id="38fc1-125">Select the display name to go to the user's details page in the Microsoft Teams admin center.</span></span></li><li><span data-ttu-id="38fc1-126">**如果使用者擁有** 此處 [ (定義之一) https://docs.microsoft.com/en-us/graph/teams-licenses 授權是是 ]。</span><span class="sxs-lookup"><span data-stu-id="38fc1-126">**Has Required License** is yes if the user has one of the required licenses as defined (here)[https://docs.microsoft.com/en-us/graph/teams-licenses].</span></span> <span data-ttu-id="38fc1-127">如果使用者沒有所需的授權，系統會顯示指派授權連結，連結會流覽至 Microsoft 系統管理中心中的使用者授權詳細資料頁面 (使用者活動使用者>選取使用者名稱  >  \*\*\*\*) 。</span><span class="sxs-lookup"><span data-stu-id="38fc1-127">If the user does not have the required license, the _Assign license_ link is displayed which navigated to the user's license detail page in the Microsoft admin center (**Users** > **Active Users** > select username).</span></span></li><li><span data-ttu-id="38fc1-128">**授權保護事件** 是針對該使用者建立、更新或刪除的郵件，將唯一變更通知事件數寄到應用程式。</span><span class="sxs-lookup"><span data-stu-id="38fc1-128">**License Protected Events** is the number of unique change notification events sent to the app against a message which was created, updated or deleted by that user.</span></span></li></ul> |
|<span data-ttu-id="38fc1-129">**4**</span><span class="sxs-lookup"><span data-stu-id="38fc1-129">**4**</span></span>   |<span data-ttu-id="38fc1-130">將報表匯出為 CSV 檔案，進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="38fc1-130">Export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="38fc1-131">選取 **匯出至Excel**，然後選取下載 **選項卡**。選取 **下載** 以在報表準備就緒時下載報表。</span><span class="sxs-lookup"><span data-stu-id="38fc1-131">Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready.</span></span> |
|<span data-ttu-id="38fc1-132">**5**</span><span class="sxs-lookup"><span data-stu-id="38fc1-132">**5**</span></span>   |<span data-ttu-id="38fc1-133">將報表匯出為 CSV 檔案，進行離線分析。</span><span class="sxs-lookup"><span data-stu-id="38fc1-133">Export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="38fc1-134">選取 **匯出至Excel**，然後選取下載 **選項卡**。選取 **下載** 以在報表準備就緒時下載報表。</span><span class="sxs-lookup"><span data-stu-id="38fc1-134">Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready.</span></span> <span data-ttu-id="38fc1-135">當您在 Excel中查看報表時，您也會看到一個識別碼和電子郵件欄，代表使用者的使用者識別碼和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="38fc1-135">When you view the report in Excel, you'll also see an **Id** and **email** column, which represents the User ID and email address of the user.</span></span> |

## <a name="make-the-user-specific-data-anonymous"></a><span data-ttu-id="38fc1-136">將使用者特定資料匿名</span><span class="sxs-lookup"><span data-stu-id="38fc1-136">Make the user-specific data anonymous</span></span>

<span data-ttu-id="38fc1-137">若要將使用者活動報告中Teams匿名，您必須是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="38fc1-137">To make the data in the Teams user activity report anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="38fc1-138">這會隱藏可辨識的資訊，例如報表及其匯出中的顯示名稱、電子郵件和 Azure AD 識別碼。</span><span class="sxs-lookup"><span data-stu-id="38fc1-138">This will hide identifiable information such as display name, email, and Azure AD ID in reports and their exports.</span></span>

1. <span data-ttu-id="38fc1-139">在 Microsoft 365 系統管理中心中，設定組織 \> 設定，然後選擇在服務選項卡下的報表 。 </span><span class="sxs-lookup"><span data-stu-id="38fc1-139">In the Microsoft 365 admin center, go to **Settings** \> **Org Settings**, and under the **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="38fc1-140">選取 **報表**，然後選擇顯示 **匿名識別碼**。</span><span class="sxs-lookup"><span data-stu-id="38fc1-140">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="38fc1-141">此設定會同時適用于系統管理中心Microsoft 365 系統管理中心使用方式Teams報告。</span><span class="sxs-lookup"><span data-stu-id="38fc1-141">This setting gets applied both to the usage reports in the Microsoft 365 admin center and the Teams admin center.</span></span>
  
3. <span data-ttu-id="38fc1-142">選取 **儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="38fc1-142">Select **Save changes**.</span></span>
