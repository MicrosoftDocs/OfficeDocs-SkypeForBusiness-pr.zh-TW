---
title: Teams 中使用者的目前狀態
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 瞭解 Teams 中的 [目前狀態] 及 [目前狀態] 功能的系統管理設定。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff5a13d6b31527138b71d2ad3b2387f827933eda
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616947"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="31c1a-103">Teams 中使用者的目前狀態</span><span class="sxs-lookup"><span data-stu-id="31c1a-103">User presence in Teams</span></span>

<span data-ttu-id="31c1a-104">顯示狀態是使用者在 Microsoft Teams (以及整個 Microsoft 365 或 Office 365) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="31c1a-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365).</span></span> <span data-ttu-id="31c1a-105">[目前狀態] 表示使用者目前的可用性與其他使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="31c1a-105">Presence indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="31c1a-106">依預設，貴組織中任何有使用 Teams 的人都可以 (幾乎即時) 查看其他使用者是否在線上。</span><span class="sxs-lookup"><span data-stu-id="31c1a-106">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span> <span data-ttu-id="31c1a-107">當您重新整理行動裝置上的頁面時，線上和傳統版會即時更新 [目前狀態]。</span><span class="sxs-lookup"><span data-stu-id="31c1a-107">Presence is updated in real time on the web and desktop versions when you refresh the page on mobile.</span></span>

 > [!Note]
 > <span data-ttu-id="31c1a-108">如需有關不同平台上 Teams 使用者設定檔的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="31c1a-108">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="31c1a-109">Teams 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="31c1a-109">Presence states in Teams</span></span>

|<span data-ttu-id="31c1a-110">使用者設定</span><span class="sxs-lookup"><span data-stu-id="31c1a-110">User configured</span></span>|<span data-ttu-id="31c1a-111">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="31c1a-111">App configured</span></span>|
|:--- |:---|
| ![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="31c1a-113">有空</span><span class="sxs-lookup"><span data-stu-id="31c1a-113">Available</span></span>|![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="31c1a-115">有空</span><span class="sxs-lookup"><span data-stu-id="31c1a-115">Available</span></span>|
|| ![空心圓圈綠色核取記號，表示外出並有空](media/Presence_Available_OOF.png) <span data-ttu-id="31c1a-117">有空，外出。</span><span class="sxs-lookup"><span data-stu-id="31c1a-117">Available, Out of Office.</span></span> <span data-ttu-id="31c1a-118">附注：在使用者設定「自動回復」的期間內，系統會自動設定為 [外出]。</span><span class="sxs-lookup"><span data-stu-id="31c1a-118">Note: Out of office is automatically set for the periods of time where the user sets "automatic replies".</span></span> <span data-ttu-id="31c1a-119">如果使用者是在這些時段內使用應用程式，可能會顯示雙重顯示 (例如「外出，有空」)。</span><span class="sxs-lookup"><span data-stu-id="31c1a-119">If the user is using the app during these periods of time, a dual presence might be shown, such as "Out of office, available".</span></span> |
|  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="31c1a-121">忙碌</span><span class="sxs-lookup"><span data-stu-id="31c1a-121">Busy</span></span> |  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="31c1a-123">忙碌</span><span class="sxs-lookup"><span data-stu-id="31c1a-123">Busy</span></span>  |
|| ![紅色實心圓圈，表示通話中忙碌](media/Presence_Busy.png) <span data-ttu-id="31c1a-125">電話中</span><span class="sxs-lookup"><span data-stu-id="31c1a-125">In a call</span></span>|
|| ![紅色實心圓圈，表示會議中忙碌](media/Presence_Busy.png) <span data-ttu-id="31c1a-127">會議中</span><span class="sxs-lookup"><span data-stu-id="31c1a-127">In a meeting</span></span> |
|| ![紅色空心圓圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="31c1a-129">通話中，外出</span><span class="sxs-lookup"><span data-stu-id="31c1a-129">On a call, out of office</span></span>|
|  ![紅色圓圈加白線，表示請勿打擾](media/Presence_DND.png) <span data-ttu-id="31c1a-131">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="31c1a-131">Do not disturb</span></span> ||
|| ![紅色圓圈加白線，表示簡報中](media/Presence_DND.png) <span data-ttu-id="31c1a-133">簡報中</span><span class="sxs-lookup"><span data-stu-id="31c1a-133">Presenting</span></span>|
|| ![紅色圓圈加白線，表示專注](media/Presence_DND.png) <span data-ttu-id="31c1a-135">專注。</span><span class="sxs-lookup"><span data-stu-id="31c1a-135">Focusing.</span></span> <span data-ttu-id="31c1a-136">當使用者在行事曆中排程 [MyAnalytics/Insights] 時，就會進入 [專注] 功能。</span><span class="sxs-lookup"><span data-stu-id="31c1a-136">Focus happens when the users schedule focus time in MyAnalytics/Insights in their calendars.</span></span>|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="31c1a-138">離開</span><span class="sxs-lookup"><span data-stu-id="31c1a-138">Away</span></span>| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="31c1a-140">離開</span><span class="sxs-lookup"><span data-stu-id="31c1a-140">Away</span></span>|
|| <span data-ttu-id="31c1a-141">![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次看到的 *時間*</span><span class="sxs-lookup"><span data-stu-id="31c1a-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黃色時鐘圖示，表示離開，馬上回來](media/Presence_Away.png) <span data-ttu-id="31c1a-143">馬上回來</span><span class="sxs-lookup"><span data-stu-id="31c1a-143">Be right back</span></span>| |
|![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) <span data-ttu-id="31c1a-145">顯示為離線</span><span class="sxs-lookup"><span data-stu-id="31c1a-145">Appear offline</span></span>|![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) <span data-ttu-id="31c1a-147">離線。</span><span class="sxs-lookup"><span data-stu-id="31c1a-147">Offline.</span></span>  <span data-ttu-id="31c1a-148">當使用者未在任何裝置上登入達數分鐘，便會顯示為 [離線]。</span><span class="sxs-lookup"><span data-stu-id="31c1a-148">When users aren't logged in on any of their devices for a few minutes, they appear offline.</span></span> | |
|| ![空心灰色圓圈，表示狀態不明](media/Presence_Unknown.png) <span data-ttu-id="31c1a-150">狀態不明</span><span class="sxs-lookup"><span data-stu-id="31c1a-150">Status unknown</span></span>|
|| ![紫色圓圈加箭號，表示外出](media/Presence_OOF.png) <span data-ttu-id="31c1a-152">外出。</span><span class="sxs-lookup"><span data-stu-id="31c1a-152">Out of Office.</span></span> <span data-ttu-id="31c1a-153">設定為自動回復時，會使用 [外出] 功能。</span><span class="sxs-lookup"><span data-stu-id="31c1a-153">Out of Office is used when an automatic reply is set.</span></span> <span data-ttu-id="31c1a-154">(只可供 Outlook 使用)</span><span class="sxs-lookup"><span data-stu-id="31c1a-154">(Available in Outlook only.)</span></span> |
|||

<span data-ttu-id="31c1a-155">應用程式設定的目前狀態是根據使用者活動 (有空、離開)、Outlook 行事曆狀態 (會議中)、或是 Teams 應用程式狀態 (通話中、簡報中)。</span><span class="sxs-lookup"><span data-stu-id="31c1a-155">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="31c1a-156">當您在行事曆中使用 [焦點模式] 時，人員會在 Teams 上看到顯示為 **[專注中]** 的狀態。</span><span class="sxs-lookup"><span data-stu-id="31c1a-156">When you're in focus mode based on your calendar, **Focusing** will be the state people see in Teams.</span></span> <span data-ttu-id="31c1a-157">在其他產品中，焦點模式會顯示為 **請勿打擾**。</span><span class="sxs-lookup"><span data-stu-id="31c1a-157">Focus mode will display as **Do not disturb** in other products.</span></span>

<span data-ttu-id="31c1a-158">當您鎖定電腦或當您的電腦進入閒置或睡眠模式時，您目前的顯示狀態會變更為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="31c1a-158">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="31c1a-159">在行動裝置上，只要 Teams 應用程式在背景作業時，您的顯示狀態即會變更為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="31c1a-159">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="31c1a-160">不管使用者目前狀態為何，都會收到所有在 Teams 中傳送給他們的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="31c1a-160">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="31c1a-161">如果他人傳送郵件給使用者時使用者已離線，聊天訊息會在使用者下次上線時顯示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="31c1a-161">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="31c1a-162">如果使用者狀態設為 [請勿打擾]，使用者仍然會收到交談訊息，但不會顯示橫幅通知。</span><span class="sxs-lookup"><span data-stu-id="31c1a-162">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="31c1a-163">使用者在所有狀態下都會收到通話，但「請勿打擾」狀態除外，在這種狀態下，通話會送往他們的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="31c1a-163">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="31c1a-164">如果受話方封鎖來電者，通話將不會傳送，且來電者看到的受話方目前狀態是「離線」。</span><span class="sxs-lookup"><span data-stu-id="31c1a-164">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="31c1a-165">使用者可以到 Teams 的 [設定]  >  [隱私權]，將人員新增至其優先存取清單。</span><span class="sxs-lookup"><span data-stu-id="31c1a-165">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="31c1a-166">具有優先存取的人員可以與使用者聯繫，即使該使用者的狀態設定為 [請勿打擾]。</span><span class="sxs-lookup"><span data-stu-id="31c1a-166">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

### <a name="dual-presence"></a><span data-ttu-id="31c1a-167">雙重狀態</span><span class="sxs-lookup"><span data-stu-id="31c1a-167">Dual presence</span></span>

  <span data-ttu-id="31c1a-168">目前的方式適用于多數使用者，是由行事曆或裝置事件中的事件 (例如通話) 所促成。</span><span class="sxs-lookup"><span data-stu-id="31c1a-168">The way presence works for most users is motivated by the events in the calendar or device events, such as a call.</span></span> <span data-ttu-id="31c1a-169">使用者可以手動設定狀態(且該設定具有一段到期時間)以在 UI 中覆寫此狀態。</span><span class="sxs-lookup"><span data-stu-id="31c1a-169">The user can override this status in the UI by manually setting states, which have some expiration time.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="31c1a-170">使用者已設定狀態到期日</span><span class="sxs-lookup"><span data-stu-id="31c1a-170">User configured states expiration</span></span>

<span data-ttu-id="31c1a-171">當使用者選取特定的目前狀態時，它會優先于所有應用程式活動更新。</span><span class="sxs-lookup"><span data-stu-id="31c1a-171">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="31c1a-172">例如，如果使用者將自己設定為「請勿打擾」，則即使她出席會議或應答通話，其目前狀態仍然會維持為「請勿打擾」。</span><span class="sxs-lookup"><span data-stu-id="31c1a-172">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="31c1a-173">使用者設定的狀態在 Teams 中有預設的到期設定，以避免使用者在一段時間後可能會顯示出不相關的狀態。</span><span class="sxs-lookup"><span data-stu-id="31c1a-173">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="31c1a-174">使用者設定狀態</span><span class="sxs-lookup"><span data-stu-id="31c1a-174">User configured state</span></span>|<span data-ttu-id="31c1a-175">預設到期日</span><span class="sxs-lookup"><span data-stu-id="31c1a-175">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="31c1a-176">忙碌</span><span class="sxs-lookup"><span data-stu-id="31c1a-176">Busy</span></span>|<span data-ttu-id="31c1a-177">1 天</span><span class="sxs-lookup"><span data-stu-id="31c1a-177">1 day</span></span>|
| <span data-ttu-id="31c1a-178">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="31c1a-178">Do not disturb</span></span>|<span data-ttu-id="31c1a-179">1 天</span><span class="sxs-lookup"><span data-stu-id="31c1a-179">1 day</span></span>|
| <span data-ttu-id="31c1a-180">其他</span><span class="sxs-lookup"><span data-stu-id="31c1a-180">Others</span></span>|<span data-ttu-id="31c1a-181">7 天</span><span class="sxs-lookup"><span data-stu-id="31c1a-181">7 days</span></span>|
|||

> [!NOTE]
> <span data-ttu-id="31c1a-182">使用者也可以為其目前狀態手動設定持續時間。</span><span class="sxs-lookup"><span data-stu-id="31c1a-182">A user can also configure manually a duration for her presence.</span></span> <span data-ttu-id="31c1a-183">例如，使用者可以將自己設定為 [顯示為離線] 直至明天早上。</span><span class="sxs-lookup"><span data-stu-id="31c1a-183">For instance, a user can set herself as Appear offline until tomorrow morning.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="31c1a-184">比較商務用 Skype 與 Teams 中的管理設定</span><span class="sxs-lookup"><span data-stu-id="31c1a-184">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="31c1a-185">下列的商務用 Skype 管理設定與 Teams 不同：</span><span class="sxs-lookup"><span data-stu-id="31c1a-185">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="31c1a-186">在 Teams 中，組織的使用者一律啟用目前狀態共用。</span><span class="sxs-lookup"><span data-stu-id="31c1a-186">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="31c1a-187">Teams 不提供「隱私」設定功能 (該功能允許您訂定誰可查看目前狀態)。</span><span class="sxs-lookup"><span data-stu-id="31c1a-187">Privacy (where you define who can see presence) configuration isn't available in Teams.</span></span>
- <span data-ttu-id="31c1a-188">Teams 中的使用者一律啟用與所有人 (包括同盟服務) 共用目前狀態。</span><span class="sxs-lookup"><span data-stu-id="31c1a-188">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="31c1a-189">他們的連絡人清單 (如果他們在商務用 Skype 中有此清單) 會顯示在 [聊天] > [連絡人] 底下或在 [通話] > [連絡人] 底下。</span><span class="sxs-lookup"><span data-stu-id="31c1a-189">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="31c1a-190">Teams 中的使用者一律啟用用戶端的「請勿打擾」和「突破」功能。</span><span class="sxs-lookup"><span data-stu-id="31c1a-190">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="31c1a-191">當 Teams 與 Outlook 整合時，一律為使用者啟用行事曆 (包括外出和其他行事曆資訊) 整合。</span><span class="sxs-lookup"><span data-stu-id="31c1a-191">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="31c1a-192">如果組織也使用商務用 Skype，Teams 中的使用者一律啟用 [上次看到] 或 [離開時間]。</span><span class="sxs-lookup"><span data-stu-id="31c1a-192">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="31c1a-193">目前不支援 Teams 系統管理員自訂這些設定的功能。</span><span class="sxs-lookup"><span data-stu-id="31c1a-193">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a><span data-ttu-id="31c1a-194">比較 Microsoft Outlook 與 Teams 中的管理設定</span><span class="sxs-lookup"><span data-stu-id="31c1a-194">Admin settings in Teams compared to Microsoft Outlook</span></span>

<span data-ttu-id="31c1a-195">針對相同組織中的聯絡人，Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="31c1a-195">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later for contacts in the same organization.</span></span>

<span data-ttu-id="31c1a-196">如果使用者帳戶的升級模式原則設定為 TeamsOnly，則 Outlook 會與 Teams 交談以取得目前狀態。</span><span class="sxs-lookup"><span data-stu-id="31c1a-196">If the upgrade mode policy of the user account is set to TeamsOnly, Outlook talks to Teams to get presence.</span></span> <span data-ttu-id="31c1a-197">如果使用者帳戶未設定為 TeamsOnly，則 Outlook 會與商務用 Skype 交談。</span><span class="sxs-lookup"><span data-stu-id="31c1a-197">If the user account isn't set to TeamsOnly, then Outlook talks to Skype for Business.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="31c1a-198">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="31c1a-198">Coexistence with Skype for Business</span></span>

<span data-ttu-id="31c1a-199">請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織使用商務用 Skype 時 Teams的運作方式詳細資料。</span><span class="sxs-lookup"><span data-stu-id="31c1a-199">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses Skype for Business.</span></span>
