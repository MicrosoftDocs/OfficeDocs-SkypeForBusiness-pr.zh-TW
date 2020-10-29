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
description: 瞭解 [離開狀態] 或 [請勿打擾] 狀態的使用者可以在其狀態訊息中明確將另一個使用者設為代理人。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790465"
---
# <a name="message-delegation"></a><span data-ttu-id="c13b7-103">訊息委派</span><span class="sxs-lookup"><span data-stu-id="c13b7-103">Message delegation</span></span>

<span data-ttu-id="c13b7-104">使用者可以已明確將其狀態設為 [離開] 或 [請勿打擾]，並提供自訂文字。</span><span class="sxs-lookup"><span data-stu-id="c13b7-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="c13b7-105">郵件委派功能的運作方式如下：</span><span class="sxs-lookup"><span data-stu-id="c13b7-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="c13b7-106">使用者 @username 在部分文字狀態訊息中提及另一個使用者，建議您在他們無法使用的人，請與 @username 提及的使用者聯繫。</span><span class="sxs-lookup"><span data-stu-id="c13b7-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="c13b7-107">獲指派為代理人的人員會收到通知，告知他們已指定為代理人。</span><span class="sxs-lookup"><span data-stu-id="c13b7-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="c13b7-108">嘗試與第一個使用者聯繫的人，可以將游標暫留在已命名的代理人上，並輕鬆地以訊息傳送給代理人。</span><span class="sxs-lookup"><span data-stu-id="c13b7-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="c13b7-109">這是用戶端中的使用者啟動的程式，且不需要系統管理員參與即可啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="c13b7-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="c13b7-110">醫療保健中的委派使用案例</span><span class="sxs-lookup"><span data-stu-id="c13b7-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="c13b7-111">*使用範例，不需設定代理人：*  Franco Piccio 是在放射式部門撥打。</span><span class="sxs-lookup"><span data-stu-id="c13b7-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="c13b7-112">他會收到一則緊急的個人通話，且必須移出幾個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="c13b7-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="c13b7-113">他在放射科中要求一位對等的人，即 Lena Ehrle，以在他離開時掩蓋給對方。</span><span class="sxs-lookup"><span data-stu-id="c13b7-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="c13b7-114">他非正式地將呼叫器移至 Ehrle，他們會在呼叫器上接聽緊急訊息和 ping，並在她的目前職責中代表 Piccio 回復。</span><span class="sxs-lookup"><span data-stu-id="c13b7-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="c13b7-115">小組中的其他人可能無法實現非正式的委派，且 ensues 患者的護理。</span><span class="sxs-lookup"><span data-stu-id="c13b7-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="c13b7-116">*設定代理人的用法範例：* Franco Piccio 是在放射式部門撥打。</span><span class="sxs-lookup"><span data-stu-id="c13b7-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="c13b7-117">他會收到一則緊急的個人通話，且必須移出幾個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="c13b7-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="c13b7-118">他在放射科中要求一位對等人，Lena Ehrle，以在他離開時掩蓋給對方。</span><span class="sxs-lookup"><span data-stu-id="c13b7-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="c13b7-119">他將自己的自訂狀態訊息變更為「無法在未來數小時內取得的內容。</span><span class="sxs-lookup"><span data-stu-id="c13b7-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="c13b7-120">請聯絡 @DrEhrle 以取得任何緊急情況。</span><span class="sxs-lookup"><span data-stu-id="c13b7-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="c13b7-121">小組中的其他人在嘗試聯絡 Piccio 時，就會立即取得委派，所以他們現在知道要與 Dr. Ehrle。</span><span class="sxs-lookup"><span data-stu-id="c13b7-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="c13b7-122">Ensues 患者的護理，幾乎無任何混淆。</span><span class="sxs-lookup"><span data-stu-id="c13b7-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="c13b7-123">團隊用戶端中使用者狀態的共存模式的影響</span><span class="sxs-lookup"><span data-stu-id="c13b7-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="c13b7-124">系統管理員應注意，狀態筆記和委派提及的行為會部分依賴于使用者的共存模式。</span><span class="sxs-lookup"><span data-stu-id="c13b7-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="c13b7-125">這個矩陣顯示的可能性如下：</span><span class="sxs-lookup"><span data-stu-id="c13b7-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="c13b7-126">Co-Existence 模式</span><span class="sxs-lookup"><span data-stu-id="c13b7-126">Co-Existence Mode</span></span> | <span data-ttu-id="c13b7-127">預期行為</span><span class="sxs-lookup"><span data-stu-id="c13b7-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="c13b7-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="c13b7-128">TeamsOnly</span></span> |<span data-ttu-id="c13b7-129">使用者只能從小組設定記事。</span><span class="sxs-lookup"><span data-stu-id="c13b7-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="c13b7-130">在團隊 & SfB 中會顯示使用者的小組記事。</span><span class="sxs-lookup"><span data-stu-id="c13b7-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="c13b7-131">離島</span><span class="sxs-lookup"><span data-stu-id="c13b7-131">Islands</span></span> | <span data-ttu-id="c13b7-132">小組中的使用者記事集只能在 [團隊] 中看到。</span><span class="sxs-lookup"><span data-stu-id="c13b7-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="c13b7-133">SfB 中的使用者記事集只能在 SfB 中看到</span><span class="sxs-lookup"><span data-stu-id="c13b7-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="c13b7-134">SfB \* 模式</span><span class="sxs-lookup"><span data-stu-id="c13b7-134">SfB\* modes</span></span> | <span data-ttu-id="c13b7-135">使用者只能從 SfB 設定記事。</span><span class="sxs-lookup"><span data-stu-id="c13b7-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="c13b7-136">使用者的 SfB 附注會顯示在 [SfB & 的小組中。</span><span class="sxs-lookup"><span data-stu-id="c13b7-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="c13b7-137">如果使用者的模式是 TeamsOnly 或孤島，就只能在團隊中設定記事。</span><span class="sxs-lookup"><span data-stu-id="c13b7-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="c13b7-138">在商務用 Skype 中顯示 [備忘稿] 設定</span><span class="sxs-lookup"><span data-stu-id="c13b7-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="c13b7-139">沒有從商務用 Skype 設定記事的視覺指示。</span><span class="sxs-lookup"><span data-stu-id="c13b7-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="c13b7-140">商務用 Skype 不會對狀態筆記強制進行字元限制。</span><span class="sxs-lookup"><span data-stu-id="c13b7-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="c13b7-141">Microsoft 團隊只會從商務用 Skype 顯示記事集的前280個字元。</span><span class="sxs-lookup"><span data-stu-id="c13b7-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="c13b7-142">[橢圓形] ( ... 在記事結尾 ) 會指出截斷。</span><span class="sxs-lookup"><span data-stu-id="c13b7-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="c13b7-143">商務用 Skype 不支援記錄的到期時間。</span><span class="sxs-lookup"><span data-stu-id="c13b7-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="c13b7-144">當使用者升級至 TeamsOnly 模式時，不支援從商務用 Skype 將筆記遷移至團隊。</span><span class="sxs-lookup"><span data-stu-id="c13b7-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c13b7-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="c13b7-145">Related topics</span></span>

[<span data-ttu-id="c13b7-146">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="c13b7-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
