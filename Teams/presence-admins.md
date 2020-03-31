---
title: Teams 中使用者的目前狀態
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 有關 Teams 中目前狀態的管理資訊。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863194"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="4e1a3-103">Teams 中使用者的目前狀態</span><span class="sxs-lookup"><span data-stu-id="4e1a3-103">User presence in Teams</span></span>

<span data-ttu-id="4e1a3-104">目前狀態是 Microsoft Teams (和整個 Office 365) 中使用者設定檔的一部分，會向其他使用顯示使用者目前的可用性和狀態。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="4e1a3-105">依預設，貴組織中任何有使用 Teams 的人都可以 (幾乎即時) 查看其他使用者是否在線上。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e1a3-106">如果您在將使用者移至 [僅 Teams]\*\*\*\* 模式之後解除安裝商務用 Skype 用戶端，則 Outlook 和其他 Office應用程式中的目前狀態將會停止運作。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="4e1a3-107">目前狀態在 Teams 中可正常運作。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-107">Presence works fine in Teams.</span></span> <span data-ttu-id="4e1a3-108">解決辦法：若要在 Outlook (和其他 Office 應用程式) 中查看目前狀態，則必須安裝商務用 Skype，即使您在 [僅 Teams]\*\*\*\* 模式中執行 Teams 亦然。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="4e1a3-109">Microsoft 已發現此問題，正在努力解決中。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="4e1a3-110">Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="4e1a3-111">Teams 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="4e1a3-111">Presence states in Teams</span></span>

<span data-ttu-id="4e1a3-112">Teams 提供的使用者目前狀態如下：</span><span class="sxs-lookup"><span data-stu-id="4e1a3-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="4e1a3-113">使用者設定</span><span class="sxs-lookup"><span data-stu-id="4e1a3-113">User configured</span></span>|<span data-ttu-id="4e1a3-114">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="4e1a3-114">App configured</span></span>|
|:--- |:---|
| ![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="4e1a3-116">有空</span><span class="sxs-lookup"><span data-stu-id="4e1a3-116">Available</span></span>|![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="4e1a3-118">有空</span><span class="sxs-lookup"><span data-stu-id="4e1a3-118">Available</span></span>|
|| ![空心圓圈綠色核取記號，表示外出並有空](media/Presence_Available_OOF.png) <span data-ttu-id="4e1a3-120">有空，外出</span><span class="sxs-lookup"><span data-stu-id="4e1a3-120">Available, Out of Office</span></span> |
|  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="4e1a3-122">忙碌</span><span class="sxs-lookup"><span data-stu-id="4e1a3-122">Busy</span></span> |  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="4e1a3-124">忙碌</span><span class="sxs-lookup"><span data-stu-id="4e1a3-124">Busy</span></span>  |
|| ![紅色實心圓圈，表示通話中忙碌](media/Presence_Busy.png) <span data-ttu-id="4e1a3-126">通話中</span><span class="sxs-lookup"><span data-stu-id="4e1a3-126">On a call</span></span>|
|| ![紅色實心圓圈，表示會議中忙碌](media/Presence_Busy.png) <span data-ttu-id="4e1a3-128">會議中</span><span class="sxs-lookup"><span data-stu-id="4e1a3-128">In a meeting</span></span> |
|| ![紅色空心圓圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="4e1a3-130">通話中，外出</span><span class="sxs-lookup"><span data-stu-id="4e1a3-130">On a call, out of office</span></span>|
|  ![紅色圓圈加白線，表示請勿打擾](media/Presence_DND.png) <span data-ttu-id="4e1a3-132">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="4e1a3-132">Do not disturb</span></span> ||
|| ![紅色圓圈加白線，表示簡報中](media/Presence_DND.png) <span data-ttu-id="4e1a3-134">簡報中</span><span class="sxs-lookup"><span data-stu-id="4e1a3-134">Presenting</span></span>|
|| ![紅色圓圈加白線，表示專注](media/Presence_DND.png) <span data-ttu-id="4e1a3-136">專注</span><span class="sxs-lookup"><span data-stu-id="4e1a3-136">Focusing</span></span>|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="4e1a3-138">離開</span><span class="sxs-lookup"><span data-stu-id="4e1a3-138">Away</span></span>| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="4e1a3-140">離開</span><span class="sxs-lookup"><span data-stu-id="4e1a3-140">Away</span></span>|
|| <span data-ttu-id="4e1a3-141">![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次看到的*時間*</span><span class="sxs-lookup"><span data-stu-id="4e1a3-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黃色時鐘圖示，表示離開，馬上回來](media/Presence_Away.png) <span data-ttu-id="4e1a3-143">馬上回來</span><span class="sxs-lookup"><span data-stu-id="4e1a3-143">Be right back</span></span>| |
|| ![黃色時鐘圖示，表示離開，下班](media/Presence_Away.png)  <span data-ttu-id="4e1a3-145">下班</span><span class="sxs-lookup"><span data-stu-id="4e1a3-145">Off Work</span></span>|
|| ![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) <span data-ttu-id="4e1a3-147">離線</span><span class="sxs-lookup"><span data-stu-id="4e1a3-147">Offline</span></span> |
|| ![空心灰色圓圈，表示狀態不明](media/Presence_Unknown.png) <span data-ttu-id="4e1a3-149">狀態不明</span><span class="sxs-lookup"><span data-stu-id="4e1a3-149">Status unknown</span></span>|
||![空心紅色圓圈加對角斜線，表示已封鎖](media/Presence_Blocked.png) <span data-ttu-id="4e1a3-151">已封鎖</span><span class="sxs-lookup"><span data-stu-id="4e1a3-151">Blocked</span></span> |
|| ![紫色圓圈加箭號，表示外出](media/Presence_OOF.png) <span data-ttu-id="4e1a3-153">外出</span><span class="sxs-lookup"><span data-stu-id="4e1a3-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="4e1a3-154">使用者可以手動將其目前狀態設定為某些選項，將其狀態反映給其他所有使用者知道。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="4e1a3-155">更多使用者目前狀態詳細資料也會自動更新。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="4e1a3-156">所做的變更是根據使用者活動 (有空、離開)、Outlook 行事曆狀態 (會議中)、或是 Teams 應用程式狀態 (簡報中)，到清單中縮排的狀態。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="4e1a3-157">將目前狀態重設為「離開」之後，會有 15 分鐘的不活動逾時。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="4e1a3-158">不管使用者目前狀態為何，都會收到所有在 Teams 中傳送給他們的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="4e1a3-159">如果他人傳送郵件給使用者時使用者已離線，聊天訊息會在使用者下次上線時顯示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="4e1a3-160">如果使用者處於「請勿打擾」狀態，使用者仍會收到聊天訊息，但不會顯示橫幅通知。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="4e1a3-161">用戶在所有狀態下都會收到通話，但「請勿打擾」狀態除外，在這種狀態下，通話會傳遞到他們的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="4e1a3-162">如果受話方封鎖來電者，通話將不會傳送，且來電者看到的受話方目前狀態是「離線」。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="4e1a3-163">使用者可以到 Teams 的 [設定]\*\*\*\*  >  [隱私權]\*\*\*\*，將人員新增至其優先存取清單。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="4e1a3-164">具有優先存取的人員可以與使用者聯繫，即使該使用者處於 [請勿打擾] 狀態。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="4e1a3-165">比較商務用 Skype 與 Teams 中的管理設定</span><span class="sxs-lookup"><span data-stu-id="4e1a3-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="4e1a3-166">下列的商務用 Skype 管理設定與 Teams 不同：</span><span class="sxs-lookup"><span data-stu-id="4e1a3-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="4e1a3-167">在 Teams 中，組織的使用者一律啟用目前狀態共用。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="4e1a3-168">Teams 沒有「隱私權」設定 (您定義誰可查看目前狀態) 。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="4e1a3-169">Teams 中的使用者一律啟用與所有人 (包括同盟服務) 共用目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="4e1a3-170">他們的連絡人清單 (如果他們在商務用 Skype 中有此清單) 會顯示在 [聊天] > [連絡人]\*\*\*\* 底下或在 [通話] > [連絡人]\*\*\*\* 底下。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="4e1a3-171">Teams 中的使用者一律啟用用戶端的「請勿打擾」和「突破」功能。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="4e1a3-172">當 Teams 與 Outlook 整合時，一律為使用者啟用行事曆 (包括外出和其他行事曆資訊) 整合。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="4e1a3-173">如果組織也使用商務用 Skype，Teams 中的使用者一律啟用 [上次看到]\*\* 或 [離開時間]\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="4e1a3-174">目前不支援 Teams 系統管理員自訂這些設定的功能。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="4e1a3-175">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="4e1a3-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="4e1a3-176">請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織使用商務用 Skype 時 Teams的運作方式詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4e1a3-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
