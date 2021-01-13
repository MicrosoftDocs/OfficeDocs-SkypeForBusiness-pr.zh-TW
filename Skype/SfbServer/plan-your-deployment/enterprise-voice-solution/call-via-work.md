---
title: 透過商務用 Skype Server 中的工作規劃通話
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 規劃透過商務用 Skype Server 中的通話，可在商務用 skype 和 PBX 電話系統之間進行整合，讓使用者可以使用商務用 Skype 來控制其 PBX 電話。
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825873"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="02924-103">透過商務用 Skype Server 中的工作規劃通話</span><span class="sxs-lookup"><span data-stu-id="02924-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="02924-104">規劃透過商務用 Skype Server 中的通話，可在商務用 skype 和 PBX 電話系統之間進行整合，讓使用者可以使用商務用 Skype 來控制其 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="02924-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="02924-105">「**從公司通話**」是商務用 skype Server 中的新功能，可讓您將商務用 skype 解決方案與現有的 PBX 電話系統進行整合。</span><span class="sxs-lookup"><span data-stu-id="02924-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="02924-106">啟用透過工作呼叫的使用者可以按一下商務用 Skype 呼叫另一個使用者，不論是在您的部署中或外部使用者。</span><span class="sxs-lookup"><span data-stu-id="02924-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="02924-107">使用使用者的 PBX 電話完成通話。</span><span class="sxs-lookup"><span data-stu-id="02924-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="02924-108">這可讓使用 PBX 電話的使用者在其豐富的商務用 Skype 交談中包含音訊。</span><span class="sxs-lookup"><span data-stu-id="02924-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="02924-109">在舊版的 Lync Server 遠端呼叫控制中，有一個功能可讓使用者透過 Lync Server 控制其 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="02924-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="02924-110">在商務用 Skype Server 中，此功能已由「透過公司來電」取代。</span><span class="sxs-lookup"><span data-stu-id="02924-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="02924-111">透過公司通話為 PBX 電話使用者啟用下列各項</span><span class="sxs-lookup"><span data-stu-id="02924-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="02924-112">隨選即用經驗，透過 PBX 電話提供音訊。</span><span class="sxs-lookup"><span data-stu-id="02924-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="02924-113">目前狀態、使用者搜尋和 IM 整合--例如，IM 會話中的兩個透過工作使用者撥打的電話，都可以透過 PBX 電話提供音訊，將音訊新增至其會話。</span><span class="sxs-lookup"><span data-stu-id="02924-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="02924-114">透過「工作通話」新增 IM、應用程式共用和檔案傳輸的功能。</span><span class="sxs-lookup"><span data-stu-id="02924-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="02924-115">按一下一次會議加入功能</span><span class="sxs-lookup"><span data-stu-id="02924-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="02924-116">運作方式</span><span class="sxs-lookup"><span data-stu-id="02924-116">How it works</span></span>

<span data-ttu-id="02924-117">「透過公司通話」使用整合通訊網頁 API (UCWA) 作為後端至後端使用者代理 (程式) PBX 系統與商務用 Skype Server 部署之間的 B2BUA，因此，您必須使用電腦支援的電信應用程式 (CSTA) 閘道才能將商務用 Skype 伺服器與 PBX 系統連線。</span><span class="sxs-lookup"><span data-stu-id="02924-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="02924-118">UCWA 是先前版本的 Lync Server 所引進的服務，可與行動裝置和 web 用戶端進行連線，並且會自動安裝在每一部前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="02924-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="02924-119">通話工作流程以供通話通話</span><span class="sxs-lookup"><span data-stu-id="02924-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="02924-120">下列說明如何啟用透過公司通話的使用者可以使用商務用 Skype 伺服器進行呼叫：</span><span class="sxs-lookup"><span data-stu-id="02924-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
![顯示通話通話期間的步驟。首先，來電者會按一下以撥打商務用 Skype 用戶端中的某人;然後，UCWA 會振鈴來電者的電話。](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="02924-123">使用者在商務用 Skype 用戶端中選取使用者，然後按一下電話圖示進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="02924-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="02924-124">或者，在 IM 交談期間，使用者按一下以撥打與其有會話的使用者。</span><span class="sxs-lookup"><span data-stu-id="02924-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="02924-125">撥打通話之使用者的 PBX 電話會開始振鈴。</span><span class="sxs-lookup"><span data-stu-id="02924-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="02924-126">此電話的來電者識別碼會顯示您已設定為透過通話通話撥打的所有使用者的來電者識別碼中所設定的全域電話號碼。</span><span class="sxs-lookup"><span data-stu-id="02924-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="02924-127">此通用電話號碼不是對應于任何一位人員電話的實際電話號碼。</span><span class="sxs-lookup"><span data-stu-id="02924-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="02924-128">相反地，這是一種視覺信號，可讓使用者知道這是自己的撥出電話，而不是在同一時間發生來電。</span><span class="sxs-lookup"><span data-stu-id="02924-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="02924-129">當您從公司部署通話時，應教育這些使用者關於此通用電話號碼及其意義。</span><span class="sxs-lookup"><span data-stu-id="02924-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="02924-130">撥打電話的使用者會拾取其 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="02924-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="02924-131">然後，商務用 Skype 會為呼叫者發起語音通話。</span><span class="sxs-lookup"><span data-stu-id="02924-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="02924-132">受話者的答案是由語音電話開始。</span><span class="sxs-lookup"><span data-stu-id="02924-132">When the callee answers, the voice call begins.</span></span> <span data-ttu-id="02924-133">如果兩位使用者已有 IM 會話，則可以繼續。</span><span class="sxs-lookup"><span data-stu-id="02924-133">If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="02924-134">加入會議，並透過公司通話</span><span class="sxs-lookup"><span data-stu-id="02924-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="02924-135">透過使用者的來電可以按一下會議 URL 來加入排程的會議。</span><span class="sxs-lookup"><span data-stu-id="02924-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="02924-136">然後，商務用 Skype 會顯示在會議服務撥打使用者的 PBX 電話之前 **，撥號至** 訊息。</span><span class="sxs-lookup"><span data-stu-id="02924-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="02924-137">「透過公司來電」使用者接著挑選 PBX 電話並加入會議。</span><span class="sxs-lookup"><span data-stu-id="02924-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="02924-138">「透過辦公室通話」使用者也可以使用商務用 Skype 中的 [ **立即開會** ] 選項來建立 [立即開會] 會議。</span><span class="sxs-lookup"><span data-stu-id="02924-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="02924-139">然後，使用者會看到 **撥號到** 郵件，以及 PBX 電話響起。</span><span class="sxs-lookup"><span data-stu-id="02924-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="02924-140">透過工作使用者的通話也可以從商務用 Skype 呼叫會議 Bridge 號碼，撥打會議。</span><span class="sxs-lookup"><span data-stu-id="02924-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="02924-141">如果需要會議 PIN，使用者必須使用 PBX 電話來輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="02924-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="02924-142">來電</span><span class="sxs-lookup"><span data-stu-id="02924-142">Incoming Calls</span></span>

<span data-ttu-id="02924-143">當啟用透過工作呼叫的使用者收到商務用 Skype 通話時，PBX 電話和使用者的商務用 Skype 用戶端會同時 (，如果使用者已設定同時振鈴) 。</span><span class="sxs-lookup"><span data-stu-id="02924-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="02924-144">使用者可以透過挑選 PBX 電話或按一下 [商務用 Skype] 通知中的 [ **接受** ] 來接受通話。</span><span class="sxs-lookup"><span data-stu-id="02924-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="02924-145">如果使用者接受使用商務用 Skype 的通話，則通話的商務用 Skype 視窗會保持開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="02924-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="02924-146">不過，如果使用者挑選 PBX 電話接受通話，則商務用 Skype 通知視窗會關閉，而且沒有商務用 Skype 會話，只會透過 PBX 電話進行語音通話。</span><span class="sxs-lookup"><span data-stu-id="02924-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="02924-147">當啟用透過工作呼叫的使用者接到 PBX 呼叫時，則只會使用 PBX 電話的環。</span><span class="sxs-lookup"><span data-stu-id="02924-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="02924-148">從公司通話的限制</span><span class="sxs-lookup"><span data-stu-id="02924-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="02924-149">「透過公司通話」是一個語音解決方案，只需要硬體安裝，但與完整 Enterprise Voice 或 remote 呼叫控制中的功能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="02924-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="02924-150">透過工作呼叫的限制如下：</span><span class="sxs-lookup"><span data-stu-id="02924-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="02924-151">如果透過公司的來電已設定來電轉接至透過工作來電號碼的來電，而某人嘗試將此使用者邀請使用者的電話號碼給會議，邀請將不會到達使用者。</span><span class="sxs-lookup"><span data-stu-id="02924-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="02924-152">您應教育使用者按一下名稱，而非電話號碼，以邀請參與者加入會議。</span><span class="sxs-lookup"><span data-stu-id="02924-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="02924-153">從公司通話通話時，增強型911功能和惡意呼叫追蹤無法使用。</span><span class="sxs-lookup"><span data-stu-id="02924-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="02924-154">啟用透過工作呼叫的使用者無法使用委派、小組通話或回應群組功能。</span><span class="sxs-lookup"><span data-stu-id="02924-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="02924-155">「透過運作的來電使用者」無法使用商務用 Skype 錄製會議、靜音或取消靜音通話、保留或轉接通話，或使用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="02924-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="02924-156">使用者無法使用「透過運作呼叫」存取其 PBX 語音訊息。</span><span class="sxs-lookup"><span data-stu-id="02924-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="02924-157">「透過運作的來電使用者」無法將開始語音電話的會話提升為包含諸如影片、Powerpoint、白板或一個附注等通訊的合作會議。</span><span class="sxs-lookup"><span data-stu-id="02924-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="02924-158">「從公司通話」的使用者無法將更多使用者新增至2人通話。</span><span class="sxs-lookup"><span data-stu-id="02924-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="02924-159">不支援 deskphone 配對或 VDI 外掛程式配對。</span><span class="sxs-lookup"><span data-stu-id="02924-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="02924-160">如果使用者使用 PBX 電話撥打或接聽電話 (但未使用商務用 Skype 視窗) ，將不會有通話記錄。</span><span class="sxs-lookup"><span data-stu-id="02924-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="02924-161">如果您的 PBX 系統不支援 **參照取代**，將會發生下列行為。</span><span class="sxs-lookup"><span data-stu-id="02924-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="02924-162">在來電通話時，如果使用者從 PBX 電話轉接進行中的通話，則通話視窗不會從商務用 Skype 視窗中消失。</span><span class="sxs-lookup"><span data-stu-id="02924-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="02924-163">如果使用者接著關閉通話視窗，則傳送目標與 transferee 之間的呼叫會結束。</span><span class="sxs-lookup"><span data-stu-id="02924-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="02924-164">從公司通話的必要條件</span><span class="sxs-lookup"><span data-stu-id="02924-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="02924-165">若要讓任何使用者都能撥打工作，您必須預先準備一些必要條件。</span><span class="sxs-lookup"><span data-stu-id="02924-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="02924-166">如需這些必要條件的詳細資訊，以及如何讓使用者能夠透過工作進行呼叫的步驟，請參閱在 [商務用 Skype Server 2015 中部署從上班的呼叫](../../deploy/deploy-call-via-work.md)。</span><span class="sxs-lookup"><span data-stu-id="02924-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="02924-167">另請參閱</span><span class="sxs-lookup"><span data-stu-id="02924-167">See also</span></span>

[<span data-ttu-id="02924-168">在商務用 Skype 中規劃遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="02924-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="02924-169">透過商務用 Skype Server 2015 部署通話</span><span class="sxs-lookup"><span data-stu-id="02924-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

