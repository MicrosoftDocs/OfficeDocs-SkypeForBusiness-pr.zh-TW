---
title: 設定 Microsoft Teams 的音訊會議
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '瞭解如何為企業中需要使用電話加入電話會議的人員設定撥入或音訊會議。 '
ms.openlocfilehash: e14cf924d039b461df3fc84d7b600d96d515be58
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838063"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="d6fc1-103">設定 Microsoft Teams 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="d6fc1-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="d6fc1-104">貴組織內的人員有時會需要透過電話來加入會議。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="d6fc1-105">Microsoft Teams 所包含的音訊會議功能正是為了這種情況所準備的！</span><span class="sxs-lookup"><span data-stu-id="d6fc1-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="d6fc1-106">人員可以透過電話加入 Teams 會議，而不必在行動裝置或電腦上透過 Teams 應用程式來參加。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="d6fc1-107">您只需要為打算排程或主持會議的人員設定音訊會議即可。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="d6fc1-108">撥入的會議出席者不需獲得任何指派的授權或進行其他設定。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="d6fc1-109">如需有關音訊會議的常見問題，請參閱[音訊會議常見問題](audio-conferencing-common-questions.md)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="d6fc1-110">步驟 1：了解您的國家/地區是否提供音訊會議</span><span class="sxs-lookup"><span data-stu-id="d6fc1-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="d6fc1-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d6fc1-111"><a name="__top"> </a></span></span>

<span data-ttu-id="d6fc1-112">移至[音訊會議與通話方案的適用國家和地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)，選取您的國家或地區，以取得有關音訊會議的提供資訊，以及電話系統、通話方案、付費和免付費電話號碼、通訊點數等資訊。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="d6fc1-113">步驟 2：取得和指派授權</span><span class="sxs-lookup"><span data-stu-id="d6fc1-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="d6fc1-114">若要使用音訊會議，您需要設定撥入會議每位使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="d6fc1-115">若要了解需要購買哪些授權及其售價，請參閱 [Microsoft Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="d6fc1-116">音訊會議包含在 Office 365 企業版 E5 授權中的附加元件。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="d6fc1-117">購買音訊會議授權之後，您必須將授權指派給組織中要排程或主持會議的人員。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="d6fc1-118">請參閱[將授權指派給商務用 Office 365 的使用者](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，將授權指派給組織中要排程或主持會議的人員。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="d6fc1-119">我們也建議您將通訊點數授權 (不需付費) 指派給您在在上一個步驟中指派授權的人員。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="d6fc1-120">若要了解如何設定通訊點數，請參閱[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d6fc1-121">您也可以設定[按分鐘計費的音訊會議](audio-conferencing-pay-per-minute.md)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="d6fc1-122">步驟 3：取得會議橋接器的服務號碼</span><span class="sxs-lookup"><span data-stu-id="d6fc1-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="d6fc1-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d6fc1-123"><a name="__top"> </a></span></span>

<span data-ttu-id="d6fc1-124">音訊會議不能使用一般的使用者電話號碼，您必須取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="d6fc1-125">您可以為您的會議橋接器取得付費或免費的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="d6fc1-126">有三種方法可以取得付費和免付費服務號碼：</span><span class="sxs-lookup"><span data-stu-id="d6fc1-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="d6fc1-127">**使用 Microsoft Teams 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="d6fc1-128">針對某些國家/地區，您可以使用 Microsoft Teams 系統管理中心為您的會議橋接器取得服務號碼。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="d6fc1-129">請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="d6fc1-130">**轉移現有的服務號碼**。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="d6fc1-131">將目前服務提供者或電信業者的現有號碼轉移至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="d6fc1-132">如需詳細資訊，請參閱[將電話號碼轉移至 Teams ](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)或[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，協助您完成此作業。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="d6fc1-133">**使用表單要求新號碼**。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="d6fc1-134">有時候 (視您的國家/地區而定) 您無法使用 Microsoft Teams 系統管理中心取得新的服務號碼，或者您將需要特定的電話號碼或區碼。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="d6fc1-135">若是如此，您將需要下載表單並將它傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="d6fc1-136">如需詳細資訊，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="d6fc1-137">步驟 4：指派服務號碼給會議橋接器</span><span class="sxs-lookup"><span data-stu-id="d6fc1-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="d6fc1-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d6fc1-138"><a name="__top"> </a></span></span>

<span data-ttu-id="d6fc1-139">當您為您的會議橋接器取得您的免費和/或免付費電話號碼後，必須指派電話號碼，以便在會議邀請中使用。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="d6fc1-140">按照以下步驟將新電話號碼指派給音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="d6fc1-141">![商務用 Skype 標誌圖示](media/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心：**</span><span class="sxs-lookup"><span data-stu-id="d6fc1-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="d6fc1-142">移至 [Microsoft 365 系統管理中心]\*\*\*\*  >  [系統管理中心]\*\*\*\*  >  [Teams]\*\*\*\*  >  [舊版入口網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="d6fc1-143">選取 [語音]\*\*\*\*  >  [電話號碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="d6fc1-144">選取電話號碼，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="d6fc1-145">如需詳細資訊，請參閱[變更音訊會議橋接器的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="d6fc1-146">步驟 5：設定會議橋接器的預設和替代語言</span><span class="sxs-lookup"><span data-stu-id="d6fc1-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="d6fc1-147"><a name="__top"> </a> 接下來，您想要[為 Microsoft Teams 的語音會議設定自動語音應答語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)，會議自動語音應答在撥入音訊會議的電話號碼時，會使用此語言用向來電者打招呼。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="d6fc1-148">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d6fc1-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d6fc1-149">在儀表板中，移至 [會議]\*\*\*\*  >  [會議橋接器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d6fc1-150">選取 [會議橋接電話號碼]，按一下 [編輯]\*\*\*\*，然後選擇預設語言。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="d6fc1-151">步驟 6：會議橋接器設定</span><span class="sxs-lookup"><span data-stu-id="d6fc1-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="d6fc1-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d6fc1-152"><a name="__top"> </a></span></span>
    
<span data-ttu-id="d6fc1-153">設定會議橋接器後，請確認預設設定 (例如，進入/退出通知、PIN 長度) 就是您要使用的設定。如果不是，可以變更。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="d6fc1-154">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d6fc1-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d6fc1-155">在儀表板中，移至 [會議]\*\*\*\*  >  [會議橋接器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d6fc1-156">選取 [橋接器設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-156">Select **Bridge settings**.</span></span> <span data-ttu-id="d6fc1-157">會開啟 [橋接器設定]\*\*\*\* 窗格。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="d6fc1-158">如需詳細資訊，請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="d6fc1-159">步驟 7：為主持會議的使用者指派撥入電話號碼</span><span class="sxs-lookup"><span data-stu-id="d6fc1-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="d6fc1-160">在您建立音訊會議橋接器之後，必須為您的使用者設定付費和免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="d6fc1-161">您必須為貴組織中負責主持或排程會議的所有人員執行此動作。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="d6fc1-162">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d6fc1-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d6fc1-163">在儀表板中，按一下 [使用者]\*\*\*\*，從清單中選取使用者，然後選取 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="d6fc1-164">選取 [音訊會議]\*\*\*\* 旁邊的 [編輯]\*\*\*\*，然後在 [音訊會議]\*\*\*\* 窗格中，選擇 [收費電話號碼]\*\*\*\* 和 [免付費]\*\*\*\* 電話號碼清單中的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="d6fc1-165">如需詳細資訊，請參閱[將 Microsoft 指派為音訊會議提供者](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="d6fc1-166">步驟 8：設定會議邀請 (選用)</span><span class="sxs-lookup"><span data-stu-id="d6fc1-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="d6fc1-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d6fc1-167"><a name="__top"> </a></span></span>
 
<span data-ttu-id="d6fc1-168">系統會自動將為使用者設定的撥入號碼新增到傳送給會議出席者的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="d6fc1-169">不過，如果您想要的話，您可以新增自己的說明和合法連結、文字訊息和小型公司圖形。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="d6fc1-170">請參閱[自訂會議邀請](meeting-settings-in-teams.md#customize-meeting-invitations)。</span><span class="sxs-lookup"><span data-stu-id="d6fc1-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="d6fc1-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="d6fc1-171">Related topics</span></span>

[<span data-ttu-id="d6fc1-172">音訊會議的常見問題</span><span class="sxs-lookup"><span data-stu-id="d6fc1-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="d6fc1-173">Microsoft Teams 音訊會議的電話號碼</span><span class="sxs-lookup"><span data-stu-id="d6fc1-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="d6fc1-174">設定線上會議和電話會議的選項</span><span class="sxs-lookup"><span data-stu-id="d6fc1-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
