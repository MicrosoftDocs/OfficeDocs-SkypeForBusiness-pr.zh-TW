---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11252c916224393c19ebc11c4c40faceab02342c
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940666"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a><span data-ttu-id="cd14e-103">與團隊和商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="cd14e-103">Coexistence with Teams and Skype for Business</span></span>

<span data-ttu-id="cd14e-104">本文將說明當您在同一個組織中執行兩個小組和商務用 Skype 用戶端時可能遇到的行為，無論使用何種模式和要使用哪種升級方法：</span><span class="sxs-lookup"><span data-stu-id="cd14e-104">This article summarizes behavior that may be experienced when running both Teams and Skype for Business clients in the same organization, regardless of what mode and what upgrade method is used:</span></span>

- [<span data-ttu-id="cd14e-105">會議</span><span class="sxs-lookup"><span data-stu-id="cd14e-105">Meetings</span></span>](#meetings)
- [<span data-ttu-id="cd14e-106">互通性</span><span class="sxs-lookup"><span data-stu-id="cd14e-106">Interoperability</span></span>](#interoperability)
- [<span data-ttu-id="cd14e-107">團隊交談-互通性與原生執行緒</span><span class="sxs-lookup"><span data-stu-id="cd14e-107">Teams conversations-Interop versus native threads</span></span>](#teams-conversations---interop-versus-native-threads)
- [<span data-ttu-id="cd14e-108">目前狀態</span><span class="sxs-lookup"><span data-stu-id="cd14e-108">Presence</span></span>](#presence)
- [<span data-ttu-id="cd14e-109">同盟</span><span class="sxs-lookup"><span data-stu-id="cd14e-109">Federation</span></span>](#federation)
- [<span data-ttu-id="cd14e-110">連絡人</span><span class="sxs-lookup"><span data-stu-id="cd14e-110">Contacts</span></span>](#contacts)



## <a name="meetings"></a><span data-ttu-id="cd14e-111">會議</span><span class="sxs-lookup"><span data-stu-id="cd14e-111">Meetings</span></span>

<span data-ttu-id="cd14e-112">無論其模式為何，使用者都可以加入受邀者（無論是商務用 Skype 或團隊）所邀請的任何類型的會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-112">Regardless of their mode, users can always join any type of meeting they are invited to, whether it is Skype for Business or Teams.</span></span>  <span data-ttu-id="cd14e-113">不過，使用者必須以符合會議類型的對應用戶端加入會議：</span><span class="sxs-lookup"><span data-stu-id="cd14e-113">However, users must join the meeting with a corresponding client that matches the meeting type:</span></span>

- <span data-ttu-id="cd14e-114">如果會議是「團隊」會議，所有參與者都 (他們是 TeamsOnly、孤島或商務用 Skype 使用者) 使用團隊用戶端加入會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-114">If the meeting is a Teams meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Teams client to join the meeting.</span></span> <span data-ttu-id="cd14e-115">如果未安裝團隊，則在試圖加入會議時，該使用者會被導向網頁。</span><span class="sxs-lookup"><span data-stu-id="cd14e-115">If Teams is not installed, the user will be directed to the web, upon attempting to join a meeting.</span></span>

- <span data-ttu-id="cd14e-116">如果會議是商務用 Skype 會議，所有參與者都 (他們是 TeamsOnly、孤島或商務用 Skype 使用者) 使用商務用 Skype 用戶端加入會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-116">If the meeting is a Skype for Business meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Skype for Business client to join the meeting.</span></span> <span data-ttu-id="cd14e-117">如果未安裝商務用 Skype 用戶端，使用者將會透過 Skype 會議應用程式導向網頁進行加入。</span><span class="sxs-lookup"><span data-stu-id="cd14e-117">If the Skype for Business client is not installed, the user will be directed to the web to join via the Skype Meeting App.</span></span>

<span data-ttu-id="cd14e-118">組織會議時，排程的會議類型是以召集人的模式為基礎，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="cd14e-118">When organizing meetings, the meeting type that gets scheduled is based on the mode of the organizer, as shown in the following table:</span></span>

| <span data-ttu-id="cd14e-119">召集人模式</span><span class="sxs-lookup"><span data-stu-id="cd14e-119">Mode of organizer</span></span>    |      <span data-ttu-id="cd14e-120">行為</span><span class="sxs-lookup"><span data-stu-id="cd14e-120">Behavior</span></span> |
| :------------------ | :---------------- |
| <span data-ttu-id="cd14e-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="cd14e-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span></span> |    <span data-ttu-id="cd14e-122">安排在團隊中的所有會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-122">All meetings scheduled in Teams.</span></span> <span data-ttu-id="cd14e-123">Outlook 中無法使用商務用 Skype 增益集。</span><span class="sxs-lookup"><span data-stu-id="cd14e-123">Skype for Business add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="cd14e-124">SfbWithTeamsCollab, SfbOnly</span><span class="sxs-lookup"><span data-stu-id="cd14e-124">SfbWithTeamsCollab, SfbOnly</span></span>   | <span data-ttu-id="cd14e-125">在商務用 Skype 中排程的所有會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-125">All meetings scheduled in Skype for Business.</span></span> <span data-ttu-id="cd14e-126">Outlook 中無法使用 [團隊] 增益集。</span><span class="sxs-lookup"><span data-stu-id="cd14e-126">Teams add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="cd14e-127">離島</span><span class="sxs-lookup"><span data-stu-id="cd14e-127">Islands</span></span> | <span data-ttu-id="cd14e-128">根據預設，可以在商務用 Skype 或團隊中排程會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-128">By default, meetings can be scheduled in either Skype for Business or Teams.</span></span> <span data-ttu-id="cd14e-129">您可以在 Outlook 中使用這兩個增益集。</span><span class="sxs-lookup"><span data-stu-id="cd14e-129">Both add-ins are available in Outlook.</span></span> <span data-ttu-id="cd14e-130">不過，您可以選擇性地要求在 Islands 中的使用者使用 PreferredMeetingProviderForIslandsMode = 團隊指派 TeamsMeetingPolicy 的實例，在小組中隨時排程會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-130">However, you can optionally require that users in Islands always schedule meetings in Teams by assigning them an instance of TeamsMeetingPolicy with the PreferredMeetingProviderForIslandsMode=Teams.</span></span>| 


## <a name="interoperability"></a><span data-ttu-id="cd14e-131">互通性</span><span class="sxs-lookup"><span data-stu-id="cd14e-131">Interoperability</span></span>

<span data-ttu-id="cd14e-132">在某些情況下，小組支援與商務用 Skype ) 的互通性 ( 「交互操作」。</span><span class="sxs-lookup"><span data-stu-id="cd14e-132">Teams supports interoperability (“interop”) with Skype for Business in certain scenarios.</span></span> <span data-ttu-id="cd14e-133">互通性通訊指的是商務用 Skype 使用者與團隊使用者之間的交談或通話。</span><span class="sxs-lookup"><span data-stu-id="cd14e-133">Interop communication refers to a chat or call between a Skype for Business user and a Teams user.</span></span>  <span data-ttu-id="cd14e-134">交互操作通訊只可以在兩個使用者之間取得;不支援多方聊天/通話或新增其他使用者。</span><span class="sxs-lookup"><span data-stu-id="cd14e-134">Interop communication is only possible between two users; multi-party chat/calling or adding additional users is not supported.</span></span>

<span data-ttu-id="cd14e-135">當下列各項都成立時，就會建立兩個使用者之間的互通性聊天或通話：</span><span class="sxs-lookup"><span data-stu-id="cd14e-135">An interop chat or call between two users is created when each of the following are true:</span></span>

- <span data-ttu-id="cd14e-136">一位使用者使用的是 [商務用 Skype]。</span><span class="sxs-lookup"><span data-stu-id="cd14e-136">One user is using Teams and the other is using Skype for Business.</span></span>

- <span data-ttu-id="cd14e-137">初始通訊的收件者模式不是孤島 (否則，如果兩個使用者都在同一個組織中，通訊就會在相同的用戶端) 中土地。</span><span class="sxs-lookup"><span data-stu-id="cd14e-137">The mode of the recipient of the initial communication is NOT Islands (otherwise the communication would land in the same client) if both users are in the same organization.</span></span> <span data-ttu-id="cd14e-138">在聯盟案例中，傳送使用者使用的是 [小組]，而收件者則不是 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="cd14e-138">In federated scenarios, the sending user is using Teams, and the recipient is not in TeamsOnly mode.</span></span> 

- <span data-ttu-id="cd14e-139">團隊使用者也不會將商務用 Skype 帳戶駐留在內部部署中。</span><span class="sxs-lookup"><span data-stu-id="cd14e-139">The Teams user does NOT also have a Skype for Business account homed on-premises.</span></span> 

<span data-ttu-id="cd14e-140">在交互操作通訊中，聊天只是純文字。</span><span class="sxs-lookup"><span data-stu-id="cd14e-140">Within the interop communication, chat is plain-text only.</span></span> <span data-ttu-id="cd14e-141">此外，在 *交互操作聊天本身中*不可能進行檔案共用和螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="cd14e-141">In addition, file sharing and screen sharing are not possible *in the interop chat itself*.</span></span> <span data-ttu-id="cd14e-142">不過，交互操作交談中的使用者可以從互通性聊天中建立點播會議，輕鬆地達到檔案和/或螢幕共用，如下所述：</span><span class="sxs-lookup"><span data-stu-id="cd14e-142">However, users in an interop conversation can easily achieve file and/or screen sharing by creating an on-demand meeting, from within the interop chat, as described below:</span></span>

- <span data-ttu-id="cd14e-143">如果小組使用者嘗試共用其畫面，系統會自動建立一個點播團隊會議，而該會議的邀請連結會傳送到商務用 Skype 使用者的用戶端。</span><span class="sxs-lookup"><span data-stu-id="cd14e-143">If the Teams user attempts to share their screen, an on-demand Teams meeting is automatically created and an invite link to that meeting is sent to the Skype for Business user’s client.</span></span> <span data-ttu-id="cd14e-144">按一下連結時，商務用 Skype 使用者將會開啟團隊並加入會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-144">Upon clicking the link, the Skype for Business user will open Teams and join the meeting.</span></span> <span data-ttu-id="cd14e-145">兩個使用者現在都在團隊會議中，而且可以視需要共用。</span><span class="sxs-lookup"><span data-stu-id="cd14e-145">Both users are now in a Teams meeting and can share as needed.</span></span>

- <span data-ttu-id="cd14e-146">如果商務用 Skype 使用者使用的是2018或更新版本的用戶端，且試圖共用任何內容，則會自動建立點播商務用 Skype 會議，而該會議的邀請連結會傳送給團隊使用者的用戶端。</span><span class="sxs-lookup"><span data-stu-id="cd14e-146">If the Skype for Business user is using a client from 2018 or later and attempts to share any content, an on-demand Skype for Business meeting is automatically created and an invite link to that meeting is sent to the Teams user’s client.</span></span> <span data-ttu-id="cd14e-147">當您按一下連結時，小組使用者會嘗試加入商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="cd14e-147">Upon clicking the link, the Teams user will attempt to join the Skype for Business meeting.</span></span> <span data-ttu-id="cd14e-148">如果團隊使用者已安裝商務用 Skype 用戶端，則會開啟並提示使用者登入 (（如果尚未登入) ）。</span><span class="sxs-lookup"><span data-stu-id="cd14e-148">If the Teams user has the Skype for Business client installed, it will open and the user is prompted to sign in (if not already signed in).</span></span>  <span data-ttu-id="cd14e-149">如果團隊使用者沒有安裝商務用 Skype 用戶端，系統會提示使用者使用 web 版本。</span><span class="sxs-lookup"><span data-stu-id="cd14e-149">If the Teams user does not have the Skype for Business client installed, the user will be prompted to use the web version.</span></span> <span data-ttu-id="cd14e-150">這兩個使用者登入之後，他們就在商務用 Skype 會議中，而且可以視需要共用。</span><span class="sxs-lookup"><span data-stu-id="cd14e-150">Once both users are signed in, they are in a Skype for Business meeting and can share as needed.</span></span>

## <a name="teams-conversations---interop-versus-native-threads"></a><span data-ttu-id="cd14e-151">團隊交談-互通性與原生執行緒</span><span class="sxs-lookup"><span data-stu-id="cd14e-151">Teams conversations - Interop versus native threads</span></span>

<span data-ttu-id="cd14e-152">因為互通性通訊不支援原生團隊交談的所有功能，所以團隊用戶端會為小組對團隊以及商務用 Skype 通訊提供獨立的交談執行緒。</span><span class="sxs-lookup"><span data-stu-id="cd14e-152">Because interop communications do not support all the features of native Teams conversation, the Teams client maintains separate conversation threads for Teams-to-Teams and Teams-to-Skype for Business communication.</span></span> <span data-ttu-id="cd14e-153">這些交談在使用者介面中會以不同的方式呈現：互通性執行緒可以與一般原生團隊執行緒區別：</span><span class="sxs-lookup"><span data-stu-id="cd14e-153">These conversations are rendered differently in the user interface: Interop threads can be differentiated from a regular native Teams thread by:</span></span>

- <span data-ttu-id="cd14e-154">不需要豐富的文字、檔案/螢幕共用、無法新增使用者的控制項。</span><span class="sxs-lookup"><span data-stu-id="cd14e-154">Lack of controls for rich text, file/screen sharing, inability to add users.</span></span>
- <span data-ttu-id="cd14e-155">針對目標使用者的圖示所做的修改，顯示商務用 Skype 的「S」。</span><span class="sxs-lookup"><span data-stu-id="cd14e-155">A modification to the target user’s icon, showing an “S” for Skype for Business.</span></span>

<span data-ttu-id="cd14e-156">下列螢幕擷取畫面顯示這些差異：</span><span class="sxs-lookup"><span data-stu-id="cd14e-156">These differences are shown in the following screenshots:</span></span>

<span data-ttu-id="cd14e-157">與使用者 G3 測試的原生團隊與團隊交談</span><span class="sxs-lookup"><span data-stu-id="cd14e-157">A native Teams-to-Teams conversation with User G3 Test</span></span>

![顯示原生團隊與團隊交談的圖表](media/teams-upgrade-native-thread.png)

<span data-ttu-id="cd14e-159">具有相同使用者 G3 測試的互通性交談</span><span class="sxs-lookup"><span data-stu-id="cd14e-159">An interop conversation with the same User G3 Test</span></span>

![顯示互通性團隊與團隊交談的圖表](media/teams-upgrade-interop-thread.png)

<span data-ttu-id="cd14e-161">建立交談執行緒之後，其類型就不會變更。</span><span class="sxs-lookup"><span data-stu-id="cd14e-161">Once a conversation thread is created, its type never changes.</span></span> <span data-ttu-id="cd14e-162">建立後，小組中的互通性執行緒將永遠會傳送給目標使用者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="cd14e-162">Once created, an interop thread in Teams will always route to the target user’s Skype for Business client.</span></span> <span data-ttu-id="cd14e-163">原生執行緒永遠會傳送給目標使用者的團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="cd14e-163">A native thread will always route to the target user’s Teams client.</span></span>  <span data-ttu-id="cd14e-164">如果收件者使用者的模式變更，現有的團隊執行緒將無法正常運作，而且會在該聊天上顯示一則筆記，其中包含開始新的原生交談的連結，如下列螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="cd14e-164">If a recipient user’s mode changes, existing Teams threads to that user will no longer function and a note will be displayed on that chat with a link to start a new native conversation as shown in the following screenshot.</span></span>


![顯示已升級的商務用 Skype 使用者聊天的圖表](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a><span data-ttu-id="cd14e-166">目前狀態</span><span class="sxs-lookup"><span data-stu-id="cd14e-166">Presence</span></span>

<span data-ttu-id="cd14e-167">指定使用者的「目前狀態」是依據客戶在服務中的活動。</span><span class="sxs-lookup"><span data-stu-id="cd14e-167">Presence for a given user is based on the user’s activity in the service via the client.</span></span> <span data-ttu-id="cd14e-168">隨後便會發佈目前狀態，供其他使用者查看。</span><span class="sxs-lookup"><span data-stu-id="cd14e-168">The presence is then published for other users to see.</span></span>  <span data-ttu-id="cd14e-169">商務用 Skype 與團隊是獨立用戶端的個別服務，所以每個服務都有自己的狀態供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="cd14e-169">Skype for Business and Teams are separate services with separate clients, so each service has its own presence state for a user.</span></span>   <span data-ttu-id="cd14e-170">在團隊與商務用 Skype Online 中的目前狀態服務之間也有同步處理。</span><span class="sxs-lookup"><span data-stu-id="cd14e-170">There is also synchronization between the presence services in Teams and in Skype for Business Online.</span></span>  <span data-ttu-id="cd14e-171">這可讓一個服務視需要從其他服務發佈使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="cd14e-171">This allows one service to potentially publish the presence of the user from the other service if needed.</span></span> 

<span data-ttu-id="cd14e-172">目前狀態發佈行為是以使用者的模式為基礎。</span><span class="sxs-lookup"><span data-stu-id="cd14e-172">Presence publishing behavior is based on the user’s mode.</span></span> <span data-ttu-id="cd14e-173">以下是三種基本案例：</span><span class="sxs-lookup"><span data-stu-id="cd14e-173">There are three basic cases:</span></span>

- <span data-ttu-id="cd14e-174">如果使用者處於 TeamsOnly 模式，則所有其他使用者都會看到該使用者的小組目前狀態，不論他們使用的是哪一個用戶端。</span><span class="sxs-lookup"><span data-stu-id="cd14e-174">If a user is in TeamsOnly mode, all other users see Teams presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="cd14e-175">如果使用者是在任何商務用 Skype 模式中，所有其他使用者都會看到該使用者的商務用 Skype 目前狀態，不論他們使用的是哪一種用戶端。</span><span class="sxs-lookup"><span data-stu-id="cd14e-175">If a user is in any of the Skype for Business modes, all other users see Skype for Business presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="cd14e-176">如果使用者使用的是孤島模式，在商務用 Skype 中發佈的目前狀態就是獨立的，因此同一個組織中的使用者所顯示的目前狀態將視其他使用者的用戶端而定。</span><span class="sxs-lookup"><span data-stu-id="cd14e-176">If a user is in Islands mode, presence published in Skype for Business and Teams are independent, so the presence shown to users within the same organization will depend on the client of the other user.</span></span> <span data-ttu-id="cd14e-177">同盟組織中的使用者會根據商務用 Skype 活動查看該使用者的目前狀態，因為在商務用 Skype 中，來自孤島模式使用者的聯盟流量。</span><span class="sxs-lookup"><span data-stu-id="cd14e-177">Users in federated organizations will see presence of that user based on their Skype for Business activity, since federated traffic to an Islands mode user lands in Skype for Business.</span></span>

<span data-ttu-id="cd14e-178">例如，假設使用者 A 處於孤島模式。</span><span class="sxs-lookup"><span data-stu-id="cd14e-178">For example, Assume User A is in Islands mode.</span></span> <span data-ttu-id="cd14e-179">如果使用者 A 在小組中使用中，但尚未登入商務用 Skype，其他使用者就會看到使用者 A 從其小組用戶端使用，但在其商務用 Skype 用戶端中，他們會看到使用者 A 為離線狀態。</span><span class="sxs-lookup"><span data-stu-id="cd14e-179">If User A is active in Teams but is not signed in to Skype for Business, other users would see User A as active from their Teams client, but in their Skype for Business client they would see User A as offline.</span></span> <span data-ttu-id="cd14e-180">這是由於設計，因為使用者 A 不在執行用戶端，所以無法到達。</span><span class="sxs-lookup"><span data-stu-id="cd14e-180">This is by design, since User A cannot be reached if they are not running the client.</span></span> 


## <a name="federation"></a><span data-ttu-id="cd14e-181">同盟</span><span class="sxs-lookup"><span data-stu-id="cd14e-181">Federation</span></span>

<span data-ttu-id="cd14e-182">從小組聯盟到另一個使用商務用 Skype 的使用者，必須讓團隊使用者在商務用 Skype 中駐留在線上。</span><span class="sxs-lookup"><span data-stu-id="cd14e-182">Federation from Teams to another user using Skype for Business requires the Teams user to be homed online in Skype for Business.</span></span> <span data-ttu-id="cd14e-183">TeamsUpgradePolicy 會控制傳入的同盟聊天和通話的路由。</span><span class="sxs-lookup"><span data-stu-id="cd14e-183">TeamsUpgradePolicy governs routing for incoming federated chats and calls.</span></span> <span data-ttu-id="cd14e-184">同盟路由行為與與相同租使用者案例相同，但在孤島模式除外。</span><span class="sxs-lookup"><span data-stu-id="cd14e-184">Federated routing behavior is the same as for same-tenant scenarios, except in Islands mode.</span></span> <span data-ttu-id="cd14e-185">當收件者處於孤島模式時：</span><span class="sxs-lookup"><span data-stu-id="cd14e-185">When recipients are in Islands mode:</span></span>

- <span data-ttu-id="cd14e-186">如果收件者是聯盟租使用者，則會從商務用 Skype 中的 [小組] 土地開始聊天和通話。</span><span class="sxs-lookup"><span data-stu-id="cd14e-186">Chats and calls initiated from Teams land in Skype for Business if the recipient is in a federated tenant.</span></span>
- <span data-ttu-id="cd14e-187">如果收件者在相同的租使用者中，就會從團隊中的團隊土地開始聊天和通話。</span><span class="sxs-lookup"><span data-stu-id="cd14e-187">Chats and calls initiated from Teams land in Teams if the recipient is in the same tenant.</span></span>
- <span data-ttu-id="cd14e-188">從商務用 Skype 發起的聊天和通話，在商務用 Skype 中永遠不間斷。</span><span class="sxs-lookup"><span data-stu-id="cd14e-188">Chats and calls initiated from Skype for Business always land in Skype for Business.</span></span>

<span data-ttu-id="cd14e-189">聯盟聊天可以是本機執行緒或交互操作執行緒。</span><span class="sxs-lookup"><span data-stu-id="cd14e-189">A federated chat can either be a native thread or an interop thread.</span></span> <span data-ttu-id="cd14e-190">請參閱 [小組交談---互通性與本機執行緒](#teams-conversations---interop-versus-native-threads)。</span><span class="sxs-lookup"><span data-stu-id="cd14e-190">See [Teams Conversations ---interop-versus-native-threads](#teams-conversations---interop-versus-native-threads).</span></span>

- <span data-ttu-id="cd14e-191">如果收件者和寄件者都在 TeamsOnly 升級模式中，則交談將是一個固有的聊天體驗，包括所有豐富的訊息和呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="cd14e-191">If the receiver and sender are both in TeamsOnly upgrade mode, the conversation will be a native chat experience which includes all the rich messaging and calling capabilities.</span></span> <span data-ttu-id="cd14e-192">若要深入瞭解，請閱讀 [團隊中的外部 (聯盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="cd14e-192">To learn more, read [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span> 

- <span data-ttu-id="cd14e-193">如果其中一個交談參與者不在 TeamsOnly 升級模式中，則交談仍會有純文字訊息的交互操作體驗。</span><span class="sxs-lookup"><span data-stu-id="cd14e-193">If either of the conversation participants is NOT in TeamsOnly upgrade mode, the conversation remains an interop experience with text-only messages.</span></span> <span data-ttu-id="cd14e-194">使用者介面會以與同一個租使用者交互操作執行緒相似的方式公開同盟聊天，但有一個指示使用者是外部的筆記。</span><span class="sxs-lookup"><span data-stu-id="cd14e-194">The user interface exposes federated chats in a similar manner to same-tenant interop threads, except there is a note indicating the user is external.</span></span>

<span data-ttu-id="cd14e-195">如需更多詳細資料，請參閱在團隊中管理[外部 (聯盟) 使用者](native-chat-for-external-users.md)的[Microsoft 團隊中的外部存取](manage-external-access.md)及原生聊天體驗。</span><span class="sxs-lookup"><span data-stu-id="cd14e-195">For more details, see [Manage external access in Microsoft Teams](manage-external-access.md) and [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span>

## <a name="contacts"></a><span data-ttu-id="cd14e-196">連絡人</span><span class="sxs-lookup"><span data-stu-id="cd14e-196">Contacts</span></span>

<span data-ttu-id="cd14e-197">[小組] 和 [商務用 Skype] 有不同的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="cd14e-197">Teams and Skype for Business have separate lists of contacts.</span></span> <span data-ttu-id="cd14e-198">這表示在單一系統中所做的連絡人新增、移除及修改，不會與其他系統同步處理。</span><span class="sxs-lookup"><span data-stu-id="cd14e-198">This means that contact additions, removal, and modifications made in one system are not synchronized to the other system.</span></span> <span data-ttu-id="cd14e-199">不過，當兩個特定事件發生時，商務用 Skype 的連絡人會自動複製到小組中：</span><span class="sxs-lookup"><span data-stu-id="cd14e-199">However, contacts from Skype for Business are automatically copied over to Teams when either of two specific events occur:</span></span> 

- <span data-ttu-id="cd14e-200">針對任何商務用 Skype Online 使用者，第一次登入小組時，商務用 Skype 的連絡人將會複製到小組。</span><span class="sxs-lookup"><span data-stu-id="cd14e-200">For any Skype for Business Online user, the first time they log onto Teams, contacts from Skype for Business will be copied over to Teams.</span></span>  <span data-ttu-id="cd14e-201">在商務用 Skype Server 中擁有內部部署帳戶的使用者無法使用此行為。</span><span class="sxs-lookup"><span data-stu-id="cd14e-201">This behavior is not available for users with an on-premises account in Skype for Business Server.</span></span>  

- <span data-ttu-id="cd14e-202">在使用者升級至 TeamsOnly (之後，您可以透過指派 TeamsUpgradePolicy 或移動 Move-csuser-MoveToTeams) ，下次使用者登入小組時，商務用 Skype 中現有的連絡人將會與已存在於團隊中的現有連絡人合併。</span><span class="sxs-lookup"><span data-stu-id="cd14e-202">After a user is upgraded to TeamsOnly (either via assigning TeamsUpgradePolicy or via Move-CsUser -MoveToTeams), the next time a user logs into Teams, existing contacts in Skype for Business will be merged with existing contacts already in Teams.</span></span> <span data-ttu-id="cd14e-203">不論使用者的商務用 Skype 帳戶是駐留在內部部署還是線上，都會發生此行為。</span><span class="sxs-lookup"><span data-stu-id="cd14e-203">This behavior happens whether the user’s Skype for Business Account is homed on-premises or online.</span></span> 

<span data-ttu-id="cd14e-204">在這兩種情況下，從商務用 Skype 將連絡人轉移至團隊是非同步，因此可能需要幾分鐘的時間，才會在團隊中顯示連絡人。</span><span class="sxs-lookup"><span data-stu-id="cd14e-204">In both cases, the transfer of contacts from Skype for Business to Teams is asynchronous so it may be a few minutes before contacts appear in Teams.</span></span> <span data-ttu-id="cd14e-205">上述兩個事件會觸發複本。</span><span class="sxs-lookup"><span data-stu-id="cd14e-205">The two events above are what trigger the copy.</span></span>  

## <a name="related-links"></a><span data-ttu-id="cd14e-206">相關連結</span><span class="sxs-lookup"><span data-stu-id="cd14e-206">Related links</span></span>

[<span data-ttu-id="cd14e-207">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="cd14e-207">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="cd14e-208">在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="cd14e-208">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="cd14e-209">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="cd14e-209">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="cd14e-210">設定您的共存與升級設定</span><span class="sxs-lookup"><span data-stu-id="cd14e-210">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="cd14e-211">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="cd14e-211">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="cd14e-212">使用會議遷移服務 (MMS) </span><span class="sxs-lookup"><span data-stu-id="cd14e-212">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

