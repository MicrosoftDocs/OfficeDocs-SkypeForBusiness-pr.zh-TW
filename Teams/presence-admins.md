---
title: 團隊中的使用者目前狀態
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 有關團隊中目前狀態的管理員資訊。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 054c3a639cc5857fb25a7e211a272868477dcb61
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573214"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="a5985-103">團隊中的使用者目前狀態</span><span class="sxs-lookup"><span data-stu-id="a5985-103">User presence in Teams</span></span>

<span data-ttu-id="a5985-104">目前狀態是 Microsoft 團隊（以及整個 Office 365）中使用者設定檔的一部分，可指出使用者目前的可用性與其他使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="a5985-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="a5985-105">根據預設，您組織中的任何人都可以在線上看到其他使用者（幾乎即時）。</span><span class="sxs-lookup"><span data-stu-id="a5985-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5985-106">如果您在將使用者移至 [**僅限團隊**] 模式之後卸載商務用 Skype 用戶端，目前狀態將會在 Outlook 和其他 Office app 中停止運作。</span><span class="sxs-lookup"><span data-stu-id="a5985-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="a5985-107">[目前狀態] 在小組中可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="a5985-107">Presence works fine in Teams.</span></span> <span data-ttu-id="a5985-108">因應措施：若要在 Outlook （以及其他 Office app）中查看目前狀態，您必須安裝商務用 Skype，即使您是在 [**僅限團隊**] 模式中執行團隊也一樣。</span><span class="sxs-lookup"><span data-stu-id="a5985-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="a5985-109">Microsoft 已注意到這個問題，正在努力解決問題。</span><span class="sxs-lookup"><span data-stu-id="a5985-109">Microsoft is aware of this problem and is working on a fix.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="a5985-110">團隊中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="a5985-110">Presence states in Teams</span></span>

<span data-ttu-id="a5985-111">團隊中提供的使用者目前狀態為：</span><span class="sxs-lookup"><span data-stu-id="a5985-111">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="a5985-112">已設定使用者</span><span class="sxs-lookup"><span data-stu-id="a5985-112">User configured</span></span>|<span data-ttu-id="a5985-113">App 已設定</span><span class="sxs-lookup"><span data-stu-id="a5985-113">App configured</span></span>|
|:--- |:---|
| ![穩定綠色核取記號，表示目前狀態為可用](media/Presence_Available.png) <span data-ttu-id="a5985-115">離線</span><span class="sxs-lookup"><span data-stu-id="a5985-115">Available</span></span>|![穩定綠色核取記號，表示目前狀態為可用](media/Presence_Available.png) <span data-ttu-id="a5985-117">離線</span><span class="sxs-lookup"><span data-stu-id="a5985-117">Available</span></span>|
|| ![開啟綠色核取記號，表示有空的 oof](media/Presence_Available_OOF.png) <span data-ttu-id="a5985-119">可用、不在辦公室</span><span class="sxs-lookup"><span data-stu-id="a5985-119">Available, Out of Office</span></span> |
|  ![實心紅圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="a5985-121">狀況</span><span class="sxs-lookup"><span data-stu-id="a5985-121">Busy</span></span> |  ![實心紅圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="a5985-123">狀況</span><span class="sxs-lookup"><span data-stu-id="a5985-123">Busy</span></span>  |
|| ![實心紅圈，表示通話中的占線](media/Presence_Busy.png) <span data-ttu-id="a5985-125">在通話中</span><span class="sxs-lookup"><span data-stu-id="a5985-125">In a call</span></span>|
|| ![實心紅圈，表示會議中的忙](media/Presence_Busy.png) <span data-ttu-id="a5985-127">在會議中</span><span class="sxs-lookup"><span data-stu-id="a5985-127">In a meeting</span></span> |
|| ![開啟紅色圓圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="a5985-129">在通話中，外出</span><span class="sxs-lookup"><span data-stu-id="a5985-129">In a call, out of office</span></span>|
|  ![紅色圓圈（含白色線條）表示 [請勿打擾]](media/Presence_DND.png) <span data-ttu-id="a5985-131">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="a5985-131">Do not disturb</span></span> ||
|| ![紅色圓圈（含白色線條）表示呈現](media/Presence_DND.png) <span data-ttu-id="a5985-133">介紹</span><span class="sxs-lookup"><span data-stu-id="a5985-133">Presenting</span></span>|
|| ![紅色圓圈（含白色線條）代表焦點](media/Presence_DND.png) <span data-ttu-id="a5985-135">致力</span><span class="sxs-lookup"><span data-stu-id="a5985-135">Focusing</span></span>|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="a5985-137">擺脫</span><span class="sxs-lookup"><span data-stu-id="a5985-137">Away</span></span>| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) <span data-ttu-id="a5985-139">擺脫</span><span class="sxs-lookup"><span data-stu-id="a5985-139">Away</span></span>|
|| <span data-ttu-id="a5985-140">![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次查看的*時間*</span><span class="sxs-lookup"><span data-stu-id="a5985-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黃色時鐘圖示，表示離開，立即返回](media/Presence_Away.png) <span data-ttu-id="a5985-142">馬上回來</span><span class="sxs-lookup"><span data-stu-id="a5985-142">Be right back</span></span>| |
|| ![黃色時鐘圖示，表示 [離開]、[下班中]](media/Presence_Away.png)  <span data-ttu-id="a5985-144">關閉工作</span><span class="sxs-lookup"><span data-stu-id="a5985-144">Off Work</span></span>|
|| ![X 的灰色圓圈表示離線](media/Presence_Offline.png) <span data-ttu-id="a5985-146">處於</span><span class="sxs-lookup"><span data-stu-id="a5985-146">Offline</span></span> |
|| ![開啟灰色圓圈，表示狀態未知](media/Presence_Unknown.png) <span data-ttu-id="a5985-148">狀態未知</span><span class="sxs-lookup"><span data-stu-id="a5985-148">Status unknown</span></span>|
||![以對角線開啟紅色圓圈，表示封鎖](media/Presence_Blocked.png) <span data-ttu-id="a5985-150">受阻</span><span class="sxs-lookup"><span data-stu-id="a5985-150">Blocked</span></span> |
|| ![含箭號的紫色圓圈表示不在辦公室](media/Presence_OOF.png) <span data-ttu-id="a5985-152">不在辦公室</span><span class="sxs-lookup"><span data-stu-id="a5985-152">Out of Office</span></span>|
|||
 
<span data-ttu-id="a5985-153">使用者可以將目前的目前狀態狀態手動設定為某些選項，而其狀態會反映給所有其他使用者。</span><span class="sxs-lookup"><span data-stu-id="a5985-153">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="a5985-154">更多使用者目前狀態詳細資料也會自動更新。</span><span class="sxs-lookup"><span data-stu-id="a5985-154">More user presence details are also automatically updated.</span></span> <span data-ttu-id="a5985-155">變更是以使用者活動（可用、離開）、Outlook 行事曆狀態（在會議中），或團隊 app 狀態（在進行中的通話中）來表示，在清單中縮排的狀態。</span><span class="sxs-lookup"><span data-stu-id="a5985-155">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="a5985-156">有15分鐘的非使用中超時，在這段時間之後，目前的目前狀態將會重設為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="a5985-156">There is a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="a5985-157">使用者可以指定誰可以中斷流覽（無論 [請勿打擾] 狀態，也表示與他們聯絡）。</span><span class="sxs-lookup"><span data-stu-id="a5985-157">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="a5985-158">[團隊用戶端] 提供這些設定。</span><span class="sxs-lookup"><span data-stu-id="a5985-158">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="a5985-159">團隊中與商務用 Skype 相比的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="a5985-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="a5985-160">下列系統管理員設定商務用 Skype 在小組中有所不同：</span><span class="sxs-lookup"><span data-stu-id="a5985-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="a5985-161">在團隊中，組織中的使用者永遠都能啟用目前狀態共用。</span><span class="sxs-lookup"><span data-stu-id="a5985-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="a5985-162">隱私權（您定義誰可以查看目前狀態）設定在團隊中無法使用。</span><span class="sxs-lookup"><span data-stu-id="a5985-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="a5985-163">[目前狀態] 與所有人共用（包括同盟服務），將會針對小組中的使用者永遠啟用。</span><span class="sxs-lookup"><span data-stu-id="a5985-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="a5985-164">連絡人清單（如果他們在商務用 Skype 中有一個）會顯示在 [**聊天] > 連絡人**] 底下，或 [**通話 > 連絡人**] 下。</span><span class="sxs-lookup"><span data-stu-id="a5985-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="a5985-165">用戶端的 [請勿打擾] 和 [突破性] 功能永遠都可供團隊中的使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="a5985-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="a5985-166">[行事曆] （包括 [不在辦公室] 和 [其他行事曆資訊]），當團隊與 Outlook 整合時，就會為使用者啟用整合。</span><span class="sxs-lookup"><span data-stu-id="a5985-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="a5985-167">如果組織也使用商務用 Skype，則 [*上次看到*] 或 [*離開*] 時，會針對小組中的使用者永遠啟用指標。</span><span class="sxs-lookup"><span data-stu-id="a5985-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="a5985-168">團隊系統管理員自訂這些設定的能力目前不受支援。</span><span class="sxs-lookup"><span data-stu-id="a5985-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="a5985-169">在商務用 Skype 中共存</span><span class="sxs-lookup"><span data-stu-id="a5985-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="a5985-170">請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織也使用商務用 skype 時，小組目前狀態如何運作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a5985-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
