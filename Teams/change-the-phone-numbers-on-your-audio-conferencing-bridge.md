---
title: 變更音訊會議橋接器上的電話號碼
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
ms.openlocfilehash: e2e1aa3d5626f6592f22e0850a8c7419d7549b38
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569185"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="1e046-103">變更音訊會議橋接器的電話號碼</span><span class="sxs-lookup"><span data-stu-id="1e046-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="1e046-104">當您購買 **音訊會議授權** 時，Microsoft 會為貴組織託管音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="1e046-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="1e046-105">音訊會議橋接器會提供不同位置的撥入電話號碼，讓會議召集人和參與者可以使用電話加入商務用 Skype 或 Microsoft Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="1e046-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="1e046-106">除了已指派給會議橋接器的電話號碼之外，您還可以取得其他位置用於音訊會議) 的其他服務號碼 [ (](/microsoftteams/getting-service-phone-numbers) 付費和免付費號碼，然後將這些號碼指派給會議橋接器，以便擴大使用者的範圍。</span><span class="sxs-lookup"><span data-stu-id="1e046-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e046-107">若要指派/取消指派會議橋接器的電話號碼，電話號碼必須是'*服務*'號碼。</span><span class="sxs-lookup"><span data-stu-id="1e046-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="1e046-108">您可以在 Microsoft Teams 系統管理中心流覽至語音電話號碼，並查看數位類型欄，以查看  >  \*\*\*\*\*\*號碼\*\* 類型。</span><span class="sxs-lookup"><span data-stu-id="1e046-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="1e046-109">使用者必須先設定 Microsoft 365 或 Office 365 通訊信用額度，才能撥打免付費號碼到橋接器。</span><span class="sxs-lookup"><span data-stu-id="1e046-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="1e046-110">將新服務電話號碼指派給會議橋接器的步驟</span><span class="sxs-lookup"><span data-stu-id="1e046-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="1e046-111">步驟 1 - 將新電話號碼指派給音訊會議橋接器</span><span class="sxs-lookup"><span data-stu-id="1e046-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="1e046-112">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="1e046-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1e046-113">在左側功能窗格中，前往 **語音**  >  **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="1e046-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="1e046-114">從清單中選取電話號碼，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="1e046-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="1e046-115">在編輯 **頁面上** 的指派 **至** 下，展開下拉式清單，然後選取會議 **橋接器**  >  **的適用**。</span><span class="sxs-lookup"><span data-stu-id="1e046-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="1e046-116">步驟 2 - 變更會議橋接器的預設電話號碼 (選項) </span><span class="sxs-lookup"><span data-stu-id="1e046-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="1e046-117">會議橋接器的預設電話號碼會定義當參與者或會議召集人從會議內撥打外寄電話時，會使用的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="1e046-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="1e046-118">只有服務付費電話號碼可以設定為會議橋接器的預設號碼; **服務免付費號碼無法設定為會議橋接器的預設號碼**。</span><span class="sxs-lookup"><span data-stu-id="1e046-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="1e046-119">如果您要指派服務付費電話號碼，並想將其設為音訊會議橋接器的新預設號碼，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1e046-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="1e046-120">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="1e046-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1e046-121">在左側功能窗格中，前往 **會議**  >  **橋接器**。</span><span class="sxs-lookup"><span data-stu-id="1e046-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="1e046-122">將您想要設定為預設值的服務付費電話號碼突顯。</span><span class="sxs-lookup"><span data-stu-id="1e046-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="1e046-123">選取 **設定為預設值**。</span><span class="sxs-lookup"><span data-stu-id="1e046-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="1e046-124">步驟 3 - 變更使用者會議邀請中包含的預設電話號碼， (選擇) </span><span class="sxs-lookup"><span data-stu-id="1e046-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="1e046-125">使用者的預設電話號碼是排程會議時，會包含在其會議邀請上的號碼。</span><span class="sxs-lookup"><span data-stu-id="1e046-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="1e046-126">有關新使用者的預設電話號碼指派方式等詳細資訊，請參閱設定 [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) 中邀請中包含的電話號碼，或設定商務用 Skype Online 邀請 [中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="1e046-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="1e046-127">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="1e046-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1e046-128">在左側功能窗格上，前往 **[** 使用者，然後按一下清單中所需使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="1e046-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="1e046-129">在 **音訊會議旁邊，** 按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="1e046-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="1e046-130">在 **付費電話號碼** 或 **免付費電話號碼** 下，從下拉式清單中選擇號碼，然後按一下 **[申請**。</span><span class="sxs-lookup"><span data-stu-id="1e046-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="1e046-131">在變更進行之後，新的預設電話號碼將會包含在下次安排新會議的召集人的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="1e046-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="1e046-132">步驟 4 - 使用會議移移服務更新使用者的現有會議邀請， (選擇) </span><span class="sxs-lookup"><span data-stu-id="1e046-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="1e046-133">在接下來兩個步驟中，您必須啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1e046-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="1e046-134">如果您更新部分或所有使用者的會議邀請中包含的預設電話號碼，您可以選擇性地更新已寄給貴組織使用者的會議邀請，之後再使用會議移移服務變更其預設電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1e046-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="1e046-135">有關其他資訊，請參閱設定會議移 ([MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="1e046-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="1e046-136">針對在步驟 2 中變更 (使用者) MMS 應用程式執行會議移移服務。</span><span class="sxs-lookup"><span data-stu-id="1e046-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="1e046-137">若要這麼做，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1e046-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="1e046-138">您也可以查看會議移移狀態。</span><span class="sxs-lookup"><span data-stu-id="1e046-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="1e046-139">在擱置或進行中狀態中沒有作業時，所有會議都會重新 *排定。*</span><span class="sxs-lookup"><span data-stu-id="1e046-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="1e046-140">取消會議橋接器服務電話號碼的未指定步驟</span><span class="sxs-lookup"><span data-stu-id="1e046-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="1e046-141">當您從會議橋接器取消分配電話號碼時，使用者將再無法使用該電話號碼加入任何會議。</span><span class="sxs-lookup"><span data-stu-id="1e046-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="1e046-142">由於電話號碼正在變更，因此更新所有可能擁有電話號碼作為預設號碼的使用者 (如果有) ，也請更新現有的會議邀請，再從音訊會議橋接器取消電話號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="1e046-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="1e046-143">如果移除電話號碼但不更新使用者及其會議，則他們現有的會議邀請可能包含無法加入其會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1e046-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="1e046-144">在前三個步驟中，您必須啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1e046-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="1e046-145">若要瞭解如何執行此操作，請按一下 [[想要瞭解如何使用 Windows PowerShell 進行管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="1e046-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="1e046-146">步驟 1 - 更新電話號碼為其中一個預設號碼的使用者</span><span class="sxs-lookup"><span data-stu-id="1e046-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="1e046-147">為擁有要取消分配的號碼的所有使用者取代預設付費或免付費電話號碼，並開始重新排程會議程式。</span><span class="sxs-lookup"><span data-stu-id="1e046-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="1e046-148">若要這麼做，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1e046-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="1e046-149">您也可以在 Microsoft Teams 系統管理中心變更預設的付費或免付費使用者人數。</span><span class="sxs-lookup"><span data-stu-id="1e046-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1e046-150">不過，這不會自動重新排定其會議。</span><span class="sxs-lookup"><span data-stu-id="1e046-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="1e046-151">其他資訊請參閱設定 [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) 中邀請中包含的電話號碼，或設定商務用 Skype Online 中邀請 [中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="1e046-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="1e046-152">視貴組織的規模大小不同，這可能需要一些時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="1e046-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="1e046-153">步驟 2 - 使用 Windows PowerShell 查看會議移移狀態</span><span class="sxs-lookup"><span data-stu-id="1e046-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="1e046-154">在擱置或進行中狀態中沒有作業時，所有會議都會 *重新* 排定。</span><span class="sxs-lookup"><span data-stu-id="1e046-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="1e046-155">有關會議移移服務的資訊，請參閱在 [MMS (設定會議 ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)移) 。</span><span class="sxs-lookup"><span data-stu-id="1e046-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="1e046-156">步驟 3 - 從音訊會議橋接器取消分配舊電話號碼</span><span class="sxs-lookup"><span data-stu-id="1e046-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="1e046-157">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="1e046-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1e046-158">在左側流覽中，前往 **語音**  >  **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="1e046-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="1e046-159">如果電話號碼是免付費電話號碼，請從清單中選取電話號碼，然後按一下 [釋 **出**。</span><span class="sxs-lookup"><span data-stu-id="1e046-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="1e046-160">如果電話號碼是付費電話號碼，請聯絡 Microsoft [支援服務](https://go.microsoft.com/fwlink/?linkid=2091806) ，將電話號碼取消分配。</span><span class="sxs-lookup"><span data-stu-id="1e046-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="1e046-161">如果電話號碼是免付費電話號碼，請在確認視窗中按一下 **[** 是。</span><span class="sxs-lookup"><span data-stu-id="1e046-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1e046-162">從音訊會議橋接器取消分配電話號碼後，使用者就無法再使用電話號碼加入新的或現有的會議。</span><span class="sxs-lookup"><span data-stu-id="1e046-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="1e046-163">節省時間並自動化</span><span class="sxs-lookup"><span data-stu-id="1e046-163">Save time and automate</span></span>

<span data-ttu-id="1e046-164">若要自動化此程式以節省時間，您可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1e046-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="1e046-165">使用 [Set-CsOnlineDialInConferencingUser Cmdlet](https://go.microsoft.com/fwlink/?LinkId=617688) 來變更特定使用者的預設付費或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1e046-165">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="1e046-166">若要變更使用者的預設免付費電話號碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="1e046-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="1e046-167">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet，根據使用者的原始預設號碼或位置來變更預設的付費或免付費人數。</span><span class="sxs-lookup"><span data-stu-id="1e046-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e046-168">若要尋找 BridgeID，請使用 **Get-CsOnlineDialInConferencing Bridge。**</span><span class="sxs-lookup"><span data-stu-id="1e046-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="1e046-169">若要為沒有 1 到 8005551234 的所有使用者設定預設的免付費電話號碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="1e046-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="1e046-170">若要將擁有 8005551234 作為預設免付費號碼的所有使用者的預設免付費電話號碼變更為 8005551239，並自動重新排程會議，請執行：</span><span class="sxs-lookup"><span data-stu-id="1e046-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="1e046-171">若要將位於美國的所有使用者的預設免付費電話號碼設為 8005551234，並自動重新排程會議，請執行：</span><span class="sxs-lookup"><span data-stu-id="1e046-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="1e046-172">上述使用的位置必須與 Microsoft 365 系統管理中心 (使用者) 的連絡人資訊相符。</span><span class="sxs-lookup"><span data-stu-id="1e046-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1e046-173">疑難排解</span><span class="sxs-lookup"><span data-stu-id="1e046-173">Troubleshooting</span></span>

<span data-ttu-id="1e046-174">**沒有可用的取消未指定按鈕**</span><span class="sxs-lookup"><span data-stu-id="1e046-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="1e046-175">您想要取消分配號碼，但該按鈕卻無法使用，而如果將游標停留在該號碼上，系統會以下列訊息重新導向至支援人員：「無法從橋接器取消呼叫預設號碼或共用號碼。 _若要取消分配專用付費電話號碼，請聯絡客戶支援_。」。</span><span class="sxs-lookup"><span data-stu-id="1e046-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="1e046-176">若要取得橋接器 () ，請執行下列 Powershell：</span><span class="sxs-lookup"><span data-stu-id="1e046-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="1e046-177">結果除了身分識別、名稱和地區等其他資訊外，也應該包含 DefaultServiceNumber。</span><span class="sxs-lookup"><span data-stu-id="1e046-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="1e046-178">**範例**，若要取消分配，DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="1e046-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="1e046-179">關於 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e046-179">About Windows PowerShell</span></span>

<span data-ttu-id="1e046-180">使用 Windows PowerShell，您可以管理使用者，以及使用者可以或不允許他們執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="1e046-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="1e046-181">Windows PowerShell 可以使用單點系統管理來協助管理 Microsoft 365 或 Office 365 和商務用 Skype Online，以簡化您的日常工作，尤其是當您需要執行多項工作時。</span><span class="sxs-lookup"><span data-stu-id="1e046-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="1e046-182">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="1e046-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="1e046-183">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="1e046-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="1e046-184">為什麼您需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e046-184">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="1e046-185">Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="1e046-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1e046-186">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="1e046-186">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="1e046-187">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="1e046-187">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="1e046-188">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="1e046-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="1e046-189">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="1e046-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="1e046-190">相關主題</span><span class="sxs-lookup"><span data-stu-id="1e046-190">Related topics</span></span>
[<span data-ttu-id="1e046-191">變更音訊會議橋接器的設定</span><span class="sxs-lookup"><span data-stu-id="1e046-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
