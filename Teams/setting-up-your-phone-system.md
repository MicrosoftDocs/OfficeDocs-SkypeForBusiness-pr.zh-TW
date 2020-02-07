---
title: 設定組織的電話系統
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
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
- Phone System
description: '瞭解如何為您的組織設定電話系統（雲端 PBX）。 '
ms.openlocfilehash: 71e12447d0a6951ef787bf7c7cd82024375e11fd
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837983"
---
# <a name="set-up-phone-system-in-your-organization"></a><span data-ttu-id="d4052-103">在組織中設定電話系統</span><span class="sxs-lookup"><span data-stu-id="d4052-103">Set up Phone System in your organization</span></span>

<span data-ttu-id="d4052-104">以下是在 Office 365 中設定電話系統的逐步指南。</span><span class="sxs-lookup"><span data-stu-id="d4052-104">The following is a step-by-step guide for setting up Phone System in Office 365.</span></span> <span data-ttu-id="d4052-105">在每個步驟的結尾，都提供其他詳細資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="d4052-105">Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="d4052-106">步驟1：確認您的國家或地區有可用的電話系統</span><span class="sxs-lookup"><span data-stu-id="d4052-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.  <span data-ttu-id="d4052-107">首先，請移至[適用于音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)，然後從頁面頂端的清單中選取您的國家或地區。</span><span class="sxs-lookup"><span data-stu-id="d4052-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.  <span data-ttu-id="d4052-108">在 [**電話系統**] 下，查看功能清單及詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d4052-108">Under **Phone System**, review the list of features and details.</span></span> 
3.  <span data-ttu-id="d4052-109">如果有可用的電話系統，請移至步驟2。</span><span class="sxs-lookup"><span data-stu-id="d4052-109">If Phone System is available, go to step 2.</span></span> 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="d4052-110">步驟2：購買並指派電話系統和通話方案授權</span><span class="sxs-lookup"><span data-stu-id="d4052-110">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="d4052-111">若要將電話系統和通話方案授權指派給單一使用者，這些步驟與指派 Office 365 授權是一樣的。</span><span class="sxs-lookup"><span data-stu-id="d4052-111">To assign a Phone System and Calling Plan license to a single user, the steps are the same as assigning an Office 365 license.</span></span>  <span data-ttu-id="d4052-112">您也可以大量指派授權給多位使用者。</span><span class="sxs-lookup"><span data-stu-id="d4052-112">You can also assign licenses to multiple users in bulk.</span></span> <span data-ttu-id="d4052-113">如需詳細資訊，請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-113">For more information, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

<span data-ttu-id="d4052-114">如果通話方案不適用於您的國家或地區，請考慮使用直接路由將您的內部部署電話結構連線至 [電話系統]。</span><span class="sxs-lookup"><span data-stu-id="d4052-114">If Calling Plans are not available for your country or region, consider using Direct Routing to connect your on-premises telephony infrastructure to Phone System.</span></span>  <span data-ttu-id="d4052-115">如需詳細資訊，請參閱[手機系統 Direct 路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-115">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="d4052-116">步驟3：為您的使用者取得電話號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-116">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="d4052-117">您必須先取得電話號碼，才能將貴組織中的使用者設定為撥打及接聽電話。</span><span class="sxs-lookup"><span data-stu-id="d4052-117">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="d4052-118">您有三種方式可取得使用者的號碼：</span><span class="sxs-lookup"><span data-stu-id="d4052-118">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="d4052-119">使用小組系統管理中心取得新數位。</span><span class="sxs-lookup"><span data-stu-id="d4052-119">Get new numbers using the Teams admin center.</span></span>
- <span data-ttu-id="d4052-120">取得小組系統管理中心無法使用的新號碼。</span><span class="sxs-lookup"><span data-stu-id="d4052-120">Get new numbers that aren't available in the Teams admin center.</span></span>
- <span data-ttu-id="d4052-121">將現有的號碼從目前的服務提供者或電話轉接到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d4052-121">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span>

<span data-ttu-id="d4052-122">您必須使用 [**新增號碼**] 頁面來查看、搜尋、取得及保留這些號碼。</span><span class="sxs-lookup"><span data-stu-id="d4052-122">You must use the **Add numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="d4052-123">您可以依 [國家/地區]、[省/市] 及 [城市] 進行搜尋，然後輸入使用者所需的電話號碼數量。</span><span class="sxs-lookup"><span data-stu-id="d4052-123">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a><span data-ttu-id="d4052-124">使用團隊系統管理中心取得新使用者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-124">Get new user phone numbers using the Teams admin center</span></span>

1. <span data-ttu-id="d4052-125">使用您的公司或學校帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d4052-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="d4052-126">移至 [**團隊系統管理中心**]。</span><span class="sxs-lookup"><span data-stu-id="d4052-126">Go to the **Teams admin center**.</span></span>
    
3. <span data-ttu-id="d4052-127">在左導覽中，前往 [**語音** > **電話號碼**]，按一下 [**新增**]，然後依照提示進行。</span><span class="sxs-lookup"><span data-stu-id="d4052-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add**, and then follow the prompts.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="d4052-128">取得團隊系統管理中心無法使用的新號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-128">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="d4052-129">有時候（視您的國家/地區而定），您將無法使用小組系統管理中心來取得新號碼。</span><span class="sxs-lookup"><span data-stu-id="d4052-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="d4052-130">在這種情況下，您必須下載表單並將它傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="d4052-130">In this case, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="d4052-131">若要瞭解如何要求新的使用者編號，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-131">To learn how to request new user numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="d4052-132">從服務提供者或電話載波傳送埠或轉移電話號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="d4052-133">如果您需要999或更少的使用者電話號碼，您可以使用 [小組系統管理中心] 中的 [**新的當地號碼埠順序**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="d4052-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Teams admin center.</span></span> <span data-ttu-id="d4052-134">遵循將[電話號碼轉接給小組](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)，以轉接您的電話號碼中找到的步驟。</span><span class="sxs-lookup"><span data-stu-id="d4052-134">Follow the steps found in [Transfer phone numbers to  Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to transfer your phone numbers.</span></span>
    
- <span data-ttu-id="d4052-135">如果您需要端口超過999的電話號碼，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以提交埠訂單服務要求或訂單。</span><span class="sxs-lookup"><span data-stu-id="d4052-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order.</span></span> 

<span data-ttu-id="d4052-136">如需取得新電話號碼或轉移現有號碼的詳細資訊，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-136">For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="d4052-137">步驟4：取得服務電話號碼（音訊會議、通話佇列、自動語音應答）</span><span class="sxs-lookup"><span data-stu-id="d4052-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="d4052-138">除了從 Office 365 取得使用者的電話號碼之外，您還可以在 [音訊會議] （適用于 [會議室]）、[自動語音應答] 和 [通話佇列] 等服務中搜尋及取得付費或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d4052-138">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="d4052-139">服務電話號碼的並行通話容量比使用者或訂閱者電話號碼要高。</span><span class="sxs-lookup"><span data-stu-id="d4052-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="d4052-140">例如，服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。</span><span class="sxs-lookup"><span data-stu-id="d4052-140">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a><span data-ttu-id="d4052-141">使用團隊系統管理中心取得新的服務號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-141">Get new service numbers using the Teams admin center</span></span>


1. <span data-ttu-id="d4052-142">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d4052-142">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d4052-143">移至 [**團隊系統管理中心**]。</span><span class="sxs-lookup"><span data-stu-id="d4052-143">Go to the **Teams admin center**.</span></span>

3. <span data-ttu-id="d4052-144">在左側流覽窗格中，移至 [**語音** > **電話號碼** > ]，**新增號碼**，然後按一下 [**新的服務號碼**]。</span><span class="sxs-lookup"><span data-stu-id="d4052-144">In the left navigation pane go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d4052-145">若要在 [團隊管理中心] 的左導覽窗格中看到 [**語音**] 選項，您必須先購買至少一個**企業版 E5 授權**、一個**電話系統**附加元件授權或一個**音訊會議**附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="d4052-145">For you to see the **Voice** option in the left navigation pane in the Teams admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="d4052-146">取得團隊系統管理中心無法使用的新號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-146">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="d4052-147">有時候（視您的國家/地區而定），您將無法使用小組系統管理中心來取得新號碼。</span><span class="sxs-lookup"><span data-stu-id="d4052-147">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="d4052-148">在這種情況下，您將需要下載表單並將它傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="d4052-148">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="d4052-149">若要瞭解如何要求新號碼，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-149">To learn how to request new numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="d4052-150">移植或轉移現有的服務號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-150">Port or transfer existing service numbers</span></span>

<span data-ttu-id="d4052-151">如果您想要從目前的服務提供者或承運人傳送服務號碼，您必須手動將埠訂單提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d4052-151">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="d4052-152">您必須針對每一種類型的服務號碼（[收費電話]）提交不同的埠順序（免付費電話），您將會使用一份授權函式（LOA）傳送。</span><span class="sxs-lookup"><span data-stu-id="d4052-152">You need to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="d4052-153">在授權信件（LOA）中，您必須選取正確的服務號碼類型。</span><span class="sxs-lookup"><span data-stu-id="d4052-153">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="d4052-154">當您聯繫 Microsoft 支援時，請指定您要轉移服務號碼（*而非使用者或訂閱者號碼*），或同時進行通話容量可能不足以處理呼叫量。</span><span class="sxs-lookup"><span data-stu-id="d4052-154">When contacting Microsoft support, specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="d4052-155">如果您想要使用電話號碼傳送電話號碼或進行其他動作，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-155">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="d4052-156">步驟5：如果您要設定通話方案</span><span class="sxs-lookup"><span data-stu-id="d4052-156">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="d4052-157">如果您已按照上述步驟進行，就表示您已購買並指派電話系統和授權，以及通話方案（步驟2），以及為使用者取得的電話號碼（步驟3），因此您的通話方案已部分設定。</span><span class="sxs-lookup"><span data-stu-id="d4052-157">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="d4052-158">若要完成設定通話方案的程式，請參閱[設定通話方案](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-158">To complete the procedures for setting up Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="d4052-159">步驟6：如果您想要設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="d4052-159">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="d4052-160">有時候貴組織中的人員必須使用電話撥入會議。</span><span class="sxs-lookup"><span data-stu-id="d4052-160">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="d4052-161">Microsoft 團隊包括音訊會議功能，只適用于這種情況。</span><span class="sxs-lookup"><span data-stu-id="d4052-161">Microsoft Teams includes the Audio Conferencing feature for just this situation.</span></span> <span data-ttu-id="d4052-162">使用者可以使用電話撥入團隊會議，而不是在行動裝置或電腦上使用 [小組] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4052-162">People can call in to  Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span>
<span data-ttu-id="d4052-163">如需如何設定音訊會議的詳細資訊，請參閱[設定適用于小組的音訊會議](set-up-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-163">For information about how to set up Audio Conferencing, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md).</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="d4052-164">步驟7：如果您想要設定雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="d4052-164">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="d4052-165">雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能，以及在通話時搜尋下一個可用的呼叫代理程式來處理通話的功能在暫停時聆聽音樂。</span><span class="sxs-lookup"><span data-stu-id="d4052-165">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="d4052-166">您可以為組織建立單一或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d4052-166">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="d4052-167">如需通話佇列的詳細資訊，請參閱[建立雲端通話佇列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-167">For more information about call queues, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="d4052-168">步驟8：如果您想要設定雲端自動助理</span><span class="sxs-lookup"><span data-stu-id="d4052-168">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="d4052-169">自動語音應答讓撥入您組織的人員，並流覽功能表系統，以取得正確的部門、呼叫佇列、人員或接線員。</span><span class="sxs-lookup"><span data-stu-id="d4052-169">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="d4052-170">您可以使用商務用 Skype 系統管理中心，為您的組織建立自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d4052-170">You can create an auto attendant for your organization by using the Skype for Business admin center.</span></span>

<span data-ttu-id="d4052-171">如需設定雲端自動 attendendant 的相關資訊，請參閱[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答。</span><span class="sxs-lookup"><span data-stu-id="d4052-171">For information about setting up a Cloud auto attendendant, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="d4052-172">步驟9：指派服務電話號碼（音訊會議、通話佇列、自動語音應答）</span><span class="sxs-lookup"><span data-stu-id="d4052-172">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="d4052-173">從**上述步驟 4**獲得您的服務號碼之後，您必須將他們指派給您想要的每一種類型的服務。</span><span class="sxs-lookup"><span data-stu-id="d4052-173">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="d4052-174">例如，如果您需要專用的服務電話號碼（付費或免費付費），您必須將號碼指派給會議橋。</span><span class="sxs-lookup"><span data-stu-id="d4052-174">For example, if you want a dedicated service phone number (toll or toll-free), you'll need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="d4052-175">對於音訊會議，您可以移至 [**團隊管理中心** > **會議** > ]**橋**，然後依照提示，將專用號碼指派給會議橋。</span><span class="sxs-lookup"><span data-stu-id="d4052-175">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Teams admin center** > **Meetings** > **Conference bridges** and follow the prompts.</span></span>  <span data-ttu-id="d4052-176">如需詳細資訊，請參閱[在音訊會議橋中變更付費或免付費電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-176">For more information, see  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="d4052-177">針對自動語音應答，您可以移至 [**小組系統管理中心** > **語音** > **自動**語音應答]，將專用號碼指派給自動語音應答，然後依照提示進行。</span><span class="sxs-lookup"><span data-stu-id="d4052-177">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to  **Teams admin center** > **Voice** > **Auto attendants** and follow the prompts.</span></span>  <span data-ttu-id="d4052-178">如需詳細資訊，請參閱[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答。</span><span class="sxs-lookup"><span data-stu-id="d4052-178">For more information, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

- <span data-ttu-id="d4052-179">如果是通話佇列，您可以移至 [**小組系統管理中心** > **語音** > **通話] 佇列**，將專用號碼指派給呼叫佇列，然後依照提示進行。</span><span class="sxs-lookup"><span data-stu-id="d4052-179">For Call Queues, you can assign a dedicated number to a call queue by going to **Teams admin center** > **Voice** > **Call queues** and follow the prompts.</span></span> <span data-ttu-id="d4052-180">如需詳細資訊，請參閱[建立雲端通話佇列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-180">For more information, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

<span data-ttu-id="d4052-181">如需取得新服務號碼和移植現有服務號碼的詳細資訊，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-181">For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="d4052-182">步驟10：為您的組織設定通訊點數</span><span class="sxs-lookup"><span data-stu-id="d4052-182">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="d4052-183">如果您想要將免付費電話號碼與 Microsoft 團隊搭配使用，您必須設定通訊點數。</span><span class="sxs-lookup"><span data-stu-id="d4052-183">If you would like to use toll-free numbers with Microsoft Teams, You'll need to set up Communications Credits.</span></span> <span data-ttu-id="d4052-184">Microsoft 建議您針對通話方案（國內或國際）及需要撥出至任何目的地的音訊會議使用者設定通訊點數。</span><span class="sxs-lookup"><span data-stu-id="d4052-184">Microsoft recommends that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to any destination.</span></span> <span data-ttu-id="d4052-185">包含許多國家/地區，但某些目的地可能不會包含在您的通話方案或音訊會議訂閱中。</span><span class="sxs-lookup"><span data-stu-id="d4052-185">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> 

<span data-ttu-id="d4052-186">如果您沒有設定通訊信用帳單，並將**通訊點數**授權指派給您的使用者，而您的組織時間卻超出了幾分鐘（視您所在國家/地區的通話方案或音訊會議方案而定），這些使用者將無法撥打電話或撥出音訊會議會議。</span><span class="sxs-lookup"><span data-stu-id="d4052-186">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="d4052-187">如需詳細資訊（包括建議的融資金額），請參閱[什麼是通訊信用？](what-are-communications-credits.md) ，並[為您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d4052-187">For more information, including recommended funding amounts, see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="d4052-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4052-188">Related topics</span></span>
[<span data-ttu-id="d4052-189">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="d4052-189">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="d4052-190">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="d4052-191">取得商務用 Skype 和 Microsoft Teams 的服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="d4052-191">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="d4052-192">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="d4052-192">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
