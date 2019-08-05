---
title: 在商務用 Skype Server 2019 中設定資源帳戶
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 針對商務用 Skype Server 2019 設定資源帳戶。
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185545"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="a9567-103">設定資源帳戶</span><span class="sxs-lookup"><span data-stu-id="a9567-103">Configure resource accounts</span></span>

<span data-ttu-id="a9567-104">商務用 Skype Server 2019 混合式實現只使用電話系統提供的雲端服務來進行整合訊息, 而且不要與 Exchange Online 整合。</span><span class="sxs-lookup"><span data-stu-id="a9567-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="a9567-105">在商務用 Skype Server 2019 中, 您現在可以使用「雲端通話佇列」和「自動語音應答」,[以下是您在 Office 365 中使用電話系統所取得的內容](/MicrosoftTeams/here-s-what-you-get-with-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="a9567-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="a9567-106">若要在商務用 Skype Server 2019 上使用這些電話系統服務, 您需要建立充當應用程式端點且可以指派電話號碼的資源帳戶, 然後使用線上團隊系統管理中心來設定通話佇列或自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="a9567-106">To use these Phone System services with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="a9567-107">此資源帳戶可以連線 (請參閱在[Microsoft 團隊中管理資源](/MicrosoftTeams/manage-resource-accounts)帳戶以在線上建立資源帳戶) 或內部部署 (請見本文所述)。</span><span class="sxs-lookup"><span data-stu-id="a9567-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premise as described in this article.</span></span> <span data-ttu-id="a9567-108">通常您會有多個電話系統服務節點, 每個節點都對應至可在線上或商務用 Skype Server 2019 中駐留的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-108">Typically you will have multiple Phone System service nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="a9567-109">如果您有現有的 Exchange UM 自動語音應答及呼叫佇列系統, 在您切換到 Exchange Server 2019 或 Exchange online 之前, 您將需要手動記錄詳細資料, 然後使用 [團隊系統管理中心] 來執行全新的系統。.</span><span class="sxs-lookup"><span data-stu-id="a9567-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="a9567-110">概觀</span><span class="sxs-lookup"><span data-stu-id="a9567-110">Overview</span></span>

<span data-ttu-id="a9567-111">如果您的電話系統服務需要服務號碼, 就可以依照下列順序來符合各種相依性:</span><span class="sxs-lookup"><span data-stu-id="a9567-111">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="a9567-112">取得服務號碼</span><span class="sxs-lookup"><span data-stu-id="a9567-112">Obtain a service number</span></span>
2. <span data-ttu-id="a9567-113">購買電話系統授權</span><span class="sxs-lookup"><span data-stu-id="a9567-113">Buy a Phone System license</span></span>
3. <span data-ttu-id="a9567-114">建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-114">Create the resource account.</span></span> <span data-ttu-id="a9567-115">需要自動語音應答或通話佇列, 才能擁有關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="a9567-116">在線上與內部部署之間等待 active directory 同步處理</span><span class="sxs-lookup"><span data-stu-id="a9567-116">Wait for an active directory sync between online and on premise</span></span>
5. <span data-ttu-id="a9567-117">將電話系統授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="a9567-118">將服務號碼指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="a9567-119">建立手機系統服務 (通話佇列或自動語音應答)</span><span class="sxs-lookup"><span data-stu-id="a9567-119">Create a Phone System service (a call queue or auto attendant)</span></span>
8. <span data-ttu-id="a9567-120">將資源帳戶與服務關聯: (新-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="a9567-120">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="a9567-121">如果自動語音應答或呼叫佇列是嵌套在頂層自動語音應答底下, 只要您想要將多個進入點輸入到自動語音應答及呼叫佇列的結構中, 相關聯的資源帳戶就只需要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="a9567-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="a9567-122">若要將來電重新導向至組織中的目前線上人員, 他們必須具備**電話系統**授權, 且可供企業語音使用或擁有 Office 365 通話方案。</span><span class="sxs-lookup"><span data-stu-id="a9567-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="a9567-123">請參閱[指派 Microsoft 團隊授權](/MicrosoftTeams/assign-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="a9567-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="a9567-124">若要啟用企業語音, 您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a9567-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="a9567-125">例如, 執行:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="a9567-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="a9567-126">如果您要建立的電話系統服務會嵌套, 且不需要電話號碼, 程式如下:</span><span class="sxs-lookup"><span data-stu-id="a9567-126">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="a9567-127">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="a9567-127">Create the resource account</span></span>  
2. <span data-ttu-id="a9567-128">在線上與內部部署之間等待 active directory 同步處理</span><span class="sxs-lookup"><span data-stu-id="a9567-128">Wait for an active directory sync between online and on premise</span></span>
3. <span data-ttu-id="a9567-129">建立手機系統服務</span><span class="sxs-lookup"><span data-stu-id="a9567-129">Create a Phone System service</span></span>
4. <span data-ttu-id="a9567-130">將資源帳戶與手機系統服務建立關聯</span><span class="sxs-lookup"><span data-stu-id="a9567-130">Associate the resource account with a Phone System service</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="a9567-131">使用電話號碼建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="a9567-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="a9567-132">若要建立使用電話號碼的資源帳戶, 必須以下列循序執行下列工作:</span><span class="sxs-lookup"><span data-stu-id="a9567-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="a9567-133">移植或取得付費或免付費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a9567-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="a9567-134">該號碼不能指派給任何其他語音服務或資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="a9567-135">將電話號碼指派給資源帳戶之前, 您將需要取得或移植現有的付費或免付費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a9567-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="a9567-136">當您收到付費或免付費服務電話號碼之後, 就會顯示在**Microsoft 團隊系統管理中心** > **語音** > **電話號碼**中, 而列出的**數位類型**則會列為 [**服務-免付費**電話]。</span><span class="sxs-lookup"><span data-stu-id="a9567-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="a9567-137">若要取得您的服務號碼, 請參閱[取得服務電話號碼](/MicrosoftTeams/getting-service-phone-numbers), 或者如果您想要轉移現有的服務號碼, 請參閱[將電話號碼轉移至 Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="a9567-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span></span>

   <span data-ttu-id="a9567-138">如果您在美國以外, 您就無法使用 Microsoft 團隊系統管理中心來取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="a9567-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="a9567-139">移至 [[管理貴組織的電話號碼](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)], 瞭解如何從美國以外的地區進行。</span><span class="sxs-lookup"><span data-stu-id="a9567-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="a9567-140">購買電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="a9567-140">Buy a Phone System license.</span></span> <span data-ttu-id="a9567-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="a9567-141">See:</span></span>  
   - [<span data-ttu-id="a9567-142">Office 365 企業版 E1 和 E3</span><span class="sxs-lookup"><span data-stu-id="a9567-142">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="a9567-143">Office 365 企業版 E5</span><span class="sxs-lookup"><span data-stu-id="a9567-143">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="a9567-144">Office 365 企業版 E5 商務版軟體</span><span class="sxs-lookup"><span data-stu-id="a9567-144">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="a9567-145">針對每個電話系統服務執行`New-CsHybridApplicationEndpoint` Cmdlet 來建立內部部署的資源帳戶, 並提供名稱、sip 位址等。</span><span class="sxs-lookup"><span data-stu-id="a9567-145">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="a9567-146">如需更多關於此命令的詳細資料, 請參閱[新-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="a9567-146">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="a9567-147">可選建立您的資源帳戶之後, 您可以在線上與內部部署之間進行 AD 同步處理, 或強制執行同步處理並繼續進行手機系統服務的線上設定。</span><span class="sxs-lookup"><span data-stu-id="a9567-147">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="a9567-148">若要強制進行同步處理, 您可以在執行 AAD 連接的電腦上執行下列命令 (如果您尚未這麼做, 則必須載入`import-module adsync`才能執行命令):</span><span class="sxs-lookup"><span data-stu-id="a9567-148">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="a9567-149">如需此命令的詳細資料, 請參閱[開始 ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="a9567-149">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="a9567-150">將電話系統授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="a9567-151">請參閱[指派 Microsoft 團隊授權](/MicrosoftTeams/assign-teams-licenses)及[指派授權給一個使用者](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。</span><span class="sxs-lookup"><span data-stu-id="a9567-151">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

    <span data-ttu-id="a9567-152">如果您要將電話號碼指派給資源帳戶, 您現在可以使用 [免付費電話系統虛擬使用者授權]。</span><span class="sxs-lookup"><span data-stu-id="a9567-152">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="a9567-153">這會提供手機系統功能給組織階層的電話號碼, 並可讓您建立自動語音應答及呼叫佇列功能。</span><span class="sxs-lookup"><span data-stu-id="a9567-153">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="a9567-154">將服務號碼指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="a9567-155">使用`Set-CsHybridApplicationEndpoint`命令, 將電話號碼 (使用-LineURI 選項) 指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-155">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="a9567-156">如需此命令的詳細資料, 請參閱[設定 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="a9567-156">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="a9567-157">若要將直接路由或混合式編號指派給資源帳戶, 請使用下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a9567-157">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="a9567-158">如果資源帳戶將指派給最上層的自動語音應答或通話佇列, 就需要指派的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="a9567-158">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="a9567-159">使用者 (訂閱者) 電話號碼無法指派給資源帳戶, 只能使用服務付費或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="a9567-159">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. <span data-ttu-id="a9567-160">建立電話系統服務。</span><span class="sxs-lookup"><span data-stu-id="a9567-160">Create the Phone system service.</span></span> <span data-ttu-id="a9567-161">請參閱下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="a9567-161">See one of the following:</span></span>

   - [<span data-ttu-id="a9567-162">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="a9567-162">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="a9567-163">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="a9567-163">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="a9567-164">將資源帳戶與您先前選擇的電話系統服務建立關聯。</span><span class="sxs-lookup"><span data-stu-id="a9567-164">Associate the resource account with the Phone system service you chose previously.</span></span>

<span data-ttu-id="a9567-165">小型企業版中的小型企業實施方案範例[-設定自動](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)語音應答及[小型企業範例-設定通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)。</span><span class="sxs-lookup"><span data-stu-id="a9567-165">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="a9567-166">建立不含電話號碼的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="a9567-166">Create a resource account without a phone number</span></span>

<span data-ttu-id="a9567-167">本節討論如何建立駐留在內部部署的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-167">This section discusses creating a resource account that is homed on premise.</span></span> <span data-ttu-id="a9567-168">若要在[Microsoft 團隊的 [管理資源帳戶] 中](/MicrosoftTeams/manage-resource-accounts)討論如何建立以線上為宿主的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9567-168">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="a9567-169">無論您是建立全新的手機系統服務系統, 或最初是在 Exchange UM 中建立的結構, 都必須執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="a9567-169">These steps are necessary whether you are creating a brand new Phone System service system, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="a9567-170">登入商務用 Skype 前端伺服器, 並執行下列 PowerShell Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a9567-170">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="a9567-171">針對每個電話系統服務執行`New-CsHybridApplicationEndpoint` Cmdlet 來建立內部部署的資源帳戶, 並提供名稱、sip 位址等。</span><span class="sxs-lookup"><span data-stu-id="a9567-171">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="a9567-172">如需更多關於此命令的詳細資料, 請參閱[新-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="a9567-172">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="a9567-173">可選建立您的資源帳戶之後, 您可以在線上與內部部署之間進行 AD 同步處理, 或強制執行同步處理並繼續進行手機系統服務的線上設定。</span><span class="sxs-lookup"><span data-stu-id="a9567-173">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="a9567-174">若要強制進行同步處理, 您可以在執行 AAD 連接的電腦上執行下列命令 (如果您尚未這麼做, 則必須載入`import-module adsync`才能執行命令):</span><span class="sxs-lookup"><span data-stu-id="a9567-174">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="a9567-175">如需此命令的詳細資料, 請參閱[開始 ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="a9567-175">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="a9567-176">建立電話系統服務。</span><span class="sxs-lookup"><span data-stu-id="a9567-176">Create the Phone system service.</span></span> <span data-ttu-id="a9567-177">請參閱下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="a9567-177">See one of the following:</span></span>
   - [<span data-ttu-id="a9567-178">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="a9567-178">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="a9567-179">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="a9567-179">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="a9567-180">將您先前選擇的資源帳戶與電話系統服務建立關聯。</span><span class="sxs-lookup"><span data-stu-id="a9567-180">Associate the resource account and the Phone System service you chose previously.</span></span>

<span data-ttu-id="a9567-181">小型企業版中的小型企業實施方案範例[-設定自動](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)語音應答及[小型企業範例-設定通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)。</span><span class="sxs-lookup"><span data-stu-id="a9567-181">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="a9567-182">測試實施</span><span class="sxs-lookup"><span data-stu-id="a9567-182">Test the implementation</span></span>

<span data-ttu-id="a9567-183">測試實現的最佳方式是撥打手機系統服務所設定的號碼, 並連接到其中一個代理程式或功能表。</span><span class="sxs-lookup"><span data-stu-id="a9567-183">The best way to test the implementation is to call the number configured for a Phone System service and connect to one of the agents or menus.</span></span> <span data-ttu-id="a9567-184">您也可以使用系統管理中心動作窗格中的 [**測試] 按鈕**, 快速進行測試通話。</span><span class="sxs-lookup"><span data-stu-id="a9567-184">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="a9567-185">如果您想要變更手機系統服務, 請選取它, 然後在 [動作] 窗格中按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="a9567-185">If you want to make changes to a Phone System service, select it and then in the Action pane click **Edit**.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="a9567-186">將 Exchange UM 自動語音應答或呼叫佇列移至電話系統</span><span class="sxs-lookup"><span data-stu-id="a9567-186">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="a9567-187">從 Exchange UM 到手機系統的遷移需要重新建立通話佇列和自動語音應答結構, 而不支援直接從其中一個遷移到另一個。</span><span class="sxs-lookup"><span data-stu-id="a9567-187">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="a9567-188">若要重新實現一組通話佇列和自動語音應答:</span><span class="sxs-lookup"><span data-stu-id="a9567-188">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="a9567-189">在 Exchange 2013 或2016系統上執行下列命令, 以系統管理員身分登入, 以取得所有 Exchange UM 自動語音應答和通話佇列的清單:</span><span class="sxs-lookup"><span data-stu-id="a9567-189">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="a9567-190">針對每個列出的 Exchange UM 通話佇列或自動語音應答, 請記下其在結構中的位置、設定, 以及取得相關音效或文字轉換語音檔案的複本 (輸出中的 guid 將是儲存檔案的資料夾名稱)。</span><span class="sxs-lookup"><span data-stu-id="a9567-190">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="a9567-191">您可以執行以下命令來取得這些詳細資料:</span><span class="sxs-lookup"><span data-stu-id="a9567-191">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="a9567-192">請參閱[UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) , 以取得更多關於此命令的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a9567-192">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="a9567-193">您可能需要捕獲的完整選項清單是在[UMAutoAttendant 成員](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx), 但最重要的選項如下所示:</span><span class="sxs-lookup"><span data-stu-id="a9567-193">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="a9567-194">商務時間</span><span class="sxs-lookup"><span data-stu-id="a9567-194">Business hours</span></span>
    - <span data-ttu-id="a9567-195">非商務時間</span><span class="sxs-lookup"><span data-stu-id="a9567-195">Non-business hours</span></span>
    - <span data-ttu-id="a9567-196">語言</span><span class="sxs-lookup"><span data-stu-id="a9567-196">Language</span></span>
    - <span data-ttu-id="a9567-197">假日排程</span><span class="sxs-lookup"><span data-stu-id="a9567-197">Holiday schedule</span></span>

3. <span data-ttu-id="a9567-198">如先前所述, 建立新的內部部署端點。</span><span class="sxs-lookup"><span data-stu-id="a9567-198">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="a9567-199">將最上層的自動語音應答指派成暫時的號碼以進行測試。</span><span class="sxs-lookup"><span data-stu-id="a9567-199">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="a9567-200">根據先前所述, 設定使用端點的電話系統服務。</span><span class="sxs-lookup"><span data-stu-id="a9567-200">Configure a Phone system service that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="a9567-201">您可能會發現在使用「小型企業版」的教學課程中使用練習, 您可以[設定自動](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)語音應答, 在舊版 Exchange UM 系統中建立階層的邏輯地圖。</span><span class="sxs-lookup"><span data-stu-id="a9567-201">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="a9567-202">測試電話系統服務。</span><span class="sxs-lookup"><span data-stu-id="a9567-202">Test the Phone System service.</span></span>
6. <span data-ttu-id="a9567-203">將連結至 Exchange UM 通話佇列或自動語音應答的電話號碼重新指派給對應的電話系統服務。</span><span class="sxs-lookup"><span data-stu-id="a9567-203">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone system service.</span></span>  

   <span data-ttu-id="a9567-204">此時, 如果您已經遷移了 UM 語音信箱, 您應該位於遷移到 Exchange Server 2019 的位置。</span><span class="sxs-lookup"><span data-stu-id="a9567-204">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9567-205">請參閱</span><span class="sxs-lookup"><span data-stu-id="a9567-205">See Also</span></span>

[<span data-ttu-id="a9567-206">建立雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="a9567-206">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="a9567-207">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="a9567-207">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="a9567-208">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="a9567-208">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="a9567-209">規劃雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="a9567-209">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="a9567-210">規劃雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="a9567-210">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="a9567-211">為內部部署使用者規劃雲端語音信箱服務</span><span class="sxs-lookup"><span data-stu-id="a9567-211">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="a9567-212">新-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="a9567-212">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="a9567-213">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="a9567-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="a9567-214">[管理 Microsoft 團隊](/MicrosoftTeams/manage-resource-accounts) - \(中的資源帳戶以建立以線上方式駐留的資源帳戶\)</span><span class="sxs-lookup"><span data-stu-id="a9567-214">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
