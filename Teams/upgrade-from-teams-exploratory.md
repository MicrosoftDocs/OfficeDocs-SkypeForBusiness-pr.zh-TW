---
title: 從 Teams Exploratory 試用版升級
author: cazawideh
ms.author: czawideh
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: ''
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 從 Teams Exploratory 試用版將使用者升級至付費授權。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: a57a34d23cc779efd1c6c596bc27f2e23d968e89
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230702"
---
# <a name="upgrade-users-from-the-teams-exploratory-trial"></a><span data-ttu-id="e7a05-103">從 Teams Exploratory 試用版升級使用者</span><span class="sxs-lookup"><span data-stu-id="e7a05-103">Upgrade users from the Teams Exploratory trial</span></span>

<span data-ttu-id="e7a05-104">本文提供如何將您的使用者從 Teams Exploratory 試用版升級為付費 Teams 授權概觀。</span><span class="sxs-lookup"><span data-stu-id="e7a05-104">This article provides an overview of how to upgrade your users from a Teams Exploratory trial to paid Teams licenses.</span></span>

- [<span data-ttu-id="e7a05-105">步驟 1：何時進行升級</span><span class="sxs-lookup"><span data-stu-id="e7a05-105">Step 1: When to upgrade</span></span>](#step-1-when-to-upgrade)

- [<span data-ttu-id="e7a05-106">步驟 2：選擇升級路徑</span><span class="sxs-lookup"><span data-stu-id="e7a05-106">Step 2: Choose an upgrade path</span></span>](#step-2-choose-an-upgrade-path)

- [<span data-ttu-id="e7a05-107">步驟 3：指派付費的授權</span><span class="sxs-lookup"><span data-stu-id="e7a05-107">Step 3: Assign paid licenses</span></span>](#step-3-assign-paid-licenses)

## <a name="step-1-when-to-upgrade"></a><span data-ttu-id="e7a05-108">步驟 1：何時進行升級</span><span class="sxs-lookup"><span data-stu-id="e7a05-108">Step 1: When to upgrade</span></span>  

<span data-ttu-id="e7a05-109">若要檢查貴組織的 Teams Exploratory 試用版何時到期，以及有多少有效使用者，請前往 Microsoft 365 系統管理中心的 **帳單 >** <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"><b>產品</b></a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-109">To check when your organization’s Teams Exploratory trial is expiring and how many active users it has, go to **Billing >** <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank"><b>Your products</b></a> in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e7a05-110">Teams Exploratory 試用版到期之前，您也會收到通知。</span><span class="sxs-lookup"><span data-stu-id="e7a05-110">You’ll also be notified before the Teams Exploratory trial expires.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7a05-111">在到期日之前，您應該規劃將使用者升級至付費的授權，讓使用者不會失去 Teams 的存取權。</span><span class="sxs-lookup"><span data-stu-id="e7a05-111">You should make a plan to upgrade your users to paid licenses before the expiration date, so users don’t lose access to Teams.</span></span>
>
> <span data-ttu-id="e7a05-112">在試用版到期日後的 30 天內，使用者將失去 Teams 的存取權。</span><span class="sxs-lookup"><span data-stu-id="e7a05-112">Users will lose access to Teams 30 days after the trial's expiration date.</span></span> <span data-ttu-id="e7a05-113">只要在到期日的 60 天內，使用者獲指派付費的授權，他們就可以重新取得 Teams 的存取權，而且所有內容仍然存在。</span><span class="sxs-lookup"><span data-stu-id="e7a05-113">As long as users are assigned a paid license within 60 days of the expiration date, they can regain access to Teams and all content still exists.</span></span> <span data-ttu-id="e7a05-114">不過，60 天后，該名使用者的資料就會遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="e7a05-114">However, after 60 days, the users’ data is deleted.</span></span> <span data-ttu-id="e7a05-115">將新授權指派給使用者以啟用 Teams 功能之後，如果是在寬限期時間範圍內新增授權，則會保留所有內容。</span><span class="sxs-lookup"><span data-stu-id="e7a05-115">After a new license is assigned to the users to enable Teams functionality, if they are added within the grace period time frame, all content remains.</span></span> <span data-ttu-id="e7a05-116">如需詳細資訊，請參閱 <a href="/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide" target="_blank">當訂閱結束時，我的資料與存取權會發生什麼情況？</a></span><span class="sxs-lookup"><span data-stu-id="e7a05-116">For more information, see <a href="/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide" target="_blank">What happens to my data and access when my subscription ends?</a></span></span>

## <a name="step-2-choose-an-upgrade-path"></a><span data-ttu-id="e7a05-117">步驟 2：選擇升級路徑</span><span class="sxs-lookup"><span data-stu-id="e7a05-117">Step 2: Choose an upgrade path</span></span>

<span data-ttu-id="e7a05-118">根據貴組織目前擁有訂閱，有三種方式可以將 Microsoft Teams Exploratory 試用版升級為付費授權：</span><span class="sxs-lookup"><span data-stu-id="e7a05-118">Depending on the subscriptions your organization currently has, there are three ways to upgrade from a Microsoft Teams Exploratory trial to a paid license:</span></span>

- <span data-ttu-id="e7a05-119">**升級現有的 Microsoft 365 訂閱。**</span><span class="sxs-lookup"><span data-stu-id="e7a05-119">**Upgrade an existing Microsoft 365 subscription.**</span></span> <span data-ttu-id="e7a05-120">如果您的組織擁有其他不包含 Teams 的 Office 產品訂閱，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e7a05-120">Use this option if your organization has subscriptions to other Office products that don’t include Teams.</span></span> <span data-ttu-id="e7a05-121">如需詳細資訊，請參閱 <a href="/microsoft-365/commerce/subscriptions/upgrade-to-different-plan?view=o365-worldwide" target="_blank">升級至其他的商務方案</a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-121">For more information, see <a href="/microsoft-365/commerce/subscriptions/upgrade-to-different-plan?view=o365-worldwide" target="_blank">Upgrade to a different business plan</a>.</span></span> <span data-ttu-id="e7a05-122">若要查看現有訂閱的作用中使用者，請移至 Microsoft 365 系統管理中心 **使用者 >** <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank"><b>作用中使用者</b></a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-122">To see active users for an existing subscription, go to **Users >** <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank"><b>Active users</b></a> in the Microsoft 365 admin center.</span></span>

- <span data-ttu-id="e7a05-123">**新增使用者至現有的 Microsoft 365 訂閱。**</span><span class="sxs-lookup"><span data-stu-id="e7a05-123">**Add users to an existing Microsoft 365 subscription.**</span></span> <span data-ttu-id="e7a05-124">如果您的組織沒有足夠的付費，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e7a05-124">Use this option if your organization doesn’t have enough paid.</span></span> <span data-ttu-id="e7a05-125">Teams 授權包含 Teams Exploratory 使用者。</span><span class="sxs-lookup"><span data-stu-id="e7a05-125">Teams licenses to cover the Teams Exploratory users.</span></span> <span data-ttu-id="e7a05-126">如需詳細資訊，請參閱 <a href="/microsoft-365/commerce/licenses/buy-licenses?view=o365-worldwide" target="_blank">購買或移除授權</a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-126">For more information, see <a href="/microsoft-365/commerce/licenses/buy-licenses?view=o365-worldwide" target="_blank">Buy or remove licenses</a>.</span></span> <span data-ttu-id="e7a05-127">若要新增使用者至已擁有足夠可用授權的現有訂閱，請參閱 <a href="/microsoft-365/commerce/subscriptions/move-users-different-subscription?view=o365-worldwide" target="_blank">將使用者移至不同的訂閱</a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-127">To add users to an existing subscription that already has enough available licenses, see <a href="/microsoft-365/commerce/subscriptions/move-users-different-subscription?view=o365-worldwide" target="_blank">Move users to a different subscription</a>.</span></span> <span data-ttu-id="e7a05-128">若要查看現有訂閱的作用中使用者，請移至 Microsoft 365 系統管理中心 **使用者 >** <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank"><b>作用中使用者</b></a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-128">To see active users for an existing subscription, go to **Users >** <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank"><b>Active users</b></a> in the Microsoft 365 admin center.</span></span>

- <span data-ttu-id="e7a05-129">**購買新的 Microsoft 365 訂閱。**</span><span class="sxs-lookup"><span data-stu-id="e7a05-129">**Buy a new Microsoft 365 subscription.**</span></span> <span data-ttu-id="e7a05-130">如果貴組織沒有任何現有的 Office 產品訂閱，或貴組織想要購買與現有訂閱不同的訂閱，以涵蓋 Teams Exploratory 使用者，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e7a05-130">Use this option if your organization doesn’t have any existing subscriptions to Office products, or if your organization wants to buy a subscription that’s different from their existing subscription to cover Teams Exploratory users.</span></span>  <span data-ttu-id="e7a05-131">如需詳細資訊，請參閱 <a href="/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide%22%20\#buy-a-different-subscription" target="_blank">購買其他商務用 Microsoft 365 訂閱</a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-131">For more information, see <a href="/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide%22%20\#buy-a-different-subscription" target="_blank">Buy a different Microsoft 365 for business subscription</a>.</span></span>

<span data-ttu-id="e7a05-132">如果您不確定要升級至哪個 Microsoft 365 訂閱，請參閱 <a href="https://www.microsoft.com/microsoft-365/business#coreui-heading-hiatrep" target="_blank">商務用 Microsoft 365</a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-132">If you’re not sure which Microsoft 365 subscription to upgrade to, see <a href="https://www.microsoft.com/microsoft-365/business#coreui-heading-hiatrep" target="_blank">Microsoft 365 for Business</a>.</span></span> <span data-ttu-id="e7a05-133">如果您在選擇訂閱時需要額外的協助，或如果您的組織需要超過 300 份授權，請聯絡您的 <a href="https://www.microsoft.com/solution-providers/home" target="_blank">Microsoft 合作夥伴</a> 或 Microsoft 帳戶代表。</span><span class="sxs-lookup"><span data-stu-id="e7a05-133">If you need additional help choosing a subscription, or if your organization needs more than 300 licenses, contact your <a href="https://www.microsoft.com/solution-providers/home" target="_blank">Microsoft partner</a> or Microsoft account representative.</span></span>

## <a name="step-3-assign-paid-licenses"></a><span data-ttu-id="e7a05-134">步驟 3：指派付費的授權</span><span class="sxs-lookup"><span data-stu-id="e7a05-134">Step 3: Assign paid licenses</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7a05-135">在您取消指派任何 Teams Exploratory 授權之前，請將新授權指派給要升級的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="e7a05-135">Before you unassign any Teams Exploratory licenses, assign the new licenses to all the users you’re upgrading.</span></span> <span data-ttu-id="e7a05-136">否則，他們將會失去 Teams 的存取權，直到您指派付費授權。</span><span class="sxs-lookup"><span data-stu-id="e7a05-136">Otherwise, they lose access to Teams until you assign a paid license.</span></span>  

<span data-ttu-id="e7a05-137">若要指派您新取得的授權，請參閱 <a href="/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide&viewFallbackFrom=o365-worldwide%22%20%5C" target="_blank">指派授權給使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-137">To assign your newly acquired licenses, see <a href="/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide&viewFallbackFrom=o365-worldwide%22%20%5C" target="_blank">Assign licenses to users</a>.</span></span>  

<span data-ttu-id="e7a05-138">指派新授權之後，請取消指派 Teams Exploratory 授權。</span><span class="sxs-lookup"><span data-stu-id="e7a05-138">After you assign the new licenses, unassign the Teams Exploratory licenses.</span></span> <span data-ttu-id="e7a05-139">請參閱 <a href="/microsoft-365/admin/manage/remove-licenses-from-users?view=o365-worldwide" target="_blank">由使用者取消指派授權</a>，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e7a05-139">See <a href="/microsoft-365/admin/manage/remove-licenses-from-users?view=o365-worldwide" target="_blank">Unassign licenses from users</a>, for more information.</span></span>

### <a name="auto-claim-policies"></a><span data-ttu-id="e7a05-140">自動聲明原則</span><span class="sxs-lookup"><span data-stu-id="e7a05-140">Auto-claim policies</span></span>

<span data-ttu-id="e7a05-141">下一次升級時，使用自動聲明原則以建立適用於貴組織的原則，以自動將付費訂閱中的授權指派給尚未取得 Teams 授權的新使用者。</span><span class="sxs-lookup"><span data-stu-id="e7a05-141">Next time you upgrade, use auto-claim policies to create policies for your organization to automatically assign licenses from paid subscriptions to new users who haven’t acquired a Teams license.</span></span> <span data-ttu-id="e7a05-142">如需詳細資訊，請參閱 <a href="/microsoft-365/commerce/licenses/manage-auto-claim-policies?view=o365-worldwide" target="_blank">自動聲明原則</a>。</span><span class="sxs-lookup"><span data-stu-id="e7a05-142">For more information, see <a href="/microsoft-365/commerce/licenses/manage-auto-claim-policies?view=o365-worldwide" target="_blank">Manage auto-claim policies</a>.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e7a05-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7a05-143">Related topics</span></span>

- [<span data-ttu-id="e7a05-144">管理 Microsoft Teams Exploratory 授權</span><span class="sxs-lookup"><span data-stu-id="e7a05-144">Manage the Microsoft Teams Exploratory license</span></span>](teams-exploratory.md)
