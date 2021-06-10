---
title: Microsoft TeamsPSTN 封鎖的使用者報告
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
description: 在系統管理中心Microsoft Teams PSTN 封鎖的使用者報告，以概觀您組織Teams無法撥打 PSTN 通話的使用者。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809333"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="8f5a3-103">Microsoft TeamsPSTN 封鎖的使用者報告</span><span class="sxs-lookup"><span data-stu-id="8f5a3-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="8f5a3-104">系統管理中心中的 PSTN 封鎖使用者報告Microsoft Teams顯示貴組織中禁止在 Teams 中撥打 PSTN Teams。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="8f5a3-105">您可以查看每個封鎖使用者的資訊，包括他們指派的電話號碼，以及他們無法撥打電話的原因。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="8f5a3-106">查看 PSTN 封鎖的使用者報告</span><span class="sxs-lookup"><span data-stu-id="8f5a3-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="8f5a3-107">在系統管理中心的左側導Microsoft Teams，按一下 [**分析&報告**  >  **使用方式報告**。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="8f5a3-108">在 [ **查看報表」** 選項卡的 [ **報表**> 下，選取 **[PSTN 封鎖的使用者**，然後按一下 [ **執行報表**> 。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="8f5a3-109">![系統管理中心中 PSTN 封鎖的使用者報告報告的螢幕擷取畫面](../media/teams-reports-pstn-blocked-users-with-callouts.png "系統管理中心中 PSTN 封鎖使用者報告的螢幕擷取畫面Microsoft Teams編號圖說說義")</span><span class="sxs-lookup"><span data-stu-id="8f5a3-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="8f5a3-110">解譯報表</span><span class="sxs-lookup"><span data-stu-id="8f5a3-110">Interpret the report</span></span>

|<span data-ttu-id="8f5a3-111">標注</span><span class="sxs-lookup"><span data-stu-id="8f5a3-111">Callout</span></span> |<span data-ttu-id="8f5a3-112">描述</span><span class="sxs-lookup"><span data-stu-id="8f5a3-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="8f5a3-113">**1**</span><span class="sxs-lookup"><span data-stu-id="8f5a3-113">**1**</span></span>   |<span data-ttu-id="8f5a3-114">每個報表都有產生日期。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="8f5a3-115">報告通常會反映啟用時間起 24 到 48 小時的延遲。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="8f5a3-116">**2**</span><span class="sxs-lookup"><span data-stu-id="8f5a3-116">**2**</span></span>   |<span data-ttu-id="8f5a3-117">X 軸是日期。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-117">The X axis is the date.</span></span> <span data-ttu-id="8f5a3-118">Y 軸是使用者數目。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="8f5a3-119">將游標停留在給定日期的點上方，以查看該日期被封鎖的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="8f5a3-120">**3**</span><span class="sxs-lookup"><span data-stu-id="8f5a3-120">**3**</span></span>   |<span data-ttu-id="8f5a3-121">下表列出所有禁止進行 PSTN 通話的使用者明細。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="8f5a3-122">它會顯示已指派電話系統或音訊會議的所有使用者，並為您提供每個使用者的更多相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="8f5a3-123">**顯示名稱** 是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="8f5a3-124">您可以按一下顯示名稱，前往系統管理中心中的使用者Microsoft Teams頁面。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="8f5a3-125">**電話** 是指派給使用者的號碼。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="8f5a3-126">**封鎖的原因** 就是使用者被封鎖撥打電話的原因。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="8f5a3-127">**封鎖的動作** 會告訴您使用者是否已被封鎖或禁止在 Teams。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="8f5a3-128">**封鎖時間** 是使用者 () 的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="8f5a3-129">若要在表格中查看您想要的資訊，請務必新增欄至資料表。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="8f5a3-130">**4**</span><span class="sxs-lookup"><span data-stu-id="8f5a3-130">**4**</span></span>   |<span data-ttu-id="8f5a3-131">選取 **編輯欄** 以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="8f5a3-132">**5**</span><span class="sxs-lookup"><span data-stu-id="8f5a3-132">**5**</span></span>   |<span data-ttu-id="8f5a3-133">選取 **全螢幕** 以全螢幕模式來查看報表。</span><span class="sxs-lookup"><span data-stu-id="8f5a3-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="8f5a3-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="8f5a3-134">Related topics</span></span>

- [<span data-ttu-id="8f5a3-135">Teams分析與報告</span><span class="sxs-lookup"><span data-stu-id="8f5a3-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)