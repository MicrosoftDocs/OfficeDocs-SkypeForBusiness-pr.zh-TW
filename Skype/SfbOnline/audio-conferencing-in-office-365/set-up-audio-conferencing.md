---
title: 設定商務用 Skype 的音訊會議
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '瞭解如何為您企業中需要使用手機加入電話會議的人員設定撥入或音訊會議。 '
ms.openlocfilehash: a36482dc6c58275491c65ac518e98cdc0ac0b787
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "37642553"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="46bb3-103">設定商務用 Skype 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="46bb3-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="46bb3-104">有時候貴組織中的人員必須使用電話撥入會議。</span><span class="sxs-lookup"><span data-stu-id="46bb3-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="46bb3-105">商務用 Skype 包括音訊會議功能，只適用于這種情況！</span><span class="sxs-lookup"><span data-stu-id="46bb3-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="46bb3-106">使用者可以使用電話撥入商務用 Skype 會議，而不是在行動裝置或電腦上使用商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="46bb3-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="46bb3-107">您只需要為規劃排程或領導會議的人員設定音訊會議。</span><span class="sxs-lookup"><span data-stu-id="46bb3-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="46bb3-108">在撥入的會議出席者不需要獲指派任何授權或其他設定。</span><span class="sxs-lookup"><span data-stu-id="46bb3-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="46bb3-109">如需音訊會議的常見問題，請參閱[音訊會議常見問題](/MicrosoftTeams/audio-conferencing-common-questions)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="46bb3-110">步驟1：瞭解您的國家/地區是否提供音訊會議</span><span class="sxs-lookup"><span data-stu-id="46bb3-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="46bb3-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="46bb3-111"></span></span>

<span data-ttu-id="46bb3-112">移至[適用于音訊會議與通話方案的國家和地區可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)，然後選取您的國家或地區以取得音訊會議的可用性資訊，以及電話系統、通話方案、免付費電話和免付費電話的相關資訊。號碼和通訊點數。</span><span class="sxs-lookup"><span data-stu-id="46bb3-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="46bb3-113">步驟2：取得並指派授權</span><span class="sxs-lookup"><span data-stu-id="46bb3-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="46bb3-114">對於音訊會議，您需要每個將會設定撥入會議的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="46bb3-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="46bb3-115">若要瞭解您需要購買哪些授權才能進行音訊會議，以及需要多少費用，請參閱[商務用 Skype 附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="46bb3-116">音訊會議包含在 Office 365 企業版 E5 授權和附加元件中。</span><span class="sxs-lookup"><span data-stu-id="46bb3-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="46bb3-117">購買音訊會議授權之後，您必須將他們指派給組織中將要排程或領導會議的人員。</span><span class="sxs-lookup"><span data-stu-id="46bb3-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="46bb3-118">請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，並將您購買給組織中將要排程或領導會議的人員。</span><span class="sxs-lookup"><span data-stu-id="46bb3-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="46bb3-119">我們也建議您在上一個步驟中指派通訊信用權（不需要支付任何費用）給您指派授權的人員。</span><span class="sxs-lookup"><span data-stu-id="46bb3-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="46bb3-120">若要瞭解如何設定通訊點數，請參閱為[您的組織設定通訊點數](/microsoftteams/set-up-communications-credits-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="46bb3-121">您也可以設定[每分鐘付費的音訊會議](/microsoftteams/audio-conferencing-pay-per-minute)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="46bb3-122">步驟3：取得會議橋的服務號碼</span><span class="sxs-lookup"><span data-stu-id="46bb3-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="46bb3-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="46bb3-123"></span></span>

<span data-ttu-id="46bb3-124">對於音訊會議，您無法將電話號碼用於使用者;您將需要取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="46bb3-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="46bb3-125">您可以取得會議橋的付費或免費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="46bb3-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="46bb3-126">有三種方法可以取得付費和免付費服務號碼：</span><span class="sxs-lookup"><span data-stu-id="46bb3-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="46bb3-127">**使用商務用 Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="46bb3-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="46bb3-128">在某些國家/地區，您可以使用商務用 Skype 系統管理中心取得會議橋的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="46bb3-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="46bb3-129">請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="46bb3-130">**移植現有的服務號碼**。</span><span class="sxs-lookup"><span data-stu-id="46bb3-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="46bb3-131">從目前的服務提供者或電話轉接至 Office 365，將現有的號碼移植或轉移至 Office。</span><span class="sxs-lookup"><span data-stu-id="46bb3-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="46bb3-132">您可以參閱[將電話號碼轉接至 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365)或[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)，以取得詳細資訊，協助您執行此動作。</span><span class="sxs-lookup"><span data-stu-id="46bb3-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="46bb3-133">**針對新號碼使用要求表單**。</span><span class="sxs-lookup"><span data-stu-id="46bb3-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="46bb3-134">有時候（視您的國家/地區而定）您無法使用商務用 Skype 系統管理中心來取得新的服務號碼，或者您需要特定的電話號碼或區功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="46bb3-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="46bb3-135">如果是這樣，您將需要下載表單並將它傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="46bb3-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="46bb3-136">如需詳細資訊，請參閱[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="46bb3-137">步驟4：將服務號碼指派給會議橋</span><span class="sxs-lookup"><span data-stu-id="46bb3-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="46bb3-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="46bb3-138"></span></span>

<span data-ttu-id="46bb3-139">當您為您的會議橋接器取得付費和/或免付費電話號碼之後，您必須指派編號，才能在會議邀請中使用。</span><span class="sxs-lookup"><span data-stu-id="46bb3-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="46bb3-140">若要將新的電話號碼指派給您的音訊會議橋接器：</span><span class="sxs-lookup"><span data-stu-id="46bb3-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="46bb3-141">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示：</span><span class="sxs-lookup"><span data-stu-id="46bb3-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="46bb3-142">移至**Microsoft 365 管理中心** > **管理中心** > **小組** > **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="46bb3-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="46bb3-143">選取 [**語音** > **電話號碼**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="46bb3-144">選取電話號碼，然後按一下 [**指派**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="46bb3-145">如需詳細資訊，請參閱[在音訊會議橋中變更電話號碼](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="46bb3-146">步驟5：設定會議橋接器的預設及備用語言</span><span class="sxs-lookup"><span data-stu-id="46bb3-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="46bb3-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="46bb3-147"></span></span>

<span data-ttu-id="46bb3-148">接下來，您想要[針對音訊會議設定自動助理語言](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)，讓會議自動語音應答在撥入音訊會議的電話號碼時，用來向來電者。</span><span class="sxs-lookup"><span data-stu-id="46bb3-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="46bb3-149">![](../images/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 microsoft 團隊標誌的圖示：</span><span class="sxs-lookup"><span data-stu-id="46bb3-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="46bb3-150">從 [儀表板] 移至 [**會議** > **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="46bb3-151">選取 [會議橋接電話號碼]，按一下 [**編輯**]，然後選擇預設語言。</span><span class="sxs-lookup"><span data-stu-id="46bb3-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="46bb3-152">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示：</span><span class="sxs-lookup"><span data-stu-id="46bb3-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="46bb3-153">移至 [系統管理中心] > 系統**管理中心** > **小組** > 的**舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="46bb3-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="46bb3-154">選取 [**音訊會議** > **Microsoft 橋接器**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="46bb3-155">選取 [會議橋接電話號碼]，選取 [**設定語言**]，然後選擇預設語言。</span><span class="sxs-lookup"><span data-stu-id="46bb3-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="46bb3-156">步驟6：設定您的會議橋設定</span><span class="sxs-lookup"><span data-stu-id="46bb3-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="46bb3-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="46bb3-157"></span></span>
    
<span data-ttu-id="46bb3-158">在設定您的會議橋接器之後，請確認您要使用的預設設定（例如 [進入/結束通知] 和 [PIN 長度]）。如果不是，您可以變更它們。</span><span class="sxs-lookup"><span data-stu-id="46bb3-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="46bb3-159">![](../images/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 microsoft 團隊標誌的圖示：</span><span class="sxs-lookup"><span data-stu-id="46bb3-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="46bb3-160">從 [儀表板] 移至 [**會議** > **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="46bb3-161">選取 [**橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-161">Select **Bridge settings**.</span></span> <span data-ttu-id="46bb3-162">這將會開啟 [**橋設定**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="46bb3-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="46bb3-163">如需詳細資訊，請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="46bb3-164">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示：</span><span class="sxs-lookup"><span data-stu-id="46bb3-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="46bb3-165">移至**Microsoft 365 管理中心** > **管理中心** > **小組** > **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="46bb3-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="46bb3-166">選取 [**音訊會議** > ] [**Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="46bb3-167">這將會開啟 [ **Microsoft 橋接器設定**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="46bb3-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="46bb3-168">如需詳細資訊，請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="46bb3-169">步驟7：為領導會議的使用者指派撥入電話號碼</span><span class="sxs-lookup"><span data-stu-id="46bb3-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="46bb3-170">建立音訊會議橋接器之後，您必須為使用者設定付費和免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="46bb3-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="46bb3-171">您必須針對組織中負責領導或排程會議的所有人員執行此動作。</span><span class="sxs-lookup"><span data-stu-id="46bb3-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="46bb3-172">![](../images/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 microsoft 團隊標誌的圖示：</span><span class="sxs-lookup"><span data-stu-id="46bb3-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="46bb3-173">從儀表板中，按一下 [**使用者**]，從清單中選取使用者，然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="46bb3-174">選取 [**音訊會議**] 旁的 [**編輯**]，然後在 [**音訊會議**] 窗格中，選擇 [**付費電話號碼**] 和 [**免付費電話**號碼] 清單中的數位。</span><span class="sxs-lookup"><span data-stu-id="46bb3-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="46bb3-175">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示：</span><span class="sxs-lookup"><span data-stu-id="46bb3-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="46bb3-176">移至**Microsoft 365 系統管理中心** > **小組** > **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="46bb3-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="46bb3-177">選取 [**音訊會議** > **使用者**]，然後從清單中選取使用者，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="46bb3-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="46bb3-178">如果您需要更多詳細資料，請參閱[將 Microsoft 指派為音訊會議提供者](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="46bb3-179">步驟8：設定會議邀請（選用）</span><span class="sxs-lookup"><span data-stu-id="46bb3-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="46bb3-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="46bb3-180"></span></span>
 
<span data-ttu-id="46bb3-181">為使用者設定的撥入號碼會自動新增至傳送給會議出席者的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="46bb3-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="46bb3-182">不過，如果您想要的話，您也可以新增自己的說明與法律連結、文字訊息及小型公司圖形。</span><span class="sxs-lookup"><span data-stu-id="46bb3-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="46bb3-183">請參閱[自訂會議邀請](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="46bb3-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="46bb3-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="46bb3-184">Related topics</span></span>

[<span data-ttu-id="46bb3-185">音訊會議常見問題</span><span class="sxs-lookup"><span data-stu-id="46bb3-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="46bb3-186">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="46bb3-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="46bb3-187">音訊會議的電話號碼</span><span class="sxs-lookup"><span data-stu-id="46bb3-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="46bb3-188">設定線上會議和電話會議的選項</span><span class="sxs-lookup"><span data-stu-id="46bb3-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
