---
title: Teams 中使用者的目前狀態
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 瞭解 [團隊] 中的目前狀態，以及目前狀態功能的管理設定。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a944616fef0c3fd9821486a41025adf5f0fdbcc
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814572"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="dcd6f-103">Teams 中使用者的目前狀態</span><span class="sxs-lookup"><span data-stu-id="dcd6f-103">User presence in Teams</span></span>

<span data-ttu-id="dcd6f-104">[目前狀態] 是 Microsoft 團隊中的使用者設定檔的一部分 (與整個 Microsoft 365 或 Office 365) ，可指出使用者目前的可用性與其他使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="dcd6f-105">依預設，貴組織中任何有使用 Teams 的人都可以 (幾乎即時) 查看其他使用者是否在線上。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="dcd6f-106">Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="dcd6f-107">如需詳細資訊，請參閱 [小組功能（依平臺](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) ）。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-107">See [Team features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) for more information.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="dcd6f-108">Teams 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="dcd6f-108">Presence states in Teams</span></span>

|<span data-ttu-id="dcd6f-109">使用者設定</span><span class="sxs-lookup"><span data-stu-id="dcd6f-109">User configured</span></span>|<span data-ttu-id="dcd6f-110">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="dcd6f-110">App configured</span></span>|
|:--- |:---|
| ![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="dcd6f-112">有空</span><span class="sxs-lookup"><span data-stu-id="dcd6f-112">Available</span></span>|![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="dcd6f-114">有空</span><span class="sxs-lookup"><span data-stu-id="dcd6f-114">Available</span></span>|
|| ![空心圓圈綠色核取記號，表示外出並有空](media/Presence_Available_OOF.png) <span data-ttu-id="dcd6f-116">有空，外出</span><span class="sxs-lookup"><span data-stu-id="dcd6f-116">Available, Out of Office</span></span> |
|  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="dcd6f-118">忙碌</span><span class="sxs-lookup"><span data-stu-id="dcd6f-118">Busy</span></span> |  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="dcd6f-120">忙碌</span><span class="sxs-lookup"><span data-stu-id="dcd6f-120">Busy</span></span>  |
|| ![紅色實心圓圈，表示通話中忙碌](media/Presence_Busy.png) <span data-ttu-id="dcd6f-122">通話中</span><span class="sxs-lookup"><span data-stu-id="dcd6f-122">On a call</span></span>|
|| ![紅色實心圓圈，表示會議中忙碌](media/Presence_Busy.png) <span data-ttu-id="dcd6f-124">會議中</span><span class="sxs-lookup"><span data-stu-id="dcd6f-124">In a meeting</span></span> |
|| ![紅色空心圓圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="dcd6f-126">通話中，外出</span><span class="sxs-lookup"><span data-stu-id="dcd6f-126">On a call, out of office</span></span>|
|  ![紅色圓圈加白線，表示請勿打擾](media/Presence_DND.png) <span data-ttu-id="dcd6f-128">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="dcd6f-128">Do not disturb</span></span> ||
|| ![紅色圓圈加白線，表示簡報中](media/Presence_DND.png) <span data-ttu-id="dcd6f-130">簡報中</span><span class="sxs-lookup"><span data-stu-id="dcd6f-130">Presenting</span></span>|
|| ![紅色圓圈加白線，表示專注](media/Presence_DND.png) <span data-ttu-id="dcd6f-132">專注</span><span class="sxs-lookup"><span data-stu-id="dcd6f-132">Focusing</span></span>|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="dcd6f-134">離開</span><span class="sxs-lookup"><span data-stu-id="dcd6f-134">Away</span></span>| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="dcd6f-136">離開</span><span class="sxs-lookup"><span data-stu-id="dcd6f-136">Away</span></span>|
|| <span data-ttu-id="dcd6f-137">![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次看到的*時間*</span><span class="sxs-lookup"><span data-stu-id="dcd6f-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黃色時鐘圖示，表示離開，馬上回來](media/Presence_Away.png) <span data-ttu-id="dcd6f-139">馬上回來</span><span class="sxs-lookup"><span data-stu-id="dcd6f-139">Be right back</span></span>| |
|| ![黃色時鐘圖示，表示離開，下班](media/Presence_Away.png)  <span data-ttu-id="dcd6f-141">下班</span><span class="sxs-lookup"><span data-stu-id="dcd6f-141">Off Work</span></span>|
|| ![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) <span data-ttu-id="dcd6f-143">離線</span><span class="sxs-lookup"><span data-stu-id="dcd6f-143">Offline</span></span> |
|| ![空心灰色圓圈，表示狀態不明](media/Presence_Unknown.png) <span data-ttu-id="dcd6f-145">狀態不明</span><span class="sxs-lookup"><span data-stu-id="dcd6f-145">Status unknown</span></span>|
||![空心紅色圓圈加對角斜線，表示已封鎖](media/Presence_Blocked.png) <span data-ttu-id="dcd6f-147">已封鎖</span><span class="sxs-lookup"><span data-stu-id="dcd6f-147">Blocked</span></span> |
|| ![紫色圓圈加箭號，表示外出](media/Presence_OOF.png) <span data-ttu-id="dcd6f-149">外出</span><span class="sxs-lookup"><span data-stu-id="dcd6f-149">Out of Office</span></span>|
|||

<span data-ttu-id="dcd6f-150">App 設定的目前狀態是以使用者活動 (提供，離開) ，Outlook 行事曆狀態 (在會議) 中，或團隊 app 的狀態 (在通話中，提出) 。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-150">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="dcd6f-151">請注意，當您是以您的行事曆為基礎的焦點模式時，焦點會是人員在團隊中看到的狀態，但在其他產品中會顯示為 [請勿打擾]。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-151">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="dcd6f-152">當您鎖定電腦或進入 [空閒] 或 [睡眠] 模式時，您的目前狀態會變更為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-152">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="dcd6f-153">在行動裝置上，當團隊 app 位於背景時，您的目前狀態會變更為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-153">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="dcd6f-154">不管使用者目前狀態為何，都會收到所有在 Teams 中傳送給他們的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-154">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="dcd6f-155">如果他人傳送郵件給使用者時使用者已離線，聊天訊息會在使用者下次上線時顯示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-155">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="dcd6f-156">如果使用者在 [請勿打擾] 中，使用者仍會收到聊天訊息，但不會顯示橫幅通知。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-156">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="dcd6f-157">使用者會在除了 [請勿打擾] 以外的所有目前狀態狀態中接收來電，讓來電移至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-157">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="dcd6f-158">如果受話方封鎖來電者，通話將不會傳送，且來電者看到的受話方目前狀態是「離線」。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-158">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="dcd6f-159">使用者可以到 Teams 的 [設定]\*\*\*\*  >  [隱私權]\*\*\*\*，將人員新增至其優先存取清單。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-159">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="dcd6f-160">即使使用者在 [請勿打擾] 時，擁有優先順序存取權的人員也可以與使用者取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-160">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="dcd6f-161">比較商務用 Skype 與 Teams 中的管理設定</span><span class="sxs-lookup"><span data-stu-id="dcd6f-161">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="dcd6f-162">下列的商務用 Skype 管理設定與 Teams 不同：</span><span class="sxs-lookup"><span data-stu-id="dcd6f-162">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="dcd6f-163">在 Teams 中，組織的使用者一律啟用目前狀態共用。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-163">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="dcd6f-164">Teams 沒有「隱私權」設定 (您定義誰可查看目前狀態) 。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-164">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="dcd6f-165">Teams 中的使用者一律啟用與所有人 (包括同盟服務) 共用目前狀態。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-165">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="dcd6f-166">他們的連絡人清單 (如果他們在商務用 Skype 中有此清單) 會顯示在 [聊天] > [連絡人]\*\*\*\* 底下或在 [通話] > [連絡人]\*\*\*\* 底下。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-166">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="dcd6f-167">Teams 中的使用者一律啟用用戶端的「請勿打擾」和「突破」功能。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-167">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="dcd6f-168">當 Teams 與 Outlook 整合時，一律為使用者啟用行事曆 (包括外出和其他行事曆資訊) 整合。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-168">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="dcd6f-169">如果組織也使用商務用 Skype，Teams 中的使用者一律啟用 [上次看到]\*\* 或 [離開時間]\*\*。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-169">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="dcd6f-170">目前不支援 Teams 系統管理員自訂這些設定的功能。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-170">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="dcd6f-171">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="dcd6f-171">Coexistence with Skype for Business</span></span>

<span data-ttu-id="dcd6f-172">請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織使用商務用 Skype 時 Teams的運作方式詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dcd6f-172">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
