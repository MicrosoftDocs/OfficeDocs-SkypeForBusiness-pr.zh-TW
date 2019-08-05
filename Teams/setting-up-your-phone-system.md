---
title: 在組織中設定電話系統
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '瞭解如何為您的組織設定電話系統 (雲端 PBX)。 '
ms.openlocfilehash: 73cae7507a7c9d4dc86ea24de51790d13a32cf27
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "36184917"
---
# <a name="setting-up-phone-system-in-your-organization"></a><span data-ttu-id="0851b-103">在組織中設定電話系統</span><span class="sxs-lookup"><span data-stu-id="0851b-103">Setting up Phone System in your organization</span></span>

<span data-ttu-id="0851b-104">以下是在 Office 365 中設定電話系統的逐步指南。</span><span class="sxs-lookup"><span data-stu-id="0851b-104">The following is a step-by-step guide for setting up Phone System in Office 365.</span></span> <span data-ttu-id="0851b-105">在每個步驟的結尾, 都提供其他詳細資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="0851b-105">Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="0851b-106">步驟 1: 確認您的國家或地區有可用的電話系統</span><span class="sxs-lookup"><span data-stu-id="0851b-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.  <span data-ttu-id="0851b-107">首先, 請移至[適用于音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), 然後從頁面頂端的清單中選取您的國家或地區。</span><span class="sxs-lookup"><span data-stu-id="0851b-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.  <span data-ttu-id="0851b-108">在 [**電話系統**] 下, 查看功能清單及詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0851b-108">Under **Phone System**, review the list of features and details.</span></span> 
3.  <span data-ttu-id="0851b-109">如果有可用的電話系統, 請移至步驟2。</span><span class="sxs-lookup"><span data-stu-id="0851b-109">If Phone System is available, go to step 2.</span></span> 

<span data-ttu-id="0851b-110">**若要深入瞭解手機系統和音訊會議的地區可用性, 請參閱[音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。**</span><span class="sxs-lookup"><span data-stu-id="0851b-110">**To learn more about regional availability of Phone System and Audio Conferencing, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**</span></span>

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="0851b-111">步驟 2: 購買並指派電話系統和通話方案授權</span><span class="sxs-lookup"><span data-stu-id="0851b-111">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="0851b-112">若要將電話系統和通話方案授權指派給單一使用者, 步驟與指派 Office 365 授權相同。</span><span class="sxs-lookup"><span data-stu-id="0851b-112">To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="0851b-113">請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="0851b-113">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="0851b-114">如果您想要大量指派多個使用者, 請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="0851b-114">If you want to assign multiple users in bulk, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="0851b-115">步驟 3: 為您的使用者取得電話號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-115">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="0851b-116">您必須先取得電話號碼, 才能將貴組織中的使用者設定為撥打及接聽電話。</span><span class="sxs-lookup"><span data-stu-id="0851b-116">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="0851b-117">您有三種方式可取得使用者的號碼:</span><span class="sxs-lookup"><span data-stu-id="0851b-117">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="0851b-118">使用商務用 Skype 系統管理中心來取得新號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-118">Get new numbers using the Skype for Business admin center.</span></span>
- <span data-ttu-id="0851b-119">取得商務用 Skype 系統管理中心無法使用的新號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-119">Get new numbers that aren't available in the Skype for Business admin center.</span></span>
- <span data-ttu-id="0851b-120">將現有的號碼從目前的服務提供者或電話轉接到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0851b-120">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span>

<span data-ttu-id="0851b-121">您必須使用 [新增**使用者編號**] 頁面來查看、搜尋、取得及保留這些號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-121">You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="0851b-122">您可以依 [國家/地區]、[省/市] 及 [城市] 進行搜尋, 然後輸入使用者所需的電話號碼數量。</span><span class="sxs-lookup"><span data-stu-id="0851b-122">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers"></a><span data-ttu-id="0851b-123">取得新使用者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-123">Get new user phone numbers</span></span> 
 
<span data-ttu-id="0851b-124">![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="0851b-124">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="0851b-125">使用您的公司或學校帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0851b-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="0851b-126">移至**Microsoft 365 管理中心** > **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="0851b-126">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0851b-127">在左導覽中, 前往 [**語音** > **電話號碼**], 按一下 [**新增號碼** ![] [新增] 按鈕, 顯示](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)為加號, 然後按一下 [**新增使用者號碼**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add new number** ![The Add button, displayed as a plus symbol](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), and then click **New user numbers**.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="0851b-128">取得商務用 Skype 系統管理中心無法使用的新號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-128">Get new numbers that aren't available in the Skype for Business admin center</span></span>
  
<span data-ttu-id="0851b-129">有時候 (視您的國家/地區而定), 您將無法使用商務用 Skype 系統管理中心來取得新號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center.</span></span> <span data-ttu-id="0851b-130">在這種情況下, 您將需要下載表單並將它傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="0851b-130">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="0851b-131">請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), 瞭解如何要求新的使用者號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-131">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="0851b-132">從服務提供者或電話載波傳送埠或轉移電話號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="0851b-133">如果您需要999或更少的使用者電話號碼, 您可以使用商務用 Skype 系統管理中心的 [**新的當地號碼埠順序**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="0851b-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center.</span></span> <span data-ttu-id="0851b-134">遵循將電話號碼[轉接至 Office 365](transfer-phone-numbers-to-office-365.md)中的步驟, 將您的電話號碼轉移到商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="0851b-134">Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.</span></span>
    
- <span data-ttu-id="0851b-135">如果您需要端口超過999的電話號碼, 請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以提交埠訂單服務要求或訂單, 以將所有這些電話號碼移植到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0851b-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order to get all of these phone numbers ported over to Office 365.</span></span> 

<span data-ttu-id="0851b-136">**如需取得新電話號碼或轉移現有號碼的詳細資訊, 請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。**</span><span class="sxs-lookup"><span data-stu-id="0851b-136">**For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="0851b-137">步驟 4: 取得服務電話號碼 (音訊會議、通話佇列、自動語音應答)</span><span class="sxs-lookup"><span data-stu-id="0851b-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="0851b-138">除了從 Office 365 取得使用者的電話號碼之外, 您還可以在 [音訊會議] (適用于 [會議室])、自動語音應答及通話佇列 (亦稱為服務號碼) 等服務中搜尋和取得付費或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-138">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="0851b-139">服務電話號碼的並行通話容量比使用者或訂閱者電話號碼要高。</span><span class="sxs-lookup"><span data-stu-id="0851b-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="0851b-140">例如, 服務號碼可以同時處理數百個通話, 而使用者的電話號碼只能同時處理幾個通話。</span><span class="sxs-lookup"><span data-stu-id="0851b-140">For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers"></a><span data-ttu-id="0851b-141">取得新的服務號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-141">Get new service numbers</span></span>

<span data-ttu-id="0851b-142">![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="0851b-142">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>


1. <span data-ttu-id="0851b-143">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0851b-143">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0851b-144">移至**Microsoft 365 管理中心** > **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="0851b-144">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0851b-145">在左導覽中, 移至 [**語音** > **電話號碼** > ],**新增號碼**, 然後按一下 [**新的服務號碼**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-145">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0851b-146">若要在商務用 Skype 系統管理中心的左側導覽中看到 [**語音**] 選項, 您必須先購買至少一個**企業版 E5 授權**、一個**電話系統**附加元件授權或一個**音訊會議**附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="0851b-146">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="0851b-147">取得商務用 Skype 系統管理中心無法使用的新號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-147">Get new numbers that aren't available in the Skype for Business admin center</span></span>
  
<span data-ttu-id="0851b-148">有時候 (視您的國家/地區而定), 您將無法使用商務用 Skype 系統管理中心來取得新號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-148">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center.</span></span> <span data-ttu-id="0851b-149">在這種情況下, 您將需要下載表單並將它傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="0851b-149">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="0851b-150">請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), 瞭解如何要求新號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-150">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers.</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="0851b-151">移植或轉移現有的服務號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-151">Port or transfer existing service numbers</span></span>

<span data-ttu-id="0851b-152">如果您想要從目前的服務提供者或承運人傳送服務號碼, 您必須手動將埠訂單提交給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0851b-152">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="0851b-153">您必須針對每一種類型的服務號碼 ([收費電話]) 提交不同的埠順序 (免付費電話), 您就會使用一份授權函式 (LOA) 來傳送。</span><span class="sxs-lookup"><span data-stu-id="0851b-153">You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="0851b-154">在授權信件 (LOA) 中, 您必須選取正確的服務號碼類型。</span><span class="sxs-lookup"><span data-stu-id="0851b-154">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="0851b-155">當您聯繫 Microsoft 支援時, 請確定您已指定要轉移服務號碼 (*而非使用者或訂閱者號碼*), 或同時進行通話容量可能不足以處理通話量。</span><span class="sxs-lookup"><span data-stu-id="0851b-155">When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="0851b-156">如果您想要使用電話號碼傳送電話號碼或進行其他動作, 請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="0851b-156">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="0851b-157">步驟 5: 如果您要設定通話方案</span><span class="sxs-lookup"><span data-stu-id="0851b-157">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="0851b-158">如果您已按照上述步驟進行, 就表示您已購買並指派電話系統和授權, 以及通話方案 (步驟 2), 以及為使用者取得的電話號碼 (步驟 3), 因此您的通話方案已部分設定。</span><span class="sxs-lookup"><span data-stu-id="0851b-158">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="0851b-159">請依照下列三個程式完成您的通話方案設定。</span><span class="sxs-lookup"><span data-stu-id="0851b-159">Follow the three procedures below to complete the setup of your Calling Plan.</span></span>

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a><span data-ttu-id="0851b-160">為您的組織新增緊急位址和位置</span><span class="sxs-lookup"><span data-stu-id="0851b-160">Add emergency addresses and locations for your organization</span></span>

1. <span data-ttu-id="0851b-161">在 [**語音**] 頁面上, 選擇 [**緊急位置** > **新增位址**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-161">On the **Voice** page, choose **Emergency locations** > **Add new address**.</span></span>

2. <span data-ttu-id="0851b-162">在 [**新增位址**] 窗格中, 輸入您的位址名稱, 然後完成剩餘的方塊。</span><span class="sxs-lookup"><span data-stu-id="0851b-162">In the **New Address** pane, enter a name for your address, and then complete the remaining boxes.</span></span>
    
     ![[新增位址] 窗格的螢幕擷取畫面](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > <span data-ttu-id="0851b-164">針對英文客戶, 如果街道名稱是一個數位, 請務必在結尾包含 "st" 或 "th", 如上述圖片所示。</span><span class="sxs-lookup"><span data-stu-id="0851b-164">For English customers, if the street name is a number, be sure to include "st" or "th" at the end, as shown in the above picture.</span></span>

3. <span data-ttu-id="0851b-165">選擇 [**驗證**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-165">Choose **Validate**.</span></span>

    <span data-ttu-id="0851b-166">如有需要, 系統會提示您對位址進行修正。</span><span class="sxs-lookup"><span data-stu-id="0851b-166">If needed, you'll be prompted to make corrections to the address.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="0851b-167">驗證街道或市政位址涉及確認其合法且格式正確。</span><span class="sxs-lookup"><span data-stu-id="0851b-167">Validating a street or civic address involves making sure that it is legitimate and correctly formatted.</span></span> <span data-ttu-id="0851b-168">部分正確的緊急位址 (例如, 如果您輸了錯誤的城市名稱), 可能仍會通過驗證。</span><span class="sxs-lookup"><span data-stu-id="0851b-168">It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation.</span></span> <span data-ttu-id="0851b-169">即使是拼錯並通過驗證, 也會將 [錯誤] 的城市名稱及其他正確的位址部分組合在一起, 以將呼叫路由至適當的緊急派單中心。</span><span class="sxs-lookup"><span data-stu-id="0851b-169">Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span></span>

    > [!TIP]
    > <span data-ttu-id="0851b-170">如果需要針對緊急回應修正位址, 就會出現綠色橫幅, 通知您位址已更新。</span><span class="sxs-lookup"><span data-stu-id="0851b-170">If the address needs to be corrected for emergency response, a green banner will appear notifying you that the address was updated.</span></span>

4. <span data-ttu-id="0851b-171">驗證網址之後, 請選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-171">After the address is validated, choose **Save**.</span></span>

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a><span data-ttu-id="0851b-172">為使用者指派電話號碼和緊急位址</span><span class="sxs-lookup"><span data-stu-id="0851b-172">Assign phone numbers and emergency addresses to users</span></span>

> [!TIP]
> <span data-ttu-id="0851b-173">如果您在執行這個步驟之前, 先將其他人新增至您的商務, 可能需要**幾個小時的時間**, 才會顯示在 [**語音使用者**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="0851b-173">If you add more people to your business right before doing this step, it may take **several hours** for them to appear on the **Voice users** page.</span></span> <span data-ttu-id="0851b-174">還有一個延隔時間。</span><span class="sxs-lookup"><span data-stu-id="0851b-174">There's a latency.</span></span>

1. <span data-ttu-id="0851b-175">在 [**語音使用者**] 頁面上, 選取您要指派電話號碼和緊急位址的人員。</span><span class="sxs-lookup"><span data-stu-id="0851b-175">On the **Voice users** page, select the people who you want to assign a phone number and emergency address to.</span></span>

2. <span data-ttu-id="0851b-176">在 [動作] 窗格中, 按一下 [**指派號碼**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-176">In the Action pane, click **Assign number**.</span></span>

3. <span data-ttu-id="0851b-177">在 [**指派號碼**] 頁面上, 于 [**選取要指派的號碼**] 清單中, 選取使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-177">On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.</span></span>

4. <span data-ttu-id="0851b-178">若要選取緊急位址, 請在方塊中輸入城市的名稱, 然後選擇 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-178">To select an emergency address, enter name of the city in the box and choose **Search**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0851b-179">如果您在美國以外的地區, 您的號碼已經有緊急位址, 但您現在可以變更它。</span><span class="sxs-lookup"><span data-stu-id="0851b-179">If you are outside the United States, your numbers already have an emergency address, but you can change it now.</span></span> <span data-ttu-id="0851b-180">請參閱[指派或變更使用者的緊急位址](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="0851b-180">See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user).</span></span> 
  
5. <span data-ttu-id="0851b-181">指派電話號碼和緊急位址之後, 請選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-181">After you assign both the phone number and emergency address, choose **Save**.</span></span>

### <a name="tell-your-users-about-their-new-phone-numbers"></a><span data-ttu-id="0851b-182">告訴使用者他們的新電話號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-182">Tell your users about their new phone numbers</span></span>


<span data-ttu-id="0851b-183">我們建議您傳送郵件, 或使用您公司的最佳通訊方法, 告訴使用者他們的新電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-183">We recommend sending mail or using your business's preferred communication method to tell the people about their new phone numbers.</span></span>

<span data-ttu-id="0851b-184">以下說明如何在其**商務用 Skype**應用程式中查看電話號碼:</span><span class="sxs-lookup"><span data-stu-id="0851b-184">Here's how they can see that phone number in their **Skype for Business** app:</span></span>

1. <span data-ttu-id="0851b-185">在桌上型電腦上登入商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="0851b-185">Sign in to Skype for Business on your desktop.</span></span>
    
2. <span data-ttu-id="0851b-186">選擇 [**設定** > **工具** > **選項**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-186">Choose **Settings** > **Tools** > **Options**.</span></span> 
    
     ![[工具] 功能表上選項的螢幕擷取畫面](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. <span data-ttu-id="0851b-188">然後選擇 [**電話**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-188">Then choose **Phones**.</span></span> 
    
    ![商務用 Skype 電話選項的螢幕擷取畫面](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
<span data-ttu-id="0851b-190">在**Microsoft 團隊**中, 使用者可以按一下左側導覽中的 [**來電**] 來查看他們的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-190">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation.</span></span> <span data-ttu-id="0851b-191">電話號碼會顯示在撥號鍵台的上方。</span><span class="sxs-lookup"><span data-stu-id="0851b-191">The phone number is shown above the dial pad.</span></span>

![按一下 [通話] 後可用選項的螢幕擷取畫面](media/teams-phone-number.png)

<span data-ttu-id="0851b-193">**如需設定通話方案所涉及之所有步驟的詳細資訊, 請參閱[設定通話方案](set-up-calling-plans.md)。**</span><span class="sxs-lookup"><span data-stu-id="0851b-193">**For more detailed information about all of the steps involved in setting up a Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).**</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="0851b-194">步驟 6: 如果您想要設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="0851b-194">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="0851b-195">有時候貴組織中的人員必須使用電話撥入會議。</span><span class="sxs-lookup"><span data-stu-id="0851b-195">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="0851b-196">商務用 Skype 和 Microsoft 團隊包括音訊會議功能, 只適用于這種情況!</span><span class="sxs-lookup"><span data-stu-id="0851b-196">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="0851b-197">使用者可以使用電話撥入商務用 Skype 或 Microsoft 團隊會議, 而不是在行動裝置或電腦上使用商務用 Skype 或 Microsoft 團隊 app。</span><span class="sxs-lookup"><span data-stu-id="0851b-197">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span>

<span data-ttu-id="0851b-198">您只需要為規劃排程或領導會議的人員設定音訊會議。</span><span class="sxs-lookup"><span data-stu-id="0851b-198">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="0851b-199">在撥入的會議出席者不需要獲指派任何授權或其他設定。</span><span class="sxs-lookup"><span data-stu-id="0851b-199">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="0851b-200">如需音訊會議的常見問題, 請參閱[音訊會議常見問題](audio-conferencing-common-questions.md)。</span><span class="sxs-lookup"><span data-stu-id="0851b-200">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
    
1. <span data-ttu-id="0851b-201">如果您購買的是 [**音訊會議**附加元件授權] 和 [通訊點數] 授權, 也請指派它們。</span><span class="sxs-lookup"><span data-stu-id="0851b-201">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="0851b-202">如需相關指示, 請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="0851b-202">For instructions, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

    <span data-ttu-id="0851b-203">決定您的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="0851b-203">Decide on your audio conferencing provider.</span></span> <span data-ttu-id="0851b-204">音訊會議提供者提供音訊會議橋。</span><span class="sxs-lookup"><span data-stu-id="0851b-204">An audio conferencing provider supplies an audio conferencing bridge.</span></span> <span data-ttu-id="0851b-205">[會議橋接] 會設定會議的撥入電話號碼、Pin 及會議 Id。</span><span class="sxs-lookup"><span data-stu-id="0851b-205">The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings.</span></span> <span data-ttu-id="0851b-206">決定要使用的是 Microsoft 或協力廠商音訊會議提供者:</span><span class="sxs-lookup"><span data-stu-id="0851b-206">Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>

    > [!NOTE]
    > <span data-ttu-id="0851b-207">Microsoft 團隊使用者無法使用者使用協力廠商音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="0851b-207">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span>

    - <span data-ttu-id="0851b-208">**Microsoft 作為音訊會議提供者**: 如果您想要最簡單的音訊會議方案, 請選擇 [Microsoft 作為您的音訊會議提供者]。</span><span class="sxs-lookup"><span data-stu-id="0851b-208">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
    - <span data-ttu-id="0851b-209">**協力廠商是您的音訊會議提供者**: 如果您所在的國家/地區無法使用 Office 365 中的音訊會議, 則服務品質不會因位置而無法正常工作, 或者您有現有的合同, 請選擇協力廠商音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="0851b-209">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider.</span></span> <span data-ttu-id="0851b-210">若要尋找提供者, 請移至[Microsoft 定點](http://go.microsoft.com/fwlink/?LinkId=797530)。</span><span class="sxs-lookup"><span data-stu-id="0851b-210">To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
 
2. <span data-ttu-id="0851b-211">將音訊會議提供者指派給領導或排程會議的人員。</span><span class="sxs-lookup"><span data-stu-id="0851b-211">Assign the audio conferencing provider to people who lead or schedule meetings.</span></span> <span data-ttu-id="0851b-212">請參閱[將 Microsoft 指派為音訊會議提供者](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="0851b-212">See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

3. <span data-ttu-id="0851b-213">設定會議邀請。</span><span class="sxs-lookup"><span data-stu-id="0851b-213">Set up meeting invitations.</span></span> <span data-ttu-id="0851b-214">下列步驟是選擇性的, 但許多管理員都要執行這些步驟:</span><span class="sxs-lookup"><span data-stu-id="0851b-214">The following steps are optional, but a lot of admins like to do them:</span></span> 
  
   1. <span data-ttu-id="0851b-215">[在商務用 Skype 中自訂會議邀請](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。</span><span class="sxs-lookup"><span data-stu-id="0851b-215">[Customize meeting invitations in Skype for Business](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations).</span></span> <span data-ttu-id="0851b-216">為使用者設定的撥入號碼會自動新增至傳送給出席者的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="0851b-216">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="0851b-217">不過, 您可以新增自己的說明與法律連結、文字訊息及小型公司圖形。</span><span class="sxs-lookup"><span data-stu-id="0851b-217">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
   2. <span data-ttu-id="0851b-218">針對[商務用 Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)或[Microsoft 團隊](set-the-phone-numbers-included-on-invites-in-teams.md)中的邀請所包含的會議召集人, 設定音訊會議電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-218">Set the Audio Conferencing phone numbers for meeting organizers that are included on invites [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) or [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span> <span data-ttu-id="0851b-219">這是將顯示在使用者排程之會議中的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-219">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
   3. <span data-ttu-id="0851b-220">[在商務用 Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing)或[Microsoft 團隊](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中設定音訊會議的自動語音應答語言, 當電話撥入音訊會議電話號碼時, 音訊會議自動語音應答會用來向來電者。</span><span class="sxs-lookup"><span data-stu-id="0851b-220">Set auto attendant languages for Audio Conferencing [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) or [in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="0851b-221">此步驟僅適用于使用 Microsoft 做為音訊提供者的情況。</span><span class="sxs-lookup"><span data-stu-id="0851b-221">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
   4. <span data-ttu-id="0851b-222">[在 Microsoft 團隊中](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)設定音訊會議會議的 PIN 長度。</span><span class="sxs-lookup"><span data-stu-id="0851b-222">Set the length of the PIN for Audio Conferencing meetings [in Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="0851b-223">使用中國由世紀運營之 Office 365 的客戶尚不提供此功能。</span><span class="sxs-lookup"><span data-stu-id="0851b-223">This feature is not yet available to customers using Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="0851b-224">若要深入瞭解, 請參閱[瞭解由世紀運營的 Office 365](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)。</span><span class="sxs-lookup"><span data-stu-id="0851b-224">To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span>

<span data-ttu-id="0851b-225">**如需音訊會議的詳細資訊, 請參閱[設定 Microsoft 團隊的音訊會議](set-up-audio-conferencing-in-teams.md)。**</span><span class="sxs-lookup"><span data-stu-id="0851b-225">**For more information about Audio Conferencing, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).**</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="0851b-226">步驟 7: 如果您想要設定雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="0851b-226">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="0851b-227">雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能, 以及在通話時搜尋下一個可用的呼叫代理程式來處理通話的功能在暫停時聆聽音樂。</span><span class="sxs-lookup"><span data-stu-id="0851b-227">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="0851b-228">您可以為組織建立單一或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="0851b-228">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="0851b-229">您必須先取得或轉讓現有的付費或免付費服務號碼, 才能建立及設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="0851b-229">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="0851b-230">當您收到付費或免付費服務電話號碼之後, 就會顯示在商務用**Skype 系統管理中心** > **的語音** > **電話號碼**中, 而且列出的**數位類型**將會列為**服務-免付費電話**.</span><span class="sxs-lookup"><span data-stu-id="0851b-230">After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="0851b-231">若要取得您的服務號碼, 請參閱[取得商務用 Skype 和 Microsoft 團隊的服務電話號碼](/microsoftteams/getting-service-phone-numbers), 或者, 如果您想要轉移與現有的服務號碼, 請參閱[將電話號碼轉接至 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0851b-231">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/microsoftteams/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0851b-232">如果您在美國以外, 您就無法使用商務用 Skype 系統管理中心來取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-232">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers.</span></span> <span data-ttu-id="0851b-233">移至 [[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)], 瞭解如何從美國以外的地區進行。</span><span class="sxs-lookup"><span data-stu-id="0851b-233">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="0851b-234">若要建立新的通話佇列, 請**在商務用 Skype 系統管理中心**中, 按一下 [**呼叫路由** > **呼叫佇列**], 按一下 [**新增**], 然後依照[建立雲端通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue)的**步驟 3**中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="0851b-234">To create a new call queue, in the **Skype for Business admin center**, click **Call routing** > **Call queues**, click **Add new**, and then follow the instructions in **Step 3** of  [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).</span></span>

<span data-ttu-id="0851b-235">**如需通話佇列的詳細資訊, 請參閱[建立雲端通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。**</span><span class="sxs-lookup"><span data-stu-id="0851b-235">**For more details about call queues, see [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="0851b-236">步驟 8: 如果您想要設定雲端自動助理</span><span class="sxs-lookup"><span data-stu-id="0851b-236">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="0851b-237">自動語音應答讓撥入您組織的人員, 並流覽功能表系統, 以取得正確的部門、呼叫佇列、人員或接線員。</span><span class="sxs-lookup"><span data-stu-id="0851b-237">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="0851b-238">您可以使用商務用 Skype 系統管理中心, 為您的組織建立自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="0851b-238">You can create an auto attendant for your organization by using the Skype for Business admin center.</span></span>

<span data-ttu-id="0851b-239">若要建立新的自動語音應答, 請在商務用 Skype 系統管理中心中, 按一下 [**呼叫路由** > **自動**語音應答], 按一下 [**新增**], 然後依照建立雲端自動語音應答**之步驟 2**中的每個頁面上的指示進行。 [](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="0851b-239">To create a new auto attendant, in the Skype for Business admin center, click **Call routing** > **Auto attendants**, click **Add new**, and then follow the instructions for each page in **Step 2** of [Create a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).</span></span>


<span data-ttu-id="0851b-240">**如需雲端自動語音應答的詳細資訊, 請參閱[設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)語音應答。**</span><span class="sxs-lookup"><span data-stu-id="0851b-240">**For more details about Cloud auto attendants, see [Set up a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).**</span></span>

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="0851b-241">步驟 9: 指派服務電話號碼 (音訊會議、通話佇列、自動語音應答)</span><span class="sxs-lookup"><span data-stu-id="0851b-241">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="0851b-242">從**上述步驟 4**獲得您的服務號碼之後, 您必須將他們指派給您想要的每一種類型的服務。</span><span class="sxs-lookup"><span data-stu-id="0851b-242">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="0851b-243">例如, 如果您需要專用的服務電話號碼 (付費或免費付費), 您必須將號碼指派給會議橋。</span><span class="sxs-lookup"><span data-stu-id="0851b-243">For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="0851b-244">在音訊會議中, 您可以移至**Microsoft 365 系統管理中心** > \*\*\*\* > 的 [**商務** > 用 Skype**音訊會議**], 將專用號碼指派給會議橋接器, 然後按一下您也可以在 [[音訊會議橋] 中查看 [變更付費或免付費號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)]。</span><span class="sxs-lookup"><span data-stu-id="0851b-244">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** and click on the conference bridge or by seeing  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="0851b-245">針對自動語音應答, 您可以移至**Microsoft 365 系統管理中心** > \*\*\*\* > , 透過**商務** > 用 Skype**呼叫路由** > 自動語音來將專用號碼指派給自動語音應答\*\*\*\* 然後按一下自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="0851b-245">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and click on the auto attendant.</span></span> <span data-ttu-id="0851b-246">在 [**一般**] 頁面上, 您已有的服務號碼會列在 [**電話號碼**] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="0851b-246">On the **General** page the service number you already have will be listed in the **Phone number** drop down.</span></span> <span data-ttu-id="0851b-247">如需詳細資訊, 請參閱[設定雲端自動](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)語音應答。</span><span class="sxs-lookup"><span data-stu-id="0851b-247">For details, see [Set up a Cloud Auto Attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).</span></span>

- <span data-ttu-id="0851b-248">在通話佇列中, 您可以移至**Microsoft 365 系統管理中心** > \*\*\*\* > 的 [**商務** > 用 Skype 呼叫**路由** > **呼叫] 佇列**, 將專用號碼指派給呼叫佇列, 然後按一下在通話佇列中。</span><span class="sxs-lookup"><span data-stu-id="0851b-248">For Call Queues, you can assign a dedicated number to a call queue by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue.</span></span> <span data-ttu-id="0851b-249">在 [**一般**] 頁面上, 您已有的服務號碼會列在 [**電話號碼**] 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="0851b-249">On the **General** page the service number you already have will be listed in the **Phone number** drop down.</span></span> <span data-ttu-id="0851b-250">如需詳細資訊, 請參閱[建立雲端通話佇列](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)。</span><span class="sxs-lookup"><span data-stu-id="0851b-250">For details, see [Create a Cloud call queue](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue).</span></span>

<span data-ttu-id="0851b-251">**如需取得新服務號碼和移植現有服務號碼的詳細資訊, 請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。**</span><span class="sxs-lookup"><span data-stu-id="0851b-251">**For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).**</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="0851b-252">步驟 10: 為您的組織設定通訊點數</span><span class="sxs-lookup"><span data-stu-id="0851b-252">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="0851b-253">如果您想要在商務用 Skype 和 Microsoft 團隊中使用免付費電話號碼, 就必須設定通訊點數。</span><span class="sxs-lookup"><span data-stu-id="0851b-253">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="0851b-254">此外, 建議您針對您的通話方案 (國內或國際) 及需要撥出至**任何目的地**的音訊會議使用者設定通訊點數。</span><span class="sxs-lookup"><span data-stu-id="0851b-254">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="0851b-255">包含許多國家/地區, 但某些目的地可能不會包含在您的通話方案或音訊會議訂閱中。</span><span class="sxs-lookup"><span data-stu-id="0851b-255">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="0851b-256">如果您沒有設定通訊信用帳單, 並將**通訊點數**授權指派給您的使用者, 而您在您的國家/地區的通話方案或音訊會議方案上是您的組織時間, 則這些使用者無法從音訊會議會議撥打或撥出電話。</span><span class="sxs-lookup"><span data-stu-id="0851b-256">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="0851b-257">您可以透過閱讀通訊點數來取得詳細資訊 (包括建議的融資金額)[嗎？](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="0851b-257">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="0851b-258">若要瞭解成本多少, 請[參閱這裡的速度](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。</span><span class="sxs-lookup"><span data-stu-id="0851b-258">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span>

### <a name="to-set-up-communications-credits"></a><span data-ttu-id="0851b-259">設定通訊點數</span><span class="sxs-lookup"><span data-stu-id="0851b-259">To set up Communications Credits</span></span>

1. <span data-ttu-id="0851b-260">使用您的公司或學校帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0851b-260">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="0851b-261">在系統管理中心的左側導覽中, 移至 [**帳單** > **訂閱** > **附加** > 元件**購買附加**元件], 然後選擇 [ \*\* \*\*  > **立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-261">In the left navigation of the admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.</span></span>

3. <span data-ttu-id="0851b-262">在 [**通訊點數**訂閱] 頁面上, 填入您的資訊, 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0851b-262">On the **Communications Credits** subscription page, fill in your information, and then click **Next**.</span></span>

4. <span data-ttu-id="0851b-263">輸入您的付款資訊, 然後按一下 [**下單**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-263">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="0851b-264">如果您是大量授權客戶, 您可以選擇要付款的企業協定號碼。</span><span class="sxs-lookup"><span data-stu-id="0851b-264">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="0851b-265">如果您有多個企業協定編號, 您可以選取要用來進行付款的企業協定。</span><span class="sxs-lookup"><span data-stu-id="0851b-265">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="0851b-266">您也可以指定要與企業協定編號 (如果適用) 關聯的採購訂單編號的機會。</span><span class="sxs-lookup"><span data-stu-id="0851b-266">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="0851b-267">**如需設定通訊點數的詳細資訊, 請參閱為[您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。**</span><span class="sxs-lookup"><span data-stu-id="0851b-267">**For more detailed information about setting up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).**</span></span>
  
### <a name="assign-a-communications-credits-license-to-users"></a><span data-ttu-id="0851b-268">指派通訊點數授權給使用者</span><span class="sxs-lookup"><span data-stu-id="0851b-268">Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="0851b-269">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0851b-269">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0851b-270">在 Microsoft 365 系統管理中心的左導覽中, 移至 [**使用者** > 作用中的**使用者**], 然後從清單中選取一個或多位使用者。</span><span class="sxs-lookup"><span data-stu-id="0851b-270">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>

3. <span data-ttu-id="0851b-271">在 [**產品授權**] 底下的 [動作] 窗格中, 按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-271">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="0851b-272">在 [**產品授權**] 頁面上, 將 [**通訊點數**] 切換至 [**開啟**] 以指派此授權, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0851b-272">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0851b-273">即使您有指派**企業版 E5**授權的使用者, 仍建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="0851b-273">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

<span data-ttu-id="0851b-274">**若要深入瞭解指派通訊點數授權的詳細資訊, 請參閱[為您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。**</span><span class="sxs-lookup"><span data-stu-id="0851b-274">**To learn more about assigning Communications Credits licenses, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).**</span></span>

## <a name="related-topics"></a><span data-ttu-id="0851b-275">相關主題</span><span class="sxs-lookup"><span data-stu-id="0851b-275">Related topics</span></span>
[<span data-ttu-id="0851b-276">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="0851b-276">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="0851b-277">取得商務用 Skype 和 Microsoft 團隊的服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="0851b-277">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="0851b-278">適用于音訊會議與通話方案的國家和地區可用性</span><span class="sxs-lookup"><span data-stu-id="0851b-278">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
