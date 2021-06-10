---
title: 在系統管理中心的活動記錄中Microsoft Teams您的Microsoft Teams作業
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在系統管理中心的活動記錄中Microsoft Teams作業活動。
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
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="d1da1-103">在活動記錄中查看您的策略指派</span><span class="sxs-lookup"><span data-stu-id="d1da1-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="d1da1-104">當您在系統管理中心指派Microsoft Teams，您可以在活動記錄中查看那些策略指派的狀態。</span><span class="sxs-lookup"><span data-stu-id="d1da1-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="d1da1-105">活動記錄會顯示過去 30 天內透過系統管理中心Microsoft Teams超過 20 個使用者批次的策略指派。</span><span class="sxs-lookup"><span data-stu-id="d1da1-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="d1da1-106">請記住，活動記錄不會顯示策略套件指派、透過 Microsoft Teams 系統管理中心指派給少於 20 位使用者的批次，或透過 PowerShell 進行策略指派。</span><span class="sxs-lookup"><span data-stu-id="d1da1-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![活動記錄頁面的螢幕擷取畫面](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="d1da1-108">在活動記錄中查看您的策略作業活動</span><span class="sxs-lookup"><span data-stu-id="d1da1-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="d1da1-109">若要在活動記錄中查看您的策略指派：</span><span class="sxs-lookup"><span data-stu-id="d1da1-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="d1da1-110">在系統管理中心的左側導Microsoft Teams，前往 **儀表板，然後在** 活動 **記錄下，** 選取查看 **詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="d1da1-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="d1da1-111">您可以查看所有策略作業，或根據狀態篩選清單，只顯示尚未開始、進行中或已完成 **的作業**。</span><span class="sxs-lookup"><span data-stu-id="d1da1-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="d1da1-112">您將看到每個作業的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d1da1-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="d1da1-113">**名稱**：策略指派的名稱。</span><span class="sxs-lookup"><span data-stu-id="d1da1-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="d1da1-114">按一下連結以查看更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d1da1-114">Click the link to view more details.</span></span> <span data-ttu-id="d1da1-115">這包括已指派策略的使用者數目，以及已完成、進行中及尚未開始的指派數目。</span><span class="sxs-lookup"><span data-stu-id="d1da1-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="d1da1-116">您也會看到批次中的使用者清單，以及每個使用者的狀態和結果。</span><span class="sxs-lookup"><span data-stu-id="d1da1-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="d1da1-117">以下是範例：</span><span class="sxs-lookup"><span data-stu-id="d1da1-117">Here's an example:</span></span>

        ![螢幕擷取畫面](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="d1da1-119">**提交日期**：已提交政策分派的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d1da1-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="d1da1-120">**完成時間**：完成策略作業的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d1da1-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="d1da1-121">**影響：** 批次中的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="d1da1-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="d1da1-122">**整體狀態**：策略工作分派的狀態。</span><span class="sxs-lookup"><span data-stu-id="d1da1-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="d1da1-123">您也可以從使用者頁面取得 **活動記錄。**</span><span class="sxs-lookup"><span data-stu-id="d1da1-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="d1da1-124">按一下 [ **申請** 以提交大量原則作業後，就會在頁面頂端看到橫幅。</span><span class="sxs-lookup"><span data-stu-id="d1da1-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="d1da1-125">按一下 **橫幅中的** [活動記錄連結。</span><span class="sxs-lookup"><span data-stu-id="d1da1-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1da1-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="d1da1-126">Related topics</span></span>

- [<span data-ttu-id="d1da1-127">指派策略給使用者</span><span class="sxs-lookup"><span data-stu-id="d1da1-127">Assign policies to users</span></span>](assign-policies.md)
