---
title: 取得服務電話號碼
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 瞭解如何取得新電話號碼，以及移轉或移轉音訊會議、自動語音電話和通話佇列的現有號碼， (電話號碼) 電話號碼Teams。
ms.openlocfilehash: 72436591411070ed7ffc67aab5d8d4470f39521d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092231"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="af5f8-103">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="af5f8-103">Getting service phone numbers</span></span>

<span data-ttu-id="af5f8-104">除了為使用者[](./getting-phone-numbers-for-your-users.md)取得電話號碼之外，您還可以取得電話或免付費電話號碼等服務，例如會議橋接器) 的音訊會議 (、自動語音機和通話佇列 (也稱為服務號碼) 。</span><span class="sxs-lookup"><span data-stu-id="af5f8-104">In addition to [getting phone numbers for your users](./getting-phone-numbers-for-your-users.md), you can get toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="af5f8-105">服務電話號碼的並行通話容量高於使用者或訂閱者電話號碼。</span><span class="sxs-lookup"><span data-stu-id="af5f8-105">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="af5f8-106">例如，服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。</span><span class="sxs-lookup"><span data-stu-id="af5f8-106">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af5f8-107">您首先必須設定通訊信用額度，才能取得免付費號碼。</span><span class="sxs-lookup"><span data-stu-id="af5f8-107">You have to first set up Communications Credits before you can get toll-free numbers.</span></span> <span data-ttu-id="af5f8-108">若要深入瞭解，請參閱 [為貴組織設定通訊信用額度](./set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="af5f8-108">To learn more, see [Set up Communications Credits for your organization](./set-up-communications-credits-for-your-organization.md).</span></span>
  
<span data-ttu-id="af5f8-109">取得服務號碼的方法有三種：</span><span class="sxs-lookup"><span data-stu-id="af5f8-109">There are three ways to get service numbers:</span></span>
  
- <span data-ttu-id="af5f8-110">**使用 Microsoft Teams系統管理中心。**</span><span class="sxs-lookup"><span data-stu-id="af5f8-110">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="af5f8-111">在某些國家和地區，您可以使用系統管理中心取得Microsoft Teams號碼。</span><span class="sxs-lookup"><span data-stu-id="af5f8-111">For some countries and regions, you can get service numbers using the Microsoft Teams admin center.</span></span> <span data-ttu-id="af5f8-112">請參閱 [取得新的服務號碼](#get-new-service-numbers)。</span><span class="sxs-lookup"><span data-stu-id="af5f8-112">See [Get new service numbers](#get-new-service-numbers).</span></span>

- <span data-ttu-id="af5f8-113">**轉移現有的號碼。**</span><span class="sxs-lookup"><span data-stu-id="af5f8-113">**Port your existing numbers.**</span></span> <span data-ttu-id="af5f8-114">您可以移轉或移轉目前服務提供者或電話電信公司的現有號碼。</span><span class="sxs-lookup"><span data-stu-id="af5f8-114">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="af5f8-115">如需詳細資訊，請參閱[將電話號碼轉接至 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)，協助您完成此作業。</span><span class="sxs-lookup"><span data-stu-id="af5f8-115">See [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="af5f8-116">**使用表單要求新號碼。**</span><span class="sxs-lookup"><span data-stu-id="af5f8-116">**Use a request form for new numbers.**</span></span> <span data-ttu-id="af5f8-117">有時候 (視您的國家/地區或地區) 您將無法使用 Microsoft Teams 系統管理中心取得新的電話號碼，或者您需要特定的電話號碼或區碼。</span><span class="sxs-lookup"><span data-stu-id="af5f8-117">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams admin center, or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="af5f8-118">如果是這樣，您必須下載表單並傳送回給我們。</span><span class="sxs-lookup"><span data-stu-id="af5f8-118">If so, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="af5f8-119">如需詳細資訊，請參閱[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="af5f8-119">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af5f8-120">您需要服務號碼，才能取得特定號碼的較高同時通話容量。</span><span class="sxs-lookup"><span data-stu-id="af5f8-120">Service numbers are needed so you can get a higher concurrent call capacity for a specific number.</span></span> <span data-ttu-id="af5f8-121">當您將號碼轉接給我們時，您可以連上 [PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) 服務台，確認您轉接的服務號碼同時有較高的通話容量。</span><span class="sxs-lookup"><span data-stu-id="af5f8-121">When you're transferring the number over to us, you can [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to make sure the service number you're transferring has a high concurrent call capacity.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="af5f8-122">取得新的服務編號</span><span class="sxs-lookup"><span data-stu-id="af5f8-122">Get new service numbers</span></span>

<span data-ttu-id="af5f8-123">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="af5f8-123">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="af5f8-124">在左側流覽中，前往 **[語音** 電話  >  **數位**，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="af5f8-124">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
2. <span data-ttu-id="af5f8-125">輸入訂單名稱並新增描述。</span><span class="sxs-lookup"><span data-stu-id="af5f8-125">Enter a name for the order and add a description.</span></span>
3. <span data-ttu-id="af5f8-126">在位置和數量頁面上，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="af5f8-126">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="af5f8-127">在 **國家/地區** 下，選取某個國家/地區。</span><span class="sxs-lookup"><span data-stu-id="af5f8-127">Under **Country or region**, select a country or region.</span></span>
    1. <span data-ttu-id="af5f8-128">在 **數位類型** 下，選取您想要的服務號碼類型。</span><span class="sxs-lookup"><span data-stu-id="af5f8-128">Under **Number type**, select the type of service number that you want.</span></span>
    1. <span data-ttu-id="af5f8-129">在 **位置下**，選取位置。</span><span class="sxs-lookup"><span data-stu-id="af5f8-129">Under **Location**, select a location.</span></span> <span data-ttu-id="af5f8-130">如果您需要建立新位置，請按一下 [ **新增位置**。</span><span class="sxs-lookup"><span data-stu-id="af5f8-130">If you need to create a new location, click **Add a location**.</span></span>
    1. <span data-ttu-id="af5f8-131">在 **區碼下**，選取區碼。</span><span class="sxs-lookup"><span data-stu-id="af5f8-131">Under **Area code**, select an area code.</span></span> 
    2. <span data-ttu-id="af5f8-132">在 **[數量**」 下，輸入貴組織想要的數位數，然後按一下 **[下** 一步> 以選取您的數位。</span><span class="sxs-lookup"><span data-stu-id="af5f8-132">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
4. <span data-ttu-id="af5f8-133">選取您想要的數位。</span><span class="sxs-lookup"><span data-stu-id="af5f8-133">Select the numbers you want.</span></span> <span data-ttu-id="af5f8-134">您還有 10 分鐘的時間來選取電話號碼並下訂單。</span><span class="sxs-lookup"><span data-stu-id="af5f8-134">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="af5f8-135">如果您花的時間超過 10 分鐘，電話號碼會回到號碼庫。</span><span class="sxs-lookup"><span data-stu-id="af5f8-135">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
5. <span data-ttu-id="af5f8-136">當您準備好要下單時，請按一下 [ **下單>**。</span><span class="sxs-lookup"><span data-stu-id="af5f8-136">When you're ready to place your order, click **Place order**.</span></span>

## <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="af5f8-137">移轉或移轉現有的服務號碼</span><span class="sxs-lookup"><span data-stu-id="af5f8-137">Port or transfer existing service numbers</span></span>

<span data-ttu-id="af5f8-138">若要將電話號碼從目前的服務提供者或電信Teams傳輸至Teams，您可以使用系統管理中心中的移轉Microsoft Teams精靈。</span><span class="sxs-lookup"><span data-stu-id="af5f8-138">To transfer your phone numbers from your current service provider or carrier to Teams, you can use the porting wizard in the Microsoft Teams admin center.</span></span> <span data-ttu-id="af5f8-139">請遵循將電話號碼[移轉至Teams。](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="af5f8-139">Follow the steps in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

<span data-ttu-id="af5f8-140">如果您的國家/地區未列在移植精靈中，您可以手動提交埠訂單，或[](phone-number-calling-plans/manually-submit-port-order.md)前往管理貴組織的電話號碼、選取您的國家[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)/地區，然後下載授權書 (LOA) 。</span><span class="sxs-lookup"><span data-stu-id="af5f8-140">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), select your country or region, and then download a Letter of Authorization (LOA).</span></span> <span data-ttu-id="af5f8-141">您必須針對每種服務編號類型提交個別的移轉訂單 (例如，使用 LOA 傳輸的付費與免付費) 。</span><span class="sxs-lookup"><span data-stu-id="af5f8-141">You'll have to submit separate port orders for each type of service number (for example, toll vs. toll-free) that you'll be transferring by using an LOA.</span></span> <span data-ttu-id="af5f8-142">在 LOA 中，您必須選取正確的服務編號類型。</span><span class="sxs-lookup"><span data-stu-id="af5f8-142">In the LOA, you must select the correct type of service number.</span></span> <span data-ttu-id="af5f8-143">請確定您指定要傳輸的服務號碼 (而非使用者或訂閱者號碼) ，或並行通話容量可能不足以處理通話量。</span><span class="sxs-lookup"><span data-stu-id="af5f8-143">Make sure you specify that you're transferring a service number (and not a user or subscriber number), or the concurrent calling capacity may not be enough to handle call volumes.</span></span>  

> [!NOTE]
> <span data-ttu-id="af5f8-144">如果您需要取得更多電話號碼，請 [連上 PSTN 服務台](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="af5f8-144">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="af5f8-145">查看貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="af5f8-145">View the phone numbers for your organization</span></span>

<span data-ttu-id="af5f8-146">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="af5f8-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span> 

<span data-ttu-id="af5f8-147">在左側流覽中，前往語音電話，以查看貴組織的數位，包括位置、  >  號碼類型和狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="af5f8-147">In the left navigation, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>

## <a name="assign-service-phone-numbers"></a><span data-ttu-id="af5f8-148">指派服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="af5f8-148">Assign service phone numbers</span></span>

<span data-ttu-id="af5f8-149">取得服務號碼後，將每個號碼指派給音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="af5f8-149">After you get your service numbers, assign each number to an Audio Conferencing bridge.</span></span> <span data-ttu-id="af5f8-150">請參閱 [變更音訊會議](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)橋接器上的付費或免付費號碼。</span><span class="sxs-lookup"><span data-stu-id="af5f8-150">See [Change the toll or toll free numbers on your Audio Conferencing bridge](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="af5f8-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="af5f8-151">Related topics</span></span>

[<span data-ttu-id="af5f8-152">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="af5f8-152">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="af5f8-153">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="af5f8-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="af5f8-154">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="af5f8-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="af5f8-155">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="af5f8-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="af5f8-156">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="af5f8-156">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)