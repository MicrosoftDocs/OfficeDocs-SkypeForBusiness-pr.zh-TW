---
title: 透過商務用 Skype Server 中的工作規劃通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 在商務用 skype Server 中進行通話規劃, 在商務用 skype 和您的 PBX 電話系統之間整合, 讓使用者可以使用商務用 Skype 來控制其 PBX 電話。
ms.openlocfilehash: b2f0e57a33f6e194dc981b623a641850ed3c8de5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187756"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="eafc5-103">透過商務用 Skype Server 中的工作規劃通話</span><span class="sxs-lookup"><span data-stu-id="eafc5-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="eafc5-104">在商務用 skype Server 中進行通話規劃, 在商務用 skype 和您的 PBX 電話系統之間整合, 讓使用者可以使用商務用 Skype 來控制其 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="eafc5-105">[透過公司**通話**] 是商務用 skype Server 中的新功能, 可讓您將商務用 skype 解決方案與現有的 PBX 電話系統整合。</span><span class="sxs-lookup"><span data-stu-id="eafc5-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="eafc5-106">您可以按一下 [在商務用 Skype 中通話], 在您的部署或外部使用者中呼叫另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="eafc5-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="eafc5-107">通話是使用使用者的 PBX 手機完成。</span><span class="sxs-lookup"><span data-stu-id="eafc5-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="eafc5-108">這可讓使用 PBX 手機的使用者在其豐富的商務用 Skype 交談中包含音訊。</span><span class="sxs-lookup"><span data-stu-id="eafc5-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="eafc5-109">在舊版 Lync Server 遠端通話控制中, 這項功能可讓使用者使用 Lync Server 控制其 PBX 手機。</span><span class="sxs-lookup"><span data-stu-id="eafc5-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="eafc5-110">在商務用 Skype Server 中, 此功能已由 [透過工作通話] 取代。</span><span class="sxs-lookup"><span data-stu-id="eafc5-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="eafc5-111">透過 [通話] 可讓 PBX 電話使用者使用下列功能</span><span class="sxs-lookup"><span data-stu-id="eafc5-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="eafc5-112">[隨打即用] 體驗, 透過 PBX 手機提供音訊。</span><span class="sxs-lookup"><span data-stu-id="eafc5-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="eafc5-113">[目前狀態]、[使用者搜尋] 和 [IM 整合]-例如, 透過 IM 會話中的工作使用者進行兩次通話, 即可透過 PBX 手機提供音訊, 將音訊新增至他們的會話中。</span><span class="sxs-lookup"><span data-stu-id="eafc5-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="eafc5-114">透過 [通話], 將 IM、應用程式共用和檔案傳輸新增至通話的功能。</span><span class="sxs-lookup"><span data-stu-id="eafc5-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="eafc5-115">一次按一下會議加入功能</span><span class="sxs-lookup"><span data-stu-id="eafc5-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="eafc5-116">運作方式</span><span class="sxs-lookup"><span data-stu-id="eafc5-116">How it works</span></span>

<span data-ttu-id="eafc5-117">透過公司通話使用整合通訊網頁 API (UCWA) 作為 PBX 系統與您的商務用 Skype Server 部署之間的後端到後的使用者代理程式 (B2BUA), 因此不需要電腦支援的電信應用程式 (CSTA) 閘道進行連接使用 PBX 系統的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="eafc5-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="eafc5-118">UCWA 是舊版 Lync Server 中引入的服務, 可與行動裝置和網路用戶端連線, 而且會自動安裝在每個前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="eafc5-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="eafc5-119">通話工作流程, 透過通話撥打通話</span><span class="sxs-lookup"><span data-stu-id="eafc5-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="eafc5-120">以下說明如何透過工作使用商務用 Skype 伺服器撥打電話給您的使用者:</span><span class="sxs-lookup"><span data-stu-id="eafc5-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
![顯示通話期間透過通話的步驟;首先, 來電者會按一下撥號給商務用 Skype 用戶端中的某人;然後 UCWA 會響鈴來電者的電話。](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="eafc5-123">使用者在其商務用 Skype 用戶端中選取使用者, 然後按一下 [電話] 圖示進行通話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="eafc5-124">或者, 在 IM 交談期間, 使用者按一下即可呼叫與其有會話的使用者。</span><span class="sxs-lookup"><span data-stu-id="eafc5-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="eafc5-125">發出通話的使用者的 PBX 電話會開始響鈴。</span><span class="sxs-lookup"><span data-stu-id="eafc5-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="eafc5-126">此電話的呼叫者識別碼會顯示您已設定的全域電話號碼, 該電話號碼會顯示在所有使用者撥打電話的本機號碼中。</span><span class="sxs-lookup"><span data-stu-id="eafc5-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="eafc5-127">這個全域電話號碼不是相對於任何一個人的電話的實際電話號碼。</span><span class="sxs-lookup"><span data-stu-id="eafc5-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="eafc5-128">相反地, 它是一個視覺信號, 讓使用者知道這是自己的撥出電話, 而不是同時進行撥入通話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="eafc5-129">當您透過工作部署通話時, 您應該教育這些使用者關於此全域電話號碼及其意義。</span><span class="sxs-lookup"><span data-stu-id="eafc5-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="eafc5-130">發出通話的使用者會挑選其 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="eafc5-131">商務用 Skype 接著會啟動呼叫者的語音通話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="eafc5-132">當來電者應答時, 語音通話就會開始。</span><span class="sxs-lookup"><span data-stu-id="eafc5-132">When the callee answers, the voice call begins.</span></span> <span data-ttu-id="eafc5-133">如果兩個使用者已經有 IM 會話, 就可以繼續。</span><span class="sxs-lookup"><span data-stu-id="eafc5-133">If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="eafc5-134">透過 [通話] 加入會議</span><span class="sxs-lookup"><span data-stu-id="eafc5-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="eafc5-135">透過工作使用者進行通話, 您可以按一下會議 URL 來加入排程會議。</span><span class="sxs-lookup"><span data-stu-id="eafc5-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="eafc5-136">[商務用 Skype] 接著會顯示 [**撥出至**] 訊息, 直到會議服務撥打使用者的 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="eafc5-137">[透過工作的通話] 使用者接著會挑選 PBX 電話並加入會議。</span><span class="sxs-lookup"><span data-stu-id="eafc5-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="eafc5-138">透過公司使用者的通話也可以使用商務用 Skype 中的 [**立即開會**] 選項來建立 [立即開會] 會議。</span><span class="sxs-lookup"><span data-stu-id="eafc5-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="eafc5-139">然後, 使用者會看到 [**撥出至**] 訊息, 以及 PBX 電話響鈴。</span><span class="sxs-lookup"><span data-stu-id="eafc5-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="eafc5-140">透過工作使用者進行通話, 您也可以從商務用 Skype 呼叫會議橋接電話來撥入會議。</span><span class="sxs-lookup"><span data-stu-id="eafc5-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="eafc5-141">如果需要會議 PIN, 使用者必須使用 PBX 手機來輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="eafc5-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="eafc5-142">來電</span><span class="sxs-lookup"><span data-stu-id="eafc5-142">Incoming Calls</span></span>

<span data-ttu-id="eafc5-143">當使用者透過工作接聽商務用 Skype 通話時, PBX 手機和使用者的商務用 Skype 用戶端都會同時撥打 (如果使用者已設定同時撥打)。</span><span class="sxs-lookup"><span data-stu-id="eafc5-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="eafc5-144">使用者可以透過挑選 PBX 手機或按一下商務用 Skype 通知中的 [**接受**] 來接受通話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="eafc5-145">如果使用者使用商務用 Skype 接受通話, 通話的商務用 Skype 視窗就會保持開啟。</span><span class="sxs-lookup"><span data-stu-id="eafc5-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="eafc5-146">但是, 如果使用者透過挑選 PBX 手機即可接受通話, 則商務用 Skype 通知視窗就會關閉, 而且沒有商務用 Skype 會話, 只需透過 PBX 電話進行語音通話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="eafc5-147">當使用者透過工作接聽 PBX 通話時, 只需 PBX 電話響鈴。</span><span class="sxs-lookup"><span data-stu-id="eafc5-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="eafc5-148">透過公司通話的限制</span><span class="sxs-lookup"><span data-stu-id="eafc5-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="eafc5-149">[透過公司通話] 是一種需要進行硬體設定的語音方案, 但與完整企業語音或遠端通話控制所提供的功能有所限制。</span><span class="sxs-lookup"><span data-stu-id="eafc5-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="eafc5-150">透過公司通話的限制如下:</span><span class="sxs-lookup"><span data-stu-id="eafc5-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="eafc5-151">如果透過工作使用者撥打電話已將來電轉接到 [透過工作撥打電話] 撥打電話給來電, 而有人嘗試邀請使用者的電話號碼來加入會議, 邀請將無法送達使用者。</span><span class="sxs-lookup"><span data-stu-id="eafc5-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="eafc5-152">您應該透過按一下名稱 (而非電話號碼) 來教育您的使用者邀請參與者加入會議。</span><span class="sxs-lookup"><span data-stu-id="eafc5-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="eafc5-153">在通話期間, 透過工作通話無法使用增強型911功能和惡意通話追蹤功能。</span><span class="sxs-lookup"><span data-stu-id="eafc5-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="eafc5-154">啟用 [透過公司通話] 的使用者無法使用委派、小組通話或回應群組功能。</span><span class="sxs-lookup"><span data-stu-id="eafc5-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="eafc5-155">[透過公司通話] 的使用者無法使用商務用 Skype 錄製會議、將通話設為靜音或取消靜音、保留或轉接通話, 或使用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="eafc5-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="eafc5-156">使用者無法透過 [呼叫] 使用通話來存取其 PBX 語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="eafc5-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="eafc5-157">透過工作進行通話的使用者無法將開始進行語音通話的會話升級為包含視頻、Powerpoint、白板或一個筆記等通訊的合作會議。</span><span class="sxs-lookup"><span data-stu-id="eafc5-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="eafc5-158">[透過工作通話的使用者] 無法將更多使用者新增至兩人通話。</span><span class="sxs-lookup"><span data-stu-id="eafc5-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="eafc5-159">不支援 deskphone 配對或 VDI 外掛程式配對。</span><span class="sxs-lookup"><span data-stu-id="eafc5-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="eafc5-160">如果使用者使用 PBX 電話撥打或接聽電話 (而不是使用商務用 Skype 視窗), 就不會有通話記錄。</span><span class="sxs-lookup"><span data-stu-id="eafc5-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="eafc5-161">如果您的 PBX 系統不支援**參照取代**, 則會發生下列行為。</span><span class="sxs-lookup"><span data-stu-id="eafc5-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="eafc5-162">透過 [通話通話] 時, 如果使用者從 PBX 手機傳送正在進行的通話, 通話視窗就不會從商務用 Skype 視窗中消失。</span><span class="sxs-lookup"><span data-stu-id="eafc5-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="eafc5-163">如果使用者接著關閉通話視窗, 則傳送目標與 transferee 之間的呼叫將會結束。</span><span class="sxs-lookup"><span data-stu-id="eafc5-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="eafc5-164">透過工作進行通話的先決條件</span><span class="sxs-lookup"><span data-stu-id="eafc5-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="eafc5-165">若要讓任何使用者都能透過工作撥打電話, 您必須準備好一些必備的功能。</span><span class="sxs-lookup"><span data-stu-id="eafc5-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="eafc5-166">如需這些必備元件的詳細資訊, 以及如何讓使用者使用商務用 Skype Server 2015 來通話的相關步驟, 請參閱在[商務用 Skype Server 中部署通話](../../deploy/deploy-call-via-work.md)。</span><span class="sxs-lookup"><span data-stu-id="eafc5-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="eafc5-167">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eafc5-167">See also</span></span>

[<span data-ttu-id="eafc5-168">在商務用 Skype 中規劃遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="eafc5-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="eafc5-169">部署商務用 Skype Server 2015 的從公司撥號功能</span><span class="sxs-lookup"><span data-stu-id="eafc5-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

