---
title: 管理團隊中的資源帳戶
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 7ccc7a26c83357d68147381101ef8a97184f03f4
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993495"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="072f0-103">在 Microsoft Teams 中管理資源帳戶</span><span class="sxs-lookup"><span data-stu-id="072f0-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="072f0-104">資源帳戶是 Azure AD 中已停用的使用者物件，而且可以用來代表資源（一般）。</span><span class="sxs-lookup"><span data-stu-id="072f0-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="072f0-105">例如，您可以在 Exchange 中使用資源帳戶來代表會議室，並允許他們擁有電話號碼和行事曆。</span><span class="sxs-lookup"><span data-stu-id="072f0-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="072f0-106">您可以使用商務用 Skype Server 2019，在 Microsoft 365 或內部部署中託管資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="072f0-107">在 Microsoft 團隊中，每個自動語音應答或通話佇列都需要有一個資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="072f0-108">您也可以將資源帳戶指派給服務電話號碼。</span><span class="sxs-lookup"><span data-stu-id="072f0-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="072f0-109">這是您將電話號碼指派給自動語音應答及呼叫佇列的方式，允許來自外部團隊的呼叫者到達自動回應或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="072f0-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="072f0-110">本文說明如何建立資源帳戶並準備好將其用於自動語音應答及呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="072f0-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="072f0-111">在您開始本文中的程式之前，請先確定您已完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="072f0-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="072f0-112">取得虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="072f0-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="072f0-113">取得服務號碼</span><span class="sxs-lookup"><span data-stu-id="072f0-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="072f0-114">取得虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="072f0-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="072f0-115">每個資源帳戶都需要授權，才能使用自動語音應答及呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="072f0-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="072f0-116">您可以使用免費的 *Microsoft 365 Phone System-虛擬使用者* 授權。</span><span class="sxs-lookup"><span data-stu-id="072f0-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="072f0-117">若要取得這些授權，請參閱 [虛擬使用者授權](teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="072f0-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="072f0-118">我們將在本文稍後的內容中，說明如何將授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="072f0-119">若要取得虛擬使用者授權，請在 Microsoft 365 系統管理中心中，移至 **帳單**  >  **購買服務**  >  **附加元件訂閱** ，然後滾動到最後，您將會看到 [ *電話系統-虛擬使用者* 授權]。</span><span class="sxs-lookup"><span data-stu-id="072f0-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="072f0-120">選取 [ **立即購買** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-120">Select **Buy now**.</span></span> <span data-ttu-id="072f0-121">有零成本，但您仍需遵循這些步驟來取得授權。</span><span class="sxs-lookup"><span data-stu-id="072f0-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="072f0-122">取得服務號碼</span><span class="sxs-lookup"><span data-stu-id="072f0-122">Obtain service numbers</span></span>

<span data-ttu-id="072f0-123">[服務號碼] 是自動語音應答及呼叫佇列的選用，不過您至少需要一個服務編號，呼叫者才能到達您的自動語音應答及呼叫佇列設定。</span><span class="sxs-lookup"><span data-stu-id="072f0-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="072f0-124">針對您想要直接透過服務號碼直接取得的任何自動語音應答或通話佇列，您必須有具有相關聯服務號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="072f0-125">資源帳戶可以使用付費或免付費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="072f0-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="072f0-126">您可以要求新的號碼或從其他運營商取得現有號碼。</span><span class="sxs-lookup"><span data-stu-id="072f0-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="072f0-127">若要取得新的服務號碼，請參閱 [取得服務電話號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="072f0-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="072f0-128">若要從另一個電信公司撥打電話給其他運輸公司，請參閱將 [電話號碼轉移給小組](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="072f0-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="072f0-129">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="072f0-129">Create a resource account</span></span>

<span data-ttu-id="072f0-130">您可以在 [團隊管理中心] 中建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-130">You can create a resource account in the Teams admin center.</span></span>

![[新增資源帳戶] 使用者介面的螢幕擷取畫面](media/resource-account-add.png)

1. <span data-ttu-id="072f0-132">在 [團隊管理中心] 中，展開 [ **整個組織的設定** ]，然後按一下 [ **資源帳戶** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-132">In the Teams admin center, expand **Org-wide settings** , and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="072f0-133">按一下 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-133">Click **Add**.</span></span>

3. <span data-ttu-id="072f0-134">在 [ **新增資源帳戶** ] 窗格中，填寫 [ **顯示名稱** **]、[** 使用者名稱] 和 [ **資源帳戶類型** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-134">In the **Add resource account** pane, fill out **Display name** , **Username** , and the **Resource account type**.</span></span> <span data-ttu-id="072f0-135">資源帳戶類型可以是 **自動** 應答或 **呼叫佇列** ，視您想要使用此資源帳戶的方式而定。</span><span class="sxs-lookup"><span data-stu-id="072f0-135">The resource account type can be either **Auto attendant** or **Call queue** , depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="072f0-136">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="072f0-136">Click **Save**.</span></span>

![資源帳戶清單的螢幕擷取畫面](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="072f0-138">指派授權</span><span class="sxs-lookup"><span data-stu-id="072f0-138">Assign a license</span></span>

<span data-ttu-id="072f0-139">針對每個資源帳戶，您必須指派 *Microsoft 365 電話系統-虛擬使用者* 授權或 *電話系統* 授權。</span><span class="sxs-lookup"><span data-stu-id="072f0-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![在 Microsoft 365 系統管理中心指派授權使用者介面的螢幕擷取畫面](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="072f0-141">在 Microsoft 365 系統管理中心，按一下您要指派授權的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="072f0-142">在 [ **授權及應用程式** ] 索引標籤的 [ **授權** ] 底下，選取 [ **Microsoft 365 電話系統-虛擬使用者** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-142">On the **Licenses and Apps** tab, under **Licenses** , select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="072f0-143">按一下 [ **儲存變更** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="072f0-144">指派服務號碼</span><span class="sxs-lookup"><span data-stu-id="072f0-144">Assign a service number</span></span>

<span data-ttu-id="072f0-145">如果您打算將資源帳戶與需要服務號碼的自動語音應答或通話佇列搭配使用，請將號碼指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![指派服務號碼使用者介面的螢幕擷取畫面](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="072f0-147">在團隊系統管理中心的 [ **資源帳戶** ] 頁面上，選取您要指派服務號碼的資源帳戶，然後按一下 [ **指派/取消指派** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="072f0-148">在 [ **電話號碼類型** ] 下拉式清單中，選擇您要使用的號碼類型。</span><span class="sxs-lookup"><span data-stu-id="072f0-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="072f0-149">在 [ **已指派的電話號碼** ] 方塊中，搜尋您要使用的號碼，然後按一下 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="072f0-150">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="072f0-150">Click **Save**.</span></span>


<span data-ttu-id="072f0-151">若要將直接路由或混合式編號指派給資源帳戶，您需要使用 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="072f0-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="072f0-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="072f0-152">Next steps</span></span>

<span data-ttu-id="072f0-153">完成資源帳戶設定並根據需要指派服務號碼之後，您就可以開始使用 [自動語音應答] 或 [通話佇列] 的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="072f0-154">請參閱下列參考資料：</span><span class="sxs-lookup"><span data-stu-id="072f0-154">See the following references:</span></span>

 - [<span data-ttu-id="072f0-155">雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="072f0-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="072f0-156">雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="072f0-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="072f0-157">您可以使用 [ **編輯** ] 選項來編輯資源帳戶的 [ **顯示名稱** ] 和 [ **資源] 帳戶** 類型。</span><span class="sxs-lookup"><span data-stu-id="072f0-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="072f0-158">完成後，按一下 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="072f0-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="072f0-159">變更現有的資源帳戶以使用虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="072f0-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="072f0-160">如果您決定將現有資源帳戶的授權從 **電話系統** 授權切換至虛擬使用者授權，您必須取得免費的虛擬使用者授權，然後依照 Microsoft 365 系統管理中心的步驟， [將使用者移至不同的訂閱](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。</span><span class="sxs-lookup"><span data-stu-id="072f0-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="072f0-161">永遠移除完整的電話系統授權，並在相同的授權活動中指派虛擬使用者授權。</span><span class="sxs-lookup"><span data-stu-id="072f0-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="072f0-162">如果您移除舊的授權，請儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="072f0-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="072f0-163">如果發生這種情況，我們建議您為虛擬使用者授權建立新的資源帳戶，並移除中斷的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="072f0-164">商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="072f0-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="072f0-165">針對駐留在商務用 Skype Server 2019 的資源帳戶（可搭配雲端通話佇列和雲端自動語音應答），請參閱 [規劃雲端通話佇列](/SkypeforBusiness/hybrid/plan-call-queue) 或 [規劃雲端自動](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)語音應答。</span><span class="sxs-lookup"><span data-stu-id="072f0-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="072f0-166">混合式實現 (以直接路由) 為宿主的號碼是使用 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) Cmdlet （在內部部署商務用 Skype server 2019 伺服器上）進行設定。</span><span class="sxs-lookup"><span data-stu-id="072f0-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="072f0-167">建立應用程式實例時所需使用的應用程式識別碼為：</span><span class="sxs-lookup"><span data-stu-id="072f0-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="072f0-168">**自動** 語音應答： ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="072f0-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="072f0-169">**通話佇列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="072f0-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="072f0-170">如果您想讓通話佇列或自動語音應答能透過商務用 Skype Server 2019 使用者進行搜尋，您應該在商務用 Skype Server 2019 上建立您的資源帳戶，因為線上資源帳戶不會同步處理到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="072f0-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="072f0-171">當 sipfederationtls 的 DNS SRV 記錄解析到商務用 Skype Server 2019 時， **必須** 使用 SfB 管理命令介面，並同步處理到 Azure AD，在商務用 skype server 2019 上建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="072f0-172">針對與商務用 Skype Server 混合使用的實現：</span><span class="sxs-lookup"><span data-stu-id="072f0-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="072f0-173">規劃雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="072f0-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="072f0-174">規劃雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="072f0-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="072f0-175">設定內部部署的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="072f0-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="072f0-176">刪除資源帳戶</span><span class="sxs-lookup"><span data-stu-id="072f0-176">Delete a resource account</span></span>

<span data-ttu-id="072f0-177">在刪除前，請確定您已將電話號碼與資源帳戶取消關聯，以免讓您的服務號碼停滯在擱置模式中。</span><span class="sxs-lookup"><span data-stu-id="072f0-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="072f0-178">完成之後，您可以在 Microsoft 365 系統管理中心的 [使用者] 索引標籤底下刪除資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="072f0-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="072f0-179">若要解除直接路由電話號碼與資源帳戶的關聯，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="072f0-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
