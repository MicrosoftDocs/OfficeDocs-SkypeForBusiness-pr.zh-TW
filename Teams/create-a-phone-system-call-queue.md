---
title: 建立通話佇列
ms.author: dstrome
author: dstrome
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft 團隊設定電話系統，以提供問候訊息、等候音樂、呼叫重新導向及其他功能。
ms.openlocfilehash: dd11e33e4947ea231310b06af2570711d55b2451
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077710"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="d2274-103">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="d2274-103">Create a Cloud call queue</span></span>

<span data-ttu-id="d2274-104">雲端通話佇列可以提供：</span><span class="sxs-lookup"><span data-stu-id="d2274-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="d2274-105">問候訊息。</span><span class="sxs-lookup"><span data-stu-id="d2274-105">A greeting message.</span></span>
- <span data-ttu-id="d2274-106">當人員正在等候時，請播放音樂。</span><span class="sxs-lookup"><span data-stu-id="d2274-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="d2274-107">在已啟用郵件的通訊群組清單和安全性群組中，將呼叫重新導向至呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="d2274-108">設定不同的參數，例如佇列大小上限、超時及呼叫處理選項。</span><span class="sxs-lookup"><span data-stu-id="d2274-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="d2274-109">呼叫者的共用語音信箱，可為組織留下訊息。</span><span class="sxs-lookup"><span data-stu-id="d2274-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="d2274-110">您不會直接將電話號碼與通話佇列進行關聯，而是將電話號碼與[資源帳戶](manage-resource-accounts.md)相關聯。</span><span class="sxs-lookup"><span data-stu-id="d2274-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="d2274-111">通話佇列可以直接撥號，或由自動語音應答上的選取進行存取。</span><span class="sxs-lookup"><span data-stu-id="d2274-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="d2274-112">來電者在暫停時，會聽到音樂，且通話會連線至呼叫代理程式 *（先進先出*（FIFO）訂單）。</span><span class="sxs-lookup"><span data-stu-id="d2274-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="d2274-113">佇列中的所有通話都是透過下列其中一種方法傳送給代理：</span><span class="sxs-lookup"><span data-stu-id="d2274-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="d2274-114">使用 [傳送助理] 時，佇列中的第一個呼叫會同時響鈴所有的 agent。</span><span class="sxs-lookup"><span data-stu-id="d2274-114">With attendant routing, the first call in the queue rings all agents at the same time.</span></span>
- <span data-ttu-id="d2274-115">在串列路由中，佇列中的第一個呼叫會逐一響鈴一個呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="d2274-116">使用最長的空閒路由，通話代理程式，其閒置時間最長的時間會接收下一個可用的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d2274-116">With longest idle routing, the call agent whose has been idle the longest time receives the next available call.</span></span> <span data-ttu-id="d2274-117">閒置時間是在通話時定義為呼叫代理者的目前狀態設定為 [**可用**] 或 [**離開**] （如果少於10分鐘）的時間長度。</span><span class="sxs-lookup"><span data-stu-id="d2274-117">The idle time is defined as the length of time a call agent's presence state is set to **Available** or **Away** (if less than 10 minutes), at the time of the call.</span></span> <span data-ttu-id="d2274-118">如果通話**代理程式的目前狀態**超過10分鐘，閒置計時器就會重設。</span><span class="sxs-lookup"><span data-stu-id="d2274-118">If a call agent's presence is **Away** for more than 10 minutes, the idle timer resets.</span></span>
- <span data-ttu-id="d2274-119">使用迴圈法，傳入通話的路由會平衡，讓每個呼叫代理程式從佇列取得相同數量的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d2274-119">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

<span data-ttu-id="d2274-120">您可以設定呼叫處理選項，例如代理程式加入宣告/自願退出、目前狀態的路線、通話等待時間，以及使用上述任何一種方法呼叫超時選項。</span><span class="sxs-lookup"><span data-stu-id="d2274-120">You can set call handling options, such as agent opt-in/opt-out, presence-based routing, call wait time, and call time-out options with any of the above methods.</span></span>

<span data-ttu-id="d2274-121">一次只有一個來電通知（適用于佇列頭的呼叫）會傳送給呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-121">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span> <span data-ttu-id="d2274-122">通話代理程式接受通話之後，佇列中的下一個來電就會開始撥打通話代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-122">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="d2274-123">本文適用于 Microsoft 團隊和商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="d2274-123">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="d2274-124">步驟1：快速入門</span><span class="sxs-lookup"><span data-stu-id="d2274-124">Step 1 — Get started</span></span>

<span data-ttu-id="d2274-125">若要開始使用通話佇列，請務必記住以下幾點：</span><span class="sxs-lookup"><span data-stu-id="d2274-125">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="d2274-126">需要通話佇列，才能擁有關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d2274-126">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="d2274-127">如需資源帳戶的詳細資訊，請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-127">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="d2274-128">當您將電話號碼指派給資源帳戶時，您現在可以使用 [免付費電話系統[虛擬使用者授權](teams-add-on-licensing/virtual-user.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2274-128">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="d2274-129">[電話系統] 可讓組織階層的電話號碼與低成本的自動語音應答及呼叫佇列服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d2274-129">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d2274-130">僅限 Microsoft 團隊使用者和代理程式支援電話佇列的直接路由服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-130">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="d2274-131">若要將來電重新導向至貴組織中的線上人員，他們必須具備**電話系統**授權，且可供企業語音使用，或是有 Microsoft 365 或 Office 365 通話方案。</span><span class="sxs-lookup"><span data-stu-id="d2274-131">To redirect calls to people in your organization who are online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="d2274-132">請參閱[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-132">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="d2274-133">若要啟用企業語音，您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d2274-133">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="d2274-134">例如，執行： ' Move-csuser-身分識別 "Amos 大理石"-EnterpriseVoiceEnabled $true。</span><span class="sxs-lookup"><span data-stu-id="d2274-134">For example, run: \`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true.</span></span>

- <span data-ttu-id="d2274-135">若要深入瞭解通話方案，請參閱[手機系統和通話方案](calling-plan-landing-page.md)，以及[Microsoft 365 或 Office 365 的通話方案](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-135">To learn more about Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="d2274-136">您只能將雲端電話列隊指派給您在**Microsoft 團隊系統管理中心**取得或從其他服務提供者轉接的免付費服務電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-136">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="d2274-137">免付費服務號碼需要通訊點數。</span><span class="sxs-lookup"><span data-stu-id="d2274-137">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2274-138">無法將使用者（訂閱者）電話號碼指派給呼叫佇列-只有服務付費電話或免付費電話號碼可供使用。</span><span class="sxs-lookup"><span data-stu-id="d2274-138">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="d2274-139">下列用戶端支援與雲端通話佇列相關聯的通話代理程式：</span><span class="sxs-lookup"><span data-stu-id="d2274-139">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="d2274-140">商務用 Skype desktop 用戶端2016（32位與64位版本）</span><span class="sxs-lookup"><span data-stu-id="d2274-140">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d2274-141">Lync 桌面用戶端2013（32位與64位版本）</span><span class="sxs-lookup"><span data-stu-id="d2274-141">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d2274-142">Microsoft 團隊支援的所有 IP 電話模型。</span><span class="sxs-lookup"><span data-stu-id="d2274-142">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="d2274-143">請參閱[取得商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="d2274-143">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="d2274-144">Mac 商務用 Skype 用戶端（版本16.8.196 及更新版本）</span><span class="sxs-lookup"><span data-stu-id="d2274-144">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="d2274-145">Android 版商務用 Skype 用戶端（版本6.16.0.9 及更新版本）</span><span class="sxs-lookup"><span data-stu-id="d2274-145">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="d2274-146">iPhone 商務用 Skype 用戶端（版本6.16.0 及更新版本）</span><span class="sxs-lookup"><span data-stu-id="d2274-146">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="d2274-147">iPad 商務用 Skype 用戶端（版本6.16.0 及更新版本）</span><span class="sxs-lookup"><span data-stu-id="d2274-147">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="d2274-148">Microsoft 團隊 Windows 用戶端（32位與64位版本）</span><span class="sxs-lookup"><span data-stu-id="d2274-148">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d2274-149">Microsoft 團隊 Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="d2274-149">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="d2274-150">Microsoft 團隊 iPhone 應用程式</span><span class="sxs-lookup"><span data-stu-id="d2274-150">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="d2274-151">Microsoft 團隊 Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="d2274-151">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2274-152">指派直接傳送號碼的呼叫佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 手機做為代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-152">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="d2274-153">步驟2：取得或轉移付費或免付費服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="d2274-153">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="d2274-154">您必須先取得或轉讓現有的付費或免付費服務號碼，才能建立及設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d2274-154">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="d2274-155">若要取得您的服務號碼，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)，或者如果您想要轉移現有的服務號碼，請參閱[將電話號碼轉移至團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-155">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="d2274-156">在您取得付費或免付費服務電話號碼之後，就會顯示在**Microsoft 團隊系統管理中心**的  >  **語音**  >  **電話號碼**中。</span><span class="sxs-lookup"><span data-stu-id="d2274-156">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="d2274-157">[免付費電話號碼] 會以**數位類型**的**服務列出（免付費電話）**。</span><span class="sxs-lookup"><span data-stu-id="d2274-157">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="d2274-158">如果您在美國以外，您就無法使用 Microsoft 團隊系統管理中心來取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-158">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="d2274-159">移至 [[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)]，瞭解如何從美國以外的地區進行。</span><span class="sxs-lookup"><span data-stu-id="d2274-159">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="d2274-160">當您設定多個自動語音應答時，通常會將電話號碼指派給主要的自動助理資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d2274-160">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="d2274-161">與嵌套自動語音應答或通話佇列相關聯的資源帳戶通常不需要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-161">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="d2274-162">即使沒有電話號碼，該自動語音應答也可以將呼叫者指引至您的通話佇列或嵌套自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d2274-162">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="d2274-163">在這些情況下，您可以在系統中建立所有自動語音應答及呼叫佇列，而無需指派撥號鍵台選項，然後在稍後編輯設定。</span><span class="sxs-lookup"><span data-stu-id="d2274-163">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="d2274-164">通話佇列或自動語音應答必須存在，才能設定為功能表選項。</span><span class="sxs-lookup"><span data-stu-id="d2274-164">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="d2274-165">步驟3：建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="d2274-165">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="d2274-166">每個通話佇列都必須有一個相關聯的[資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-166">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="d2274-167">您必須先建立資源帳戶，然後才能將它與通話佇列建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d2274-167">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="d2274-168">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d2274-168">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="d2274-169">在**Microsoft 團隊系統管理中心**、**語音**  >  **通話佇列**中，按一下 [ **+ 新增**]：</span><span class="sxs-lookup"><span data-stu-id="d2274-169">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="d2274-170">設定顯示名稱和資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d2274-170">Set the display name and resource account</span></span>

![含編號標注的新通話佇列的螢幕擷取畫面](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="d2274-172">![數位1的圖示，在先前的螢幕擷取畫面名稱中參照標注 ](media/teamscallout1.png)
 **Name**輸入通話佇列的描述性顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="d2274-172">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="d2274-173">這個名稱是必要的，而且最多可以包含64個字元，包括空格。</span><span class="sxs-lookup"><span data-stu-id="d2274-173">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="d2274-174">此名稱會顯示在撥入通話的通知中。</span><span class="sxs-lookup"><span data-stu-id="d2274-174">This name is displayed in the notification for the incoming call.</span></span>

* * *

<span data-ttu-id="d2274-175">![數位2的圖示，在前一個螢幕擷取畫面中參照標注 [ ](media/teamscallout2.png)
 **新增帳戶**] 會選取資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d2274-175">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="d2274-176">所有通話佇列都必須有資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d2274-176">All call queues are required to have a resource account.</span></span> <span data-ttu-id="d2274-177">資源帳戶不需要擁有服務付費或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-177">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="d2274-178">如果沒有列出任何資料，請先取得服務號碼，然後將其指派給資源帳戶，然後再建立通話佇列，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="d2274-178">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="d2274-179">若要取得您的服務號碼，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-179">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="d2274-180">如需如何指派電話號碼的詳細資訊，請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-180">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="d2274-181">如果您想要或需要指派**網域**，您可以將它指派給通話佇列的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d2274-181">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="d2274-182">設定保留時播放的問候語和音樂</span><span class="sxs-lookup"><span data-stu-id="d2274-182">Set the greeting and music played while on hold</span></span>

![含編號標注的問候和音樂選項螢幕擷取畫面](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

<span data-ttu-id="d2274-184">![數位1的圖示，在先前的螢幕擷取畫面問候語中參照標注， ](media/teamscallout1.png)
 **Greeting**對於呼叫佇列號碼的人而言，會播放選用的問候語。</span><span class="sxs-lookup"><span data-stu-id="d2274-184">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="d2274-185">您可以上傳音訊檔（.wav、mp3 或 .wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="d2274-185">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

<span data-ttu-id="d2274-186">![數位2的圖示會在先前的螢幕擷取畫面中參照標注 [ ](media/teamscallout2.png)
 **暫停**] 您可以在通話佇列中使用預設的音樂保留。</span><span class="sxs-lookup"><span data-stu-id="d2274-186">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="d2274-187">您也可以將音訊檔案上傳成 .wav、mp3 或 .wma 格式，以供您的自訂音樂保留時使用。</span><span class="sxs-lookup"><span data-stu-id="d2274-187">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="d2274-188">選取呼叫應答選項</span><span class="sxs-lookup"><span data-stu-id="d2274-188">Select the call answering options</span></span>

![通話應答選項的螢幕擷取畫面](media/teams-cq-call-answering-options.png)

<span data-ttu-id="d2274-190">![數位1的圖示會參照前一個螢幕擷取畫面中的標注 ](media/teamscallout1.png)
 **呼叫代理程式和群組**，以直接新增個別的代理程式，而不將其新增至群組，請按一下 [**新增使用者**]。</span><span class="sxs-lookup"><span data-stu-id="d2274-190">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Call agents and groups** To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="d2274-191">將個別的代理放在您想要他們接聽通話的順序。</span><span class="sxs-lookup"><span data-stu-id="d2274-191">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="d2274-192">您最多可以新增20個獨立的代理程式（若要新增20個以上的專案，請將它們放在群組中）。</span><span class="sxs-lookup"><span data-stu-id="d2274-192">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="d2274-193">呼叫會先路由到個別的 agent，然後路由到群組中的代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-193">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="d2274-194">您最多可以選取200呼叫代理程式，其屬於下列任何一種郵寄清單或群組：</span><span class="sxs-lookup"><span data-stu-id="d2274-194">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="d2274-195">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="d2274-195">Microsoft 365 group</span></span>
- <span data-ttu-id="d2274-196">安全性群組</span><span class="sxs-lookup"><span data-stu-id="d2274-196">Security group</span></span>
- <span data-ttu-id="d2274-197">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="d2274-197">Distribution list</span></span>

<span data-ttu-id="d2274-198">所選取的通話代理程式必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d2274-198">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="d2274-199">已啟用手機系統授權和企業語音的線上使用者</span><span class="sxs-lookup"><span data-stu-id="d2274-199">Online users with a Phone System license and Enterprise Voice enabled</span></span>
- <span data-ttu-id="d2274-200">使用通話方案的線上使用者</span><span class="sxs-lookup"><span data-stu-id="d2274-200">Online users with a Calling Plan</span></span>
- <span data-ttu-id="d2274-201">內部部署商務用 Skype 伺服器使用者</span><span class="sxs-lookup"><span data-stu-id="d2274-201">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="d2274-202">如果您想要將來電重新導向至組織中線上的人員，也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="d2274-202">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="d2274-203">這些人必須具備手機系統授權和企業語音功能，*或是*有通話方案。</span><span class="sxs-lookup"><span data-stu-id="d2274-203">These individuals must have a Phone System license and Enterprise Voice enabled *or* have a Calling Plan.</span></span> <span data-ttu-id="d2274-204">如需詳細資訊，請參閱[指派商務用 Skype 授權](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)、[指派 Microsoft 團隊授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)，或適合[您的通話計畫？](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="d2274-204">For more information, see [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

   <span data-ttu-id="d2274-205">若要啟用企業語音的代理程式，您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d2274-205">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="d2274-206">例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d2274-206">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="d2274-207">已加入手機系統授權或通話方案（已新增至 Microsoft 365 群組、已啟用郵件功能的通訊群組清單或安全性群組）的使用者。</span><span class="sxs-lookup"><span data-stu-id="d2274-207">Users with a Phone System license or a Calling Plan that are added to a Microsoft 365 Group, a mail-enabled distribution list, or a security group.</span></span> <span data-ttu-id="d2274-208">當您將通訊群組清單或安全群組中的代理程式新增為通話佇列代理程式時，第一次呼叫到貨最多可能需要3小時的時間。</span><span class="sxs-lookup"><span data-stu-id="d2274-208">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="d2274-209">新建立的通訊群組清單或安全性群組可能需要長達48小時才能與通話佇列搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d2274-209">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="d2274-210">新建立的 Microsoft 365 群組幾乎會立即提供給您。</span><span class="sxs-lookup"><span data-stu-id="d2274-210">Newly created Microsoft 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="d2274-211">如果您的代理正在使用 Microsoft 團隊 app 進行通話佇列通話，則必須在 TeamsOnly 模式中。</span><span class="sxs-lookup"><span data-stu-id="d2274-211">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="d2274-212">![數位2的圖示，參照前一個螢幕擷取畫面 ](media/teamscallout2.png)
 **會議模式**會議模式中的標注，可大大減少呼叫者在接受呼叫後連線至代理程式所需的時間量。</span><span class="sxs-lookup"><span data-stu-id="d2274-212">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Conference mode** Conference mode significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="d2274-213">如果您有一個以上的通話佇列，您可以在部分或所有通話佇列中啟用會議模式。啟用或停用某個通話佇列的會議模式時，不會影響任何其他通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d2274-213">If you have more than one call queue, you can enable conference mode on some or all of your call queues; enabling or disabling conference mode on one call queue doesn't impact any other call queues.</span></span>

<span data-ttu-id="d2274-214">會議模式預設為停用狀態，但在符合下列條件時可隨時啟用：</span><span class="sxs-lookup"><span data-stu-id="d2274-214">Conference mode is disabled by default but can be enabled at any time if the following requirements are met:</span></span>

- <span data-ttu-id="d2274-215">加入通話佇列的代理程式必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="d2274-215">Agents added to the call queue need to use one of the following clients:</span></span>
  - <span data-ttu-id="d2274-216">最新版本的 Microsoft 團隊桌面用戶端、Android 應用程式或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="d2274-216">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="d2274-217">Microsoft 團隊手機版本 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d2274-217">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
- <span data-ttu-id="d2274-218">必須將代理的小群組帳戶設定為 [僅限團隊模式]</span><span class="sxs-lookup"><span data-stu-id="d2274-218">Agents' Teams accounts need to be set to Teams-only mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2274-219">如果上述的代理需求不符合，且在通話佇列中啟用「會議模式」，則不符合需求的工程師不會包含在通話傳送清單中。</span><span class="sxs-lookup"><span data-stu-id="d2274-219">If the agent requirements above aren't met and conference mode is enabled on a call queue, agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="d2274-220">不在通話傳送清單中的工程師將不會收到來電。</span><span class="sxs-lookup"><span data-stu-id="d2274-220">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="d2274-221">如果您的代理商不符合上述的代理需求，請不要在通話佇列中啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="d2274-221">If you have agents who don't meet the agent requirements above, don't enable conference mode on the call queue.</span></span>

<span data-ttu-id="d2274-222">在通話佇列中啟用會議模式之後，只要透過下列其中一種方法接收，通話就會從較快的連線時間獲益：</span><span class="sxs-lookup"><span data-stu-id="d2274-222">After conference mode is enabled on a call queue, calls will benefit from the faster connection time if they're received via one of the following methods:</span></span>

- <span data-ttu-id="d2274-223">來自另一個 Microsoft 團隊桌面用戶端的 VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="d2274-223">VoIP calls from another Microsoft Teams desktop client</span></span>
- <span data-ttu-id="d2274-224">通話規劃 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="d2274-224">Calling Plan PSTN calls</span></span>
- <span data-ttu-id="d2274-225">直接路由 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="d2274-225">Direct Routing PSTN calls</span></span>

<span data-ttu-id="d2274-226">大多數通話是透過上述其中一種方法來接收。</span><span class="sxs-lookup"><span data-stu-id="d2274-226">The majority of calls are received via one of the methods listed above.</span></span> <span data-ttu-id="d2274-227">如果是透過另一個方法（例如來自商務用 Skype 用戶端的 VoIP 通話）接收通話，該通話仍會新增至通話佇列，不過連線速度越快，就不會有任何益處。</span><span class="sxs-lookup"><span data-stu-id="d2274-227">If a call is received via another method (such as a VoIP call from a Skype for Business client), the call will still be added to the call queue, however, it won't benefit from the faster connection time.</span></span>

<span data-ttu-id="d2274-228">![數位3的圖示：參照前一個螢幕擷取畫面 ](media/teamscallout3.png)
 **路由方法**中的標注，您可以選擇**Attendant**[立即]、[**串列**]、[**最長閒置**] 或 [**迴圈複用**] 做為配送方法。</span><span class="sxs-lookup"><span data-stu-id="d2274-228">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Routing method** You can choose either **Attendant**, **Serial**, **Longest idle**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="d2274-229">所有新的和現有的通話佇列都會依預設選取 [助理] 路由。</span><span class="sxs-lookup"><span data-stu-id="d2274-229">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="d2274-230">使用 [接聽] 路由時，佇列中的第一次呼叫會同時響鈴所有呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-230">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="d2274-231">第一個呼叫代理程式接聽電話，即可取得通話。</span><span class="sxs-lookup"><span data-stu-id="d2274-231">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="d2274-232">[行事鈴**路由**] 會讓佇列中的第一個呼叫同時撥打所有通話代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-232">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="d2274-233">第一個呼叫代理程式接聽電話，即可取得通話。</span><span class="sxs-lookup"><span data-stu-id="d2274-233">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="d2274-234">從撥號代理程式清單的開始，**串列路由**撥出電話會逐一撥打所有呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-234">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="d2274-235">無法在通話代理程式清單中排序代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-235">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="d2274-236">如果代理程式關閉或沒接聽來電，該通話會撥打下一個代理程式，並嘗試所有的代理程式，直到它被挑選或超時為止。</span><span class="sxs-lookup"><span data-stu-id="d2274-236">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
- <span data-ttu-id="d2274-237">[**最長閒置**] 會將下一個來電路由到已空閒最長時間的通話代理程式。</span><span class="sxs-lookup"><span data-stu-id="d2274-237">**Longest idle** routes the next available call to the call agent whose has been idle the longest time.</span></span> <span data-ttu-id="d2274-238">閒置時間是在通話時定義為呼叫代理者的目前狀態設定為 [**可用**] 或 [**離開**] （如果少於10分鐘）的時間長度。</span><span class="sxs-lookup"><span data-stu-id="d2274-238">The idle time is defined as the length of time a call agent's presence state is set to **Available** or **Away** (if less than 10 minutes), at the time of the call.</span></span> <span data-ttu-id="d2274-239">如果通話代理程式的目前狀態設定為 [**離開**] 超過10分鐘，閒置計時器就會重設。</span><span class="sxs-lookup"><span data-stu-id="d2274-239">If a call agent's presence is set to **Away** for more than 10 minutes, the idle timer resets.</span></span> <span data-ttu-id="d2274-240">使用者的目前狀態會每分鐘查詢一次。</span><span class="sxs-lookup"><span data-stu-id="d2274-240">Presence states of users are queried every minute.</span></span>

    <span data-ttu-id="d2274-241">您必須知道啟用此設定會強制啟用目前**狀態路由**。</span><span class="sxs-lookup"><span data-stu-id="d2274-241">It's important to know that enabling this setting forces **Presence-based routing** to also be enabled.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d2274-242">啟用商務用 Skype 用戶端的代理程式在啟用最長空閒設定時不會收到來電。</span><span class="sxs-lookup"><span data-stu-id="d2274-242">Agents who use the Skype for Business client won't receive calls when the longest idle setting is enabled.</span></span> <span data-ttu-id="d2274-243">如果您有使用 Skype 或商務用的代理，請不要啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="d2274-243">If you have agents who use Skype or Business, don't enable this setting.</span></span>
- <span data-ttu-id="d2274-244">**迴圈**平衡：將來電進行路由，讓每個通話代理程式從佇列取得相同數目的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d2274-244">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="d2274-245">這在入站銷售環境中可能是您想要的，以確保所有通話代理程式之間有同等的機會。</span><span class="sxs-lookup"><span data-stu-id="d2274-245">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

<span data-ttu-id="d2274-246">![數位4的圖示會參照前一個螢幕擷取畫面目前狀態路由狀態路由中的標注，這 ](media/teamscallout4.png)
 **Presence-based routing**會使用呼叫代理程式的可用性狀態，判斷是否應將工程師納入所選路由方法的通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="d2274-246">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**Presence-based routing** Presence-based routing uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="d2274-247">[通話傳送] 清單中包含 [**提供給可用**] 的呼叫代理程式，並可接聽來電。</span><span class="sxs-lookup"><span data-stu-id="d2274-247">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="d2274-248">其可用性狀態設定為任何其他狀態的代理會從 [呼叫傳送清單] 中排除，而且在其可用性狀態變更回 [**可用**] 之前，將不會收到來電。</span><span class="sxs-lookup"><span data-stu-id="d2274-248">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span>  

<span data-ttu-id="d2274-249">您可以使用任何一種路由方法來啟用目前狀態的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="d2274-249">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="d2274-250">如果代理程式無法取得來電，無論其可用性狀態為何，都不會包含在通話傳送清單中。</span><span class="sxs-lookup"><span data-stu-id="d2274-250">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d2274-251">啟用商務用 Skype 用戶端的代理程式不會包含在 [通話] 路由清單中（無論其可用性狀態為何）。</span><span class="sxs-lookup"><span data-stu-id="d2274-251">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled, regardless of their availability status.</span></span> <span data-ttu-id="d2274-252">不在通話傳送清單中的工程師將不會收到來電。</span><span class="sxs-lookup"><span data-stu-id="d2274-252">Agents who aren't in the call routing list won't receive calls.</span></span> <span data-ttu-id="d2274-253">如果您有使用商務用 Skype 的代理商，請不要啟用目前狀態的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="d2274-253">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="d2274-254">選取代理退出宣告選項</span><span class="sxs-lookup"><span data-stu-id="d2274-254">Select an agent opt-out option</span></span>

![含編號標注的代理退出宣告選項的螢幕擷取畫面](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

<span data-ttu-id="d2274-256">![數位1的圖示，在前一個螢幕擷取畫面代理程式中參照標注， ](media/teamscallout1.png)
 **即可選擇不取得來電**：啟用此選項，即可允許呼叫佇列代理程式退出宣告來自特定佇列的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d2274-256">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="d2274-257">啟用此選項可讓此佇列中的所有代理程式從該呼叫佇列開始或停止接聽通話。</span><span class="sxs-lookup"><span data-stu-id="d2274-257">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="d2274-258">您隨時都可以取消選取核取方塊，讓代理程式再次自動加入此佇列（所有代理的預設設定），以隨時撤銷代理自願退出許可權。</span><span class="sxs-lookup"><span data-stu-id="d2274-258">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="d2274-259">若要存取退出宣告選項，工程師可以：</span><span class="sxs-lookup"><span data-stu-id="d2274-259">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="d2274-260">開啟其桌面商務用 Skype 用戶端中的**選項**。</span><span class="sxs-lookup"><span data-stu-id="d2274-260">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="d2274-261">在 [**來電轉接**] 索引標籤上，按一下 [**編輯線上編輯設定**] 連結。</span><span class="sxs-lookup"><span data-stu-id="d2274-261">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="d2274-262">在 [使用者設定] 頁面上，按一下 [**通話佇列**]，然後清除核取方塊以退出宣告佇列。</span><span class="sxs-lookup"><span data-stu-id="d2274-262">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2274-263">使用商務用 Skype Desktop 以外的 app 或端點的代理程式可從 [使用者設定] 入口網站存取 [退出宣告] 選項 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) 。</span><span class="sxs-lookup"><span data-stu-id="d2274-263">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="d2274-264">如果代理程式位於 Microsoft 團隊桌面用戶端，則他們可以使用通話設定退出宣告。</span><span class="sxs-lookup"><span data-stu-id="d2274-264">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

<span data-ttu-id="d2274-265">![數位2的圖示，會參照先前螢幕擷取畫面的 [ ](media/teamscallout2.png)
 **警示] 設定**中的標注</span><span class="sxs-lookup"><span data-stu-id="d2274-265">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="d2274-266">這會定義在串列或迴圈路由方法移至下一個代理程式之前，收到呼叫通知代理程式的持續時間。</span><span class="sxs-lookup"><span data-stu-id="d2274-266">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="d2274-267">預設設定為30秒，但最多可設定3分鐘。</span><span class="sxs-lookup"><span data-stu-id="d2274-267">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="d2274-268">設定通話溢位與超時處理選項</span><span class="sxs-lookup"><span data-stu-id="d2274-268">Set the call overflow and timeout handling options</span></span>

![含編號標注的溢出處理選項之螢幕擷取畫面](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

<span data-ttu-id="d2274-270">![數位1的圖示會參照前一個螢幕擷取畫面中的標注 ](media/teamscallout1.png)
 **最大通話數上限**，使用此設定可以同時在佇列中等候的最大通話數。</span><span class="sxs-lookup"><span data-stu-id="d2274-270">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="d2274-271">預設值為50，但範圍可以是0到200。</span><span class="sxs-lookup"><span data-stu-id="d2274-271">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="d2274-272">達到這個限制之後，就會按照您在 [**達到最大通話數**] 設定時所設定的方式來處理通話。</span><span class="sxs-lookup"><span data-stu-id="d2274-272">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

<span data-ttu-id="d2274-273">![數位2的圖示在 ](media/teamscallout2.png)
 通話佇列達到其最大值（使用 [佇列] 設定中的 [**最大通話**數] 設定）時，參照上一個螢幕擷取畫面中的標注，您可以選擇新的來電所要採取**的**動作。</span><span class="sxs-lookup"><span data-stu-id="d2274-273">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="d2274-274">**中斷**連線通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="d2274-274">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="d2274-275">重新**導向至**當您選擇此選項時，請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d2274-275">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="d2274-276">**組織中的人員**具備電話系統授權且可供企業語音使用或有通話方案的線上使用者。</span><span class="sxs-lookup"><span data-stu-id="d2274-276">**Person in organization** An online user with a Phone System license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="d2274-277">您可以設定它，讓來電者可以傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="d2274-277">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="d2274-278">若要這樣做，請選取貴組織中的人員，並將其來電設定為直接轉寄給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="d2274-278">To do this, select a person in your organization and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="d2274-279">若要瞭解語音信箱所需的授權，請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-279">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="d2274-280">**語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="d2274-280">**Voice app** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

  - <span data-ttu-id="d2274-281">**外部電話號碼**選擇此值以將來電者轉接至您指定的外部電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-281">**External phone number** Choose this to transfer the caller to an external phone number that you specify.</span></span> <span data-ttu-id="d2274-282">請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="d2274-282">Note the following:</span></span>

    - <span data-ttu-id="d2274-283">與使 PSTN 向外傳送的應用程式相關聯的資源帳戶，必須有電話號碼，並獲指派虛擬電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="d2274-283">The resource account associated with the application making the PSTN transfer out must have a phone number and be assigned a Virtual Phone System license.</span></span> <span data-ttu-id="d2274-284">不支援電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="d2274-284">Phone System licenses aren't supported.</span></span> <span data-ttu-id="d2274-285">此外，資源帳戶必須具有下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d2274-285">Additionally, the resource account must have one of the following:</span></span>
        - <span data-ttu-id="d2274-286">針對含有通話方案編號的資源帳戶，請指派[通話方案](calling-plans-for-office-365.md)授權。</span><span class="sxs-lookup"><span data-stu-id="d2274-286">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
        - <span data-ttu-id="d2274-287">針對有直接傳送號碼的資源帳戶，請指派[線上語音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-287">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>
    - <span data-ttu-id="d2274-288">顯示的輸出電話號碼是由以下所示：</span><span class="sxs-lookup"><span data-stu-id="d2274-288">The outbound phone number that's displayed is determined as follows:</span></span>
        - <span data-ttu-id="d2274-289">針對通話方案編號，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-289">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
        - <span data-ttu-id="d2274-290">針對直接路由編號，傳送的數位是以 SBC 上的 P 宣稱身分識別（PAI）設定為基礎，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2274-290">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
            - <span data-ttu-id="d2274-291">如果設定為 [停用]，則會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-291">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="d2274-292">這是預設及建議的設定。</span><span class="sxs-lookup"><span data-stu-id="d2274-292">This is the default and recommended setting.</span></span>
            - <span data-ttu-id="d2274-293">如果設定為 [啟用]，則會顯示資源帳戶的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-293">If set to Enabled, the resource account phone number is displayed.</span></span>
    - <span data-ttu-id="d2274-294">不支援通話方案 trunks 和直接路由 trunks 之間的轉移。</span><span class="sxs-lookup"><span data-stu-id="d2274-294">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

* * *

<span data-ttu-id="d2274-295">![數位3的圖示，在前一個螢幕擷取畫面通話超時中參照標注 ](media/teamscallout3.png)
 **：最長等待時間**您也可以決定該通話在超時前的保留時間，以及需要重新導向或中斷連線。</span><span class="sxs-lookup"><span data-stu-id="d2274-295">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="d2274-296">重新導向的位置，取決於您設定**通話超時**設定的方式。</span><span class="sxs-lookup"><span data-stu-id="d2274-296">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="d2274-297">您可以設定從0到45分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="d2274-297">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="d2274-298">超時值可以設定為以秒為單位，以15秒為間隔。</span><span class="sxs-lookup"><span data-stu-id="d2274-298">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="d2274-299">這可讓您以較精細的細微性操作通話流程。</span><span class="sxs-lookup"><span data-stu-id="d2274-299">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="d2274-300">例如，您可以指定在30秒內未由代理程式接聽的任何通話移至目錄搜尋自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d2274-300">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

<span data-ttu-id="d2274-301">![數位4的圖示：當來電達到您在 [佇列] ](media/teamscallout4.png)
 設定中所設定的**電話**撥入時，您可以選擇來電時，會參照前**一個螢幕擷取畫面**中的標注：</span><span class="sxs-lookup"><span data-stu-id="d2274-301">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="d2274-302">**中斷**連線通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="d2274-302">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="d2274-303">**將此通話重新導向至**當您選擇此選項時，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="d2274-303">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="d2274-304">**組織中的人員**具備電話系統授權且可供企業語音或有通話方案的線上使用者。</span><span class="sxs-lookup"><span data-stu-id="d2274-304">**Person in organization** An online user with a Phone System license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="d2274-305">若要進行設定，讓撥入的人能傳送給語音信箱，請選取貴組織中的人員，並將其呼叫設定為直接轉接至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="d2274-305">To set it up so the person calling in can be sent to voicemail, select a person in your organization and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="d2274-306">若要瞭解語音信箱所需的授權，請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-306">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="d2274-307">**語音應用程式**選取與您已建立之通話佇列或自動助理相關聯之資源帳戶的名稱。</span><span class="sxs-lookup"><span data-stu-id="d2274-307">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

  - <span data-ttu-id="d2274-308">**外部電話號碼**選擇此值以將來電者轉接至您指定的外部電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-308">**External phone number** Choose this to transfer the caller to an external phone number that you specify.</span></span> <span data-ttu-id="d2274-309">請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="d2274-309">Note the following:</span></span>

    - <span data-ttu-id="d2274-310">與使 PSTN 向外傳送的應用程式相關聯的資源帳戶，必須有電話號碼，並獲指派虛擬電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="d2274-310">The resource account associated with the application making the PSTN transfer out must have a phone number and be assigned a Virtual Phone System license.</span></span> <span data-ttu-id="d2274-311">不支援電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="d2274-311">Phone System licenses aren't supported.</span></span> <span data-ttu-id="d2274-312">此外，資源帳戶必須具有下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d2274-312">Additionally, the resource account must have one of the following:</span></span>
        - <span data-ttu-id="d2274-313">針對含有通話方案編號的資源帳戶，請指派[通話方案](calling-plans-for-office-365.md)授權。</span><span class="sxs-lookup"><span data-stu-id="d2274-313">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
        - <span data-ttu-id="d2274-314">針對有直接傳送號碼的資源帳戶，請指派[線上語音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d2274-314">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>
    - <span data-ttu-id="d2274-315">顯示的輸出電話號碼是由以下所示：</span><span class="sxs-lookup"><span data-stu-id="d2274-315">The outbound phone number that's displayed is determined as follows:</span></span>
        - <span data-ttu-id="d2274-316">針對通話方案編號，會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-316">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
        - <span data-ttu-id="d2274-317">針對直接路由編號，傳送的數位是以 SBC 上的 P 宣稱身分識別（PAI）設定為基礎，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2274-317">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
            - <span data-ttu-id="d2274-318">如果設定為 [停用]，則會顯示原始來電者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-318">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="d2274-319">這是預設及建議的設定。</span><span class="sxs-lookup"><span data-stu-id="d2274-319">This is the default and recommended setting.</span></span>
            - <span data-ttu-id="d2274-320">如果設定為 [啟用]，則會顯示資源帳戶的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2274-320">If set to Enabled, the resource account phone number is displayed.</span></span>
    - <span data-ttu-id="d2274-321">不支援通話方案 trunks 和直接路由 trunks 之間的轉移。</span><span class="sxs-lookup"><span data-stu-id="d2274-321">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="d2274-322">變更撥出電話的本機號碼</span><span class="sxs-lookup"><span data-stu-id="d2274-322">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="d2274-323">若要保護通話代理程式的身分識別，請將本機號碼撥打電話給來電佇列、自動語音應答，或使用**新的 CsCallingLineIdentity** Cmdlet 的任何服務號碼，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="d2274-323">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="d2274-324">然後使用**授與 CallingLineIdentity** Cmdlet 將原則套用到使用者，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="d2274-324">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="d2274-325">如需詳細資訊，請參閱[如何在您的組織中使用來電](/microsoftteams/how-can-caller-id-be-used-in-your-organization)顯示。</span><span class="sxs-lookup"><span data-stu-id="d2274-325">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="d2274-326">通話佇列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d2274-326">Call queue cmdlets</span></span>

<span data-ttu-id="d2274-327">您也可以使用 Windows PowerShell 來建立及設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d2274-327">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="d2274-328">以下是您用來管理通話佇列的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2274-328">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="d2274-329">新-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d2274-329">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="d2274-330">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d2274-330">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="d2274-331">CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d2274-331">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="d2274-332">移除-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d2274-332">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="d2274-333">深入瞭解 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2274-333">More about Windows PowerShell</span></span>

- <span data-ttu-id="d2274-334">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="d2274-334">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d2274-335">在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="d2274-335">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="d2274-336">當您有多個工作需要執行時，它可以簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="d2274-336">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d2274-337">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="d2274-337">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d2274-338">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="d2274-338">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="d2274-339">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2274-339">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="d2274-340">當您一次為多位使用者進行變更時，Windows PowerShell 的速度、簡潔性和生產率都有許多優點。</span><span class="sxs-lookup"><span data-stu-id="d2274-340">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="d2274-341">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="d2274-341">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d2274-342">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="d2274-342">Manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="d2274-343">設定 Windows PowerShell 電腦</span><span class="sxs-lookup"><span data-stu-id="d2274-343">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="d2274-344">相關主題</span><span class="sxs-lookup"><span data-stu-id="d2274-344">Related topics</span></span>

[<span data-ttu-id="d2274-345">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="d2274-345">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="d2274-346">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="d2274-346">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="d2274-347">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="d2274-347">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="d2274-348">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="d2274-348">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
