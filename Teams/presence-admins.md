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
ms.openlocfilehash: ea756b24a0292a35d4e47252383bfc954fcb8fa7
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096968"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="157b7-103">Teams 中使用者的目前狀態</span><span class="sxs-lookup"><span data-stu-id="157b7-103">User presence in Teams</span></span>

<span data-ttu-id="157b7-104">目前狀態是 Microsoft 團隊（以及整個 Office 365）中使用者設定檔的一部分，可指出使用者目前的可用性與其他使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="157b7-104">Presence is part of a user's profile in Microsoft Teams (and throughout Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="157b7-105">依預設，貴組織中任何有使用 Teams 的人都可以 (幾乎即時) 查看其他使用者是否在線上。</span><span class="sxs-lookup"><span data-stu-id="157b7-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="157b7-106">如果您在將使用者移至 [僅 Teams]\*\*\*\* 模式之後解除安裝商務用 Skype 用戶端，則 Outlook 和其他 Office應用程式中的目前狀態將會停止運作。</span><span class="sxs-lookup"><span data-stu-id="157b7-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="157b7-107">目前狀態在 Teams 中可正常運作。</span><span class="sxs-lookup"><span data-stu-id="157b7-107">Presence works fine in Teams.</span></span> <span data-ttu-id="157b7-108">解決辦法：若要在 Outlook (和其他 Office 應用程式) 中查看目前狀態，則必須安裝商務用 Skype，即使您在 [僅 Teams]\*\*\*\* 模式中執行 Teams 亦然。</span><span class="sxs-lookup"><span data-stu-id="157b7-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="157b7-109">Microsoft 已發現此問題，正在努力解決中。</span><span class="sxs-lookup"><span data-stu-id="157b7-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="157b7-110">Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。</span><span class="sxs-lookup"><span data-stu-id="157b7-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="157b7-111">Teams 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="157b7-111">Presence states in Teams</span></span>

|<span data-ttu-id="157b7-112">使用者設定</span><span class="sxs-lookup"><span data-stu-id="157b7-112">User configured</span></span>|<span data-ttu-id="157b7-113">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="157b7-113">App configured</span></span>|
|:--- |:---|
| ![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="157b7-115">有空</span><span class="sxs-lookup"><span data-stu-id="157b7-115">Available</span></span>|![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) <span data-ttu-id="157b7-117">有空</span><span class="sxs-lookup"><span data-stu-id="157b7-117">Available</span></span>|
|| ![空心圓圈綠色核取記號，表示外出並有空](media/Presence_Available_OOF.png) <span data-ttu-id="157b7-119">有空，外出</span><span class="sxs-lookup"><span data-stu-id="157b7-119">Available, Out of Office</span></span> |
|  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="157b7-121">忙碌</span><span class="sxs-lookup"><span data-stu-id="157b7-121">Busy</span></span> |  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="157b7-123">忙碌</span><span class="sxs-lookup"><span data-stu-id="157b7-123">Busy</span></span>  |
|| ![紅色實心圓圈，表示通話中忙碌](media/Presence_Busy.png) <span data-ttu-id="157b7-125">通話中</span><span class="sxs-lookup"><span data-stu-id="157b7-125">On a call</span></span>|
|| ![紅色實心圓圈，表示會議中忙碌](media/Presence_Busy.png) <span data-ttu-id="157b7-127">會議中</span><span class="sxs-lookup"><span data-stu-id="157b7-127">In a meeting</span></span> |
|| ![紅色空心圓圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="157b7-129">通話中，外出</span><span class="sxs-lookup"><span data-stu-id="157b7-129">On a call, out of office</span></span>|
|  ![紅色圓圈加白線，表示請勿打擾](media/Presence_DND.png) <span data-ttu-id="157b7-131">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="157b7-131">Do not disturb</span></span> ||
|| ![紅色圓圈加白線，表示簡報中](media/Presence_DND.png) <span data-ttu-id="157b7-133">簡報中</span><span class="sxs-lookup"><span data-stu-id="157b7-133">Presenting</span></span>|
|| ![紅色圓圈加白線，表示專注](media/Presence_DND.png) <span data-ttu-id="157b7-135">專注</span><span class="sxs-lookup"><span data-stu-id="157b7-135">Focusing</span></span>|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="157b7-137">離開</span><span class="sxs-lookup"><span data-stu-id="157b7-137">Away</span></span>| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="157b7-139">離開</span><span class="sxs-lookup"><span data-stu-id="157b7-139">Away</span></span>|
|| <span data-ttu-id="157b7-140">![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次看到的*時間*</span><span class="sxs-lookup"><span data-stu-id="157b7-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黃色時鐘圖示，表示離開，馬上回來](media/Presence_Away.png) <span data-ttu-id="157b7-142">馬上回來</span><span class="sxs-lookup"><span data-stu-id="157b7-142">Be right back</span></span>| |
|| ![黃色時鐘圖示，表示離開，下班](media/Presence_Away.png)  <span data-ttu-id="157b7-144">下班</span><span class="sxs-lookup"><span data-stu-id="157b7-144">Off Work</span></span>|
|| ![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) <span data-ttu-id="157b7-146">離線</span><span class="sxs-lookup"><span data-stu-id="157b7-146">Offline</span></span> |
|| ![空心灰色圓圈，表示狀態不明](media/Presence_Unknown.png) <span data-ttu-id="157b7-148">狀態不明</span><span class="sxs-lookup"><span data-stu-id="157b7-148">Status unknown</span></span>|
||![空心紅色圓圈加對角斜線，表示已封鎖](media/Presence_Blocked.png) <span data-ttu-id="157b7-150">已封鎖</span><span class="sxs-lookup"><span data-stu-id="157b7-150">Blocked</span></span> |
|| ![紫色圓圈加箭號，表示外出](media/Presence_OOF.png) <span data-ttu-id="157b7-152">外出</span><span class="sxs-lookup"><span data-stu-id="157b7-152">Out of Office</span></span>|
|||

<span data-ttu-id="157b7-153">App 設定的目前狀態是以使用者活動（可用、離開）、Outlook 行事曆狀態（在會議中）或團隊 app 狀態（在通話中）為基礎。</span><span class="sxs-lookup"><span data-stu-id="157b7-153">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="157b7-154">當您鎖定電腦或進入 [空閒] 或 [睡眠] 模式時，您的目前狀態會變更為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="157b7-154">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="157b7-155">在行動裝置上，當團隊 app 位於背景時，您的目前狀態會變更為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="157b7-155">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="157b7-156">不管使用者目前狀態為何，都會收到所有在 Teams 中傳送給他們的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="157b7-156">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="157b7-157">如果他人傳送郵件給使用者時使用者已離線，聊天訊息會在使用者下次上線時顯示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="157b7-157">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="157b7-158">如果使用者在 [請勿打擾] 中，使用者仍會收到聊天訊息，但不會顯示橫幅通知。</span><span class="sxs-lookup"><span data-stu-id="157b7-158">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="157b7-159">使用者會在除了 [請勿打擾] 以外的所有目前狀態狀態中接收來電，讓來電移至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="157b7-159">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="157b7-160">如果受話方封鎖來電者，通話將不會傳送，且來電者看到的受話方目前狀態是「離線」。</span><span class="sxs-lookup"><span data-stu-id="157b7-160">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="157b7-161">使用者可以到 Teams 的 [設定]\*\*\*\*  >  [隱私權]\*\*\*\*，將人員新增至其優先存取清單。</span><span class="sxs-lookup"><span data-stu-id="157b7-161">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="157b7-162">即使使用者在 [請勿打擾] 時，擁有優先順序存取權的人員也可以與使用者取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="157b7-162">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="157b7-163">比較商務用 Skype 與 Teams 中的管理設定</span><span class="sxs-lookup"><span data-stu-id="157b7-163">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="157b7-164">下列的商務用 Skype 管理設定與 Teams 不同：</span><span class="sxs-lookup"><span data-stu-id="157b7-164">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="157b7-165">在 Teams 中，組織的使用者一律啟用目前狀態共用。</span><span class="sxs-lookup"><span data-stu-id="157b7-165">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="157b7-166">Teams 沒有「隱私權」設定 (您定義誰可查看目前狀態) 。</span><span class="sxs-lookup"><span data-stu-id="157b7-166">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="157b7-167">Teams 中的使用者一律啟用與所有人 (包括同盟服務) 共用目前狀態。</span><span class="sxs-lookup"><span data-stu-id="157b7-167">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="157b7-168">他們的連絡人清單 (如果他們在商務用 Skype 中有此清單) 會顯示在 [聊天] > [連絡人]\*\*\*\* 底下或在 [通話] > [連絡人]\*\*\*\* 底下。</span><span class="sxs-lookup"><span data-stu-id="157b7-168">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="157b7-169">Teams 中的使用者一律啟用用戶端的「請勿打擾」和「突破」功能。</span><span class="sxs-lookup"><span data-stu-id="157b7-169">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="157b7-170">當 Teams 與 Outlook 整合時，一律為使用者啟用行事曆 (包括外出和其他行事曆資訊) 整合。</span><span class="sxs-lookup"><span data-stu-id="157b7-170">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="157b7-171">如果組織也使用商務用 Skype，Teams 中的使用者一律啟用 [上次看到]\*\* 或 [離開時間]\*\*。</span><span class="sxs-lookup"><span data-stu-id="157b7-171">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="157b7-172">目前不支援 Teams 系統管理員自訂這些設定的功能。</span><span class="sxs-lookup"><span data-stu-id="157b7-172">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="157b7-173">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="157b7-173">Coexistence with Skype for Business</span></span>

<span data-ttu-id="157b7-174">請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織使用商務用 Skype 時 Teams的運作方式詳細資料。</span><span class="sxs-lookup"><span data-stu-id="157b7-174">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
