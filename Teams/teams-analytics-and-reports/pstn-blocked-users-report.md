---
title: Microsoft 團隊 PSTN 封鎖的使用者報告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: 使用 Microsoft 團隊系統管理中心中的 PSTN 封鎖使用者報告，以瞭解貴組織的小組使用者是否已封鎖進行 PSTN 通話。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 511485fa156ba448368809edf54728ada1b80be7
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904905"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="75653-103">Microsoft 團隊 PSTN 封鎖的使用者報告</span><span class="sxs-lookup"><span data-stu-id="75653-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="75653-104">Microsoft 團隊系統管理中心的 PSTN 封鎖的使用者報告會顯示您組織中被封鎖在團隊中進行 PSTN 通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="75653-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="75653-105">您可以查看每個封鎖使用者的詳細資訊，包括其指派的電話號碼，以及他們被封鎖撥打的原因。</span><span class="sxs-lookup"><span data-stu-id="75653-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="75653-106">查看 PSTN 封鎖的使用者報告</span><span class="sxs-lookup"><span data-stu-id="75653-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="75653-107">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**分析] & 報告** > **使用方式報告**。</span><span class="sxs-lookup"><span data-stu-id="75653-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="75653-108">在 [**查看報表**] 索引標籤的 [**報表**] 底下，選取 [ **PSTN 封鎖的使用者**]，然後按一下 [**執行報表**]。</span><span class="sxs-lookup"><span data-stu-id="75653-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="75653-109">![系統管理中心的 PSTN 已封鎖使用者報告報告的螢幕擷取畫面](../media/teams-reports-pstn-blocked-users-with-callouts.png "使用編號標注的 Microsoft 團隊系統管理中心的 PSTN 已封鎖使用者報告螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="75653-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="75653-110">解讀報表</span><span class="sxs-lookup"><span data-stu-id="75653-110">Interpret the report</span></span>

|<span data-ttu-id="75653-111">圖說文字</span><span class="sxs-lookup"><span data-stu-id="75653-111">Callout</span></span> |<span data-ttu-id="75653-112">說明</span><span class="sxs-lookup"><span data-stu-id="75653-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="75653-113">**1**</span><span class="sxs-lookup"><span data-stu-id="75653-113">**1**</span></span>   |<span data-ttu-id="75653-114">每個報告都有產生的日期。</span><span class="sxs-lookup"><span data-stu-id="75653-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="75653-115">報告通常會反映來自啟用時間的24到48小時延遲時間。</span><span class="sxs-lookup"><span data-stu-id="75653-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="75653-116">**2**</span><span class="sxs-lookup"><span data-stu-id="75653-116">**2**</span></span>   |<span data-ttu-id="75653-117">X 軸是日期。</span><span class="sxs-lookup"><span data-stu-id="75653-117">The X axis is the date.</span></span> <span data-ttu-id="75653-118">Y 軸是使用者數目。</span><span class="sxs-lookup"><span data-stu-id="75653-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="75653-119">將游標停留在指定日期上的點上，即可查看該日期封鎖的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="75653-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="75653-120">**3**</span><span class="sxs-lookup"><span data-stu-id="75653-120">**3**</span></span>   |<span data-ttu-id="75653-121">下表提供封鎖撥打 PSTN 通話的所有使用者明細。</span><span class="sxs-lookup"><span data-stu-id="75653-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="75653-122">它會顯示已指派電話系統或音訊會議的所有使用者，並提供每個使用者的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="75653-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="75653-123">[**顯示名稱**] 是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="75653-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="75653-124">您可以按一下顯示名稱，移至 Microsoft 團隊系統管理中心的 [使用者設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="75653-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="75653-125">[**電話**] 是指派給使用者的號碼。</span><span class="sxs-lookup"><span data-stu-id="75653-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="75653-126">**封鎖的原因**是封鎖使用者進行通話的原因。</span><span class="sxs-lookup"><span data-stu-id="75653-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="75653-127">**封鎖的動作**會告知您使用者是否已被封鎖或解除封鎖，無法在小組中進行 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="75653-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="75653-128">**封鎖時間**是封鎖使用者撥打電話的日期和時間（UTC）。</span><span class="sxs-lookup"><span data-stu-id="75653-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="75653-129">若要在表格中查看您想要的資訊，請務必將資料行新增至資料表。</span><span class="sxs-lookup"><span data-stu-id="75653-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="75653-130">**4**</span><span class="sxs-lookup"><span data-stu-id="75653-130">**4**</span></span>   |<span data-ttu-id="75653-131">選取 [**編輯欄**] 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="75653-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="75653-132">**500**</span><span class="sxs-lookup"><span data-stu-id="75653-132">**5**</span></span>   |<span data-ttu-id="75653-133">選取 [**全螢幕**]，以全螢幕模式查看報告。</span><span class="sxs-lookup"><span data-stu-id="75653-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="75653-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="75653-134">Related topics</span></span>

- [<span data-ttu-id="75653-135">團隊分析和報告</span><span class="sxs-lookup"><span data-stu-id="75653-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)