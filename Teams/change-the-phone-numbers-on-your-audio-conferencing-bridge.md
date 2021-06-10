---
title: 在音訊會議橋接器上變更電話號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解為會議橋接器指派新服務電話號碼以擴大使用者範圍所需的步驟。
ms.openlocfilehash: f477c583db36e6dee514a84f32de202361d01c11
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102659"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="325eb-103">變更音訊會議橋接器的電話號碼</span><span class="sxs-lookup"><span data-stu-id="325eb-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="325eb-104">當您購買 **音訊會議授權** 時，Microsoft 會為貴組織託管您的音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="325eb-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="325eb-105">音訊會議橋接器會提供不同位置的撥入電話號碼，讓會議召集人和參與者可以使用電話商務用 Skype或Microsoft Teams會議。</span><span class="sxs-lookup"><span data-stu-id="325eb-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="325eb-106">除了已指派給會議橋接器的電話號碼之外，您還可以從其他位置取得用於音訊會議) 的其他服務號碼 [ (](./getting-service-phone-numbers.md) 付費和免付費號碼，然後將這些號碼指派給會議橋接器，以便擴大使用者的涵蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="325eb-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](./getting-service-phone-numbers.md) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="325eb-107">若要指派/取消指派會議橋接器的電話號碼，電話號碼必須是'*服務*'號碼。</span><span class="sxs-lookup"><span data-stu-id="325eb-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="325eb-108">您可以流覽至系統管理中心中的 Voice 電話號碼，Microsoft Teams數位類型欄來查看  >  \*\*\*\*\*\*號碼\*\* 類型。</span><span class="sxs-lookup"><span data-stu-id="325eb-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="325eb-109">Microsoft 365或Office 365通訊信用額度必須先設定，使用者才能撥打免付費號碼撥入橋接器。</span><span class="sxs-lookup"><span data-stu-id="325eb-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="325eb-110">將新服務電話號碼指派給會議橋接器的步驟</span><span class="sxs-lookup"><span data-stu-id="325eb-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="325eb-111">步驟 1 - 將新電話號碼指派給音訊會議橋接器</span><span class="sxs-lookup"><span data-stu-id="325eb-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="325eb-112">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="325eb-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="325eb-113">在左側流覽窗格中，前往語音電話  >  **號碼**。</span><span class="sxs-lookup"><span data-stu-id="325eb-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="325eb-114">從清單中選取電話號碼，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="325eb-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="325eb-115">在編輯 **頁面上\*\*\*\*，展開下** 拉式清單的下拉式清單，然後選取 **會議橋接器**  >  **的 Apply**。</span><span class="sxs-lookup"><span data-stu-id="325eb-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="325eb-116">步驟 2 - 變更會議橋接器的預設電話號碼 (選項) </span><span class="sxs-lookup"><span data-stu-id="325eb-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="325eb-117">會議橋接器的預設電話號碼會定義參與者或召集人從會議內撥打外寄電話時，會使用的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="325eb-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="325eb-118">只有服務付費號碼可以設定為會議橋接器的預設號碼; **服務免付費號碼無法設定為會議橋接器的預設號碼**。</span><span class="sxs-lookup"><span data-stu-id="325eb-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="325eb-119">如果您要指派服務付費號碼，並想將其設定為音訊會議橋接器的新預設號碼，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="325eb-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="325eb-120">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="325eb-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="325eb-121">在左側流覽窗格中，前往 **會議**  >  **會議橋接器**。</span><span class="sxs-lookup"><span data-stu-id="325eb-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="325eb-122">強調您想要設定為預設值的服務付費號碼。</span><span class="sxs-lookup"><span data-stu-id="325eb-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="325eb-123">選取 **設定為預設值**。</span><span class="sxs-lookup"><span data-stu-id="325eb-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="325eb-124">步驟 3 - 變更使用者會議邀請中包含的預設電話號碼， () </span><span class="sxs-lookup"><span data-stu-id="325eb-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="325eb-125">使用者的預設電話號碼是排程會議時包含在會議邀請中的號碼。</span><span class="sxs-lookup"><span data-stu-id="325eb-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="325eb-126">詳細資訊，包括新使用者的預設電話號碼指派方式，請參閱在 Microsoft Teams 中設定邀請中包含的電話號碼，或在[商務用 Skype](set-the-phone-numbers-included-on-invites-in-teams.md) Online 中設定邀請[中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="325eb-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="325eb-127">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="325eb-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="325eb-128">在左側流覽窗格上，前往 **[使用者** ，然後按一下清單中所需使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="325eb-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="325eb-129">在音訊 **會議旁邊**，按一下 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="325eb-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="325eb-130">在 **[付費號碼** 或 **免** 付費號碼> 下，從下拉式清單中選擇號碼，然後按一下 [ **申請**。</span><span class="sxs-lookup"><span data-stu-id="325eb-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="325eb-131">在已採用變更之後，新的預設電話號碼會包含在下次安排新會議的召集人的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="325eb-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="325eb-132">步驟 4 - 使用會議移移服務更新使用者的現有會議邀請 (選擇性) </span><span class="sxs-lookup"><span data-stu-id="325eb-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="325eb-133">接下來兩個步驟，您必須開始Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="325eb-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="325eb-134">如果您更新了部分或所有使用者的會議邀請中包含的預設電話號碼，您可以選擇更新已寄給貴組織使用者的會議邀請，然後再使用會議移移服務變更其預設電話號碼。</span><span class="sxs-lookup"><span data-stu-id="325eb-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="325eb-135">有關其他資訊，請參閱設定會議移 ([MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="325eb-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="325eb-136">針對在步驟 2 中變更 (使用者) MMS 帳戶執行會議移移服務。</span><span class="sxs-lookup"><span data-stu-id="325eb-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="325eb-137">若要這麼做，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="325eb-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="325eb-138">您也可以查看會議移移狀態。</span><span class="sxs-lookup"><span data-stu-id="325eb-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="325eb-139">在擱置或進行中狀態中沒有任何作業時，所有會議都會 *重新排期*。</span><span class="sxs-lookup"><span data-stu-id="325eb-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="325eb-140">取消為會議橋接器未指定服務電話號碼的步驟</span><span class="sxs-lookup"><span data-stu-id="325eb-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="325eb-141">當您從會議橋接器取消分配電話號碼時，使用者將無法使用該電話號碼加入任何會議。</span><span class="sxs-lookup"><span data-stu-id="325eb-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="325eb-142">由於電話號碼正在變更，因此必須更新所有可能以電話號碼做為預設號碼 (如果有) 的使用者，並更新現有的會議邀請，再從音訊會議橋接器中取消分配電話號碼。</span><span class="sxs-lookup"><span data-stu-id="325eb-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="325eb-143">如果移除電話號碼而不更新使用者及其會議，他們現有的會議邀請可能包含無法加入其會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="325eb-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="325eb-144">在前三個步驟中，您必須開始Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="325eb-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="325eb-145">若要瞭解如何執行此操作，請按一下 [[想要瞭解如何使用 Windows PowerShell？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="325eb-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="325eb-146">步驟 1 - 更新電話號碼被未指定為其中一個預設號碼的使用者</span><span class="sxs-lookup"><span data-stu-id="325eb-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="325eb-147">為號碼未未指定為預設號碼的所有使用者取代預設付費或免付費號碼，並開始重新排程會議程式。</span><span class="sxs-lookup"><span data-stu-id="325eb-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="325eb-148">若要這麼做，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="325eb-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="325eb-149">您也可以在系統管理中心變更預設付費或免付費Microsoft Teams人數。</span><span class="sxs-lookup"><span data-stu-id="325eb-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="325eb-150">不過，這不會自動重新排期他們的會議。</span><span class="sxs-lookup"><span data-stu-id="325eb-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="325eb-151">有關其他資訊，請參閱在 Microsoft Teams 中設定邀請中包含的電話號碼，[或在](set-the-phone-numbers-included-on-invites-in-teams.md)[商務用 Skype Online 中設定商務用 Skype電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="325eb-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="325eb-152">視貴組織的大小，這可能需要一些時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="325eb-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="325eb-153">步驟 2 - 使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="325eb-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="325eb-154">一旦沒有在擱置或進行中狀態中的作業，所有會議都會 *重新* 排期。</span><span class="sxs-lookup"><span data-stu-id="325eb-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="325eb-155">有關會議移移服務的資訊，請參閱設定會議移 ([MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="325eb-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="325eb-156">步驟 3 - 取消從音訊會議橋接器中舊的電話號碼</span><span class="sxs-lookup"><span data-stu-id="325eb-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="325eb-157">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="325eb-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="325eb-158">在左側流覽中，前往 **Voice**  >  **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="325eb-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="325eb-159">如果電話號碼是免付費號碼，請從清單中選取電話號碼，然後按一下 [ **釋出**> 。</span><span class="sxs-lookup"><span data-stu-id="325eb-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="325eb-160">如果電話號碼是付費號碼，請聯絡 Microsoft [支援](/microsoft-365/admin/contact-support-for-business-products) 人員，將電話號碼取消分配。</span><span class="sxs-lookup"><span data-stu-id="325eb-160">If the phone number is a toll number, please contact [Microsoft support](/microsoft-365/admin/contact-support-for-business-products) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="325eb-161">如果電話號碼是免付費號碼，請在確認視窗中按一下[是。</span><span class="sxs-lookup"><span data-stu-id="325eb-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="325eb-162">從音訊會議橋接器中未指定電話號碼之後，使用者就無法再使用電話號碼加入新的或現有的會議。</span><span class="sxs-lookup"><span data-stu-id="325eb-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="325eb-163">節省時間並自動化</span><span class="sxs-lookup"><span data-stu-id="325eb-163">Save time and automate</span></span>

<span data-ttu-id="325eb-164">若要自動化此程式以節省時間，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlets。</span><span class="sxs-lookup"><span data-stu-id="325eb-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="325eb-165">使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet 變更特定使用者的預設付費或免付費號碼。</span><span class="sxs-lookup"><span data-stu-id="325eb-165">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="325eb-166">若要變更使用者的預設免付費號碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="325eb-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="325eb-167">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet，根據使用者的原始預設號碼或位置，變更預設的付費或免付費使用者數目。</span><span class="sxs-lookup"><span data-stu-id="325eb-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="325eb-168">若要尋找 BridgeID，請使用 **Get-CsOnlineDialInConferencing Bridge**。</span><span class="sxs-lookup"><span data-stu-id="325eb-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="325eb-169">若要為沒有 1 的所有使用者設定預設的免付費號碼至 8005551234，請執行：</span><span class="sxs-lookup"><span data-stu-id="325eb-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="325eb-170">若要將具有 8005551234 作為預設免付費號碼的所有使用者的預設免付費號碼變更為 8005551239，並自動重新排定會議，請執行：</span><span class="sxs-lookup"><span data-stu-id="325eb-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="325eb-171">若要將位於美國的所有使用者的預設免付費號碼設為 8005551234，並自動重新排定會議，請執行：</span><span class="sxs-lookup"><span data-stu-id="325eb-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="325eb-172">上述使用的位置必須與系統管理中心 (使用者) 連絡人資訊Microsoft 365相符。</span><span class="sxs-lookup"><span data-stu-id="325eb-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="325eb-173">疑難排解</span><span class="sxs-lookup"><span data-stu-id="325eb-173">Troubleshooting</span></span>

<span data-ttu-id="325eb-174">**無法使用取消分配按鈕**</span><span class="sxs-lookup"><span data-stu-id="325eb-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="325eb-175">您想要取消分配號碼，但該按鈕卻無法使用，如果將游標停留在該號碼上方，系統會重新導向您，以下列訊息連連支援人員：「無法從橋接器取消分配預設號碼或共用號碼。」 _若要取消分配專用付費號碼，請聯絡支援人員_。」。</span><span class="sxs-lookup"><span data-stu-id="325eb-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="325eb-176">若要取得橋接器和 () 詳細資訊，請執行下列 Powershell：</span><span class="sxs-lookup"><span data-stu-id="325eb-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="325eb-177">結果，除了身分識別、名稱和地區等其他資訊之外，也應該包含 DefaultServiceNumber。</span><span class="sxs-lookup"><span data-stu-id="325eb-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="325eb-178">**範例**，若要取消分配，DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="325eb-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="325eb-179">關於 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="325eb-179">About Windows PowerShell</span></span>

<span data-ttu-id="325eb-180">有了Windows PowerShell，您可以管理使用者及其允許或不允許執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="325eb-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="325eb-181">Windows PowerShell單一系統管理Microsoft 365或 Office 365 和 商務用 Skype Online，可簡化您的日常工作，尤其是當您有多個工作需要執行時。</span><span class="sxs-lookup"><span data-stu-id="325eb-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="325eb-182">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="325eb-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="325eb-183">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="325eb-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="325eb-184">為什麼您需要使用 PowerShell Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="325eb-184">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

<span data-ttu-id="325eb-185">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="325eb-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="325eb-186">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="325eb-186">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="325eb-187">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="325eb-187">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="325eb-188">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="325eb-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="325eb-189">使用Windows PowerShell執行線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="325eb-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="325eb-190">相關主題</span><span class="sxs-lookup"><span data-stu-id="325eb-190">Related topics</span></span>
[<span data-ttu-id="325eb-191">變更音訊會議橋接器的設定</span><span class="sxs-lookup"><span data-stu-id="325eb-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)