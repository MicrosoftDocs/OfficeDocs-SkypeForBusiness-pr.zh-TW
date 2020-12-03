---
title: Teams 中使用者的目前狀態
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 瞭解團隊中的目前狀態和目前狀態功能的管理設定。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: cacdcb89af5d588489028ef306a5a7f24b89f4d4
ms.sourcegitcommit: e285f55a7e9563a2ab764d44805513d7bf1a3851
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "49557947"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="22518-103">Teams 中使用者的目前狀態</span><span class="sxs-lookup"><span data-stu-id="22518-103">User presence in Teams</span></span>

<span data-ttu-id="22518-104">[目前狀態] 是 Microsoft 團隊 (與整個 Microsoft 365 或 Office 365) 中使用者設定檔的一部分。</span><span class="sxs-lookup"><span data-stu-id="22518-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365).</span></span> <span data-ttu-id="22518-105">[目前狀態] 表示使用者目前的可用性與其他使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="22518-105">Presence indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="22518-106">依預設，貴組織中任何有使用 Teams 的人都可以 (幾乎即時) 查看其他使用者是否在線上。</span><span class="sxs-lookup"><span data-stu-id="22518-106">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span> <span data-ttu-id="22518-107">當您重新整理行動裝置上的頁面時，目前狀態會在網頁和桌上出版本上即時更新。</span><span class="sxs-lookup"><span data-stu-id="22518-107">Presence is updated in real time on the web and desktop versions when you refresh the page on mobile.</span></span>

 > [!Note]
 > <span data-ttu-id="22518-108">如需不同平臺上團隊使用者設定檔的詳細資訊，請參閱 [依平臺的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="22518-108">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="22518-109">Teams 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="22518-109">Presence states in Teams</span></span>

|<span data-ttu-id="22518-110">使用者設定</span><span class="sxs-lookup"><span data-stu-id="22518-110">User configured</span></span>|<span data-ttu-id="22518-111">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="22518-111">App configured</span></span>|
|:--- |:---|
| ![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="22518-113">有空</span><span class="sxs-lookup"><span data-stu-id="22518-113">Available</span></span>|![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="22518-115">有空</span><span class="sxs-lookup"><span data-stu-id="22518-115">Available</span></span>|
|| ![空心圓圈綠色核取記號，表示外出並有空](media/Presence_Available_OOF.png) <span data-ttu-id="22518-117">可用、不在辦公室。</span><span class="sxs-lookup"><span data-stu-id="22518-117">Available, Out of Office.</span></span> <span data-ttu-id="22518-118">注意：在使用者設定「自動回復」的時段內，系統會自動設定 [不在辦公室]。</span><span class="sxs-lookup"><span data-stu-id="22518-118">Note: Out of office is automatically set for the periods of time where the user sets "automatic replies".</span></span> <span data-ttu-id="22518-119">如果使用者在這段時間內使用 app，可能會顯示雙重目前狀態，例如「不在辦公室」。</span><span class="sxs-lookup"><span data-stu-id="22518-119">If the user is using the app during these periods of time, a dual presence might be shown, such as "Out of office, available".</span></span> |
|  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="22518-121">忙碌</span><span class="sxs-lookup"><span data-stu-id="22518-121">Busy</span></span> |  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="22518-123">忙碌</span><span class="sxs-lookup"><span data-stu-id="22518-123">Busy</span></span>  |
|| ![紅色實心圓圈，表示通話中忙碌](media/Presence_Busy.png) <span data-ttu-id="22518-125">在通話中</span><span class="sxs-lookup"><span data-stu-id="22518-125">In a call</span></span>|
|| ![紅色實心圓圈，表示會議中忙碌](media/Presence_Busy.png) <span data-ttu-id="22518-127">會議中</span><span class="sxs-lookup"><span data-stu-id="22518-127">In a meeting</span></span> |
|| ![紅色空心圓圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="22518-129">通話中，外出</span><span class="sxs-lookup"><span data-stu-id="22518-129">On a call, out of office</span></span>|
|  ![紅色圓圈加白線，表示請勿打擾](media/Presence_DND.png) <span data-ttu-id="22518-131">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="22518-131">Do not disturb</span></span> ||
|| ![紅色圓圈加白線，表示簡報中](media/Presence_DND.png) <span data-ttu-id="22518-133">簡報中</span><span class="sxs-lookup"><span data-stu-id="22518-133">Presenting</span></span>|
|| ![紅色圓圈加白線，表示專注](media/Presence_DND.png) <span data-ttu-id="22518-135">致力.</span><span class="sxs-lookup"><span data-stu-id="22518-135">Focusing.</span></span> <span data-ttu-id="22518-136">當使用者在其行事曆中的 MyAnalytics/真知灼見中排程焦點時間時，就會發生焦點。</span><span class="sxs-lookup"><span data-stu-id="22518-136">Focus happens when the users schedule focus time in MyAnalytics/Insights in their calendars.</span></span>|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="22518-138">離開</span><span class="sxs-lookup"><span data-stu-id="22518-138">Away</span></span>| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="22518-140">離開</span><span class="sxs-lookup"><span data-stu-id="22518-140">Away</span></span>|
|| <span data-ttu-id="22518-141">![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次看到的 *時間*</span><span class="sxs-lookup"><span data-stu-id="22518-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黃色時鐘圖示，表示離開，馬上回來](media/Presence_Away.png) <span data-ttu-id="22518-143">馬上回來</span><span class="sxs-lookup"><span data-stu-id="22518-143">Be right back</span></span>| |
|![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) <span data-ttu-id="22518-145">顯示為離線</span><span class="sxs-lookup"><span data-stu-id="22518-145">Appear offline</span></span>|![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) <span data-ttu-id="22518-147">處於.</span><span class="sxs-lookup"><span data-stu-id="22518-147">Offline.</span></span>  <span data-ttu-id="22518-148">如果使用者沒有在任何裝置上登入，幾分鐘後，就會顯示為離線。</span><span class="sxs-lookup"><span data-stu-id="22518-148">When users aren't logged in on any of their devices for a few minutes, they appear offline.</span></span> | |
|| ![空心灰色圓圈，表示狀態不明](media/Presence_Unknown.png) <span data-ttu-id="22518-150">狀態不明</span><span class="sxs-lookup"><span data-stu-id="22518-150">Status unknown</span></span>|
|| ![紫色圓圈加箭號，表示外出](media/Presence_OOF.png) <span data-ttu-id="22518-152">[不在辦公室]。</span><span class="sxs-lookup"><span data-stu-id="22518-152">Out of Office.</span></span> <span data-ttu-id="22518-153">當您設定自動回復時，就會使用 [不在辦公室]。</span><span class="sxs-lookup"><span data-stu-id="22518-153">Out of Office is used when an automatic reply is set.</span></span> <span data-ttu-id="22518-154"> (僅適用于 Outlook。 ) </span><span class="sxs-lookup"><span data-stu-id="22518-154">(Available in Outlook only.)</span></span> |
|||

<span data-ttu-id="22518-155">App 設定的目前狀態是以使用者活動 (提供，離開) ，Outlook 行事曆狀態 (在會議) 中，或團隊 app 的狀態 (在通話中，提出) 。</span><span class="sxs-lookup"><span data-stu-id="22518-155">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="22518-156">當您是以您的行事曆為基礎的焦點模式 **時，焦點** 會是人員在團隊中看到的狀態。</span><span class="sxs-lookup"><span data-stu-id="22518-156">When you're in focus mode based on your calendar, **Focusing** will be the state people see in Teams.</span></span> <span data-ttu-id="22518-157">焦點模式將在其他產品中顯示為 [ **請勿打擾** ]。</span><span class="sxs-lookup"><span data-stu-id="22518-157">Focus mode will display as **Do not disturb** in other products.</span></span>

<span data-ttu-id="22518-158">當您鎖定電腦或電腦進入 [空閒] 或 [睡眠] 模式時，您的目前狀態會變更為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="22518-158">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="22518-159">在行動裝置上，只要團隊 app 在背景中，您的目前狀態就會變更為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="22518-159">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="22518-160">不管使用者目前狀態為何，都會收到所有在 Teams 中傳送給他們的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="22518-160">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="22518-161">如果他人傳送郵件給使用者時使用者已離線，聊天訊息會在使用者下次上線時顯示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="22518-161">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="22518-162">如果使用者狀態設定為 [請勿打擾]，使用者仍會收到聊天訊息，但不會顯示橫幅通知。</span><span class="sxs-lookup"><span data-stu-id="22518-162">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="22518-163">使用者會在除了 [請勿打擾] 以外的所有目前狀態狀態中接收來電，讓來電移至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="22518-163">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="22518-164">如果受話方封鎖來電者，通話將不會傳送，且來電者看到的受話方目前狀態是「離線」。</span><span class="sxs-lookup"><span data-stu-id="22518-164">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="22518-165">使用者可以到 Teams 的 [設定]  >  [隱私權]，將人員新增至其優先存取清單。</span><span class="sxs-lookup"><span data-stu-id="22518-165">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="22518-166">即使使用者的狀態設定為 [請勿打擾]，擁有優先順序存取權的人員也可以與使用者聯繫。</span><span class="sxs-lookup"><span data-stu-id="22518-166">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

### <a name="dual-presence"></a><span data-ttu-id="22518-167">雙重目前狀態</span><span class="sxs-lookup"><span data-stu-id="22518-167">Dual presence</span></span>

  <span data-ttu-id="22518-168">對於大多數使用者而言，目前狀態的運作方式是由行事曆或裝置事件（例如通話）中的事件所導致。</span><span class="sxs-lookup"><span data-stu-id="22518-168">The way presence works for most users is motivated by the events in the calendar or device events, such as a call.</span></span> <span data-ttu-id="22518-169">使用者可以透過手動設定狀態（有一些到期時間），在 UI 中覆寫此狀態。</span><span class="sxs-lookup"><span data-stu-id="22518-169">The user can override this status in the UI by manually setting states, which have some expiration time.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="22518-170">使用者設定的狀態到期日</span><span class="sxs-lookup"><span data-stu-id="22518-170">User configured states expiration</span></span>

<span data-ttu-id="22518-171">當使用者選取特定的目前狀態時，它會優先于任何 app 活動更新。</span><span class="sxs-lookup"><span data-stu-id="22518-171">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="22518-172">例如，如果使用者將自己設為 [請勿打擾]，即使她出席會議或接聽電話，她的目前狀態仍會保留為 [請勿打擾]。</span><span class="sxs-lookup"><span data-stu-id="22518-172">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="22518-173">使用者設定的狀態在 [團隊] 中有預設的到期設定，以避免使用者顯示在一段時間之後可能不相關的狀態。</span><span class="sxs-lookup"><span data-stu-id="22518-173">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="22518-174">使用者設定的狀態</span><span class="sxs-lookup"><span data-stu-id="22518-174">User configured state</span></span>|<span data-ttu-id="22518-175">預設到期日</span><span class="sxs-lookup"><span data-stu-id="22518-175">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="22518-176">忙碌</span><span class="sxs-lookup"><span data-stu-id="22518-176">Busy</span></span>|<span data-ttu-id="22518-177">1天</span><span class="sxs-lookup"><span data-stu-id="22518-177">1 day</span></span>|
| <span data-ttu-id="22518-178">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="22518-178">Do not disturb</span></span>|<span data-ttu-id="22518-179">1天</span><span class="sxs-lookup"><span data-stu-id="22518-179">1 day</span></span>|
| <span data-ttu-id="22518-180">公司</span><span class="sxs-lookup"><span data-stu-id="22518-180">Others</span></span>|<span data-ttu-id="22518-181">7天</span><span class="sxs-lookup"><span data-stu-id="22518-181">7 days</span></span>|
|||

> [!NOTE]
> <span data-ttu-id="22518-182">使用者也可以針對她的目前狀態，手動設定持續時間。</span><span class="sxs-lookup"><span data-stu-id="22518-182">A user can also configure manually a duration for her presence.</span></span> <span data-ttu-id="22518-183">例如，使用者可以在明天早上將自己設為離線顯示。</span><span class="sxs-lookup"><span data-stu-id="22518-183">For instance, a user can set herself as Appear offline until tomorrow morning.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="22518-184">比較商務用 Skype 與 Teams 中的管理設定</span><span class="sxs-lookup"><span data-stu-id="22518-184">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="22518-185">下列的商務用 Skype 管理設定與 Teams 不同：</span><span class="sxs-lookup"><span data-stu-id="22518-185">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="22518-186">在 Teams 中，組織的使用者一律啟用目前狀態共用。</span><span class="sxs-lookup"><span data-stu-id="22518-186">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="22518-187">隱私權 (您可以在此定義哪些人員可以查看目前狀態) 設定無法在團隊中取得。</span><span class="sxs-lookup"><span data-stu-id="22518-187">Privacy (where you define who can see presence) configuration isn't available in Teams.</span></span>
- <span data-ttu-id="22518-188">Teams 中的使用者一律啟用與所有人 (包括同盟服務) 共用目前狀態。</span><span class="sxs-lookup"><span data-stu-id="22518-188">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="22518-189">他們的連絡人清單 (如果他們在商務用 Skype 中有此清單) 會顯示在 [聊天] > [連絡人] 底下或在 [通話] > [連絡人] 底下。</span><span class="sxs-lookup"><span data-stu-id="22518-189">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="22518-190">Teams 中的使用者一律啟用用戶端的「請勿打擾」和「突破」功能。</span><span class="sxs-lookup"><span data-stu-id="22518-190">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="22518-191">當 Teams 與 Outlook 整合時，一律為使用者啟用行事曆 (包括外出和其他行事曆資訊) 整合。</span><span class="sxs-lookup"><span data-stu-id="22518-191">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="22518-192">如果組織也使用商務用 Skype，Teams 中的使用者一律啟用 [上次看到] 或 [離開時間]。</span><span class="sxs-lookup"><span data-stu-id="22518-192">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="22518-193">目前不支援 Teams 系統管理員自訂這些設定的功能。</span><span class="sxs-lookup"><span data-stu-id="22518-193">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a><span data-ttu-id="22518-194">團隊中與 Microsoft Outlook 比較的管理員設定</span><span class="sxs-lookup"><span data-stu-id="22518-194">Admin settings in Teams compared to Microsoft Outlook</span></span>

<span data-ttu-id="22518-195">Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="22518-195">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

<span data-ttu-id="22518-196">如果使用者帳戶的 [升級模式] 原則設定為 [TeamsOnly]，Outlook 就會與團隊進行交談，以取得目前狀態。</span><span class="sxs-lookup"><span data-stu-id="22518-196">If the upgrade mode policy of the user account is set to TeamsOnly, Outlook talks to Teams to get presence.</span></span> <span data-ttu-id="22518-197">如果使用者帳戶未設為 TeamsOnly，Outlook 就會與商務用 Skype 交談。</span><span class="sxs-lookup"><span data-stu-id="22518-197">If the user account isn't set to TeamsOnly, then Outlook talks to Skype for Business.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="22518-198">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="22518-198">Coexistence with Skype for Business</span></span>

<span data-ttu-id="22518-199">請參閱 [與商務用 Skype 共存](coexistence-chat-calls-presence.md) ，以取得貴組織也使用商務用 skype 時，小組目前狀態如何運作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="22518-199">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses Skype for Business.</span></span>
