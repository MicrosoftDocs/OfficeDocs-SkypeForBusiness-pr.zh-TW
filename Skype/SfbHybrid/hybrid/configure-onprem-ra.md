---
title: 在商務用 Skype Server 2019 中設定資源帳戶
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 為商務用 Skype Server 2019 設定資源帳戶。
ms.openlocfilehash: b5397a1d179ade5e9d70d6c9cf857bae9319d155
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221133"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="d31b9-103">設定資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d31b9-103">Configure resource accounts</span></span>

<span data-ttu-id="d31b9-104">商務用 Skype Server 2019 混合式的實現只會使用電話系統提供的雲端服務以進行整合通訊，而且不會與 Exchange Online 整合。</span><span class="sxs-lookup"><span data-stu-id="d31b9-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="d31b9-105">在商務用 Skype Server 2019 中，您現在可以使用下列所述的雲端通話佇列和自動語音應答，這是[您在 Microsoft 365 或 Office 365 中的電話系統所取得的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="d31b9-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="d31b9-106">若要使用電話系統自動語音應答或具有商務用 Skype Server 2019 的通話佇列，您將需要建立充當應用程式端點且可以指派電話號碼的資源帳戶，然後使用線上團隊系統管理中心來設定通話佇列或自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d31b9-106">To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="d31b9-107">這個資源帳戶可在線上上進行（請參閱[管理 Microsoft 小組中的資源帳戶](/MicrosoftTeams/manage-resource-accounts)以建立線上資源帳戶）或內部部署（如本文所述）。</span><span class="sxs-lookup"><span data-stu-id="d31b9-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premises as described in this article.</span></span> <span data-ttu-id="d31b9-108">一般來說，您會有多個電話系統自動語音應答或通話佇列節點，每個節點都對應至可在線上或商務用 Skype Server 2019 中的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-108">Typically you will have multiple Phone System auto attendant or call queue nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="d31b9-109">如果您有現有的 Exchange UM 自動語音應答及通話佇列系統，在切換至 Exchange Server 2019 或 Exchange online 之前，您必須先手動記錄詳細資料，然後再使用團隊系統管理中心執行全新的系統。</span><span class="sxs-lookup"><span data-stu-id="d31b9-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="d31b9-110">概觀</span><span class="sxs-lookup"><span data-stu-id="d31b9-110">Overview</span></span>

<span data-ttu-id="d31b9-111">如果您的電話系統自動語音應答或通話佇列需要服務號碼，可依下列順序滿足各種相依性：</span><span class="sxs-lookup"><span data-stu-id="d31b9-111">If your Phone System auto attendant or call queue will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="d31b9-112">取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d31b9-112">Obtain a service number.</span></span>
2. <span data-ttu-id="d31b9-113">取得免費的電話系統[虛擬使用者授權](/MicrosoftTeams/teams-add-on-licensing/virtual-user)或付費電話系統授權，以與資源帳戶搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d31b9-113">Obtain a free Phone System - [Virtual User license](/MicrosoftTeams/teams-add-on-licensing/virtual-user) or a paid Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="d31b9-114">建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-114">Create the resource account.</span></span> <span data-ttu-id="d31b9-115">必須有自動語音應答或通話佇列具有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="d31b9-116">在線上和內部部署之間等候 active directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="d31b9-116">Wait for an active directory sync between online and on premises.</span></span>
5. <span data-ttu-id="d31b9-117">將電話系統授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="d31b9-118">將服務號碼指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="d31b9-119">建立電話系統通話佇列或自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d31b9-119">Create a Phone System call queue or auto attendant.</span></span>
8. <span data-ttu-id="d31b9-120">關聯資源帳戶與自動語音應答或通話佇列：（New-CsApplicationInstanceAssociation）。</span><span class="sxs-lookup"><span data-stu-id="d31b9-120">Associate the resource account with an auto attendant or call queue: (New-CsApplicationInstanceAssociation).</span></span>

<span data-ttu-id="d31b9-121">如果 [自動語音應答] 或 [通話佇列] 嵌套在最上層的自動語音應答之下，只要您想要將多個專案點組成至自動語音應答及通話佇列的結構，相關聯的資源帳戶才需要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d31b9-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="d31b9-122">若要將來電重新導向至組織中的線上人員，他們必須具備**電話系統**授權，並可供 Enterprise Voice 使用，或具有 Microsoft 365 或 Office 365 通話方案。</span><span class="sxs-lookup"><span data-stu-id="d31b9-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="d31b9-123">請參閱[指派 Microsoft 團隊授權](/MicrosoftTeams/assign-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="d31b9-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="d31b9-124">若要啟用企業語音，您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d31b9-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="d31b9-125">例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="d31b9-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="d31b9-126">如果您要建立的電話系統自動語音應答或通話佇列將會嵌套，而且不需要電話號碼，則程式為：</span><span class="sxs-lookup"><span data-stu-id="d31b9-126">If the Phone system auto attendant or call queue you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="d31b9-127">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d31b9-127">Create the resource account</span></span>  
2. <span data-ttu-id="d31b9-128">在線上和內部部署之間等候 active directory 同步處理</span><span class="sxs-lookup"><span data-stu-id="d31b9-128">Wait for an active directory sync between online and on premises</span></span>
3. <span data-ttu-id="d31b9-129">建立電話系統自動語音應答或通話佇列</span><span class="sxs-lookup"><span data-stu-id="d31b9-129">Create a Phone System auto attendant or call queue</span></span>
4. <span data-ttu-id="d31b9-130">關聯資源帳戶與電話系統自動語音應答或通話佇列</span><span class="sxs-lookup"><span data-stu-id="d31b9-130">Associate the resource account with a Phone System auto attendant or call queue</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="d31b9-131">使用電話號碼建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d31b9-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="d31b9-132">若要建立使用電話號碼的資源帳戶，必須依下列循序執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="d31b9-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="d31b9-133">埠或取得收費或免付費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d31b9-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="d31b9-134">無法將號碼指派給任何其他語音服務或資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="d31b9-135">在您將電話號碼指派給資源帳戶之前，您必須先取得或接收您現有收費或免付費服務號碼的埠。</span><span class="sxs-lookup"><span data-stu-id="d31b9-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="d31b9-136">當您取得收費或免付費服務電話號碼後，他們會顯示在**Microsoft 小組系統管理中心**的  >  **語音**  >  **電話號碼**中，而且所列的**號碼類型**會列為「**服務-免付費**」。</span><span class="sxs-lookup"><span data-stu-id="d31b9-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="d31b9-137">若要取得服務號碼，請參閱[取得服務電話號碼](/MicrosoftTeams/getting-service-phone-numbers)，如果您想要轉接現有的服務號碼，請參閱[將電話號碼轉移給小組](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="d31b9-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

   <span data-ttu-id="d31b9-138">如果您是在美國境外，您就無法使用 Microsoft 團隊系統管理中心取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d31b9-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="d31b9-139">請移至 [[管理組織的電話號碼](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)]，以瞭解如何從美國以外的國家/地區執行。</span><span class="sxs-lookup"><span data-stu-id="d31b9-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="d31b9-140">購買電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="d31b9-140">Buy a Phone System license.</span></span> <span data-ttu-id="d31b9-141">請參閱：</span><span class="sxs-lookup"><span data-stu-id="d31b9-141">See:</span></span>  
   - [<span data-ttu-id="d31b9-142">電話系統-虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="d31b9-142">Phone System–Virtual User license</span></span>](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [<span data-ttu-id="d31b9-143">Office 365 企業版 E1 和 E3</span><span class="sxs-lookup"><span data-stu-id="d31b9-143">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="d31b9-144">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="d31b9-144">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="d31b9-145">Office 365 企業版 E5 商務軟體</span><span class="sxs-lookup"><span data-stu-id="d31b9-145">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="d31b9-146">`New-CsHybridApplicationEndpoint`針對每個電話系統自動語音應答或通話佇列執行 Cmdlet，以建立內部部署資源帳戶，並提供每個名稱、sip 位址等的指令程式。</span><span class="sxs-lookup"><span data-stu-id="d31b9-146">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="d31b9-147">如需此命令的詳細資訊，請參閱[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="d31b9-147">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="d31b9-148">選建立資源帳戶後，您可以等候 AD 在線上和內部部署之間同步處理，或是強制進行同步處理，並繼續進行電話系統自動語音應答或通話佇列的線上設定。</span><span class="sxs-lookup"><span data-stu-id="d31b9-148">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="d31b9-149">若要強制進行同步處理，您可以在執行 AAD 連線的電腦上執行下列命令（如果您尚未執行此動作，則必須先載入 `import-module adsync` 才能執行命令）：</span><span class="sxs-lookup"><span data-stu-id="d31b9-149">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="d31b9-150">如需此命令的詳細資訊，請參閱[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="d31b9-150">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="d31b9-151">將電話系統虛擬使用者或電話系統授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-151">Assign the Phone System - Virtual User or Phone System license to the resource account.</span></span> <span data-ttu-id="d31b9-152">請參閱[指派 Microsoft 團隊附加元件授權](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)，並[指派授權給一位使用者](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。</span><span class="sxs-lookup"><span data-stu-id="d31b9-152">See [Assign Microsoft Teams add-on licenses](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

   <span data-ttu-id="d31b9-153">若要將電話號碼指派給資源帳戶，您現在可以使用「成本免費電話系統-虛擬」使用者授權。</span><span class="sxs-lookup"><span data-stu-id="d31b9-153">If you are assigning a phone number to a resource account you can now use the cost-free Phone System - Virtual User license.</span></span> <span data-ttu-id="d31b9-154">這為組織層級的電話號碼提供電話系統功能，並讓您建立自動語音應答及通話佇列功能。</span><span class="sxs-lookup"><span data-stu-id="d31b9-154">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="d31b9-155">將服務號碼指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-155">Assign the service number to the resource account.</span></span> <span data-ttu-id="d31b9-156">使用 `Set-CsHybridApplicationEndpoint` 命令將電話號碼（使用-LineURI 選項）指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-156">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="d31b9-157">請參閱[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)以取得更多有關此命令的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d31b9-157">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="d31b9-158">若要將直接路由或混合式號碼指派給資源帳戶，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d31b9-158">To assign a Direct Routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   <span data-ttu-id="d31b9-159">若要將其指派給最上層的自動語音應答或通話佇列，則資源帳戶需要指派的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d31b9-159">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="d31b9-160">無法將使用者（訂戶）電話號碼指派給資源帳戶，只能使用服務收費或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d31b9-160">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

     <span data-ttu-id="d31b9-161">您可以將直接路由或混合式號碼指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-161">You can assign a Direct Routing or hybrid number to your resource account.</span></span> <span data-ttu-id="d31b9-162">如需詳細資訊，請參閱[Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) And [plan Cloud auto](plan-cloud-auto-attendant.md)direct。</span><span class="sxs-lookup"><span data-stu-id="d31b9-162">For details, see [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="d31b9-163">指派給自動語音應答和通話佇列之資源帳戶的直接路由服務編號，僅支援 Microsoft 團隊使用者和代理程式。</span><span class="sxs-lookup"><span data-stu-id="d31b9-163">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

7. <span data-ttu-id="d31b9-164">建立電話系統自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d31b9-164">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="d31b9-165">請參閱下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d31b9-165">See one of the following:</span></span>

   - [<span data-ttu-id="d31b9-166">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="d31b9-166">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="d31b9-167">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="d31b9-167">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="d31b9-168">將資源帳戶與您先前所選擇的電話系統自動語音應答或通話佇列相關聯。</span><span class="sxs-lookup"><span data-stu-id="d31b9-168">Associate the resource account with the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="d31b9-169">小型企業可使用小型企業的範例範例[-設定自動](/microsoftteams/tutorial-org-aa)語音應答和[小型企業範例-設定通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)。</span><span class="sxs-lookup"><span data-stu-id="d31b9-169">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="d31b9-170">建立沒有電話號碼的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d31b9-170">Create a resource account without a phone number</span></span>

<span data-ttu-id="d31b9-171">本節討論如何建立駐留在內部部署的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-171">This section discusses creating a resource account that is homed on premises.</span></span> <span data-ttu-id="d31b9-172">若要在[Microsoft 小組的 [管理資源帳戶] 中](/MicrosoftTeams/manage-resource-accounts)討論如何建立以線上處理的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="d31b9-172">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="d31b9-173">您必須執行這些步驟，不論您是建立全新的電話系統自動語音應答或通話佇列結構，或是最初在 Exchange UM 中建立的結構重建。</span><span class="sxs-lookup"><span data-stu-id="d31b9-173">These steps are necessary whether you are creating a brand new Phone System auto attendant or call queue structure, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="d31b9-174">登入商務用 Skype 前端伺服器，並執行下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d31b9-174">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="d31b9-175">`New-CsHybridApplicationEndpoint`針對每個電話系統自動語音應答或通話佇列執行 Cmdlet，以建立內部部署資源帳戶，並提供每個名稱、sip 位址等的指令程式。</span><span class="sxs-lookup"><span data-stu-id="d31b9-175">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="d31b9-176">如需此命令的詳細資訊，請參閱[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="d31b9-176">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="d31b9-177">選建立資源帳戶後，您可以等候 AD 在線上和內部部署之間同步處理，或是強制進行同步處理，並繼續進行電話系統自動語音應答或通話佇列的線上設定。</span><span class="sxs-lookup"><span data-stu-id="d31b9-177">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="d31b9-178">若要強制進行同步處理，您可以在執行 AAD 連線的電腦上執行下列命令（如果您尚未執行此動作，則必須先載入 `import-module adsync` 才能執行命令）：</span><span class="sxs-lookup"><span data-stu-id="d31b9-178">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="d31b9-179">如需此命令的詳細資訊，請參閱[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="d31b9-179">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="d31b9-180">建立電話系統自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d31b9-180">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="d31b9-181">請參閱下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d31b9-181">See one of the following:</span></span>
   - [<span data-ttu-id="d31b9-182">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="d31b9-182">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="d31b9-183">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="d31b9-183">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="d31b9-184">關聯先前所選的資源帳戶和電話系統自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d31b9-184">Associate the resource account and the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="d31b9-185">小型企業可使用小型企業的範例範例[-設定自動](/microsoftteams/tutorial-org-aa)語音應答和[小型企業範例-設定通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)。</span><span class="sxs-lookup"><span data-stu-id="d31b9-185">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="d31b9-186">測試實施</span><span class="sxs-lookup"><span data-stu-id="d31b9-186">Test the implementation</span></span>

<span data-ttu-id="d31b9-187">測試實現的最佳方式是呼叫為電話系統自動語音應答或通話佇列設定的號碼，並連接至其中一個代理程式或功能表。</span><span class="sxs-lookup"><span data-stu-id="d31b9-187">The best way to test the implementation is to call the number configured for a Phone System auto attendant or call queue and connect to one of the agents or menus.</span></span> <span data-ttu-id="d31b9-188">您也可以使用 [系統管理中心] 動作窗格中的 [**測試] 按鈕**，快速進行測試呼叫。</span><span class="sxs-lookup"><span data-stu-id="d31b9-188">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="d31b9-189">如果您想變更電話系統自動語音應答或通話佇列，請選取它，然後按一下動作窗格中的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d31b9-189">If you want to make changes to a Phone System auto attendant or call queue, select it and then in the Action pane click **Edit**.</span></span> 

> [!TIP]
> <span data-ttu-id="d31b9-190">如果資源帳戶對通話佇列或自動語音應答指派困難，請參閱 microsoft 小組的[已知問題](/MicrosoftTeams/Known-issues#phone-system)，以及 Microsoft 小組博客中的[如何修正混合應用程式實例](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)一節。</span><span class="sxs-lookup"><span data-stu-id="d31b9-190">If your resource account has difficulties with being assigned to a call queue or auto attendant, see [Known issues for Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) and the [How to fix my hybrid application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) section in the Microsoft Teams Blog.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="d31b9-191">將 Exchange UM 自動語音應答或通話佇列移至電話系統</span><span class="sxs-lookup"><span data-stu-id="d31b9-191">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="d31b9-192">從 Exchange UM 向電話系統進行遷移時，將需要重新建立通話佇列和自動語音應答結構，但不支援直接從一個遷移至另一個。</span><span class="sxs-lookup"><span data-stu-id="d31b9-192">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="d31b9-193">若要重新執行一組呼叫佇列和自動語音應答：</span><span class="sxs-lookup"><span data-stu-id="d31b9-193">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="d31b9-194">在以系統管理員身分登入的 Exchange 2013 或2016系統上執行下列命令，以取得所有 Exchange UM 自動語音應答及通話佇列的清單。</span><span class="sxs-lookup"><span data-stu-id="d31b9-194">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="d31b9-195">針對每個列出的 Exchange UM 通話佇列或自動語音應答，請注意其在結構中的位置、設定，以及取得關聯的聲音或文字語音轉換檔案的副本（輸出中的 guid 將是儲存檔案的資料夾名稱）。</span><span class="sxs-lookup"><span data-stu-id="d31b9-195">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="d31b9-196">您可以執行下列命令來取得這些詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d31b9-196">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="d31b9-197">如需這個命令的詳細資訊，請參閱[Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 。</span><span class="sxs-lookup"><span data-stu-id="d31b9-197">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="d31b9-198">您可能需要捕獲的完整選項清單是在[disable-umautoattendant 成員](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx)，但是最重要的附注如下：</span><span class="sxs-lookup"><span data-stu-id="d31b9-198">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="d31b9-199">營業時間</span><span class="sxs-lookup"><span data-stu-id="d31b9-199">Business hours</span></span>
    - <span data-ttu-id="d31b9-200">非上班時間</span><span class="sxs-lookup"><span data-stu-id="d31b9-200">Non-business hours</span></span>
    - <span data-ttu-id="d31b9-201">語言</span><span class="sxs-lookup"><span data-stu-id="d31b9-201">Language</span></span>
    - <span data-ttu-id="d31b9-202">假日排程</span><span class="sxs-lookup"><span data-stu-id="d31b9-202">Holiday schedule</span></span>

3. <span data-ttu-id="d31b9-203">如先前所述，建立新的內部部署端點。</span><span class="sxs-lookup"><span data-stu-id="d31b9-203">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="d31b9-204">將最上層的自動語音應答指派給用於測試目的的臨時號碼。</span><span class="sxs-lookup"><span data-stu-id="d31b9-204">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="d31b9-205">如先前所述，設定電話系統自動語音應答或使用端點的通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d31b9-205">Configure a Phone System auto attendant or call queue that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="d31b9-206">您可能會發現使用「[小型企業」範例](/microsoftteams/tutorial-org-aa)中的練習，設定自動語音應答來建立舊 Exchange UM 系統中階層的邏輯對應。</span><span class="sxs-lookup"><span data-stu-id="d31b9-206">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="d31b9-207">測試電話系統自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d31b9-207">Test the Phone System auto attendant or call queue.</span></span>
6. <span data-ttu-id="d31b9-208">將連結至 Exchange UM 通話佇列或自動語音應答的電話號碼重新指派至對應的電話系統自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d31b9-208">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone System auto attendant or call queue.</span></span>  

   <span data-ttu-id="d31b9-209">此時，如果您已遷移 UM 語音信箱，您應該位於遷移至 Exchange Server 2019 的位置。</span><span class="sxs-lookup"><span data-stu-id="d31b9-209">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="d31b9-210">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d31b9-210">See Also</span></span>

[<span data-ttu-id="d31b9-211">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="d31b9-211">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="d31b9-212">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="d31b9-212">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="d31b9-213">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="d31b9-213">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="d31b9-214">規劃雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="d31b9-214">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="d31b9-215">規劃雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="d31b9-215">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="d31b9-216">規劃內部部署使用者的雲端語音信箱服務</span><span class="sxs-lookup"><span data-stu-id="d31b9-216">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="d31b9-217">新 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="d31b9-217">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="d31b9-218">新 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="d31b9-218">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="d31b9-219">[管理 Microsoft 小組](/MicrosoftTeams/manage-resource-accounts)  -  \( 中的資源帳戶建立線上資源帳戶\)</span><span class="sxs-lookup"><span data-stu-id="d31b9-219">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
