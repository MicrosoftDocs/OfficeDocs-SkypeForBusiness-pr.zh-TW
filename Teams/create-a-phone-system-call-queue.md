---
title: 建立通話佇列
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: 瞭解如何在 Microsoft 團隊中設定雲端通話佇列的電話系統。
ms.openlocfilehash: 95cf9701705950d997e1d200fee117b5f8f9738b
ms.sourcegitcommit: 2fab6105dfc4c225de8c09ab79d9c2c273a3e4f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2020
ms.locfileid: "41005166"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="95bc7-103">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="95bc7-103">Create a Cloud call queue</span></span>

<span data-ttu-id="95bc7-104">雲端通話佇列可以提供：</span><span class="sxs-lookup"><span data-stu-id="95bc7-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="95bc7-105">問候訊息。</span><span class="sxs-lookup"><span data-stu-id="95bc7-105">A greeting message.</span></span>
- <span data-ttu-id="95bc7-106">當人員正在等候時，請播放音樂。</span><span class="sxs-lookup"><span data-stu-id="95bc7-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="95bc7-107">在已啟用郵件的通訊群組清單和安全性群組中，將呼叫重新導向至呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="95bc7-108">設定不同的參數，例如佇列大小上限、超時及呼叫處理選項。</span><span class="sxs-lookup"><span data-stu-id="95bc7-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="95bc7-109">呼叫者的共用語音信箱，可為組織留下訊息。</span><span class="sxs-lookup"><span data-stu-id="95bc7-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="95bc7-110">您可以使用[資源帳戶](manage-resource-accounts.md)將電話號碼與通話佇列建立關聯。</span><span class="sxs-lookup"><span data-stu-id="95bc7-110">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="95bc7-111">通話佇列可以直接撥號，或由自動語音應答上的選取進行存取。</span><span class="sxs-lookup"><span data-stu-id="95bc7-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="95bc7-112">來電者在暫停時，會聽到音樂，且通話會連線至呼叫代理程式 *（先進先出*（FIFO）訂單）。</span><span class="sxs-lookup"><span data-stu-id="95bc7-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="95bc7-113">佇列中的所有通話都是透過下列其中一種方法傳送給代理：</span><span class="sxs-lookup"><span data-stu-id="95bc7-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="95bc7-114">使用 [傳送助理] 時，佇列中的第一個呼叫會同時響鈴所有的 agent。</span><span class="sxs-lookup"><span data-stu-id="95bc7-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="95bc7-115">在串列路由中，佇列中的第一個呼叫會逐一響鈴一個呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="95bc7-116">使用迴圈法，傳入通話的路由會平衡，讓每個呼叫代理程式從佇列取得相同數量的呼叫。</span><span class="sxs-lookup"><span data-stu-id="95bc7-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95bc7-117">呼叫已**離線**、將其目前狀態設定為 [**請勿打擾]，** 或自願退出通話佇列的代理程式將不會收到來電。</span><span class="sxs-lookup"><span data-stu-id="95bc7-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="95bc7-118">一次只有一個來電通知（適用于佇列頭的呼叫）會傳送給呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="95bc7-119">通話代理程式接受通話之後，佇列中的下一個來電就會開始撥打通話代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="95bc7-120">本文適用于 Microsoft 團隊和商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="95bc7-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="95bc7-121">步驟1：快速入門</span><span class="sxs-lookup"><span data-stu-id="95bc7-121">Step 1 — Get started</span></span>

<span data-ttu-id="95bc7-122">若要開始使用通話佇列，請務必記住以下幾點：</span><span class="sxs-lookup"><span data-stu-id="95bc7-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="95bc7-123">需要通話佇列，才能擁有關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="95bc7-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="95bc7-124">如需資源帳戶的詳細資訊，請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="95bc7-125">當您將電話號碼指派給資源帳戶時，您現在可以使用 [免付費電話系統[虛擬使用者授權](teams-add-on-licensing/virtual-user.md)]。</span><span class="sxs-lookup"><span data-stu-id="95bc7-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="95bc7-126">[電話系統] 可讓組織階層的電話號碼與低成本的自動語音應答及呼叫佇列服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="95bc7-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="95bc7-127">僅限 Microsoft 團隊使用者和代理程式支援電話佇列的直接路由服務號碼。</span><span class="sxs-lookup"><span data-stu-id="95bc7-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="95bc7-128">若要將來電重新導向至貴組織中的線上人員，他們必須具備**電話系統**授權，且可供企業語音使用或擁有 Office 365 通話方案。</span><span class="sxs-lookup"><span data-stu-id="95bc7-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="95bc7-129">請參閱[指派商務用 Skype 授權](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[指派 Microsoft 團隊授權](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-129">See [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="95bc7-130">若要啟用企業語音，您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="95bc7-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="95bc7-131">例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="95bc7-131">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="95bc7-132">若要深入瞭解 Office 365 通話方案，請參閱[手機系統和通話方案](calling-plan-landing-page.md)與[Office 365 的通話方案](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="95bc7-133">您只能將雲端電話列隊指派給您在**Microsoft 團隊系統管理中心**取得或從其他服務提供者轉接的免付費服務電話號碼。</span><span class="sxs-lookup"><span data-stu-id="95bc7-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="95bc7-134">免付費服務號碼需要通訊點數。</span><span class="sxs-lookup"><span data-stu-id="95bc7-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95bc7-135">無法將使用者（訂閱者）電話號碼指派給呼叫佇列-只有服務付費電話或免付費電話號碼可供使用。</span><span class="sxs-lookup"><span data-stu-id="95bc7-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="95bc7-136">下列用戶端支援與雲端通話佇列相關聯的通話代理程式：</span><span class="sxs-lookup"><span data-stu-id="95bc7-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="95bc7-137">商務用 Skype desktop 用戶端2016（32位與64位版本）</span><span class="sxs-lookup"><span data-stu-id="95bc7-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="95bc7-138">Lync 桌面用戶端2013（32位與64位版本）</span><span class="sxs-lookup"><span data-stu-id="95bc7-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="95bc7-139">Microsoft 團隊支援的所有 IP 電話模型。</span><span class="sxs-lookup"><span data-stu-id="95bc7-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="95bc7-140">請參閱[取得商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="95bc7-141">Mac 商務用 Skype 用戶端（版本16.8.196 及更新版本）</span><span class="sxs-lookup"><span data-stu-id="95bc7-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="95bc7-142">Android 版商務用 Skype 用戶端（版本6.16.0.9 及更新版本）</span><span class="sxs-lookup"><span data-stu-id="95bc7-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="95bc7-143">iPhone 商務用 Skype 用戶端（版本6.16.0 及更新版本）</span><span class="sxs-lookup"><span data-stu-id="95bc7-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="95bc7-144">iPad 商務用 Skype 用戶端（版本6.16.0 及更新版本）</span><span class="sxs-lookup"><span data-stu-id="95bc7-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="95bc7-145">Microsoft 團隊 Windows 用戶端（32位與64位版本）</span><span class="sxs-lookup"><span data-stu-id="95bc7-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="95bc7-146">Microsoft 團隊 Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="95bc7-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="95bc7-147">Microsoft 團隊 iPhone 應用程式</span><span class="sxs-lookup"><span data-stu-id="95bc7-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="95bc7-148">Microsoft 團隊 Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="95bc7-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="95bc7-149">指派直接傳送號碼的通話佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 手機做為代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span> 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="95bc7-150">步驟2：取得或轉移付費或免付費服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="95bc7-150">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="95bc7-151">您必須先取得或轉讓現有的付費或免付費服務號碼，才能建立及設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="95bc7-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="95bc7-152">當您收到付費或免付費服務電話號碼之後，就會顯示在**Microsoft 團隊系統管理中心** > **的語音** > **電話號碼** > **新增**>，而**數位類型**則會列為 [服務] **（免付費）**。</span><span class="sxs-lookup"><span data-stu-id="95bc7-152">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers** > **ADD** >, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="95bc7-153">若要取得您的服務號碼，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)，或者如果您想要轉移現有的服務號碼，請參閱[將電話號碼轉移至 Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-153">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="95bc7-154">如果您在美國以外，您就無法使用 Microsoft 團隊系統管理中心來取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="95bc7-154">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="95bc7-155">移至 [[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)]，瞭解如何從美國以外的地區進行。</span><span class="sxs-lookup"><span data-stu-id="95bc7-155">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="95bc7-156">設定多個自動語音應答時，您可能只會將電話號碼指派給主要的自動助理資源帳戶，這可以讓呼叫者直接加入通話佇列或嵌套自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="95bc7-156">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="95bc7-157">在這些情況下，您不需指派撥號鍵台選項，就能在您的系統中建立所有自動語音應答及呼叫佇列，然後在稍後編輯設定。</span><span class="sxs-lookup"><span data-stu-id="95bc7-157">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="95bc7-158">這是必要的，因為您不允許建立連結至通話佇列的選項，或是不存在的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="95bc7-158">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="95bc7-159">步驟3：建立新的通話佇列</span><span class="sxs-lookup"><span data-stu-id="95bc7-159">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="95bc7-160">每個通話佇列都必須有一個相關聯的[資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-160">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="95bc7-161">您必須先建立資源帳戶，然後才能將它與通話佇列建立關聯。</span><span class="sxs-lookup"><span data-stu-id="95bc7-161">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="95bc7-162">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="95bc7-162">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="95bc7-163">在**Microsoft 團隊系統管理中心**、**語音** > **通話佇列**中，按一下 [ **+ 新增**]：</span><span class="sxs-lookup"><span data-stu-id="95bc7-163">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="95bc7-164">設定通話佇列顯示名稱和資源帳戶</span><span class="sxs-lookup"><span data-stu-id="95bc7-164">Set the call queue display name and resource account</span></span>

![含編號標注的新通話佇列的螢幕擷取畫面](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="95bc7-166">![在前一個螢幕擷取畫面](media/sfbcallout1.png)
**名稱**中參照標注的數位1圖示輸入通話佇列的描述性顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="95bc7-166">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="95bc7-167">這個名稱是必要的，而且最多可以包含64個字元，包括空格。</span><span class="sxs-lookup"><span data-stu-id="95bc7-167">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="95bc7-168">此名稱會顯示在撥入通話的通知中。</span><span class="sxs-lookup"><span data-stu-id="95bc7-168">This name is displayed in the notification for the incoming call.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="95bc7-170">**新增帳戶**選取資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="95bc7-170">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="95bc7-171">資源帳戶可以或不與電話號碼的服務付費或免付費電話號碼相關聯，但每個通話佇列都需要相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="95bc7-171">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="95bc7-172">如果沒有列出任何專案，您必須先取得服務號碼並將其指派給資源帳戶，然後才能建立此通話佇列（如前文所述）。</span><span class="sxs-lookup"><span data-stu-id="95bc7-172">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="95bc7-173">若要取得您的服務號碼，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-173">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="95bc7-174">如果您希望通話佇列擁有相關聯的電話號碼，請按照[管理團隊中的資源帳戶](manage-resource-accounts.md)中所述的方式來建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="95bc7-174">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="95bc7-175">如果您想要或需要指派**網域**，您可以將它指派給通話佇列的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="95bc7-175">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="95bc7-176">設定保留時播放的問候語和音樂</span><span class="sxs-lookup"><span data-stu-id="95bc7-176">Set the greeting and music played while on hold</span></span>

![含編號標注的問候和音樂選項螢幕擷取畫面](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="95bc7-179">[**問候語**] 是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="95bc7-179">**Greeting** is optional.</span></span> <span data-ttu-id="95bc7-180">這是呼叫撥入電話號碼的使用者所播放的問候語。</span><span class="sxs-lookup"><span data-stu-id="95bc7-180">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="95bc7-181">您可以上傳音訊檔（.wav、mp3 或 .wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="95bc7-181">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="95bc7-183">**等候音樂**您可以將預設的音樂保留在通話佇列中，或者您可以將音訊檔案上傳成 .wav、mp3 或 .wma 格式，以供您的自訂音樂保留使用。</span><span class="sxs-lookup"><span data-stu-id="95bc7-183">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="95bc7-184">選取呼叫應答選項</span><span class="sxs-lookup"><span data-stu-id="95bc7-184">Select the call answering options</span></span>

![通話應答選項的螢幕擷取畫面](media/5d249515-d532-4af2-90da-011404028b89.png) 

<span data-ttu-id="95bc7-186">若要直接新增個別的代理程式，而不將其新增至群組，請按一下 [**新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="95bc7-186">To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="95bc7-187">將個別的代理放在您想要他們接聽通話的順序。</span><span class="sxs-lookup"><span data-stu-id="95bc7-187">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="95bc7-188">您最多可以新增20個獨立的代理程式（若要新增20個以上的專案，請將它們放在群組中）。</span><span class="sxs-lookup"><span data-stu-id="95bc7-188">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="95bc7-189">呼叫會先路由到個別的 agent，然後路由到群組中的代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-189">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="95bc7-190">您最多可以選取200呼叫代理程式，其屬於下列任何一種郵寄清單或群組：</span><span class="sxs-lookup"><span data-stu-id="95bc7-190">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="95bc7-191">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="95bc7-191">Office 365 group</span></span>
- <span data-ttu-id="95bc7-192">安全性群組</span><span class="sxs-lookup"><span data-stu-id="95bc7-192">Security group</span></span>
- <span data-ttu-id="95bc7-193">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="95bc7-193">Distribution list</span></span>

<span data-ttu-id="95bc7-194">所選取的通話代理程式必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="95bc7-194">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="95bc7-195">已啟用手機系統授權和企業語音的線上使用者</span><span class="sxs-lookup"><span data-stu-id="95bc7-195">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="95bc7-196">使用通話方案的線上使用者</span><span class="sxs-lookup"><span data-stu-id="95bc7-196">Online users with a Calling Plan</span></span>
- <span data-ttu-id="95bc7-197">內部部署商務用 Skype 伺服器使用者</span><span class="sxs-lookup"><span data-stu-id="95bc7-197">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="95bc7-198">如果您想要將來電重新導向至組織中線上的人員，也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="95bc7-198">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="95bc7-199">這些人必須具備**手機系統**授權和企業語音功能，**或是**有通話方案。</span><span class="sxs-lookup"><span data-stu-id="95bc7-199">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="95bc7-200">如需詳細資訊，請參閱[指派商務用 Skype 授權](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、[指派 Microsoft 團隊授權](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)，或適合[您的通話計畫？](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="95bc7-200">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="95bc7-201">若要啟用企業語音的代理程式，您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="95bc7-201">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="95bc7-202">例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="95bc7-202">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="95bc7-203">已新增至 Office 365 群組的**電話系統**授權或通話方案的使用者;已啟用郵件的通訊群組清單;或 [安全性群組]。</span><span class="sxs-lookup"><span data-stu-id="95bc7-203">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="95bc7-204">在通訊群組清單或安全性群組中，新新增的代理程式可能需要長達3小時，才能開始從通話佇列接收通話。</span><span class="sxs-lookup"><span data-stu-id="95bc7-204">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="95bc7-205">新建立的通訊群組清單或安全性群組可能需要長達48小時才能與通話佇列搭配使用。</span><span class="sxs-lookup"><span data-stu-id="95bc7-205">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="95bc7-206">新建立的 Office 365 群組幾乎會立即提供給您。</span><span class="sxs-lookup"><span data-stu-id="95bc7-206">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="95bc7-207">如果您的代理程式是使用 Microsoft 團隊 App 接聽通話佇列通話，則必須在 TeamsOnly 模式中。</span><span class="sxs-lookup"><span data-stu-id="95bc7-207">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

![[新增撥號代理程式] 窗格的螢幕擷取畫面](media/skype-for-business-add-agents-to-call-queue.png)

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="95bc7-210">**路由方法**您**可以為通話**佇列發佈方法選擇 [行事等]、[**串列**] 或 [**迴圈**]。</span><span class="sxs-lookup"><span data-stu-id="95bc7-210">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="95bc7-211">所有新的和現有的通話佇列都會依預設選取 [助理] 路由。</span><span class="sxs-lookup"><span data-stu-id="95bc7-211">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="95bc7-212">使用 [接聽] 路由時，佇列中的第一次呼叫會同時響鈴所有呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-212">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="95bc7-213">第一個呼叫代理程式接聽電話，即可取得通話。</span><span class="sxs-lookup"><span data-stu-id="95bc7-213">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="95bc7-214">[行事鈴**路由**] 會讓佇列中的第一個呼叫同時撥打所有通話代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-214">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="95bc7-215">第一個呼叫代理程式接聽電話，即可取得通話。</span><span class="sxs-lookup"><span data-stu-id="95bc7-215">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="95bc7-216">從呼叫代理程式清單的開頭開始，逐一撥打電話**給來電代理**程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-216">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="95bc7-217">無法在通話代理程式清單中排序代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-217">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="95bc7-218">如果代理程式關閉或沒接聽電話，通話會撥打清單中的下一個代理程式，並一次嘗試一個代理程式，直到在佇列中被拾取或等待超時為止。</span><span class="sxs-lookup"><span data-stu-id="95bc7-218">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="95bc7-219">串列路由會略過**離線**、將其目前狀態設定為 [**請勿打擾**]，或已**選擇**不在此佇列中取得呼叫的代理程式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-219">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="95bc7-220">**迴圈**平衡：將來電進行路由，讓每個通話代理程式從佇列取得相同數目的呼叫。</span><span class="sxs-lookup"><span data-stu-id="95bc7-220">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="95bc7-221">這在入站銷售環境中可能是您想要的，以確保所有通話代理程式之間有同等的機會。</span><span class="sxs-lookup"><span data-stu-id="95bc7-221">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="95bc7-222">選取代理退出宣告選項</span><span class="sxs-lookup"><span data-stu-id="95bc7-222">Select an agent opt-out option</span></span>

![含編號標注的代理退出宣告選項的螢幕擷取畫面](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="95bc7-225">**工程師可以選擇不接聽電話**您可以透過啟用此選項，選擇允許呼叫佇列代理程式退出宣告來自特定佇列的呼叫。</span><span class="sxs-lookup"><span data-stu-id="95bc7-225">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="95bc7-226">啟用此選項可讓此佇列中的所有代理程式從該呼叫佇列開始或停止接聽通話。</span><span class="sxs-lookup"><span data-stu-id="95bc7-226">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="95bc7-227">您隨時都可以取消選取核取方塊，讓代理程式再次自動加入此佇列（所有代理的預設設定），以隨時撤銷代理自願退出許可權。</span><span class="sxs-lookup"><span data-stu-id="95bc7-227">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="95bc7-228">若要存取退出宣告選項，工程師可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="95bc7-228">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="95bc7-229">開啟其桌面商務用 Skype 用戶端中的**選項**。</span><span class="sxs-lookup"><span data-stu-id="95bc7-229">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="95bc7-230">在 [**來電轉接**] 索引標籤上，按一下 [**編輯線上編輯設定**] 連結。</span><span class="sxs-lookup"><span data-stu-id="95bc7-230">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="95bc7-231">在 [使用者設定] 頁面上，按一下 [**通話佇列**]，然後清除任何要退出宣告之佇列的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="95bc7-231">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95bc7-232">使用商務用 Skype Desktop 以外的 app 或端點的代理程式可從 [使用者設定] 入口網站[https://aka.ms/cqsettings](https://aka.ms/cqsettings)存取 [退出宣告] 選項。</span><span class="sxs-lookup"><span data-stu-id="95bc7-232">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="95bc7-233">如果代理程式位於 Microsoft 團隊桌面用戶端，則他們可以使用通話設定退出宣告。</span><span class="sxs-lookup"><span data-stu-id="95bc7-233">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

![[退出宣告通話設定] 的螢幕擷取畫面](media/create-a-phone-system-call-queue-image1.png)

<span data-ttu-id="95bc7-235">![數位2的圖示，在先前的螢幕擷取畫面](media/sfbcallout2.png)
中參照標注**Agent 提醒設定**</span><span class="sxs-lookup"><span data-stu-id="95bc7-235">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="95bc7-236">這會定義在串列或迴圈路由方法移至下一個代理程式之前，收到呼叫通知代理程式的持續時間。</span><span class="sxs-lookup"><span data-stu-id="95bc7-236">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="95bc7-237">預設設定為30秒，但最多可設定3分鐘。</span><span class="sxs-lookup"><span data-stu-id="95bc7-237">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="95bc7-238">設定通話溢位與超時處理選項</span><span class="sxs-lookup"><span data-stu-id="95bc7-238">Set the call overflow and timeout handling options</span></span>

![含編號標注的溢出處理選項之螢幕擷取畫面](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<span data-ttu-id="95bc7-241">**佇列中的最大通話**數使用此功能來設定可以同時在佇列中等候的最大通話數。</span><span class="sxs-lookup"><span data-stu-id="95bc7-241">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="95bc7-242">預設值為50，但範圍可以是0到200。</span><span class="sxs-lookup"><span data-stu-id="95bc7-242">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="95bc7-243">達到這個限制之後，就會按照您在 [**達到最大通話數**] 設定時所設定的方式來處理通話。</span><span class="sxs-lookup"><span data-stu-id="95bc7-243">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<span data-ttu-id="95bc7-245">**達到最大通話數時**當通話佇列達到其大小上限時（使用 **[佇列] 設定中的最大通話**設定），您可以選擇新的來電所要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="95bc7-245">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="95bc7-246">**中斷**連線通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="95bc7-246">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="95bc7-247">重新**導向至**當您選擇此選項時，請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="95bc7-247">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="95bc7-248">**貴公司中的人員**具備**電話系統**授權且可供企業語音使用或有通話方案的線上使用者。</span><span class="sxs-lookup"><span data-stu-id="95bc7-248">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="95bc7-249">您可以設定它，讓來電者可以傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="95bc7-249">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="95bc7-250">若要這樣做，請選取**貴公司中的人員**，並將其呼叫權直接轉寄給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="95bc7-250">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="95bc7-251">若要瞭解語音信箱所需的授權，請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-251">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="95bc7-252">**語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="95bc7-252">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

<span data-ttu-id="95bc7-254">**通話超時：最長等待時間**您也可以決定該通話在超時之前保留多少時間，且需要重新導向或中斷連線。</span><span class="sxs-lookup"><span data-stu-id="95bc7-254">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="95bc7-255">重新導向的位置，取決於您設定**通話超時**設定的方式。</span><span class="sxs-lookup"><span data-stu-id="95bc7-255">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="95bc7-256">您可以設定從0到45分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="95bc7-256">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="95bc7-257">超時值可以設定為以秒為單位，以15秒為間隔。</span><span class="sxs-lookup"><span data-stu-id="95bc7-257">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="95bc7-258">這可讓您以較精細的細微性操作通話流程。</span><span class="sxs-lookup"><span data-stu-id="95bc7-258">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="95bc7-259">例如，您可以指定在30秒內未由代理程式接聽的任何通話移至目錄搜尋自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="95bc7-259">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

<span data-ttu-id="95bc7-261">**通話超時**當通話達到您在 [佇列] 設定**中等候通話**的限制時間時，您可以選擇此通話會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="95bc7-261">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="95bc7-262">**中斷**連線通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="95bc7-262">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="95bc7-263">**將此通話重新導向至**當您選擇此選項時，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="95bc7-263">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="95bc7-264">**貴公司中的人員**具備**電話系統**授權且可供企業語音或有通話方案的線上使用者。</span><span class="sxs-lookup"><span data-stu-id="95bc7-264">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="95bc7-265">您可以將它設定為可將呼叫的人傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="95bc7-265">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="95bc7-266">若要這樣做，請選取**貴公司中的人員**，並將其呼叫權直接轉寄給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="95bc7-266">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="95bc7-267">若要瞭解語音信箱所需的授權，請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="95bc7-267">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="95bc7-268">**語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="95bc7-268">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="95bc7-269">變更撥出通話的使用者本機號碼</span><span class="sxs-lookup"><span data-stu-id="95bc7-269">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="95bc7-270">您可以改為使用 CsCallingLineIdentity Cmdlet，將電話撥入**式**呼叫的本機號碼改為呼叫佇列、自動語音應答或任何服務號碼，以保護使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="95bc7-270">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="95bc7-271">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="95bc7-271">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="95bc7-272">然後使用**授與 CallingLineIdentity** Cmdlet 將原則套用到使用者。</span><span class="sxs-lookup"><span data-stu-id="95bc7-272">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="95bc7-273">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="95bc7-273">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="95bc7-274">您可以[在組織中](/microsoftteams/how-can-caller-id-be-used-in-your-organization)，取得如何在組織中設定本機號碼設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="95bc7-274">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="95bc7-275">通話佇列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="95bc7-275">Call queue cmdlets</span></span>

<span data-ttu-id="95bc7-276">您也可以使用 Windows PowerShell 來建立及設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="95bc7-276">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="95bc7-277">以下是您用來管理通話佇列的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95bc7-277">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="95bc7-278">新-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="95bc7-278">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="95bc7-279">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="95bc7-279">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="95bc7-280">CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="95bc7-280">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="95bc7-281">移除-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="95bc7-281">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="95bc7-282">深入瞭解 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95bc7-282">More about Windows PowerShell</span></span>

- <span data-ttu-id="95bc7-283">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="95bc7-283">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="95bc7-284">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和 Microsoft 團隊，讓您有多個工作要執行，即可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="95bc7-284">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="95bc7-285">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="95bc7-285">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="95bc7-286">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="95bc7-286">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="95bc7-287">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="95bc7-287">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="95bc7-288">Windows PowerShell 在 Microsoft 團隊系統管理中心的速度、簡潔性和生產力上有許多優點，例如當您同時為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="95bc7-288">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="95bc7-289">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="95bc7-289">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="95bc7-290">使用 Windows PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="95bc7-290">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="95bc7-291">設定 Windows PowerShell 電腦</span><span class="sxs-lookup"><span data-stu-id="95bc7-291">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="95bc7-292">相關主題</span><span class="sxs-lookup"><span data-stu-id="95bc7-292">Related topics</span></span>

[<span data-ttu-id="95bc7-293">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="95bc7-293">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="95bc7-294">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="95bc7-294">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="95bc7-295">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="95bc7-295">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="95bc7-296">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="95bc7-296">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
