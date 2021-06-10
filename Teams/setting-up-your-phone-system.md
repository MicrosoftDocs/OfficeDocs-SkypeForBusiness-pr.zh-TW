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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: 逐步指南詳述如何在 電話系統 (或) 中為貴組織Microsoft 365雲端 PBX Office 365。
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701211"
---
# <a name="set-up-phone-system-in-your-organization"></a><span data-ttu-id="6249c-103">設定貴組織的 [電話系統]</span><span class="sxs-lookup"><span data-stu-id="6249c-103">Set up Phone System in your organization</span></span>

<span data-ttu-id="6249c-104">以下是在 電話系統 或 Microsoft 365 中設定Microsoft 365逐步Office 365。</span><span class="sxs-lookup"><span data-stu-id="6249c-104">The following is a step-by-step guide for setting up Phone System in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="6249c-105">其他詳細資訊的連結可在每個步驟的結尾提供。</span><span class="sxs-lookup"><span data-stu-id="6249c-105">Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="6249c-106">步驟 1：確定電話系統國家/地區提供</span><span class="sxs-lookup"><span data-stu-id="6249c-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.    <span data-ttu-id="6249c-107">首先前往 [音訊](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)會議與通話方案的國家/地區可用性，然後從頁面頂端的清單選取您的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="6249c-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.    <span data-ttu-id="6249c-108">在 **電話系統** 下，查看功能與詳細資料清單。</span><span class="sxs-lookup"><span data-stu-id="6249c-108">Under **Phone System**, review the list of features and details.</span></span> 
3.    <span data-ttu-id="6249c-109">如果電話系統，請前往步驟 2。</span><span class="sxs-lookup"><span data-stu-id="6249c-109">If Phone System is available, go to step 2.</span></span> 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="6249c-110">步驟 2：購買並指派電話系統通話方案授權</span><span class="sxs-lookup"><span data-stu-id="6249c-110">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="6249c-111">若要指派電話系統通話方案授權給單一使用者，步驟與指派授權Microsoft 365或Office 365相同。</span><span class="sxs-lookup"><span data-stu-id="6249c-111">To assign a Phone System and Calling Plan license to a single user, the steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span>  <span data-ttu-id="6249c-112">您也可以大量指派授權給多個使用者。</span><span class="sxs-lookup"><span data-stu-id="6249c-112">You can also assign licenses to multiple users in bulk.</span></span> <span data-ttu-id="6249c-113">若要詳細資訊，請參閱指派[Microsoft Teams附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-113">For more information, see [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

<span data-ttu-id="6249c-114">如果您的國家/地區無法使用通話方案，請考慮使用直接路由將您的內部部署電話基礎結構電話系統。</span><span class="sxs-lookup"><span data-stu-id="6249c-114">If Calling Plans are not available for your country or region, consider using Direct Routing to connect your on-premises telephony infrastructure to Phone System.</span></span>  <span data-ttu-id="6249c-115">詳細資訊請參閱直接路由[電話系統。](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="6249c-115">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="6249c-116">步驟 3：取得使用者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-116">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="6249c-117">在您可以設定貴組織中使用者撥打和接聽電話之前，您必須先取得他們的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6249c-117">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="6249c-118">您擁有三種為使用者取得數位的方法：</span><span class="sxs-lookup"><span data-stu-id="6249c-118">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="6249c-119">使用系統管理中心取得Teams號碼。</span><span class="sxs-lookup"><span data-stu-id="6249c-119">Get new numbers using the Teams admin center.</span></span>
- <span data-ttu-id="6249c-120">取得系統管理中心Teams號碼。</span><span class="sxs-lookup"><span data-stu-id="6249c-120">Get new numbers that aren't available in the Teams admin center.</span></span>
- <span data-ttu-id="6249c-121">將現有的號碼從目前的服務提供者或電話電信公司移轉或移轉Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="6249c-121">Port or transfer your existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="6249c-122">您必須使用新增 **數位** 頁面來查看、搜尋、取得及保留這些數位。</span><span class="sxs-lookup"><span data-stu-id="6249c-122">You must use the **Add numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="6249c-123">您可以根據國家/地區、省/市和縣/市進行搜尋，然後輸入使用者所需的電話號碼數目。</span><span class="sxs-lookup"><span data-stu-id="6249c-123">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a><span data-ttu-id="6249c-124">使用系統管理中心取得Teams電話號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-124">Get new user phone numbers using the Teams admin center</span></span>

1. <span data-ttu-id="6249c-125">使用公司Microsoft 365學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="6249c-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="6249c-126">請前往 **Teams 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="6249c-126">Go to the **Teams admin center**.</span></span>
    
3. <span data-ttu-id="6249c-127">在左側流覽中，前往 **[** 語音電話  >  數位，按一下 **[新增**，然後按照提示操作。</span><span class="sxs-lookup"><span data-stu-id="6249c-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add**, and then follow the prompts.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="6249c-128">取得系統管理中心Teams號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-128">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="6249c-129">有時候 (視您的國家/地區/地區) 您將無法使用系統管理中心取得Teams號碼。</span><span class="sxs-lookup"><span data-stu-id="6249c-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="6249c-130">在這種情況下，您必須下載表單並傳送回給我們。</span><span class="sxs-lookup"><span data-stu-id="6249c-130">In this case, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="6249c-131">若要瞭解如何要求新的使用者號碼，請參閱 [管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-131">To learn how to request new user numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="6249c-132">從服務提供者或電話電信公司移轉或移轉電話號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="6249c-133">如果您需要使用者的電話號碼少於 999 個，您可以在系統管理中心使用新的當地號碼Teams精靈。</span><span class="sxs-lookup"><span data-stu-id="6249c-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Teams admin center.</span></span> <span data-ttu-id="6249c-134">請遵循將電話號碼轉接至[Teams以轉接](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6249c-134">Follow the steps found in [Transfer phone numbers to  Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to transfer your phone numbers.</span></span>
    
- <span data-ttu-id="6249c-135">如果您需要端口超過 999 個電話號碼，請參閱管理貴[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)組織的電話號碼，以提交埠訂單服務要求或訂單。</span><span class="sxs-lookup"><span data-stu-id="6249c-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order.</span></span> 

<span data-ttu-id="6249c-136">有關取得新電話號碼或傳輸現有號碼的詳細資訊，請參閱管理 [貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-136">For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="6249c-137">步驟 4：取得服務電話號碼 (音訊會議、通話佇列、自動語音) </span><span class="sxs-lookup"><span data-stu-id="6249c-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="6249c-138">除了從 Microsoft 365 或 Office 365 取得使用者的電話號碼之外，您還可以搜尋及取得電話或免付費電話號碼，以取得會議橋接器 (、自動語音服務及通話佇列等服務 () 。</span><span class="sxs-lookup"><span data-stu-id="6249c-138">In addition to getting phone numbers for your users from Microsoft 365 or Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="6249c-139">服務電話號碼的並行通話容量高於使用者或訂閱者電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6249c-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="6249c-140">例如，服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。</span><span class="sxs-lookup"><span data-stu-id="6249c-140">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a><span data-ttu-id="6249c-141">使用系統管理中心取得Teams號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-141">Get new service numbers using the Teams admin center</span></span>


1. <span data-ttu-id="6249c-142">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="6249c-142">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="6249c-143">請前往 **Teams 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="6249c-143">Go to the **Teams admin center**.</span></span>

3. <span data-ttu-id="6249c-144">在左側流覽窗格中，前往 **[** 語音電話  >    >  **號碼 新增號碼**，然後按一下 [**新增服務號碼**> 。</span><span class="sxs-lookup"><span data-stu-id="6249c-144">In the left navigation pane go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6249c-145">若要在 Teams系統管理中心的左側流覽窗格中看到語音選項，您必須先購買至少一個 **Enterprise E5** 授權、一個 **電話系統** 附加元件授權或一個音訊會議附加元件授權。 </span><span class="sxs-lookup"><span data-stu-id="6249c-145">For you to see the **Voice** option in the left navigation pane in the Teams admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="6249c-146">取得系統管理中心Teams號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-146">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="6249c-147">有時候 (視您的國家/地區/地區) 您將無法使用系統管理中心取得Teams號碼。</span><span class="sxs-lookup"><span data-stu-id="6249c-147">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="6249c-148">在這種情況下，您必須下載表單並傳送回給我們。</span><span class="sxs-lookup"><span data-stu-id="6249c-148">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="6249c-149">若要瞭解如何要求新號碼，請參閱 [管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-149">To learn how to request new numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="6249c-150">移轉或移轉現有的服務號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-150">Port or transfer existing service numbers</span></span>

<span data-ttu-id="6249c-151">如果您想要從目前的服務提供者或電信公司移轉服務號碼，您必須手動提交移轉訂單給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="6249c-151">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="6249c-152">您必須針對每種類型的服務號碼提交個別的移轉訂單 (收費與免付費) 您將使用授權書或 LOA (進行) 。</span><span class="sxs-lookup"><span data-stu-id="6249c-152">You need to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="6249c-153">在授權書 (LOA) ，您必須選取正確的服務號碼類型。</span><span class="sxs-lookup"><span data-stu-id="6249c-153">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="6249c-154">與 Microsoft 支援服務聯繫時，請指定您傳輸的是服務號碼 (而非使用者或訂閱 *者號碼*) ，或是同時通話容量可能不足以處理通話量。</span><span class="sxs-lookup"><span data-stu-id="6249c-154">When contacting Microsoft support, specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="6249c-155">如果您想要傳輸電話號碼或使用電話號碼執行其他工作，請參閱管理 [貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-155">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="6249c-156">步驟 5：如果您想要設定通話方案</span><span class="sxs-lookup"><span data-stu-id="6249c-156">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="6249c-157">如果您一直遵循上述步驟，表示您已經購買並指派 電話系統 和授權，以及您的使用者的通話方案 (步驟 2) ，並取得使用者的電話號碼 (步驟 3) ，因此您的通話方案已部分設定。</span><span class="sxs-lookup"><span data-stu-id="6249c-157">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="6249c-158">若要完成設定通話方案的程式，請參閱 [設定通話方案](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-158">To complete the procedures for setting up Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="6249c-159">步驟 6：如果您想要設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="6249c-159">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="6249c-160">貴組織內的人員有時會需要透過電話來加入會議。</span><span class="sxs-lookup"><span data-stu-id="6249c-160">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="6249c-161">Microsoft Teams音訊會議功能，</span><span class="sxs-lookup"><span data-stu-id="6249c-161">Microsoft Teams includes the Audio Conferencing feature for just this situation.</span></span> <span data-ttu-id="6249c-162">使用者可以使用電話Teams會議，而不是在行動裝置Teams或 PC 上使用 Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="6249c-162">People can call in to  Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span>
<span data-ttu-id="6249c-163">若要瞭解如何設定音訊會議，請參閱設定音訊會議[Teams。](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6249c-163">For information about how to set up Audio Conferencing, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md).</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="6249c-164">步驟 7：如果您想要設定雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="6249c-164">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="6249c-165">雲端通話佇列包括當某人來電到貴組織的電話號碼時所使用的問候語、自動保留通話的能力，以及搜尋下一個可用的通話代理程式來處理通話，而通話者正在聆聽保留的音樂。</span><span class="sxs-lookup"><span data-stu-id="6249c-165">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="6249c-166">您可以為貴組織建立單一或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="6249c-166">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="6249c-167">有關通話佇列詳細資訊，請參閱 [建立雲端通話佇列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-167">For more information about call queues, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="6249c-168">步驟 8：如果您想要設定雲端自動總機</span><span class="sxs-lookup"><span data-stu-id="6249c-168">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="6249c-169">自動電話機會讓來電到貴組織的人，並流覽功能表系統，讓他們到正確的部門、通話佇列、人員或接線生。</span><span class="sxs-lookup"><span data-stu-id="6249c-169">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="6249c-170">您可以使用系統管理中心，為組織建立Teams機。</span><span class="sxs-lookup"><span data-stu-id="6249c-170">You can create an auto attendant for your organization by using the Teams admin center.</span></span>

<span data-ttu-id="6249c-171">有關設定雲端自動出席者的資訊，請參閱 [設定雲端自動出席者](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-171">For information about setting up a Cloud auto attendendant, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="6249c-172">步驟 9：指派服務電話號碼 (音訊會議、通話佇列、自動語音) </span><span class="sxs-lookup"><span data-stu-id="6249c-172">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="6249c-173">一旦從上述步驟 **4** 獲得您的服務號碼後，您需要將號碼指派給您想要的每一種服務類型。</span><span class="sxs-lookup"><span data-stu-id="6249c-173">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="6249c-174">例如，如果您想要專用服務電話號碼 (付費或免付費) ，您必須將號碼指派給會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="6249c-174">For example, if you want a dedicated service phone number (toll or toll-free), you'll need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="6249c-175">針對音訊會議，您可以到系統管理中心會議橋接器，Teams會議橋接器並遵循提示，將專用號碼指派給會議  >    >  橋接器。</span><span class="sxs-lookup"><span data-stu-id="6249c-175">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Teams admin center** > **Meetings** > **Conference bridges** and follow the prompts.</span></span>  <span data-ttu-id="6249c-176">詳細資訊，請參閱變更音訊會議橋接器上的付費或免  [付費號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-176">For more information, see  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="6249c-177">針對自動語音留言，您可以到系統管理中心語音自動語音Teams，然後按照提示，將專用號碼指派給自動語音  >    >  機。</span><span class="sxs-lookup"><span data-stu-id="6249c-177">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to  **Teams admin center** > **Voice** > **Auto attendants** and follow the prompts.</span></span>  <span data-ttu-id="6249c-178">詳細資訊，請參閱 [設定雲端自動助理](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-178">For more information, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

- <span data-ttu-id="6249c-179">針對通話佇列，您可以指定專用號碼給通話佇列 **，Teams** 系統管理中心語音通話佇列，然後按照  >    >  提示操作。</span><span class="sxs-lookup"><span data-stu-id="6249c-179">For Call Queues, you can assign a dedicated number to a call queue by going to **Teams admin center** > **Voice** > **Call queues** and follow the prompts.</span></span> <span data-ttu-id="6249c-180">詳細資訊，請參閱 [建立雲端通話佇列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-180">For more information, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

<span data-ttu-id="6249c-181">有關取得新服務號碼及移植現有服務號碼的詳細資訊，請參閱取得 [服務電話號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-181">For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="6249c-182">步驟 10：為貴組織設定通訊信用額度</span><span class="sxs-lookup"><span data-stu-id="6249c-182">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="6249c-183">如果您想要將免付費號碼與 Microsoft Teams一起使用，您必須設定通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="6249c-183">If you would like to use toll-free numbers with Microsoft Teams, You'll need to set up Communications Credits.</span></span> <span data-ttu-id="6249c-184">Microsoft 建議您為需要撥出到任何目的地之 (國內或國際電話) 音訊會議使用者設定通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="6249c-184">Microsoft recommends that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to any destination.</span></span> <span data-ttu-id="6249c-185">包含許多國家/地區，但部分目的地可能不包含在通話方案或音訊會議訂閱中。</span><span class="sxs-lookup"><span data-stu-id="6249c-185">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> 

<span data-ttu-id="6249c-186">如果您沒有設定通訊信用額度帳單，並指派通訊信用額度授權給使用者，而貴組織的通話分鐘數 (取決於您的國家/地區) 中的通話方案或音訊會議方案，這些使用者將無法撥打電話或撥出音訊會議。</span><span class="sxs-lookup"><span data-stu-id="6249c-186">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="6249c-187">有關詳細資訊 ，包括建議的基金金額，請參閱 [什麼是通訊信用額度？](what-are-communications-credits.md) 以及為貴組織設定通訊 [信用額度](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="6249c-187">For more information, including recommended funding amounts, see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="6249c-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="6249c-188">Related topics</span></span>
[<span data-ttu-id="6249c-189">以下是在 電話系統 或 Microsoft 365 中Office 365</span><span class="sxs-lookup"><span data-stu-id="6249c-189">Here's what you get with Phone System in Microsoft 365 or Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="6249c-190">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="6249c-191">取得商務用 Skype 和 Microsoft Teams 的服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="6249c-191">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="6249c-192">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="6249c-192">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
