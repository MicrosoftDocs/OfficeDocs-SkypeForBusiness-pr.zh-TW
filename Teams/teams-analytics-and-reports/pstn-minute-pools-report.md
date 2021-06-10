---
title: Microsoft TeamsPSTN 分鐘數庫報告
author: cichur
ms.author: v-cichur
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
description: 如何在系統管理中心Teams PSTN 分鐘Microsoft Teams報表來查看貴組織目前月份內使用的分鐘數。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d28e33ae820407ffe8c9561cae8c79863532417
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305987"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a><span data-ttu-id="0632a-103">Microsoft TeamsPSTN 分鐘數庫報告</span><span class="sxs-lookup"><span data-stu-id="0632a-103">Microsoft Teams PSTN minute pools report</span></span>

<span data-ttu-id="0632a-104">Microsoft Teams 系統管理中心中的 Teams PSTN 分鐘數庫報告，顯示您當月所耗用分鐘數，讓您概觀貴組織的音訊會議和通話活動。</span><span class="sxs-lookup"><span data-stu-id="0632a-104">The Teams PSTN minute pools report in the Microsoft Teams admin center gives you an overview of audio conferencing and calling activity in your organization by showing you the number of minutes consumed during the current month.</span></span> <span data-ttu-id="0632a-105">您可以查看活動明細，包括通話使用授權、通話總分鐘數、已用分鐘數，以及授權使用量 。根據位置。</span><span class="sxs-lookup"><span data-stu-id="0632a-105">You can see a breakdown of activity including the license used for calls, total minutes available, used minutes, and license usage by location.</span></span>

## <a name="view-the-pstn-minute-pools-report"></a><span data-ttu-id="0632a-106">查看 PSTN 分鐘數庫報告</span><span class="sxs-lookup"><span data-stu-id="0632a-106">View the PSTN minute pools report</span></span>

<span data-ttu-id="0632a-107">在系統管理中心的左側導Microsoft Teams，按一下 [分析&**報告**  >  **使用方式報告**。</span><span class="sxs-lookup"><span data-stu-id="0632a-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="0632a-108">在 [ **查看報表>** 選項卡的 [ **報表>** 下，選取 **[PSTN 分鐘數庫**，然後按一下 [ **執行報表**> 。</span><span class="sxs-lookup"><span data-stu-id="0632a-108">On the **View reports** tab, under **Report**, select **PSTN minute pools**, and then click **Run report**.</span></span>

<span data-ttu-id="0632a-109">![系統管理中心Teams PSTN 分鐘數庫報表的螢幕擷取畫面](../media/teams-reports-pstn-minute-pools-with-callouts.png "系統管理中心Teams PSTN 分鐘Microsoft Teams包含編號圖說義的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="0632a-109">![Screenshot of the Teams PSTN minute pools report in the admin center](../media/teams-reports-pstn-minute-pools-with-callouts.png "Screenshot of the Teams PSTN minute pools report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="0632a-110">解譯報表</span><span class="sxs-lookup"><span data-stu-id="0632a-110">Interpret the report</span></span>

|<span data-ttu-id="0632a-111">標注</span><span class="sxs-lookup"><span data-stu-id="0632a-111">Callout</span></span> |<span data-ttu-id="0632a-112">描述</span><span class="sxs-lookup"><span data-stu-id="0632a-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="0632a-113">**1**</span><span class="sxs-lookup"><span data-stu-id="0632a-113">**1**</span></span>   |<span data-ttu-id="0632a-114">每個報表都有產生日期。</span><span class="sxs-lookup"><span data-stu-id="0632a-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="0632a-115">報告通常會反映啟用時間起 24 到 48 小時的延遲。</span><span class="sxs-lookup"><span data-stu-id="0632a-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="0632a-116">**2**</span><span class="sxs-lookup"><span data-stu-id="0632a-116">**2**</span></span>   |<span data-ttu-id="0632a-117">按一下授權 (功能) 以查看該功能的活動。</span><span class="sxs-lookup"><span data-stu-id="0632a-117">Click a capability (license) to view activity for that capability.</span></span> |
|<span data-ttu-id="0632a-118">**3**</span><span class="sxs-lookup"><span data-stu-id="0632a-118">**3**</span></span>   |<span data-ttu-id="0632a-119">X 軸是國家/地區。</span><span class="sxs-lookup"><span data-stu-id="0632a-119">The X axis is country or region.</span></span> <span data-ttu-id="0632a-120">Y 軸是分鐘數。</span><span class="sxs-lookup"><span data-stu-id="0632a-120">The Y axis is number of minutes.</span></span> <br><span data-ttu-id="0632a-121">將游標停留在圖表上的橫條圖上，以查看該使用位置的活動。</span><span class="sxs-lookup"><span data-stu-id="0632a-121">Hover over a bar on the chart to see the activity for that usage location.</span></span>  |
|<span data-ttu-id="0632a-122">**4**</span><span class="sxs-lookup"><span data-stu-id="0632a-122">**4**</span></span>   |<span data-ttu-id="0632a-123">您可以按一下圖例中的專案來篩選圖表上看到的專案。</span><span class="sxs-lookup"><span data-stu-id="0632a-123">You can filter what you see on the chart by clicking an item in the legend.</span></span> <span data-ttu-id="0632a-124">例如，按一下 [ **未使用的**、 **國內** 使用者、沒有 **資料** 或 **國際資料，** 只用來查看每個使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="0632a-124">For example, click **Unused**, **Domestic users**, **No data**, or **International used** to see only the info related to each one.</span></span> |
|<span data-ttu-id="0632a-125">**5**</span><span class="sxs-lookup"><span data-stu-id="0632a-125">**5**</span></span>   |<span data-ttu-id="0632a-126">表格提供您根據功能及使用位置細分的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="0632a-126">The table gives you a breakdown of minute pools by capability and usage location.</span></span> <ul><li><span data-ttu-id="0632a-127">**國家/地區是** 使用位置。</span><span class="sxs-lookup"><span data-stu-id="0632a-127">**Country or region** is the usage location.</span></span> </li><li><span data-ttu-id="0632a-128">**功能描述** 是通話使用之授權的描述。</span><span class="sxs-lookup"><span data-stu-id="0632a-128">**Capability description** is the description of the license used for the call.</span></span>  <span data-ttu-id="0632a-129">您可能會在此報告中看到的功能描述包括：</span><span class="sxs-lookup"><span data-stu-id="0632a-129">The capability descriptions you may see in this report include:</span></span> <ul><li><span data-ttu-id="0632a-130">國內及國際通話方案 (1200 分鐘) </span><span class="sxs-lookup"><span data-stu-id="0632a-130">Domestic and international calling plan (1200 domestic minutes)</span></span></li><li><span data-ttu-id="0632a-131">國內及國際通話方案 (3000 分鐘) </span><span class="sxs-lookup"><span data-stu-id="0632a-131">Domestic and international calling plan (3000 domestic minutes)</span></span></li><li><span data-ttu-id="0632a-132">國內及國際通話方案 (600 分鐘) </span><span class="sxs-lookup"><span data-stu-id="0632a-132">Domestic and international calling plan (600 international minutes)</span></span></li></ul></li><br><li><span data-ttu-id="0632a-133">**總分鐘** 數是一個月的總可用分鐘數。</span><span class="sxs-lookup"><span data-stu-id="0632a-133">**Total minutes** is the total number of minutes available for the month.</span></span></li><li><span data-ttu-id="0632a-134">**使用分鐘** 數是每個月使用的分鐘數</span><span class="sxs-lookup"><span data-stu-id="0632a-134">**Minutes used** is the number of minutes used each month</span></span></li> <li><span data-ttu-id="0632a-135">**可用的分鐘** 數是該月的剩餘分鐘數。</span><span class="sxs-lookup"><span data-stu-id="0632a-135">**Minutes available** is the number of minutes remaining for the month.</span></span></li><li><span data-ttu-id="0632a-136">**功能** 是通話所使用的授權。</span><span class="sxs-lookup"><span data-stu-id="0632a-136">**Capability** is the license used for the call.</span></span> <span data-ttu-id="0632a-137">您可能會看到下列授權：</span><span class="sxs-lookup"><span data-stu-id="0632a-137">The licenses you may see include:</span></span><ul><li><span data-ttu-id="0632a-138">**MCOPSTN1** - 國內通話方案 (3000 分鐘美國 / 1200 分鐘的歐盟方案) </span><span class="sxs-lookup"><span data-stu-id="0632a-138">**MCOPSTN1** - Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span></li><li><span data-ttu-id="0632a-139">**MCOPSTN2** - 國際通話方案</span><span class="sxs-lookup"><span data-stu-id="0632a-139">**MCOPSTN2** - International Calling Plan</span></span></li><li><span data-ttu-id="0632a-140">**MCOPSTN5** - 國內通話方案 (120 分鐘的通話方案) </span><span class="sxs-lookup"><span data-stu-id="0632a-140">**MCOPSTN5** - Domestic Calling Plan (120 min calling plan)</span></span></li><li><span data-ttu-id="0632a-141">**MCOPSTN6** - 國內通話方案 (240 分鐘的通話方案) </span><span class="sxs-lookup"><span data-stu-id="0632a-141">**MCOPSTN6** - Domestic Calling Plan (240 min calling plan)</span></span></li><li><span data-ttu-id="0632a-142">**MCOMEETADD** - 音訊會議</span><span class="sxs-lookup"><span data-stu-id="0632a-142">**MCOMEETADD** - Audio Conferencing</span></span></li></ul></li> </ul> <span data-ttu-id="0632a-143">若要在表格中查看您想要的資訊，請務必新增欄至資料表。</span><span class="sxs-lookup"><span data-stu-id="0632a-143">To see the information that you want in the table, make sure to add the columns to the table.</span></span>|
|<span data-ttu-id="0632a-144">**6**</span><span class="sxs-lookup"><span data-stu-id="0632a-144">**6**</span></span>   |<span data-ttu-id="0632a-145">選取 **編輯欄** 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="0632a-145">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="0632a-146">**7**</span><span class="sxs-lookup"><span data-stu-id="0632a-146">**7**</span></span>   |<span data-ttu-id="0632a-147">選取 **全螢幕** 以全螢幕模式來查看報表。</span><span class="sxs-lookup"><span data-stu-id="0632a-147">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="0632a-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="0632a-148">Related topics</span></span>

- [<span data-ttu-id="0632a-149">Teams分析與報告</span><span class="sxs-lookup"><span data-stu-id="0632a-149">Teams analytics and reporting</span></span>](teams-reporting-reference.md)
