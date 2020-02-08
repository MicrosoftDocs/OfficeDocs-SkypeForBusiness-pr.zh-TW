---
title: Teams 中的使用者目前狀態
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 有關團隊中目前狀態的管理員資訊。
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
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863194"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="a69a3-103">Teams 中的使用者目前狀態</span><span class="sxs-lookup"><span data-stu-id="a69a3-103">User presence in Teams</span></span>

<span data-ttu-id="a69a3-104">目前狀態是 Microsoft 團隊（以及整個 Office 365）中使用者設定檔的一部分，可指出使用者目前的可用性與其他使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="a69a3-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="a69a3-105">根據預設，您組織中的任何人都可以在線上看到其他使用者（幾乎即時）。</span><span class="sxs-lookup"><span data-stu-id="a69a3-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a69a3-106">如果您在將使用者移至 [僅 Teams]\*\*\*\* 模式之後解除安裝商務用 Skype 用戶端，則 Outlook 和其他 Office應用程式中的目前狀態將會停止運作。</span><span class="sxs-lookup"><span data-stu-id="a69a3-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="a69a3-107">目前狀態在 Teams 中可正常運作。</span><span class="sxs-lookup"><span data-stu-id="a69a3-107">Presence works fine in Teams.</span></span> <span data-ttu-id="a69a3-108">因應措施：若要在 Outlook （以及其他 Office app）中查看目前狀態，您必須安裝商務用 Skype，即使您是在 [**僅限團隊**] 模式中執行團隊也一樣。</span><span class="sxs-lookup"><span data-stu-id="a69a3-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="a69a3-109">Microsoft 已發現此問題，正在努力解決中。</span><span class="sxs-lookup"><span data-stu-id="a69a3-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="a69a3-110">Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="a69a3-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="a69a3-111">團隊中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="a69a3-111">Presence states in Teams</span></span>

<span data-ttu-id="a69a3-112">團隊中提供的使用者目前狀態為：</span><span class="sxs-lookup"><span data-stu-id="a69a3-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="a69a3-113">已設定使用者</span><span class="sxs-lookup"><span data-stu-id="a69a3-113">User configured</span></span>|<span data-ttu-id="a69a3-114">App 已設定</span><span class="sxs-lookup"><span data-stu-id="a69a3-114">App configured</span></span>|
|:--- |:---|
| ![穩定綠色核取記號，表示目前狀態為可用](media/Presence_Available.png) <span data-ttu-id="a69a3-116">離線</span><span class="sxs-lookup"><span data-stu-id="a69a3-116">Available</span></span>|![穩定綠色核取記號，表示目前狀態為可用](media/Presence_Available.png) <span data-ttu-id="a69a3-118">離線</span><span class="sxs-lookup"><span data-stu-id="a69a3-118">Available</span></span>|
|| ![開啟綠色核取記號，表示有空的 oof](media/Presence_Available_OOF.png) <span data-ttu-id="a69a3-120">可用、不在辦公室</span><span class="sxs-lookup"><span data-stu-id="a69a3-120">Available, Out of Office</span></span> |
|  ![實心紅圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="a69a3-122">狀況</span><span class="sxs-lookup"><span data-stu-id="a69a3-122">Busy</span></span> |  ![實心紅圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="a69a3-124">狀況</span><span class="sxs-lookup"><span data-stu-id="a69a3-124">Busy</span></span>  |
|| ![實心紅圈，表示通話中的占線](media/Presence_Busy.png) <span data-ttu-id="a69a3-126">通話中</span><span class="sxs-lookup"><span data-stu-id="a69a3-126">On a call</span></span>|
|| ![實心紅圈，表示會議中的忙](media/Presence_Busy.png) <span data-ttu-id="a69a3-128">在會議中</span><span class="sxs-lookup"><span data-stu-id="a69a3-128">In a meeting</span></span> |
|| ![開啟紅色圓圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="a69a3-130">在通話中，外出</span><span class="sxs-lookup"><span data-stu-id="a69a3-130">On a call, out of office</span></span>|
|  ![紅色圓圈（含白色線條）表示 [請勿打擾]](media/Presence_DND.png) <span data-ttu-id="a69a3-132">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="a69a3-132">Do not disturb</span></span> ||
|| ![紅色圓圈（含白色線條）表示呈現](media/Presence_DND.png) <span data-ttu-id="a69a3-134">介紹</span><span class="sxs-lookup"><span data-stu-id="a69a3-134">Presenting</span></span>|
|| ![紅色圓圈（含白色線條）代表焦點](media/Presence_DND.png) <span data-ttu-id="a69a3-136">致力</span><span class="sxs-lookup"><span data-stu-id="a69a3-136">Focusing</span></span>|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="a69a3-138">擺脫</span><span class="sxs-lookup"><span data-stu-id="a69a3-138">Away</span></span>| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="a69a3-140">擺脫</span><span class="sxs-lookup"><span data-stu-id="a69a3-140">Away</span></span>|
|| <span data-ttu-id="a69a3-141">![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次查看的*時間*</span><span class="sxs-lookup"><span data-stu-id="a69a3-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黃色時鐘圖示，表示離開，立即返回](media/Presence_Away.png) <span data-ttu-id="a69a3-143">馬上回來</span><span class="sxs-lookup"><span data-stu-id="a69a3-143">Be right back</span></span>| |
|| ![黃色時鐘圖示，表示 [離開]、[下班中]](media/Presence_Away.png)  <span data-ttu-id="a69a3-145">關閉工作</span><span class="sxs-lookup"><span data-stu-id="a69a3-145">Off Work</span></span>|
|| ![X 的灰色圓圈表示離線](media/Presence_Offline.png) <span data-ttu-id="a69a3-147">處於</span><span class="sxs-lookup"><span data-stu-id="a69a3-147">Offline</span></span> |
|| ![開啟灰色圓圈，表示狀態未知](media/Presence_Unknown.png) <span data-ttu-id="a69a3-149">狀態未知</span><span class="sxs-lookup"><span data-stu-id="a69a3-149">Status unknown</span></span>|
||![以對角線開啟紅色圓圈，表示封鎖](media/Presence_Blocked.png) <span data-ttu-id="a69a3-151">受阻</span><span class="sxs-lookup"><span data-stu-id="a69a3-151">Blocked</span></span> |
|| ![含箭號的紫色圓圈表示不在辦公室](media/Presence_OOF.png) <span data-ttu-id="a69a3-153">不在辦公室</span><span class="sxs-lookup"><span data-stu-id="a69a3-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="a69a3-154">使用者可以將目前的目前狀態狀態手動設定為某些選項，而其狀態會反映給所有其他使用者。</span><span class="sxs-lookup"><span data-stu-id="a69a3-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="a69a3-155">更多使用者目前狀態詳細資料也會自動更新。</span><span class="sxs-lookup"><span data-stu-id="a69a3-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="a69a3-156">變更是以使用者活動（可用、離開）、Outlook 行事曆狀態（在會議中），或團隊 app 狀態（在進行中的通話中）來表示，在清單中縮排的狀態。</span><span class="sxs-lookup"><span data-stu-id="a69a3-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="a69a3-157">有15分鐘的非使用中超時，在這段時間之後，目前的目前狀態將會重設為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="a69a3-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="a69a3-158">使用者會收到所有在小組中傳送給他們的聊天訊息，而不管他們的目前狀態為何。</span><span class="sxs-lookup"><span data-stu-id="a69a3-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="a69a3-159">如果使用者是在某人傳送訊息時離線，就會在使用者下次線上時，在小組中出現聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="a69a3-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="a69a3-160">如果使用者處於 [請勿打擾] 狀態，使用者仍會收到聊天訊息，但不會顯示橫幅通知。</span><span class="sxs-lookup"><span data-stu-id="a69a3-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="a69a3-161">使用者會在除了 [請勿打擾] 狀態以外的所有目前狀態狀態中接收來電，讓來電傳送至其語音信箱。</span><span class="sxs-lookup"><span data-stu-id="a69a3-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="a69a3-162">如果收件者封鎖來電者，通話就不會傳送，而且來電者會看到收件者的目前狀態為 [離線]。</span><span class="sxs-lookup"><span data-stu-id="a69a3-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="a69a3-163">使用者可以移至 [小組] 中的 [**設定** > **隱私權**]，將人員新增至他們的優先順序存取清單中。</span><span class="sxs-lookup"><span data-stu-id="a69a3-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="a69a3-164">即使使用者處於 [請勿打擾] 狀態，擁有優先順序存取權的人員也可以與使用者取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="a69a3-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="a69a3-165">團隊中與商務用 Skype 相比的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="a69a3-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="a69a3-166">下列系統管理員設定商務用 Skype 在小組中有所不同：</span><span class="sxs-lookup"><span data-stu-id="a69a3-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="a69a3-167">在團隊中，組織中的使用者永遠都能啟用目前狀態共用。</span><span class="sxs-lookup"><span data-stu-id="a69a3-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="a69a3-168">隱私權（您定義誰可以查看目前狀態）設定在團隊中無法使用。</span><span class="sxs-lookup"><span data-stu-id="a69a3-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="a69a3-169">[目前狀態] 與所有人共用（包括同盟服務），將會針對小組中的使用者永遠啟用。</span><span class="sxs-lookup"><span data-stu-id="a69a3-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="a69a3-170">連絡人清單（如果他們在商務用 Skype 中有一個）會顯示在 [**聊天] > 連絡人**] 底下，或 [**通話 > 連絡人**] 下。</span><span class="sxs-lookup"><span data-stu-id="a69a3-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="a69a3-171">用戶端的 [請勿打擾] 和 [突破性] 功能永遠都可供團隊中的使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="a69a3-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="a69a3-172">[行事曆] （包括 [不在辦公室] 和 [其他行事曆資訊]），當團隊與 Outlook 整合時，就會為使用者啟用整合。</span><span class="sxs-lookup"><span data-stu-id="a69a3-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="a69a3-173">如果組織也使用商務用 Skype，則 [*上次看到*] 或 [*離開*] 時，會針對小組中的使用者永遠啟用指標。</span><span class="sxs-lookup"><span data-stu-id="a69a3-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="a69a3-174">團隊系統管理員自訂這些設定的能力目前不受支援。</span><span class="sxs-lookup"><span data-stu-id="a69a3-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="a69a3-175">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="a69a3-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="a69a3-176">請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織也使用商務用 skype 時，小組目前狀態如何運作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a69a3-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
