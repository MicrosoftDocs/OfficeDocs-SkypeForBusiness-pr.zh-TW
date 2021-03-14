---
title: 訊息委派
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 了解狀態為 [離開] 或 [請勿打擾] 的使用者如何在狀態訊息中明確地將另一個使用者設定為代理人。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790465"
---
# <a name="message-delegation"></a><span data-ttu-id="c12ab-103">訊息委派</span><span class="sxs-lookup"><span data-stu-id="c12ab-103">Message delegation</span></span>

<span data-ttu-id="c12ab-104">使用者可以明確將狀態設定為 [離開] 或 [請勿打擾] ，並提供自訂文字。</span><span class="sxs-lookup"><span data-stu-id="c12ab-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="c12ab-105">郵件委派功能運作方式如下：</span><span class="sxs-lookup"><span data-stu-id="c12ab-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="c12ab-106">使用者透過「@使用者名稱」在文字狀態訊息的一部分提及另一位使用者，表示當使用者無法連絡到他們時，請改為聯絡「@使用者名稱」所提及的使用者。</span><span class="sxs-lookup"><span data-stu-id="c12ab-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="c12ab-107">獲指派為代理人的人會收到通知，告知他們已被指定為代理人。</span><span class="sxs-lookup"><span data-stu-id="c12ab-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="c12ab-108">接著，嘗試連絡第一位使用者的使用者可以將游標停留在指定的代理人上方，並輕鬆地改為以訊息通知代理人。</span><span class="sxs-lookup"><span data-stu-id="c12ab-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="c12ab-109">這是一項使用者自行在用戶端中啟動的進程，而不需要系統管理員介入來啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="c12ab-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="c12ab-110">醫療保健中的委派使用案例</span><span class="sxs-lookup"><span data-stu-id="c12ab-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="c12ab-111">*未設定代理人的使用範例：* Franco Piccio 醫生在放射學部門值班。</span><span class="sxs-lookup"><span data-stu-id="c12ab-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="c12ab-112">他接到緊急個人電話，必須離開幾小時。</span><span class="sxs-lookup"><span data-stu-id="c12ab-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="c12ab-113">他要求放射學部門的其中一位同僚 Lena Ehrle 醫生在離開時為他代班。</span><span class="sxs-lookup"><span data-stu-id="c12ab-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="c12ab-114">他非正式地將自己的呼叫器給 Ehrle 醫生，後者在她目前的職責之外，還負責聆聽緊急訊息和在呼叫器上偵測，並代表 Piccio 醫生回應他們。</span><span class="sxs-lookup"><span data-stu-id="c12ab-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="c12ab-115">團隊中的其他人可能不知道這項非正式委派，而在病患的照護上造成混淆。</span><span class="sxs-lookup"><span data-stu-id="c12ab-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="c12ab-116">*設定代理人的使用範例：* Franco Piccio 醫生在放射學部門值班。</span><span class="sxs-lookup"><span data-stu-id="c12ab-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="c12ab-117">他接到緊急個人電話，必須離開幾小時。</span><span class="sxs-lookup"><span data-stu-id="c12ab-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="c12ab-118">他要求放射學部門的其中一位同僚 Lena Ehrle 醫生在離開時為他代班。</span><span class="sxs-lookup"><span data-stu-id="c12ab-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="c12ab-119">他變更了自訂狀態訊息，內容類似於「我接下來幾個小時人不在。</span><span class="sxs-lookup"><span data-stu-id="c12ab-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="c12ab-120">如有任何緊急狀況，請聯絡 @DrEhrle。」</span><span class="sxs-lookup"><span data-stu-id="c12ab-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="c12ab-121">團隊中的其他人在嘗試與 Piccio 醫生聯繫時，得知這項委派，因此他們現在知道要與 Ehrle 醫生聯繫。</span><span class="sxs-lookup"><span data-stu-id="c12ab-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="c12ab-122">對於病患的照護，幾乎未造成混淆。</span><span class="sxs-lookup"><span data-stu-id="c12ab-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="c12ab-123">共存模式對 Teams 用戶端中使用者狀態的影響</span><span class="sxs-lookup"><span data-stu-id="c12ab-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="c12ab-124">系統管理員應注意，狀態備註和委派提及行為會部分取決於使用者的共存模式。</span><span class="sxs-lookup"><span data-stu-id="c12ab-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="c12ab-125">此矩陣顯示可能性：</span><span class="sxs-lookup"><span data-stu-id="c12ab-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="c12ab-126">共存模式</span><span class="sxs-lookup"><span data-stu-id="c12ab-126">Co-Existence Mode</span></span> | <span data-ttu-id="c12ab-127">預期的結果</span><span class="sxs-lookup"><span data-stu-id="c12ab-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="c12ab-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="c12ab-128">TeamsOnly</span></span> |<span data-ttu-id="c12ab-129">使用者只能從 Teams 設定備註。</span><span class="sxs-lookup"><span data-stu-id="c12ab-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="c12ab-130">使用者的 Teams 備註可在 Teams 和 SfB 中看見。</span><span class="sxs-lookup"><span data-stu-id="c12ab-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="c12ab-131">Islands</span><span class="sxs-lookup"><span data-stu-id="c12ab-131">Islands</span></span> | <span data-ttu-id="c12ab-132">在 Teams 中設定的使用者備註只能在 Teams 中顯示。</span><span class="sxs-lookup"><span data-stu-id="c12ab-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="c12ab-133">在 SfB 中設定的使用者備註只能在 SfB 中顯示</span><span class="sxs-lookup"><span data-stu-id="c12ab-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="c12ab-134">SfB\* 模式</span><span class="sxs-lookup"><span data-stu-id="c12ab-134">SfB\* modes</span></span> | <span data-ttu-id="c12ab-135">使用者只能從 SfB 設定備註。</span><span class="sxs-lookup"><span data-stu-id="c12ab-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="c12ab-136">使用者的 SfB 備註可在 SfB 和 Teams 中看見。</span><span class="sxs-lookup"><span data-stu-id="c12ab-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="c12ab-137">使用者只有在其模式為 TeamsOnly 或 Islands 時，才能在 Teams 中設定備註。</span><span class="sxs-lookup"><span data-stu-id="c12ab-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="c12ab-138">顯示在商務用 Skype 中設定的備註</span><span class="sxs-lookup"><span data-stu-id="c12ab-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="c12ab-139">並無視覺效果可表示備註是在商務用 Skype 中所設定。</span><span class="sxs-lookup"><span data-stu-id="c12ab-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="c12ab-140">商務用 Skype 不會在狀態資訊上強制執行字元限制。</span><span class="sxs-lookup"><span data-stu-id="c12ab-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="c12ab-141">Microsoft Teams 只會顯示在商務用 Skype 中所備註的前 280 個字元。</span><span class="sxs-lookup"><span data-stu-id="c12ab-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="c12ab-142">備註結尾的省略號 (...) 表示截斷。</span><span class="sxs-lookup"><span data-stu-id="c12ab-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="c12ab-143">商務用 Skype 不支援備註的到期時間。</span><span class="sxs-lookup"><span data-stu-id="c12ab-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="c12ab-144">當使用者升級至 TeamsOnly 模式時，不支援將備註從商務用 Skype 移轉至 Teams。</span><span class="sxs-lookup"><span data-stu-id="c12ab-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c12ab-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="c12ab-145">Related topics</span></span>

[<span data-ttu-id="c12ab-146">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="c12ab-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
