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
description: 資訊管理員需要瞭解團隊中的目前狀態。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b3c36f0f83937e72ae4477ad38c9bd3187c6577
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244824"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="48513-103">團隊中的使用者目前狀態</span><span class="sxs-lookup"><span data-stu-id="48513-103">User presence in Teams</span></span>

<span data-ttu-id="48513-104">目前狀態是 Microsoft 團隊 (以及整個 Office 365) 中使用者設定檔的一部分, 指出使用者目前的可用性與組織中其他使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="48513-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="48513-105">根據預設, 您組織中的任何人都可以在幾乎即時看到, 不論其他使用者是否都能在線上使用。</span><span class="sxs-lookup"><span data-stu-id="48513-105">By default, anyone in your organization using Teams can see – in nearly real time – whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="48513-106">團隊中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="48513-106">Presence states in Teams</span></span>

<span data-ttu-id="48513-107">團隊中提供的使用者目前狀態為:</span><span class="sxs-lookup"><span data-stu-id="48513-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="48513-108">已設定使用者</span><span class="sxs-lookup"><span data-stu-id="48513-108">User configured</span></span>|<span data-ttu-id="48513-109">App 已設定</span><span class="sxs-lookup"><span data-stu-id="48513-109">App configured</span></span>|
|:--- |:---|
| ![穩定綠色 chek 標記, 表示目前狀態為可用](media/Presence_Available.png) <span data-ttu-id="48513-111">離線</span><span class="sxs-lookup"><span data-stu-id="48513-111">Available</span></span>|![穩定綠色 chek 標記, 表示目前狀態為可用](media/Presence_Available.png) <span data-ttu-id="48513-113">離線</span><span class="sxs-lookup"><span data-stu-id="48513-113">Available</span></span>|
|| ![開啟 [綠色 chek] 標記, 指出可用的 oof](media/Presence_Available_OOF.png) <span data-ttu-id="48513-115">可用、不在辦公室</span><span class="sxs-lookup"><span data-stu-id="48513-115">Available, Out of Office</span></span> |
|  ![實心紅色圓圈, 表示占線](media/Presence_Busy.png) <span data-ttu-id="48513-117">狀況</span><span class="sxs-lookup"><span data-stu-id="48513-117">Busy</span></span> |  ![實心紅色圓圈, 表示占線](media/Presence_Busy.png) <span data-ttu-id="48513-119">狀況</span><span class="sxs-lookup"><span data-stu-id="48513-119">Busy</span></span>  |
|| ![紅色實心圓圈, 表示通話中的占線](media/Presence_Busy.png) <span data-ttu-id="48513-121">在通話中</span><span class="sxs-lookup"><span data-stu-id="48513-121">In a call</span></span>|
|| ![實心紅色圓圈, 表示會議中的忙](media/Presence_Busy.png) <span data-ttu-id="48513-123">在會議中</span><span class="sxs-lookup"><span data-stu-id="48513-123">In a meeting</span></span> |
|| ![開啟紅色圓圈, 表示忙碌的 oof](media/Presence_Busy_OOF.png) <span data-ttu-id="48513-125">在通話中, 外出</span><span class="sxs-lookup"><span data-stu-id="48513-125">In a call, out of office</span></span>|
|  ![含白色線條的紅色圓圈, 表示 [請勿打擾]](media/Presence_DND.png) <span data-ttu-id="48513-127">請勿打擾</span><span class="sxs-lookup"><span data-stu-id="48513-127">Do not disturb</span></span> ||
|| ![含白色線條的紅色圓圈, 表示簡報](media/Presence_DND.png) <span data-ttu-id="48513-129">介紹</span><span class="sxs-lookup"><span data-stu-id="48513-129">Presenting</span></span>|
| ![黃色時鐘圖示, 表示離開](media/Presence_Away.png) <span data-ttu-id="48513-131">擺脫</span><span class="sxs-lookup"><span data-stu-id="48513-131">Away</span></span>| ![黃色時鐘圖示, 表示離開](media/Presence_Away.png) <span data-ttu-id="48513-133">擺脫</span><span class="sxs-lookup"><span data-stu-id="48513-133">Away</span></span>|
|| <span data-ttu-id="48513-134">![黃色時鐘圖示, 表示離開](media/Presence_Away.png)上次查看*時間*</span><span class="sxs-lookup"><span data-stu-id="48513-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黃色時鐘圖示, 表示背向後](media/Presence_Away.png) <span data-ttu-id="48513-136">馬上回來</span><span class="sxs-lookup"><span data-stu-id="48513-136">Be right back</span></span>| |
|| ![黃色時鐘圖示, 表示 [離開]、[下班中]](media/Presence_Away.png)  <span data-ttu-id="48513-138">關閉工作</span><span class="sxs-lookup"><span data-stu-id="48513-138">Off Work</span></span>|
|| ![包含 x 的灰色圓圈, 表示離線](media/Presence_Offline.png) <span data-ttu-id="48513-140">處於</span><span class="sxs-lookup"><span data-stu-id="48513-140">Offline</span></span> |
|| ![開啟灰色圓圈, 指出狀態未知](media/Presence_Unknown.png) <span data-ttu-id="48513-142">狀態未知</span><span class="sxs-lookup"><span data-stu-id="48513-142">Status unknown</span></span>|
||![以對角線開啟紅色圓圈, 表示已封鎖](media/Presence_Blocked.png) <span data-ttu-id="48513-144">受阻</span><span class="sxs-lookup"><span data-stu-id="48513-144">Blocked</span></span> |
|| ![含箭號的紫色圓圈, 表示不在辦公室](media/Presence_OOF.png) <span data-ttu-id="48513-146">不在辦公室</span><span class="sxs-lookup"><span data-stu-id="48513-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="48513-147">使用者可以將目前的目前狀態狀態手動設定為某些選項, 而其狀態會反映給所有其他使用者。</span><span class="sxs-lookup"><span data-stu-id="48513-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="48513-148">其他使用者目前狀態詳細資料也會根據使用者活動 (例如 [可用] 或 [離開])、Outlook 行事曆狀態 (例如會議), 或團隊 app 狀態 (在進行中的通話中), 自動更新至清單中的縮排狀態。</span><span class="sxs-lookup"><span data-stu-id="48513-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="48513-149">有15分鐘的非使用中超時, 在此時間之後, 使用者的目前狀態將會重設為 [離開]。</span><span class="sxs-lookup"><span data-stu-id="48513-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="48513-150">使用者可以指定誰可以中斷流覽 (請將其取代為 [請勿打擾] 設定)。</span><span class="sxs-lookup"><span data-stu-id="48513-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="48513-151">這些設定可在應用程式中使用。</span><span class="sxs-lookup"><span data-stu-id="48513-151">These settings are available in-app.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="48513-152">團隊中與商務用 Skype 相比的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="48513-152">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="48513-153">下列系統管理員設定商務用 Skype 在小組中有所不同:</span><span class="sxs-lookup"><span data-stu-id="48513-153">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="48513-154">在團隊中, 組織中的使用者永遠都能啟用目前狀態共用。</span><span class="sxs-lookup"><span data-stu-id="48513-154">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="48513-155">[隱私權] (決定誰可以查看目前狀態) 設定無法在小組中使用。</span><span class="sxs-lookup"><span data-stu-id="48513-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="48513-156">[目前狀態] 與所有人共用 (包括同盟服務), 將會針對小組中的使用者永遠啟用。</span><span class="sxs-lookup"><span data-stu-id="48513-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="48513-157">連絡人清單 (如果他們在商務用 Skype 中有一個) 會顯示在 [**聊天] > 連絡人**] 底下, 或 [**通話 > 連絡人**] 下。</span><span class="sxs-lookup"><span data-stu-id="48513-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="48513-158">用戶端的 [請勿打擾] 和 [突破性] 功能永遠都可供團隊中的使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="48513-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="48513-159">[行事曆] (包括 [不在辦公室] 和 [其他行事曆資訊]), 如果您已與 Outlook 整合, 就會針對團隊中的使用者,</span><span class="sxs-lookup"><span data-stu-id="48513-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="48513-160">[*最近*] 或 [*離開*] (如果在使用商務用 Skype 的雙重環境中) 指示符針對小組中的使用者。</span><span class="sxs-lookup"><span data-stu-id="48513-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="48513-161">團隊系統管理員自訂這些設定的能力目前不受支援。</span><span class="sxs-lookup"><span data-stu-id="48513-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="48513-162">在商務用 Skype 中共存</span><span class="sxs-lookup"><span data-stu-id="48513-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="48513-163">請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md), 以取得在與商務用 skype 共存時, 小組目前狀態如何運作的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="48513-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
