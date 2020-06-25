---
title: 管理團隊中的資源帳戶
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何在 Microsoft 團隊中建立、編輯和管理資源帳戶。
ms.openlocfilehash: b47e00323129211f657ec1dafc4e62a7cd6e4321
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868610"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="b9c41-103">在 Microsoft Teams 中管理資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="b9c41-104">資源帳戶也稱為 Azure AD 中*已停用的使用者物件*，而且可以用來代表一般的資源。</span><span class="sxs-lookup"><span data-stu-id="b9c41-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="b9c41-105">例如，在 Exchange 中可能會用來代表會議室，並允許他們擁有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b9c41-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="b9c41-106">您可以使用商務用 Skype Server 2019，在 Microsoft 365 或內部部署中託管資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="b9c41-107">在 Microsoft 團隊或商務用 Skype Online 中，每個電話系統通話佇列或自動語音應答都必須至少有一個相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="b9c41-108">資源帳戶是否需要指派的電話號碼，取決於相關通話佇列或自動語音應答的用途，如下列圖表所示。</span><span class="sxs-lookup"><span data-stu-id="b9c41-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="b9c41-109">在將電話號碼指派給資源帳戶之前，您也可以參閱在本文底部連結的通話佇列和自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="b9c41-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![資源帳戶和使用者授權的範例](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="b9c41-111">本文適用于 Microsoft 團隊和商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="b9c41-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="b9c41-112">針對駐留在商務用 Skype Server 2019 的資源帳戶，請參閱[設定資源帳戶](/SkypeForBusiness/hybrid/configure-onprem-ra)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="b9c41-113">將電話號碼指派給電話系統通話佇列</span><span class="sxs-lookup"><span data-stu-id="b9c41-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="b9c41-114">如果您的組織已經使用至少一個電話系統授權，請將電話號碼指派給電話系統呼叫佇列，處理常式為：</span><span class="sxs-lookup"><span data-stu-id="b9c41-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="b9c41-115">取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="b9c41-115">Obtain a service number.</span></span>
2. <span data-ttu-id="b9c41-116">取得免費的電話系統-[虛擬使用者授權](teams-add-on-licensing/virtual-user.md)或付費電話系統授權，以與資源帳戶或電話系統授權搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b9c41-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="b9c41-117">建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-117">Create the resource account.</span></span> <span data-ttu-id="b9c41-118">需要自動語音應答或通話佇列，才能擁有關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="b9c41-119">將電話系統或電話系統-虛擬使用者授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="b9c41-120">將服務電話號碼指派給您剛指派授權給之資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="b9c41-121">建立電話系統通話佇列或自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b9c41-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="b9c41-122">連結資源帳戶與通話佇列或自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="b9c41-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="b9c41-123">如果自動語音應答或呼叫佇列嵌套在頂層自動語音應答底下，且您想要將多個進入點輸入到自動語音應答及呼叫佇列的結構中，相關聯的資源帳戶只需要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b9c41-123">If the auto attendant or call queue is nested under a top-level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="b9c41-124">若要將來電重新導向至您組織中的線上人員，他們必須具備**手機系統**授權，且可供企業語音使用，或是有 Microsoft 365 或 Office 365 通話方案。</span><span class="sxs-lookup"><span data-stu-id="b9c41-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="b9c41-125">請參閱[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-125">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="b9c41-126">若要啟用企業語音，您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b9c41-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b9c41-127">例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b9c41-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="b9c41-128">為了避免發生資源帳戶的問題，請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="b9c41-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="b9c41-129">如果您正在建立的電話系統通話佇列或自動語音應答將會嵌套，而且不需要電話號碼，程式如下：</span><span class="sxs-lookup"><span data-stu-id="b9c41-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="b9c41-130">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-130">Create the resource account</span></span>
2. <span data-ttu-id="b9c41-131">建立電話系統通話佇列或自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b9c41-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="b9c41-132">將資源帳戶與電話系統通話佇列或自動語音關聯</span><span class="sxs-lookup"><span data-stu-id="b9c41-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="b9c41-133">使用電話號碼建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="b9c41-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c41-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9c41-135">電話號碼不會直接指派給自動語音應答或通話佇列，而是與自動語音應答或通話佇列相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="b9c41-136">最上層的自動語音應答或通話佇列，必須將電話號碼連結至它的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="b9c41-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="b9c41-137">若要建立使用電話號碼的資源帳戶，程式為：</span><span class="sxs-lookup"><span data-stu-id="b9c41-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="b9c41-138">移植或取得付費或免付費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="b9c41-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="b9c41-139">該號碼不能指派給任何其他語音服務或資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="b9c41-140">在您將電話號碼指派給資源帳戶之前，您必須先取得或移植現有的付費或免付費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="b9c41-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="b9c41-141">當您收到付費或免付費服務電話號碼之後，就會顯示在**Microsoft 團隊系統管理中心**的  >  **語音**  >  **電話號碼**中，而**數位類型**則會列為 [**服務-免付費**電話]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="b9c41-142">若要取得您的服務號碼，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)，或者如果您想要轉移現有的服務號碼，請參閱[將電話號碼轉移至團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="b9c41-143">如果您要將電話號碼指派給資源帳戶，您現在可以使用 [免付費電話系統虛擬使用者授權]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="b9c41-144">這會提供手機系統功能給組織階層的電話號碼，並可讓您建立自動語音應答及呼叫佇列功能。</span><span class="sxs-lookup"><span data-stu-id="b9c41-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="b9c41-145">取得電話系統虛擬使用者授權或一般的電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="b9c41-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="b9c41-146">若要取得虛擬使用者授權，請在 Microsoft 365 系統管理中心中，移至**帳單**  >  **購買服務**  >  **附加元件訂閱**，然後滾動至最後-您會看到「電話系統-虛擬使用者」授權。</span><span class="sxs-lookup"><span data-stu-id="b9c41-146">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="b9c41-147">選取 [**立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-147">Select **Buy now**.</span></span> <span data-ttu-id="b9c41-148">有零成本，但您仍需遵循這些步驟來取得授權。</span><span class="sxs-lookup"><span data-stu-id="b9c41-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="b9c41-149">建立新的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-149">Create a new resource account.</span></span> <span data-ttu-id="b9c41-150">請參閱在[Microsoft 團隊系統管理中心建立資源帳戶](#create-a-resource-account-in-the-microsoft-teams-admin-center)或[在 Powershell 中建立資源帳戶](#create-a-resource-account-in-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-150">See [Create a resource account in the Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="b9c41-151">將電話系統-[虛擬使用者授權](teams-add-on-licensing/virtual-user.md)或電話系統授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="b9c41-152">請參閱[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)和[指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-152">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
5. <span data-ttu-id="b9c41-153">將服務號碼指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="b9c41-154">請參閱[指派/取消指派電話號碼和服務](#assignunassign-phone-numbers-and-services)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="b9c41-155">設定下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b9c41-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="b9c41-156">雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b9c41-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="b9c41-157">雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="b9c41-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="b9c41-158">將資源帳戶連結到自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="b9c41-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="b9c41-159">請參閱[指派/取消指派電話號碼和服務](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="b9c41-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="b9c41-160">建立自動語音應答時，當您建立資源帳戶時，系統會自動套用授權。</span><span class="sxs-lookup"><span data-stu-id="b9c41-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="b9c41-161">建立不含電話號碼的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="b9c41-162">嵌套的自動語音應答或呼叫佇列將需要資源帳戶，但在許多情況下，對應的資源帳戶不需要電話號碼和支援電話號碼所需的授權。</span><span class="sxs-lookup"><span data-stu-id="b9c41-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="b9c41-163">若要建立不需要電話號碼的資源帳戶，必須以下列循序執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="b9c41-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="b9c41-164">建立新的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-164">Create a new resource account.</span></span> <span data-ttu-id="b9c41-165">請參閱[在 Microsoft 團隊系統管理中心建立資源帳戶](#create-a-resource-account-in-the-microsoft-teams-admin-center)或[在 Powershell 中建立資源帳戶](#create-a-resource-account-in-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>

2. <span data-ttu-id="b9c41-166">設定下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b9c41-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="b9c41-167">雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b9c41-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="b9c41-168">雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="b9c41-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
   
3. <span data-ttu-id="b9c41-169">將資源帳戶指派給通話佇列或自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="b9c41-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="b9c41-170">請參閱[指派/取消指派電話號碼和服務](#assignunassign-phone-numbers-and-services)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b9c41-171">在 Microsoft [團隊管理中心] 中建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-171">Create a resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b9c41-172">在您購買電話系統授權之後，請在 Microsoft 團隊系統管理中心的左導覽中，移至**組織範圍的設定**  >  **資源帳戶**。</span><span class="sxs-lookup"><span data-stu-id="b9c41-172">After you've bought a Phone System license, in the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**.</span></span>

![[資源帳戶] 頁面的螢幕擷取畫面](media/r-a-master.png)

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/teamscallout1.png)

<span data-ttu-id="b9c41-175">若要建立新的資源帳戶，**請按一下 [新增]**。</span><span class="sxs-lookup"><span data-stu-id="b9c41-175">To create a new resource account, click **Add**.</span></span> <span data-ttu-id="b9c41-176">在 [**新增資源帳戶**] 窗格**中，填寫 [** **顯示名稱**]、[使用者名稱] （功能變數名稱必須自動填入），以及資源帳戶的**資源帳戶類型**。</span><span class="sxs-lookup"><span data-stu-id="b9c41-176">In the **Add resource account** pane, fill out **Display name**, **Username** (the domain name should populate automatically), and **Resource account type** for the resource account.</span></span> <span data-ttu-id="b9c41-177">資源帳戶類型可以是 [**自動**應答] 或 [**呼叫佇列**]，視您想要與資源帳戶建立關聯的 app 而定。</span><span class="sxs-lookup"><span data-stu-id="b9c41-177">The resource account type can be either **Auto attendant** or **Call queue**, depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="b9c41-178">當您準備好時，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-178">When you're ready, click **Save**.</span></span>

![[新增資源帳戶] 選項的螢幕擷取畫面](media/res-acct.png)

<span data-ttu-id="b9c41-180">接著，將授權套用至 Microsoft 365 系統管理中心的資源帳戶，如[將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)中所述。</span><span class="sxs-lookup"><span data-stu-id="b9c41-180">Next, apply a license to the resource account in the Microsoft 365 Admin center, as described in [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="b9c41-181">編輯資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-181">Edit resource account</span></span> 

<span data-ttu-id="b9c41-182">![數位2的圖示，參照前一個螢幕擷取畫面中的標注， ](media/teamscallout2.png) 您可以使用 [**編輯**] 選項編輯資源帳戶**顯示名稱**和**資源帳戶**類型。</span><span class="sxs-lookup"><span data-stu-id="b9c41-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="b9c41-183">完成後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-183">Click **Save** when you are done.</span></span>

![[編輯資源帳戶] 選項的螢幕擷取畫面](media/r-a-edit.png)

<span data-ttu-id="b9c41-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c41-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="b9c41-186">指派/取消指派電話號碼和服務</span><span class="sxs-lookup"><span data-stu-id="b9c41-186">Assign/unassign phone numbers and services</span></span>

<span data-ttu-id="b9c41-187">![數位3的圖示，在您建立資源帳戶並指派授權之後，在前一個螢幕擷取畫面中參照標注， ](media/teamscallout3.png) 您可以按一下 [**指派/取消指派**]，將服務號碼指派給資源帳戶、設定電話號碼類型，或將資源帳戶指派給已經存在的特定自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="b9c41-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) After you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="b9c41-188">指派直接路由號碼只能使用 Cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="b9c41-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="b9c41-189">如果您尚未建立要與資源帳戶相關聯的通話佇列或自動語音應答，請將該欄位留白。</span><span class="sxs-lookup"><span data-stu-id="b9c41-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account, leave that field blank.</span></span> <span data-ttu-id="b9c41-190">您可以在建立資源帳戶時將它連結。</span><span class="sxs-lookup"><span data-stu-id="b9c41-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="b9c41-191">完成後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="b9c41-192">**電話號碼類型**的選項如下：</span><span class="sxs-lookup"><span data-stu-id="b9c41-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="b9c41-193">無</span><span class="sxs-lookup"><span data-stu-id="b9c41-193">None</span></span>
- <span data-ttu-id="b9c41-194">Online</span><span class="sxs-lookup"><span data-stu-id="b9c41-194">Online</span></span>
- <span data-ttu-id="b9c41-195">免付費電話</span><span class="sxs-lookup"><span data-stu-id="b9c41-195">Toll-free</span></span>
- <span data-ttu-id="b9c41-196">內部部署</span><span class="sxs-lookup"><span data-stu-id="b9c41-196">On-premises</span></span>

![[指派/取消指派] 選項的螢幕擷取畫面](media/r-a-assign.png)

<span data-ttu-id="b9c41-198">若要將直接路由或混合式編號指派給資源帳戶，您將需要使用 PowerShell，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="b9c41-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9c41-199">如果您的資源帳戶沒有有效的授權，當您嘗試將電話號碼指派給資源帳戶時，可能會發生內部檢查失敗。</span><span class="sxs-lookup"><span data-stu-id="b9c41-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="b9c41-200">您無法指派號碼或將資源帳戶與通話佇列或自動語音助理建立關聯。</span><span class="sxs-lookup"><span data-stu-id="b9c41-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9c41-201">電話號碼不會直接指派給自動語音應答或通話佇列，而是與自動語音應答或通話佇列相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="b9c41-202">變更現有的資源帳戶以使用虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="b9c41-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="b9c41-203">如果您決定將現有資源帳戶的授權從電話系統授權切換至虛擬使用者授權，您必須取得免費的虛擬使用者授權，然後依照 Microsoft 365 系統管理中心的步驟，[將使用者移至不同的訂閱](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-203">If you decide to switch the licenses on your existing resource account from a Phone System license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="b9c41-204">永遠移除完整的電話系統授權，並在相同的授權活動中指派虛擬使用者授權。</span><span class="sxs-lookup"><span data-stu-id="b9c41-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="b9c41-205">如果您移除舊的授權，請儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="b9c41-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="b9c41-206">如果發生這種情況，我們建議您為虛擬使用者授權建立新的資源帳戶，並移除中斷的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="b9c41-207">在 Powershell 中建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-207">Create a resource account in Powershell</span></span>

<span data-ttu-id="b9c41-208">根據您的資源帳戶是位於線上或商務用 Skype Server 2019，您必須使用系統管理員許可權連線至適當的 Powershell 提示。</span><span class="sxs-lookup"><span data-stu-id="b9c41-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="b9c41-209">下列 Powershell Cmdlet 範例顯示如何使用[新的 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)建立以線上為宿主的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-209">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="b9c41-210">針對駐留在商務用 Skype Server 2019 的資源帳戶（可搭配雲端通話佇列和雲端自動語音應答），請參閱[規劃雲端通話佇列](/SkypeforBusiness/hybrid/plan-call-queue)或[規劃雲端自動](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)語音應答。</span><span class="sxs-lookup"><span data-stu-id="b9c41-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="b9c41-211">混合式實現（駐留在直接路由上的號碼）是使用[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) Cmdlet （在內部部署商務用 Skype server 2019 伺服器上）進行設定。</span><span class="sxs-lookup"><span data-stu-id="b9c41-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="b9c41-212">您在建立應用程式實例時所需使用的應用程式識別碼為：</span><span class="sxs-lookup"><span data-stu-id="b9c41-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="b9c41-213">**自動**語音應答： ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="b9c41-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="b9c41-214">**通話佇列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="b9c41-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="b9c41-215">如果您想讓通話佇列或自動語音應答能透過商務用 Skype Server 2019 使用者進行搜尋，您應該在商務用 Skype Server 2019 上建立您的資源帳戶，因為線上資源帳戶不會同步處理到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="b9c41-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="b9c41-216">當 sipfederationtls 的 DNS SRV 記錄解析到商務用 Skype Server 2019 時，**必須**使用 SfB 管理命令介面，並同步處理至 ONLINE Azure AD，在商務用 skype server 2019 上建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="b9c41-217">若要在線上建立與自動語音助理搭配使用的資源帳戶，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b9c41-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="b9c41-218">您必須先將授權套用至該資源帳戶，才能使用該帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="b9c41-219">若要瞭解如何將授權套用至 Microsoft 365 系統管理中心的帳戶，請參閱[指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)以及[指派商務用 Skype 授權](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="b9c41-219">To learn how to apply a license to an account in the Microsoft 365 admin center, see[Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="b9c41-220">可選將正確的授權套用至資源帳戶之後，您就可以將電話號碼指派給資源帳戶，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b9c41-220">(Optional) After the correct license is applied to the resource account, you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="b9c41-221">並非所有資源帳戶都需要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b9c41-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="b9c41-222">如果您沒有將授權套用至資源帳戶，電話號碼指派將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b9c41-222">If you didn't apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="b9c41-223">如需此命令的詳細資料，請參閱[設定 CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="b9c41-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b9c41-224">您最簡單的做法是使用 Microsoft 團隊系統管理中心來設定線上電話號碼，如先前所述。</span><span class="sxs-lookup"><span data-stu-id="b9c41-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="b9c41-225">若要將直接傳送電話號碼指派給資源帳戶（無論是在 Microsoft 團隊或商務用 Skype Server 2019 中），請針對商務用 Skype Online Powershell 使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b9c41-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b9c41-226">在 Microsoft 團隊系統管理中心中管理資源帳戶設定</span><span class="sxs-lookup"><span data-stu-id="b9c41-226">Manage resource account settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b9c41-227">若要在 Microsoft 團隊系統管理中心中管理資源帳戶設定，請移至 [**整個組織的設定**  >  **資源帳戶**]，選取您要變更其設定的資源帳戶，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-227">To manage resource account settings in Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click **Edit**.</span></span> <span data-ttu-id="b9c41-228">在 [**編輯資源帳戶**] 窗格中，您可以變更這些設定：</span><span class="sxs-lookup"><span data-stu-id="b9c41-228">On the **Edit resource account** pane, you can change these settings:</span></span>

- <span data-ttu-id="b9c41-229">帳戶的**顯示名稱**</span><span class="sxs-lookup"><span data-stu-id="b9c41-229">**Display name** for the account</span></span>
- <span data-ttu-id="b9c41-230">使用帳戶的通話佇列或自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b9c41-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="b9c41-231">指派給帳戶的電話號碼</span><span class="sxs-lookup"><span data-stu-id="b9c41-231">Phone number assigned to the account</span></span>

<span data-ttu-id="b9c41-232">完成後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-232">When finished, click **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="b9c41-233">刪除資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-233">Delete a resource account</span></span>

<span data-ttu-id="b9c41-234">在刪除前，請確定您已將電話號碼與資源帳戶取消關聯，以免讓您的服務號碼停滯在擱置模式中。</span><span class="sxs-lookup"><span data-stu-id="b9c41-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="b9c41-235">您可以使用下列 Cmdlet 來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="b9c41-235">You can do that using the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="b9c41-236">完成之後，您可以在 Microsoft 365 系統管理中心的 [使用者] 索引標籤底下刪除資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-236">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="b9c41-237">若要解除直接路由電話號碼與資源帳戶的關聯，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b9c41-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="b9c41-238">疑難排解</span><span class="sxs-lookup"><span data-stu-id="b9c41-238">Troubleshooting</span></span>

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b9c41-239">在 Microsoft 團隊系統管理中心中，您沒有看到指派給資源帳戶的電話號碼</span><span class="sxs-lookup"><span data-stu-id="b9c41-239">You don't see the phone number assigned to the resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b9c41-240">如果您在 Microsoft 團隊系統管理中心中沒有看到指派給資源帳戶的電話號碼，而且您無法指派該號碼，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="b9c41-240">If you don't see the phone number assigned to the resource account in the Microsoft Teams admin center and you are unable to assign the number from there, check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="b9c41-241">如果 [部門] 屬性顯示商務用 Skype 應用程式端點，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b9c41-241">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="b9c41-242">在執行 cmldet 之後重新整理團隊管理中心網頁，您應該能夠正確指派號碼。</span><span class="sxs-lookup"><span data-stu-id="b9c41-242">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a><span data-ttu-id="b9c41-243">您會收到「我們無法使用此資源帳戶來服務」。</span><span class="sxs-lookup"><span data-stu-id="b9c41-243">You get a "We can't use this resource account for services."</span></span> <span data-ttu-id="b9c41-244">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="b9c41-244">error message</span></span>

<span data-ttu-id="b9c41-245"><a name="blocksignin"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c41-245"><a name="blocksignin"> </a></span></span>

<span data-ttu-id="b9c41-246">當您嘗試使用資源帳戶時，會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="b9c41-246">You get the following error message when you try to use a resource account:</span></span>

<span data-ttu-id="b9c41-247">「我們無法將此資源帳戶用於服務。</span><span class="sxs-lookup"><span data-stu-id="b9c41-247">"We can't use this resource account for services.</span></span> <span data-ttu-id="b9c41-248">您必須停用並封鎖資源帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b9c41-248">The resource account must be DISABLED and BLOCKED from signing in.</span></span> <span data-ttu-id="b9c41-249">您必須在 Microsoft 365 系統管理中心的 [使用者] 頁面上封鎖此資源帳戶的登入。</span><span class="sxs-lookup"><span data-stu-id="b9c41-249">You must BLOCK sign-ins for this resource account on the Users page in the Microsoft 365 admin center."</span></span>

<span data-ttu-id="b9c41-250">當您建立資源帳戶時，預設會停用該帳戶，且系統會封鎖帳戶的登入。</span><span class="sxs-lookup"><span data-stu-id="b9c41-250">When you create a resource account, by default, it's disabled and sign in is blocked for the account.</span></span> <span data-ttu-id="b9c41-251">不應變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="b9c41-251">These settings shouldn't be changed.</span></span> <span data-ttu-id="b9c41-252">若要解決此錯誤訊息，請封鎖資源帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b9c41-252">To resolve this error message, block the resource account from signing in.</span></span> <span data-ttu-id="b9c41-253">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="b9c41-253">To do this:</span></span>

1. <span data-ttu-id="b9c41-254">在 Microsoft 365 系統管理中心中，移至 [**使用者**]、[搜尋]，然後選取資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9c41-254">In the Microsoft 365 admin center, go to **Users**, search for, and then select the resource account.</span></span>
2. <span data-ttu-id="b9c41-255">在窗格頂端的 [顯示名稱] 底下，按一下 [**封鎖此使用者？**]，選取 [**封鎖此使用者登入**] 核取方塊，然後選取 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-255">At the top of the pane under the display name, click **Block this user?**, select the **Block this user from signing in** check box, and then select **Save changes**.</span></span>

   ![[封鎖此使用者] 選項的螢幕擷取畫面](media/res-acct-block.png)

    <span data-ttu-id="b9c41-257">執行此動作之後，您會在顯示名稱底下看到 [登入封鎖]。</span><span class="sxs-lookup"><span data-stu-id="b9c41-257">After you do this, you'll see "Sign in blocked" under the display name.</span></span>

      ![登入封鎖郵件的螢幕擷取畫面](media/res-acct-sign-in-blocked.png)

## <a name="related-information"></a><span data-ttu-id="b9c41-259">相關資訊</span><span class="sxs-lookup"><span data-stu-id="b9c41-259">Related Information</span></span>

<span data-ttu-id="b9c41-260">針對與商務用 Skype Server 混合使用的實現：</span><span class="sxs-lookup"><span data-stu-id="b9c41-260">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="b9c41-261">規劃雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b9c41-261">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="b9c41-262">規劃雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="b9c41-262">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="b9c41-263">設定內部部署的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b9c41-263">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="b9c41-264">針對團隊或商務用 Skype Online 中的 [實現]：</span><span class="sxs-lookup"><span data-stu-id="b9c41-264">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="b9c41-265">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="b9c41-265">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="b9c41-266">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b9c41-266">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="b9c41-267">小型企業範例 - 設定自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b9c41-267">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="b9c41-268">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="b9c41-268">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="b9c41-269">新-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="b9c41-269">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="b9c41-270">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="b9c41-270">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="b9c41-271">新-CsOnlineApplicationInstanceAssociation</span><span class="sxs-lookup"><span data-stu-id="b9c41-271">New-CsOnlineApplicationInstanceAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[<span data-ttu-id="b9c41-272">電話系統-虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="b9c41-272">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
