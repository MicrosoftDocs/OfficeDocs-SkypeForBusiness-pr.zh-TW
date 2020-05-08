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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: '瞭解如何為企業中需要使用電話加入電話會議的人員設定撥入或音訊會議。 '
ms.openlocfilehash: bfd9c9ec31736b0f7fc16f15a907c87406113871
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163942"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="0c5e5-103">設定商務用 Skype 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="0c5e5-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="0c5e5-104">貴組織內的人員有時會需要透過電話來加入會議。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="0c5e5-105">商務用 Skype 包括音訊會議功能，只適用于這種情況！</span><span class="sxs-lookup"><span data-stu-id="0c5e5-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="0c5e5-106">使用者可以使用電話撥入商務用 Skype 會議，而不是在行動裝置或電腦上使用商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="0c5e5-107">您只需要為打算排程或主持會議的人員設定音訊會議即可。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="0c5e5-108">撥入的會議出席者不需獲得任何指派的授權或進行其他設定。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="0c5e5-109">如需有關音訊會議的常見問題，請參閱[音訊會議常見問題](/MicrosoftTeams/audio-conferencing-common-questions)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="0c5e5-110">步驟 1：了解您的國家/地區是否提供音訊會議</span><span class="sxs-lookup"><span data-stu-id="0c5e5-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="0c5e5-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0c5e5-111"><a name="__top"> </a></span></span>

<span data-ttu-id="0c5e5-112">移至[音訊會議與通話方案的適用國家和地區](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)，選取您的國家或地區，以取得有關音訊會議的提供資訊，以及電話系統、通話方案、付費和免付費電話號碼、通訊點數等資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="0c5e5-113">步驟 2：取得和指派授權</span><span class="sxs-lookup"><span data-stu-id="0c5e5-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="0c5e5-114">若要使用音訊會議，您需要設定撥入會議每位使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="0c5e5-115">若要瞭解您需要購買哪些授權才能進行音訊會議，以及需要多少費用，請參閱[商務用 Skype 附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="0c5e5-116">音訊會議包含在 Office 365 企業版 E5 授權中的附加元件。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="0c5e5-117">購買音訊會議授權之後，您必須將授權指派給組織中要排程或主持會議的人員。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="0c5e5-118">請參閱[指派或移除商務用 Microsoft 365 應用程式的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，以供您購買給組織中要排程或領導會議的人員。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-118">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="0c5e5-119">我們也建議您將通訊點數授權 (不需付費) 指派給您在在上一個步驟中指派授權的人員。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="0c5e5-120">若要了解如何設定通訊點數，請參閱[設定貴組織的通訊點數](/microsoftteams/set-up-communications-credits-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0c5e5-121">您也可以設定[按分鐘計費的音訊會議](/microsoftteams/audio-conferencing-pay-per-minute)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="0c5e5-122">步驟 3：取得會議橋接器的服務號碼</span><span class="sxs-lookup"><span data-stu-id="0c5e5-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="0c5e5-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0c5e5-123"><a name="__top"> </a></span></span>

<span data-ttu-id="0c5e5-124">音訊會議不能使用一般的使用者電話號碼，您必須取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="0c5e5-125">您可以為您的會議橋接器取得付費或免費的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="0c5e5-126">有三種方法可以取得付費和免付費服務號碼：</span><span class="sxs-lookup"><span data-stu-id="0c5e5-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="0c5e5-127">**使用商務用 Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="0c5e5-128">在某些國家/地區，您可以使用商務用 Skype 系統管理中心取得會議橋的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="0c5e5-129">請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="0c5e5-130">**轉移現有的服務號碼**。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="0c5e5-131">將目前服務提供者或電話聽筒中的現有號碼移植或轉接至 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0c5e5-132">如需詳細資訊，請參閱[將電話號碼轉移至 Teams ](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)或[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)，協助您完成此作業。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-132">You can see [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="0c5e5-133">**使用表單要求新號碼**。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="0c5e5-134">有時候（視您的國家/地區而定）您無法使用商務用 Skype 系統管理中心來取得新的服務號碼，或者您需要特定的電話號碼或區功能變數代碼。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="0c5e5-135">若是如此，您將需要下載表單並將它傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="0c5e5-136">如需詳細資訊，請參閱[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="0c5e5-137">步驟 4：指派服務號碼給會議橋接器</span><span class="sxs-lookup"><span data-stu-id="0c5e5-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="0c5e5-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0c5e5-138"><a name="__top"> </a></span></span>

<span data-ttu-id="0c5e5-139">當您為您的會議橋接器取得您的免費和/或免付費電話號碼後，必須指派電話號碼，以便在會議邀請中使用。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="0c5e5-140">若要將新的電話號碼指派給您的音訊會議橋接器：</span><span class="sxs-lookup"><span data-stu-id="0c5e5-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="0c5e5-141">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心：**</span><span class="sxs-lookup"><span data-stu-id="0c5e5-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="0c5e5-142">移至 [Microsoft 365 系統管理中心]\*\*\*\*  >  [系統管理中心]\*\*\*\*  >  [Teams]\*\*\*\*  >  [舊版入口網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="0c5e5-143">選取 [語音]\*\*\*\*  >  [電話號碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="0c5e5-144">選取電話號碼，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="0c5e5-145">如需詳細資訊，請參閱[在音訊會議橋中變更電話號碼](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="0c5e5-146">步驟 5：設定會議橋接器的預設和替代語言</span><span class="sxs-lookup"><span data-stu-id="0c5e5-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="0c5e5-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0c5e5-147"><a name="__top"> </a></span></span>

<span data-ttu-id="0c5e5-148">接下來，您想要[針對音訊會議設定自動助理語言](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)，讓會議自動語音應答在撥入音訊會議的電話號碼時，用來向來電者。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="0c5e5-149">![Microsoft Teams 標誌圖示](../images/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="0c5e5-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="0c5e5-150">在儀表板中，移至 [會議]\*\*\*\*  >  [會議橋接器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="0c5e5-151">選取 [會議橋接電話號碼]，按一下 [編輯]\*\*\*\*，然後選擇預設語言。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="0c5e5-152">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示：</span><span class="sxs-lookup"><span data-stu-id="0c5e5-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="0c5e5-153">移至 [系統管理中心] > 系統**管理中心** > **小組** > 的**舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="0c5e5-154">選取 [**音訊會議** > **Microsoft 橋接器**]。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="0c5e5-155">選取 [會議橋接電話號碼]，選取 [**設定語言**]，然後選擇預設語言。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="0c5e5-156">步驟 6：會議橋接器設定</span><span class="sxs-lookup"><span data-stu-id="0c5e5-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="0c5e5-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0c5e5-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="0c5e5-158">設定會議橋接器後，請確認預設設定 (例如，進入/退出通知、PIN 長度) 就是您要使用的設定。如果不是，可以變更。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="0c5e5-159">![Microsoft Teams 標誌圖示](../images/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="0c5e5-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="0c5e5-160">在儀表板中，移至 [會議]\*\*\*\*  >  [會議橋接器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="0c5e5-161">選取 [橋接器設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-161">Select **Bridge settings**.</span></span> <span data-ttu-id="0c5e5-162">會開啟 [橋接器設定]\*\*\*\* 窗格。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="0c5e5-163">如需詳細資訊，請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="0c5e5-164">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心：**</span><span class="sxs-lookup"><span data-stu-id="0c5e5-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="0c5e5-165">移至 [Microsoft 365 系統管理中心]\*\*\*\*  >  [系統管理中心]\*\*\*\*  >  [Teams]\*\*\*\*  >  [舊版入口網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="0c5e5-166">選取 [**音訊會議** > ] [**Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="0c5e5-167">這將會開啟 [ **Microsoft 橋接器設定**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="0c5e5-168">如需詳細資訊，請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="0c5e5-169">步驟 7：為主持會議的使用者指派撥入電話號碼</span><span class="sxs-lookup"><span data-stu-id="0c5e5-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="0c5e5-170">在您建立音訊會議橋接器之後，必須為您的使用者設定付費和免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="0c5e5-171">您必須為貴組織中負責主持或排程會議的所有人員執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="0c5e5-172">![Microsoft Teams 標誌圖示](../images/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="0c5e5-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="0c5e5-173">在儀表板中，按一下 [使用者]\*\*\*\*，從清單中選取使用者，然後選取 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="0c5e5-174">選取 [音訊會議]\*\*\*\* 旁邊的 [編輯]\*\*\*\*，然後在 [音訊會議]\*\*\*\* 窗格中，選擇 [收費電話號碼]\*\*\*\* 和 [免付費]\*\*\*\* 電話號碼清單中的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="0c5e5-175">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心：**</span><span class="sxs-lookup"><span data-stu-id="0c5e5-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="0c5e5-176">移至**Microsoft 365 系統管理中心** > **小組** > **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="0c5e5-177">選取 [**音訊會議** > **使用者**]，然後從清單中選取使用者，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="0c5e5-178">如需詳細資訊，請參閱[將 Microsoft 指派為音訊會議提供者](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="0c5e5-179">步驟 8：設定會議邀請 (選用)</span><span class="sxs-lookup"><span data-stu-id="0c5e5-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="0c5e5-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="0c5e5-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="0c5e5-181">系統會自動將為使用者設定的撥入號碼新增到傳送給會議出席者的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="0c5e5-182">不過，如果您想要的話，您可以新增自己的說明和合法連結、文字訊息和小型公司圖形。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="0c5e5-183">請參閱[自訂會議邀請](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="0c5e5-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="0c5e5-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="0c5e5-184">Related topics</span></span>

[<span data-ttu-id="0c5e5-185">音訊會議的常見問題</span><span class="sxs-lookup"><span data-stu-id="0c5e5-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="0c5e5-186">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="0c5e5-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="0c5e5-187">音訊會議的電話號碼</span><span class="sxs-lookup"><span data-stu-id="0c5e5-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="0c5e5-188">設定線上會議和電話會議的選項</span><span class="sxs-lookup"><span data-stu-id="0c5e5-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
