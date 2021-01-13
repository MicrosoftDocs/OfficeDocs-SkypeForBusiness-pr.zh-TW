---
title: 在 Microsoft 團隊系統管理中心的活動記錄中查看您的原則指派
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊系統管理中心的活動記錄中查看原則指派活動。
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821313"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="efbaf-103">在活動記錄記錄中查看您的原則指派</span><span class="sxs-lookup"><span data-stu-id="efbaf-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="efbaf-104">當您在 Microsoft 團隊系統管理中心將原則指派給使用者時，您可以在活動記錄中查看這些原則指派的狀態。</span><span class="sxs-lookup"><span data-stu-id="efbaf-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="efbaf-105">活動記錄會顯示在過去30天內，透過 Microsoft [小組系統管理中心] 向超過20名使用者批次的原則作業。</span><span class="sxs-lookup"><span data-stu-id="efbaf-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="efbaf-106">請記住，活動記錄不會顯示原則套件指派、原則指派，透過 Microsoft 團隊系統管理中心的使用者數目少於20個，或透過 PowerShell 進行原則作業。</span><span class="sxs-lookup"><span data-stu-id="efbaf-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![[活動記錄] 頁面的螢幕擷取畫面](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="efbaf-108">在活動記錄記錄中查看原則指派活動</span><span class="sxs-lookup"><span data-stu-id="efbaf-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="efbaf-109">若要在活動記錄中查看您的原則指派：</span><span class="sxs-lookup"><span data-stu-id="efbaf-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="efbaf-110">在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **儀表板**]，然後在 [ **活動記錄**] 底下，選取 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="efbaf-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="efbaf-111">您可以查看所有原則指派，或依狀態篩選清單，只顯示 **未開始**、 **進行中** 或 **已完成** 的作業。</span><span class="sxs-lookup"><span data-stu-id="efbaf-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="efbaf-112">您將會看到有關每個作業的下列相關資訊：</span><span class="sxs-lookup"><span data-stu-id="efbaf-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="efbaf-113">**Name （名稱**）：原則指派的名稱。</span><span class="sxs-lookup"><span data-stu-id="efbaf-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="efbaf-114">按一下連結以查看更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="efbaf-114">Click the link to view more details.</span></span> <span data-ttu-id="efbaf-115">這包括指派給該原則的使用者數目，以及已完成的作業數、進行中以及尚未開始的人數。</span><span class="sxs-lookup"><span data-stu-id="efbaf-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="efbaf-116">您也會看到批次中的使用者清單，以及每個使用者的狀態和結果。</span><span class="sxs-lookup"><span data-stu-id="efbaf-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="efbaf-117">以下是一個範例：</span><span class="sxs-lookup"><span data-stu-id="efbaf-117">Here's an example:</span></span>

        ![的螢幕擷取畫面](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="efbaf-119">已 **提交**：提交原則指派的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="efbaf-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="efbaf-120">**完成時間**：已完成原則指派的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="efbaf-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="efbaf-121">**影響**：批次中的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="efbaf-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="efbaf-122">**整體狀態**：原則指派的狀態。</span><span class="sxs-lookup"><span data-stu-id="efbaf-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="efbaf-123">您也可以從 [ **使用者** ] 頁面取得活動記錄。</span><span class="sxs-lookup"><span data-stu-id="efbaf-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="efbaf-124">**按一下 [** 套用] 以提交大量原則指派之後，您就會在頁面頂端看到橫幅。</span><span class="sxs-lookup"><span data-stu-id="efbaf-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="efbaf-125">按一下橫幅中的 [ **活動記錄** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="efbaf-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="efbaf-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="efbaf-126">Related topics</span></span>

- [<span data-ttu-id="efbaf-127">指派原則給使用者</span><span class="sxs-lookup"><span data-stu-id="efbaf-127">Assign policies to users</span></span>](assign-policies.md)
