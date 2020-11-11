---
title: 在 Microsoft 團隊中設定假日
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft 團隊中設定假日，以搭配您的自動語音應答使用。
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993469"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="6746b-103">在 Microsoft 團隊中設定假日</span><span class="sxs-lookup"><span data-stu-id="6746b-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="6746b-104">您可以使用 [小組假日] 功能來提供備用訊息，並將特定日期和時間的呼叫者路由給來電者，以取得特定日期和時間，讓您組織中的通話佇列或人員會在不同的工作時間或無法使用。</span><span class="sxs-lookup"><span data-stu-id="6746b-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="6746b-105">例如，您可能會在您的組織關閉時，為新年新的一天建立假日。</span><span class="sxs-lookup"><span data-stu-id="6746b-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="6746b-106">您在這裡建立的假日是在您 [設定自動](create-a-phone-system-auto-attendant.md)語音應答時提供，每個都有自己的問候及呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="6746b-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="6746b-107">建立假日</span><span class="sxs-lookup"><span data-stu-id="6746b-107">Create a holiday</span></span>

<span data-ttu-id="6746b-108">若要建立假日</span><span class="sxs-lookup"><span data-stu-id="6746b-108">To create a holiday</span></span>

1. <span data-ttu-id="6746b-109">在 Microsoft [團隊管理中心] 中，移至 [ **全組織的設定**  >  **假日** ]。</span><span class="sxs-lookup"><span data-stu-id="6746b-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="6746b-110">選取 [ **新假日** ]。</span><span class="sxs-lookup"><span data-stu-id="6746b-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="6746b-111">輸入假日的名稱。</span><span class="sxs-lookup"><span data-stu-id="6746b-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="6746b-112">選取 [ **新增日期** ]。</span><span class="sxs-lookup"><span data-stu-id="6746b-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="6746b-113">在 [ **開始時間** ] 底下，選取行事曆圖示，然後選擇您想要的假日開始的日期。</span><span class="sxs-lookup"><span data-stu-id="6746b-113">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="6746b-114">使用下拉式清單來選取假日的開始時間。</span><span class="sxs-lookup"><span data-stu-id="6746b-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="6746b-115">在 [ **結束時間** ] 底下，選取行事曆圖示，然後選擇您要結束假日的日期。</span><span class="sxs-lookup"><span data-stu-id="6746b-115">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="6746b-116">使用下拉式清單來選取假日的結束時間。</span><span class="sxs-lookup"><span data-stu-id="6746b-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="6746b-117">[ **結束時間** ] 必須在 **開始時間** 之後。</span><span class="sxs-lookup"><span data-stu-id="6746b-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="6746b-118">如果該假日是一個全天 (（即24小時期間) ）， **結束時間** 應該設定為下一天，並將時間設為 12:00 AM。</span><span class="sxs-lookup"><span data-stu-id="6746b-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="6746b-119">例如，如果您的組織是在新年年1月1日關閉，請將 [ **開始時間** ] 設定為 [淩晨 1 12:00 年1月 12:00 2]，並將 [ **結束時間** ] 設定為 [年1月 2]。</span><span class="sxs-lookup"><span data-stu-id="6746b-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="6746b-120">您也可以選擇新增更多的週期性假日日期。</span><span class="sxs-lookup"><span data-stu-id="6746b-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="6746b-121">選取 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="6746b-121">Select **Save**.</span></span>

    ![在三年期內設定日期的假日使用者介面螢幕擷取畫面](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="6746b-123">變更假日</span><span class="sxs-lookup"><span data-stu-id="6746b-123">Change a holiday</span></span>

<span data-ttu-id="6746b-124">變更假日</span><span class="sxs-lookup"><span data-stu-id="6746b-124">To change a holiday</span></span>

1. <span data-ttu-id="6746b-125">在 Microsoft [團隊管理中心] 中，移至 [ **全組織的設定**  >  **假日** ]。</span><span class="sxs-lookup"><span data-stu-id="6746b-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="6746b-126">從清單中選取 [假日]。</span><span class="sxs-lookup"><span data-stu-id="6746b-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="6746b-127">在 [ **開始時間** ] 底下，選取行事曆圖示，然後選擇您想要的假日開始的日期。</span><span class="sxs-lookup"><span data-stu-id="6746b-127">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="6746b-128">使用下拉式清單來選取假日的開始時間。</span><span class="sxs-lookup"><span data-stu-id="6746b-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="6746b-129">在 [ **結束時間** ] 底下，選取行事曆圖示，然後選擇您要結束假日的日期。</span><span class="sxs-lookup"><span data-stu-id="6746b-129">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="6746b-130">使用下拉式清單來選取假日的結束時間。</span><span class="sxs-lookup"><span data-stu-id="6746b-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="6746b-131">[ **結束時間** ] 必須在 **開始時間** 之後。</span><span class="sxs-lookup"><span data-stu-id="6746b-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="6746b-132">選取 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="6746b-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6746b-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="6746b-133">Related topics</span></span>

<span data-ttu-id="6746b-134">[規劃小組自動語音應答及呼叫佇列](plan-auto-attendant-call-queue.md)？</span><span class="sxs-lookup"><span data-stu-id="6746b-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
