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
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918749"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="6b2ff-103">變更音訊會議橋接器的電話號碼</span><span class="sxs-lookup"><span data-stu-id="6b2ff-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="6b2ff-104">當您購買 **音訊會議授權** 時，Microsoft 會為貴組織主持音訊會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="6b2ff-105">音訊會議橋接器會提供不同位置的撥入電話號碼，讓會議召集人和參與者可以使用他們使用電話加入商務用 Skype 或 Microsoft Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="6b2ff-106">除了已指派給會議橋接器的電話號碼外，您還可以取得其他位置用於音訊會議的其他服務號碼 [ (](/microsoftteams/getting-service-phone-numbers) 付費和免付費號碼) ，然後將這些號碼指派到會議橋接器，這樣您才能擴大使用者的涵蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b2ff-107">為了能夠指派/取消指派會議橋接器的電話號碼，電話號碼必須是'*服務*'號碼。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="6b2ff-108">您可以流覽至 Microsoft Teams 系統管理中心的語音電話號碼，並查看數位類型欄，查看  >  \*\*\*\*\*\*號碼\*\* 類型。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="6b2ff-109">使用者必須先設定 Microsoft 365 或 Office 365 通訊信用額度，才能撥打免付費電話進入橋接器。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="6b2ff-110">將新服務電話號碼指派給會議橋接器的步驟</span><span class="sxs-lookup"><span data-stu-id="6b2ff-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="6b2ff-111">步驟 1 - 將新電話號碼指派到音訊會議橋接器</span><span class="sxs-lookup"><span data-stu-id="6b2ff-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="6b2ff-112">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="6b2ff-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6b2ff-113">在左側流覽窗格上，**前往語音**  >  **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="6b2ff-114">從清單中選取電話號碼，然後按一下 **[編輯**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="6b2ff-115">在編輯 **頁面上**，在已指派 **至** 下展開下拉式清單，然後選取會議 **橋接器**  >  **的適用選項**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="6b2ff-116">步驟 2 - 變更會議橋接器的預設電話號碼， (選項) </span><span class="sxs-lookup"><span data-stu-id="6b2ff-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="6b2ff-117">會議橋接器的預設電話號碼會定義參與者或會議內的召集人撥打外寄通話時所會使用的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="6b2ff-118">只有服務付費電話號碼可以設定為會議橋接器的預設號碼; **服務免付費號碼無法設定為會議橋接器的預設號碼**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="6b2ff-119">如果您要指派服務付費電話號碼，並想將其設為音訊會議橋接器的新預設號碼，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="6b2ff-120">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="6b2ff-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6b2ff-121">在左側流覽窗格上，前往 **會議**  >  **橋接器**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="6b2ff-122">強調顯示要設定為預設值的服務付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="6b2ff-123">選取 **設定成預設值**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="6b2ff-124">步驟 3 - 變更會議邀請中包含的預設電話號碼， (選擇性) </span><span class="sxs-lookup"><span data-stu-id="6b2ff-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="6b2ff-125">使用者的預設電話號碼是當使用者排程會議時，包含在其會議邀請中的號碼。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="6b2ff-126">有關詳細資訊，包括如何為新使用者指派預設電話號碼，請參閱設定 [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) 邀請中包含的電話號碼，或設定商務用 Skype Online 邀請中包含的 [電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="6b2ff-127">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="6b2ff-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6b2ff-128">在左側流覽窗格上，前往[使用者，然後按一下清單中所需使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="6b2ff-129">在音訊 **會議旁邊，** 按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="6b2ff-130">在 **付費電話號碼** 或 **免付費** 電話號碼下，從下拉式清單中選擇要撥打的號碼，然後按一下 [ **申請**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="6b2ff-131">在變更適用之後，新的預設電話號碼將會包含在下次安排新會議的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="6b2ff-132">步驟 4 - 更新使用會議移移服務的現有會議邀請， (選擇性) </span><span class="sxs-lookup"><span data-stu-id="6b2ff-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="6b2ff-133">接下來的兩個步驟中，您必須啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="6b2ff-134">如果您更新了會議邀請中部分或所有使用者的預設電話號碼，您可以選擇性地更新已在使用會議移移服務變更使用者的預設電話號碼之前，已寄給貴組織使用者的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="6b2ff-135">有關其他資訊，請參閱[設定會議移 (MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="6b2ff-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="6b2ff-136">針對在步驟 2 變更 (使用者) MMS 應用程式執行會議移移服務。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="6b2ff-137">若要這麼做，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="6b2ff-138">您也可以查看會議移移狀態。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="6b2ff-139">在擱置或進行中狀態沒有作業時，所有會議都會 *重新排排*。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="6b2ff-140">取消會議橋接器的服務電話號碼的未指定步驟</span><span class="sxs-lookup"><span data-stu-id="6b2ff-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="6b2ff-141">當您從會議橋接器取消未指定電話號碼時，使用者將再無法使用此電話號碼加入任何會議。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="6b2ff-142">由於電話號碼正在變更，因此更新所有可能會以電話號碼作為預設號碼的使用者 (如果有任何) ，以及更新其現有的會議邀請，再取消音訊會議橋接器中的電話號碼的呼叫，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="6b2ff-143">如果移除電話號碼而不更新使用者及其會議，則他們現有的會議邀請可能包含無法加入其會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="6b2ff-144">在前三個步驟中，您必須啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="6b2ff-145">若要瞭解如何執行這項操作，請按一下 [想知道如何使用 [Windows PowerShell 進行管理嗎？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="6b2ff-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="6b2ff-146">步驟 1 - 更新將電話號碼取消被當做預設號碼之一的使用者</span><span class="sxs-lookup"><span data-stu-id="6b2ff-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="6b2ff-147">對於將取消未指定作為預設號碼的所有使用者，取代預設付費或免付費電話號碼，並開始進行排程會議程式。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="6b2ff-148">若要這麼做，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="6b2ff-149">您也可以在 Microsoft Teams 系統管理中心變更預設的付費或免付費使用者數目。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6b2ff-150">不過，這不會自動重新排期其會議。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="6b2ff-151">其他資訊請參閱設定 [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) 邀請中包含的電話號碼，或設定商務用 Skype Online 邀請 [中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="6b2ff-152">視貴組織的規模大小不同，這可能需要一些時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="6b2ff-153">步驟 2 - 使用 Windows PowerShell 查看會議移移狀態</span><span class="sxs-lookup"><span data-stu-id="6b2ff-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="6b2ff-154">在擱置或進行中狀態沒有作業時，所有會議都會 *重新排排*。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="6b2ff-155">有關會議移移服務詳細資訊，請參閱設定會議移 ([MMS) 。](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="6b2ff-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="6b2ff-156">步驟 3 - 取消在音訊會議橋接器中管理舊電話號碼</span><span class="sxs-lookup"><span data-stu-id="6b2ff-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="6b2ff-157">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="6b2ff-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6b2ff-158">在左側流覽區中，前往 **語音**  >  **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="6b2ff-159">如果電話號碼是免付費電話號碼，請從清單中選取電話號碼，然後按一下 [ **釋放**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="6b2ff-160">如果電話號碼是付費電話號碼，請聯絡 Microsoft [支援服務](https://go.microsoft.com/fwlink/?linkid=2091806) ，讓電話號碼取消未指定。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="6b2ff-161">如果電話號碼是免付費電話號碼，請在 **確認** 視窗中按一下 [是。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6b2ff-162">取消音訊會議橋接器中的電話號碼之後，使用者就無法再加入新的或現有的會議。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6b2ff-163">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="6b2ff-163">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="6b2ff-164"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="6b2ff-164"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="6b2ff-165">驗證 Windows PowerShell 已準備就緒</span><span class="sxs-lookup"><span data-stu-id="6b2ff-165">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="6b2ff-166">這些步驟檢查您執行的是 Windows PowerShell 3.0 版或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-166">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="6b2ff-167">輸入 **Windows**  >  **PowerShell 的開始功能表**。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-167">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="6b2ff-168">在 _Windows PowerShell_ 視窗中輸入 **Get-Host** 以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-168">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="6b2ff-169">如果您沒有 3.0 版或更新版本，則需要下載並安裝 Windows PowerShell 的更新。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-169">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="6b2ff-170">請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 以下載並更新 Windows PowerShell 至 4.0 版。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-170">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="6b2ff-171">當系統提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-171">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="6b2ff-172">您也需要安裝商務用 Skype Online 的 Windows PowerShell 模組，可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-172">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="6b2ff-173">此模組僅支援 64 位的電腦，可從商務用 Skype Online 的 [Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-173">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="6b2ff-174">如果系統提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-174">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="6b2ff-175">如果您需要瞭解更多，請參閱在單一 Windows PowerShell 視窗中，連接至所有 [Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-175">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="6b2ff-176">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b2ff-176">To start Windows PowerShell</span></span>

 <span data-ttu-id="6b2ff-177">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="6b2ff-177">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="6b2ff-178">從Windows  >  **PowerShell** 的開始功能表。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-178">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="6b2ff-179">在 **Windows PowerShell** 視窗中，以以下方式連接至 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-179">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>

> [!NOTE]
> <span data-ttu-id="6b2ff-180">商務用 Skype Online Connector 目前屬於最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-180">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="6b2ff-181">如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開版本，則不需要安裝商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-181">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="6b2ff-182">第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需要執行 **Import-Module** 命令。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-182">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="6b2ff-183">如果您需要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連線到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或是使用 Windows PowerShell 連線到商務用[Skype Online。](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6b2ff-183">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="6b2ff-184">節省時間並自動化</span><span class="sxs-lookup"><span data-stu-id="6b2ff-184">Save time and automate</span></span>

<span data-ttu-id="6b2ff-185">若要將這項程式自動化以節省時間，您可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-185">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="6b2ff-186">使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) Cmdlet 來變更特定使用者的預設付費或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-186">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="6b2ff-187">若要變更使用者的預設免付費電話號碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-187">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="6b2ff-188">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet 來根據使用者的原始預設號碼或位置來變更預設付費或免付費數目。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-188">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b2ff-189">若要尋找 BridgeID，請使用 **Get-CsOnlineDialInConferencingBridge。**</span><span class="sxs-lookup"><span data-stu-id="6b2ff-189">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="6b2ff-190">若要將所有使用者的預設免付費電話號碼設為 8005551234，請執行：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-190">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="6b2ff-191">若要將擁有 8005551234 作為預設免付費電話號碼的所有使用者的預設免付費號碼變更為 8005551239，並自動重新排約其會議，請執行：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-191">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="6b2ff-192">若要將位於美國的所有使用者的預設免付費號碼設為 8005551234，並自動重新排定會議，請執行：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-192">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="6b2ff-193">上述使用的位置必須與 Microsoft 365 系統管理 (所) 之使用者的連絡人資訊相符。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-193">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6b2ff-194">疑難排解</span><span class="sxs-lookup"><span data-stu-id="6b2ff-194">Troubleshooting</span></span>

<span data-ttu-id="6b2ff-195">**沒有可用的取消未指定按鈕**</span><span class="sxs-lookup"><span data-stu-id="6b2ff-195">**Unassign button isn't available**</span></span>

<span data-ttu-id="6b2ff-196">您想要取消號碼，但按鈕無法使用，而當游標停留在該號碼上方時，您會被重新導向至客戶支援，並收到下列訊息：「預設號碼或共用號碼無法從橋接器取消呼叫。 _若要取消付費專用電話號碼，請與支援人員聯繫。」。_</span><span class="sxs-lookup"><span data-stu-id="6b2ff-196">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="6b2ff-197">若要取得有關橋接器或 () ，請執行下列 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-197">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="6b2ff-198">結果除了身分識別、名稱和地區等其他資訊外，也應該包含 DefaultServiceNumber。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-198">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="6b2ff-199">**要** 取消分配的範例，DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="6b2ff-199">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="6b2ff-200">關於 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b2ff-200">About Windows PowerShell</span></span>

<span data-ttu-id="6b2ff-201">您可以使用 Windows PowerShell 來管理使用者，以及使用者可以或不允許他們執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-201">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="6b2ff-202">Windows PowerShell 可以單一系統管理點，來協助管理 Microsoft 365 或 Office 365 和商務用 Skype Online，以簡化您的日常工作，尤其當您需要執行多項工作時。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-202">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="6b2ff-203">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-203">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="6b2ff-204">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="6b2ff-204">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="6b2ff-205">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b2ff-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="6b2ff-206">Windows PowerShell 在速度、簡化及生產力方面有許多優點，是僅用 Microsoft 365 系統管理中心所長，例如當您要一次為許多使用者變更設定時。</span><span class="sxs-lookup"><span data-stu-id="6b2ff-206">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6b2ff-207">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="6b2ff-207">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="6b2ff-208">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="6b2ff-208">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="6b2ff-209">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="6b2ff-209">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="6b2ff-210">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="6b2ff-210">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="6b2ff-211">相關主題</span><span class="sxs-lookup"><span data-stu-id="6b2ff-211">Related topics</span></span>
[<span data-ttu-id="6b2ff-212">變更音訊會議橋接器的設定</span><span class="sxs-lookup"><span data-stu-id="6b2ff-212">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
