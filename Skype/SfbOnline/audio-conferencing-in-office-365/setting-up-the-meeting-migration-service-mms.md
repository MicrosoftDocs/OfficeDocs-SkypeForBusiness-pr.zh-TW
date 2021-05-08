---
title: '使用會議移 (MMS) '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 會議移 (MMS) 是一種在背景中執行的服務，並自動更新商務用 Skype Microsoft Teams會議。 MMS 的設計目的是讓使用者無需執行會議移移工具，以更新商務用 Skype Microsoft Teams會議。
ms.openlocfilehash: db4889bb30ec453a64bfcf760a1233fbc7c1e2f5
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282110"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="4d746-104">使用會議移 (MMS) </span><span class="sxs-lookup"><span data-stu-id="4d746-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="4d746-105">會議移 (MMS) 是一項服務，可更新使用者在下列情況下的現有會議：</span><span class="sxs-lookup"><span data-stu-id="4d746-105">The Meeting Migration Service (MMS) is a service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="4d746-106">當使用者從內部部署移至雲端時， (是移商務用 Skype或 TeamsOnly) 。</span><span class="sxs-lookup"><span data-stu-id="4d746-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="4d746-107">當系統管理員變更使用者的音訊會議設定時</span><span class="sxs-lookup"><span data-stu-id="4d746-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="4d746-108">當線上使用者僅升級Teams或 TeamsUpgradePolicy 中的使用者模式設定為 SfBwithTeamsCollabAndMeetings 時</span><span class="sxs-lookup"><span data-stu-id="4d746-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="4d746-109">當您使用 PowerShell 時</span><span class="sxs-lookup"><span data-stu-id="4d746-109">When you use PowerShell</span></span> 


<span data-ttu-id="4d746-110">根據預設，MMS 會在每一種情況下自動觸發，不過系統管理員可以在租使用者層級停用 MMS。</span><span class="sxs-lookup"><span data-stu-id="4d746-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="4d746-111">此外，系統管理員可以使用 PowerShell Cmdlet 為給定使用者手動觸發會議移轉。</span><span class="sxs-lookup"><span data-stu-id="4d746-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="4d746-112">**限制**：如果適用下列任何一項，就無法使用會議移移服務：</span><span class="sxs-lookup"><span data-stu-id="4d746-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="4d746-113">使用者的信箱是託管在內部Exchange中。</span><span class="sxs-lookup"><span data-stu-id="4d746-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="4d746-114">使用者正從雲端移商務用 Skype Server內部部署。</span><span class="sxs-lookup"><span data-stu-id="4d746-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>


## <a name="how-mms-works"></a><span data-ttu-id="4d746-115">MMS 運作方式</span><span class="sxs-lookup"><span data-stu-id="4d746-115">How MMS works</span></span>

<span data-ttu-id="4d746-116">當為給定使用者觸發 MMS 時，該使用者的移入要求會置於佇列中。</span><span class="sxs-lookup"><span data-stu-id="4d746-116">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="4d746-117">為了避免任何競賽條件，排入佇列的要求會經過至少 90 分鐘之後，才會刻意處理。</span><span class="sxs-lookup"><span data-stu-id="4d746-117">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="4d746-118">MMS 處理要求後，會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="4d746-118">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="4d746-119">它會搜尋該使用者的信箱，以搜尋該使用者組織並在未來排程的所有現有會議。</span><span class="sxs-lookup"><span data-stu-id="4d746-119">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="4d746-120">根據使用者信箱中的資訊，它會更新或排程該使用者在 Teams 或 商務用 Skype Online 中的新會議，視確切案例。</span><span class="sxs-lookup"><span data-stu-id="4d746-120">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="4d746-121">在電子郵件訊息中，它會取代會議詳細資料中的線上會議區塊。</span><span class="sxs-lookup"><span data-stu-id="4d746-121">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="4d746-122">它會代表會議召集人，將會議的更新版本傳送給所有會議收件者。</span><span class="sxs-lookup"><span data-stu-id="4d746-122">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="4d746-123">會議受邀者會收到一份會議更新，其電子郵件中會包含更新的會議座標。</span><span class="sxs-lookup"><span data-stu-id="4d746-123">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![由 MMS 更新的會議區塊](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="4d746-125">從 MMS 觸發起，一般需要大約 2 小時，直到使用者的會議移移。</span><span class="sxs-lookup"><span data-stu-id="4d746-125">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="4d746-126">不過，如果使用者的會議數量很多，可能需要較長的時間。</span><span class="sxs-lookup"><span data-stu-id="4d746-126">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="4d746-127">如果 MMS 在移移使用者的一或多個會議時發生錯誤，它會在 24 小時內定期重試 9 次。</span><span class="sxs-lookup"><span data-stu-id="4d746-127">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="4d746-128">**附注：**</span><span class="sxs-lookup"><span data-stu-id="4d746-128">**Notes**:</span></span>

- <span data-ttu-id="4d746-129">當會議移移時，MMS 會取代線上會議資訊區塊中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="4d746-129">MMS replaces everything in the online meeting information block when a meeting is migrated.</span></span> <span data-ttu-id="4d746-130">因此，如果使用者已編輯該區塊，其變更將會被覆蓋。</span><span class="sxs-lookup"><span data-stu-id="4d746-130">Therefore, if a user has edited that block, their changes will be overwritten.</span></span> <span data-ttu-id="4d746-131">他們在線上會議資訊區塊以外的會議詳細資料中擁有的任何內容都不受影響。</span><span class="sxs-lookup"><span data-stu-id="4d746-131">Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span> <span data-ttu-id="4d746-132">這表示任何附加至會議邀請的檔案仍然會包含在內。</span><span class="sxs-lookup"><span data-stu-id="4d746-132">This means any files attached to the meeting invite will still be included.</span></span> 
- <span data-ttu-id="4d746-133">只有商務用 Skype或 Microsoft Teams 會議，方法是按一下 Outlook 網頁中的新增 Skype會議按鈕，或是使用 Outlook 的 Skype 會議附加元件來排程的會議。</span><span class="sxs-lookup"><span data-stu-id="4d746-133">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="4d746-134">如果使用者複製並Skype將線上會議資訊從一個會議複製到新會議，新會議將不會更新，因為原始服務沒有會議。</span><span class="sxs-lookup"><span data-stu-id="4d746-134">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="4d746-135">建立或附加至會議的會議內容 (白板、投票等內容) MMS 執行之後不會保留。</span><span class="sxs-lookup"><span data-stu-id="4d746-135">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="4d746-136">如果您的會議召集人事先將內容附加至會議，則 MMS 執行之後，必須重新重新組織內容。</span><span class="sxs-lookup"><span data-stu-id="4d746-136">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="4d746-137">在日曆專案以及會議內部共用會議筆記的連結Skype也會被覆蓋。</span><span class="sxs-lookup"><span data-stu-id="4d746-137">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="4d746-138">請注意，儲存在 OneNote 中的實際會議記事仍然會存在;只有已覆蓋之共用筆記的連結。</span><span class="sxs-lookup"><span data-stu-id="4d746-138">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="4d746-139">超過 250 位出席者的會議 (包括) 將不會移移。</span><span class="sxs-lookup"><span data-stu-id="4d746-139">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="4d746-140">邀請內文中的某些 UNICODE 字元可能無法正確更新為下列其中一個特殊字元：1、1/2、。</span><span class="sxs-lookup"><span data-stu-id="4d746-140">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="4d746-141">觸發使用者的 MMS</span><span class="sxs-lookup"><span data-stu-id="4d746-141">Triggering MMS for a user</span></span>

<span data-ttu-id="4d746-142">本節說明在下列每一種情況下觸發 MMS 時會發生什麼情況：</span><span class="sxs-lookup"><span data-stu-id="4d746-142">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="4d746-143">當使用者從內部部署移至雲端時</span><span class="sxs-lookup"><span data-stu-id="4d746-143">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="4d746-144">當系統管理員變更使用者的音訊會議設定時</span><span class="sxs-lookup"><span data-stu-id="4d746-144">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="4d746-145">當使用者在 TeamsUpgradePolicy 中的模式設定為 TeamsOnly 或 SfBWithTeamsCollabAndMeetings (使用 Powershell 或 Teams 系統管理入口網站) </span><span class="sxs-lookup"><span data-stu-id="4d746-145">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="4d746-146">當您使用 PowerShell Cmdlet 時，請Start-CsExMeetingMigration</span><span class="sxs-lookup"><span data-stu-id="4d746-146">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="4d746-147">將內部部署使用者移至雲端時更新會議</span><span class="sxs-lookup"><span data-stu-id="4d746-147">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="4d746-148">這是最常見的案例，MMS 可協助使用者建立更順暢的轉場效果。</span><span class="sxs-lookup"><span data-stu-id="4d746-148">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="4d746-149">若沒有會議移轉，使用者在內部商務用 Skype Server中組織的現有會議在使用者移至線上後就無法再使用。</span><span class="sxs-lookup"><span data-stu-id="4d746-149">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="4d746-150">因此，當您使用內部部署管理工具 (系統管理控制台) 將使用者移至雲端時，現有的會議會自動移至雲端， `Move-CsUser` 如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d746-150">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="4d746-151">如果 `MoveToTeams` 已指定切換，會議會直接移Teams `Move-CsUser` 使用者將位於 TeamsOnly 模式中。</span><span class="sxs-lookup"><span data-stu-id="4d746-151">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="4d746-152">使用此開關需要在 2015 商務用 Skype Server CU8 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4d746-152">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="4d746-153">這些使用者仍可使用商務用 Skype用戶端或會議應用程式加入商務用 Skype會議Skype會議。</span><span class="sxs-lookup"><span data-stu-id="4d746-153">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="4d746-154">否則會議會移商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="4d746-154">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="4d746-155">在這兩種情況下，如果使用者在移至雲端之前已指派音訊會議授權，會議會以撥入座標建立。</span><span class="sxs-lookup"><span data-stu-id="4d746-155">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="4d746-156">如果您將使用者從內部部署移至雲端，而且想要該使用者使用音訊會議，建議您先指派音訊會議，然後再移動使用者，這樣只會觸發 1 個會議移轉。</span><span class="sxs-lookup"><span data-stu-id="4d746-156">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="4d746-157">當使用者的音訊會議設定變更時更新會議</span><span class="sxs-lookup"><span data-stu-id="4d746-157">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="4d746-158">在下列情況下，MMS 會更新現有的商務用 Skype Microsoft Teams會議，以新增、移除或修改撥入座標：</span><span class="sxs-lookup"><span data-stu-id="4d746-158">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="4d746-159">當您指派或移除 Microsoft Audio 會議服務授權給使用者時，且該使用者並未為協力廠商音訊會議提供者啟用。</span><span class="sxs-lookup"><span data-stu-id="4d746-159">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="4d746-160">當您將使用者的音訊會議提供者從任何其他提供者變更為 Microsoft 時，只要該使用者獲得 Microsoft 音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="4d746-160">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="4d746-161">詳細資訊，請參閱指派 [Microsoft 做為音訊會議提供者](./assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="4d746-161">For more information, see [Assign Microsoft as the audio conferencing provider](./assign-microsoft-as-the-audio-conferencing-provider.md).</span></span> <span data-ttu-id="4d746-162">另請注意，如先前宣佈的，協力廠商音訊會議提供者 [ACP] 的支援計畫在 2019 年 4 月 1 日[結束。](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)</span><span class="sxs-lookup"><span data-stu-id="4d746-162">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md).</span></span>
- <span data-ttu-id="4d746-163">當您為使用者啟用或停用音訊會議時。</span><span class="sxs-lookup"><span data-stu-id="4d746-163">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="4d746-164">當您變更或重設已設定為使用公用會議之使用者的會議 ID 時。</span><span class="sxs-lookup"><span data-stu-id="4d746-164">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="4d746-165">當您將使用者移至新的音訊會議橋接器時。</span><span class="sxs-lookup"><span data-stu-id="4d746-165">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="4d746-166">當音訊會議橋接器的電話號碼未指定時。</span><span class="sxs-lookup"><span data-stu-id="4d746-166">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="4d746-167">這是需要額外步驟的複雜案例。</span><span class="sxs-lookup"><span data-stu-id="4d746-167">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="4d746-168">詳細資訊，請參閱 [變更音訊會議橋接器上的電話號碼](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="4d746-168">For more information, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="4d746-169">並非所有使用者的音訊會議設定變更都觸發 MMS。</span><span class="sxs-lookup"><span data-stu-id="4d746-169">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="4d746-170">具體來說，下列兩項變更不會導致 MMS 更新會議：</span><span class="sxs-lookup"><span data-stu-id="4d746-170">Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="4d746-171">當您變更會議召集人的 SIP 位址時 (SIP 使用者名稱或 SIP 網域) </span><span class="sxs-lookup"><span data-stu-id="4d746-171">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="4d746-172">當您使用命令變更組織的會議 `Update-CsTenantMeetingUrl` URL 時。</span><span class="sxs-lookup"><span data-stu-id="4d746-172">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="4d746-173">指派 TeamsUpgradePolicy 時更新會議</span><span class="sxs-lookup"><span data-stu-id="4d746-173">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="4d746-174">根據預設，當使用者獲與 或 的實例時，會自動觸發會議 `TeamsUpgradePolicy` `mode=TeamsOnly` 移移 `mode= SfBWithTeamsCollabAndMeetings` 。</span><span class="sxs-lookup"><span data-stu-id="4d746-174">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="4d746-175">如果您在授予任一模式時不想遷移會議，請于 (中指定是否使用 PowerShell) ，或取消勾選方塊以在設定使用者的並存模式時 (如果使用 Teams 系統管理入口網站 `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy`) 。</span><span class="sxs-lookup"><span data-stu-id="4d746-175">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="4d746-176">另請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="4d746-176">Also note the following:</span></span>

- <span data-ttu-id="4d746-177">只有在您為特定使用者授予時，才能 `TeamsUpgradePolicy` 啟用會議移移。</span><span class="sxs-lookup"><span data-stu-id="4d746-177">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="4d746-178">如果您以 `TeamsUpgradePolicy` 租使用者為基礎或以租使用者為基礎授予，則會議 `mode=TeamsOnly` 移移 `mode=SfBWithTeamsCollabAndMeetings` 不會被援用。 </span><span class="sxs-lookup"><span data-stu-id="4d746-178">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="4d746-179">使用者只能在使用者位於線上時獲得 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="4d746-179">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="4d746-180">內部部署使用者必須使用先前所述 `Move-CsUser` 移動。</span><span class="sxs-lookup"><span data-stu-id="4d746-180">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="4d746-181">授予 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 模式不會將現有的 Teams 會議轉換為商務用 Skype會議。</span><span class="sxs-lookup"><span data-stu-id="4d746-181">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="4d746-182">透過 PowerShell Cmdlet 手動觸發會議移轉</span><span class="sxs-lookup"><span data-stu-id="4d746-182">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="4d746-183">除了自動會議移轉之外，系統管理員也可以執行 Cmdlet，手動觸發使用者的會議移轉 `Start-CsExMeetingMigration` 。</span><span class="sxs-lookup"><span data-stu-id="4d746-183">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="4d746-184">此 Cmdlet 會為指定的使用者排排移轉要求佇列。</span><span class="sxs-lookup"><span data-stu-id="4d746-184">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="4d746-185">除了必要的參數之外，它需要兩個選擇性參數，以及 ，這允許您 `Identity` `SourceMeetingType` `TargetMeetingType` 指定如何遷移會議：</span><span class="sxs-lookup"><span data-stu-id="4d746-185">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="4d746-186">**TargetMeetingType：**</span><span class="sxs-lookup"><span data-stu-id="4d746-186">**TargetMeetingType:**</span></span>

- <span data-ttu-id="4d746-187">使用 `TargetMeetingType Current` 指定會議商務用 Skype保留商務用 Skype，Teams會議Teams保留。</span><span class="sxs-lookup"><span data-stu-id="4d746-187">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="4d746-188">不過，音訊會議座標可能會變更，而且任何內部部署商務用 Skype會議都會移商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="4d746-188">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="4d746-189">這是 TargetMeetingType 的預設值。</span><span class="sxs-lookup"><span data-stu-id="4d746-189">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="4d746-190">使用 指定任何現有的會議都必須移入 Teams，無論會議是在 商務用 Skype 線上或內部部署中託管，也不論是否需要任何音訊會議 `TargetMeetingType Teams` 更新。</span><span class="sxs-lookup"><span data-stu-id="4d746-190">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="4d746-191">**SourceMeetingType：**</span><span class="sxs-lookup"><span data-stu-id="4d746-191">**SourceMeetingType:**</span></span>
- <span data-ttu-id="4d746-192">使用表示只有商務用 Skype會議 (內部部署或線上) `SourceMeetingType SfB` 更新。</span><span class="sxs-lookup"><span data-stu-id="4d746-192">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="4d746-193">使用 `SourceMeetingType Teams` 表示只有Teams會議應該更新。</span><span class="sxs-lookup"><span data-stu-id="4d746-193">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="4d746-194">使用 `SourceMeetingType All` 表示應該商務用 Skype會議Teams會議。</span><span class="sxs-lookup"><span data-stu-id="4d746-194">Using `SourceMeetingType All` indicates that both Skype for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="4d746-195">這是 SourceMeetingType 的預設值。</span><span class="sxs-lookup"><span data-stu-id="4d746-195">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="4d746-196">以下範例顯示如何針對使用者啟動會議移 ashaw@contoso.com，讓所有會議移Teams：</span><span class="sxs-lookup"><span data-stu-id="4d746-196">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="4d746-197">管理 MMS</span><span class="sxs-lookup"><span data-stu-id="4d746-197">Managing MMS</span></span>

<span data-ttu-id="4d746-198">您可以使用 Windows PowerShell，檢查進行中的移移狀態、手動觸發會議移移，以及完全停用移移。</span><span class="sxs-lookup"><span data-stu-id="4d746-198">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="4d746-199">檢查會議移移的狀態</span><span class="sxs-lookup"><span data-stu-id="4d746-199">Check the status of meeting migrations</span></span>

<span data-ttu-id="4d746-200">您可以使用 `Get-CsMeetingMigrationStatus` Cmdlet 檢查會議移轉的狀態。</span><span class="sxs-lookup"><span data-stu-id="4d746-200">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="4d746-201">以下是一些範例。</span><span class="sxs-lookup"><span data-stu-id="4d746-201">Below are some examples.</span></span>

- <span data-ttu-id="4d746-202">若要取得所有 MMS 移移的摘要狀態，請執行下列命令，提供所有移移狀態的表格式視圖：</span><span class="sxs-lookup"><span data-stu-id="4d746-202">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="4d746-203">若要取得特定時段內所有移移的完整詳細資料，請使用 和 `StartTime` `EndTime` 參數。</span><span class="sxs-lookup"><span data-stu-id="4d746-203">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="4d746-204">例如，下列命令會針對從 2018 年 10 月 1 日到 2018 年 10 月 8 日進行的所有移移，返回完整詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4d746-204">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="4d746-205">若要檢查特定使用者的移移狀態，請使用 `Identity` 參數。</span><span class="sxs-lookup"><span data-stu-id="4d746-205">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="4d746-206">例如，下列命令會返回使用者 ashaw@contoso.com：</span><span class="sxs-lookup"><span data-stu-id="4d746-206">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="4d746-207">如果您看到任何移轉失敗，請採取動作，儘快解決這些問題，因為使用者無法撥入這些使用者組織的會議，直到您解決它們。</span><span class="sxs-lookup"><span data-stu-id="4d746-207">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="4d746-208">如果 `Get-CsMeetingMigrationStatus` 顯示失敗狀態的任何移移，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="4d746-208">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="4d746-209">判斷受影響的使用者。</span><span class="sxs-lookup"><span data-stu-id="4d746-209">Determine which users are affected.</span></span> <span data-ttu-id="4d746-210">執行下列命令以取得受影響的使用者清單，以及報告的特定錯誤：</span><span class="sxs-lookup"><span data-stu-id="4d746-210">Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. <span data-ttu-id="4d746-211">針對每個受影響的使用者，執行會議移移工具，以手動移移其會議。</span><span class="sxs-lookup"><span data-stu-id="4d746-211">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="4d746-212">如果移移仍然無法與會議移移工具一起使用，則有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="4d746-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="4d746-213">讓使用者在會議中Skype會議。</span><span class="sxs-lookup"><span data-stu-id="4d746-213">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="4d746-214">[請與支援人員聯繫](/microsoft-365/Admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="4d746-214">[Contact support](/microsoft-365/Admin/contact-support-for-business-products).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="4d746-215">啟用及停用 MMS</span><span class="sxs-lookup"><span data-stu-id="4d746-215">Enabling and disabling MMS</span></span>

<span data-ttu-id="4d746-216">MMS 預設會針對所有組織啟用，但可以停用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d746-216">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="4d746-217">完全停用租使用者。</span><span class="sxs-lookup"><span data-stu-id="4d746-217">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="4d746-218">僅針對與音訊會議相關的變更停用。</span><span class="sxs-lookup"><span data-stu-id="4d746-218">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="4d746-219">在這種情況下，當使用者從內部部署移遷移到雲端，或當您在 中授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式時，MMS 仍然會執行 `TeamsUpgradePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="4d746-219">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="4d746-220">例如，您可能會想要手動遷移所有會議，或暫時停用 MMS，同時大幅變更貴組織的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="4d746-220">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="4d746-221">若要查看貴組織是否已啟用 MMS，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="4d746-221">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="4d746-222">如果參數為 ，MMS `MeetingMigrationEnabled` 會啟用 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="4d746-222">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```PowerShell
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="4d746-223">若要完全啟用或停用 MMS，請使用 `Set-CsTenantMigrationConfiguration` 命令。</span><span class="sxs-lookup"><span data-stu-id="4d746-223">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="4d746-224">例如，若要停用 MMS，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4d746-224">For example, to disable MMS, run the following command:</span></span>

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="4d746-225">如果組織中已啟用 MMS，而且您想要檢查是否已啟用音訊會議更新，請檢查 輸出中的參數 `AutomaticallyMigrateUserMeetings` 值 `Get-CsOnlineDialInConferencingTenantSettings` 。</span><span class="sxs-lookup"><span data-stu-id="4d746-225">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="4d746-226">若要啟用或停用音訊會議用 MMS，請使用 `Set-CsOnlineDialInConferencingTenantSettings` 。</span><span class="sxs-lookup"><span data-stu-id="4d746-226">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="4d746-227">例如，若要停用音訊會議用 MMS，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4d746-227">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="4d746-228">相關主題</span><span class="sxs-lookup"><span data-stu-id="4d746-228">Related topics</span></span>

[<span data-ttu-id="4d746-229">嘗試或購買音訊會議Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="4d746-229">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="4d746-230">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="4d746-230">Move users between on-premises and cloud</span></span>](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
