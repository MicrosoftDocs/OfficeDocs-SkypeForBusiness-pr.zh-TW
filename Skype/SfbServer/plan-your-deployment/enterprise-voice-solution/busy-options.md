---
title: 規劃商務用 Skype Server 的繁忙選項
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 請參閱商務用 Skype Server 中的「忙碌選項」功能。
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813693"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="b4575-103">規劃商務用 Skype Server 的繁忙選項</span><span class="sxs-lookup"><span data-stu-id="b4575-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="b4575-104">請參閱商務用 Skype Server 中的「忙碌選項」功能。</span><span class="sxs-lookup"><span data-stu-id="b4575-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="b4575-105">「忙碌選項」是在2016累積更新中引進的新語音原則，可讓您設定使用者已在通話或會議中處理來電的方式，或已將來電置於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="b4575-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="b4575-106">您可以使用繁忙的信號或轉接至語音信箱來拒絕新的或來電的來電。</span><span class="sxs-lookup"><span data-stu-id="b4575-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="b4575-107">在成對前端集區和 Survivable Branch Server (SBS) 上，支援容錯移轉和嚴重損壞修復功能的 [忙碌選項] 原則。</span><span class="sxs-lookup"><span data-stu-id="b4575-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="b4575-108">本主題說明忙碌選項的功能。</span><span class="sxs-lookup"><span data-stu-id="b4575-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="b4575-109">如需如何安裝及設定忙碌選項的詳細資訊，請參閱 [安裝及設定商務用 Skype Server 的繁忙選項](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="b4575-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="b4575-110">設定選項</span><span class="sxs-lookup"><span data-stu-id="b4575-110">Configuration options</span></span>

<span data-ttu-id="b4575-111">如果為組織啟用忙碌選項，組織中的所有使用者（Enterprise Voice 和非企業語音使用者）都可以使用下列功能：</span><span class="sxs-lookup"><span data-stu-id="b4575-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="b4575-112">忙於忙碌-當使用者忙碌時，將會以忙碌信號拒絕新的來電。</span><span class="sxs-lookup"><span data-stu-id="b4575-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="b4575-113">在忙碌中的語音信箱，當使用者忙碌時，會將新的來電轉送到語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b4575-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="b4575-114">「忙碌選項」功能提供容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="b4575-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="b4575-115">如果發生問題，且使用者已容錯移轉至另一部前端伺服器或在商務用 Skype Server 中的另一個集區，則會保留其「忙碌選項」設定。</span><span class="sxs-lookup"><span data-stu-id="b4575-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="b4575-116">不論其忙碌選項的設定方式為何，通話或會議中的使用者或是具有保留狀態的使用者，都不會被禁止撥打新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="b4575-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="b4575-117">設定之後，「忙碌選項」設定會作用於所有使用者的商務用 Skype 通話裝置和用戶端。</span><span class="sxs-lookup"><span data-stu-id="b4575-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="b4575-118">根據使用者的「忙碌選項」設定，拒絕或傳送至語音信箱的呼叫，不會在使用者的任何呼叫裝置上振鈴，包括使用者已登入的 Macintosh、Windows 桌面、行動用戶端或 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="b4575-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="b4575-119">使用者將會在其商務用 Skype 用戶端和裝置上看到未接來電通知，也會透過電子郵件通知他們。</span><span class="sxs-lookup"><span data-stu-id="b4575-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="b4575-120">來電因忙碌而遭到拒絕的來電者，將會在其商務用 Skype 用戶端中看到通知，告知使用者嘗試到達的使用者正忙於另一個呼叫。</span><span class="sxs-lookup"><span data-stu-id="b4575-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="b4575-121">您可以使用商務用 Skype PowerShell Cmdlet 來設定「忙碌選項」功能，以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b4575-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="b4575-122">啟用或停用企業的繁忙選項語音原則。</span><span class="sxs-lookup"><span data-stu-id="b4575-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="b4575-123">針對企業中的所有使用者，管理忙碌的繁忙或語音信箱占線。</span><span class="sxs-lookup"><span data-stu-id="b4575-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="b4575-124">為位於特定前端集區中的所有使用者，管理忙碌的繁忙或語音信箱忙碌狀態。</span><span class="sxs-lookup"><span data-stu-id="b4575-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="b4575-125">在使用者清單忙碌時，管理忙碌或語音信箱等忙碌狀況。</span><span class="sxs-lookup"><span data-stu-id="b4575-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="b4575-126">針對單一使用者，管理忙碌的繁忙或語音信箱忙碌狀態。</span><span class="sxs-lookup"><span data-stu-id="b4575-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="b4575-127">與語音應用程式交互操作</span><span class="sxs-lookup"><span data-stu-id="b4575-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="b4575-128">繁忙選項可在商務用 Skype 中與下列語音應用程式互通性：</span><span class="sxs-lookup"><span data-stu-id="b4575-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="b4575-129">回應群組 (RGS) </span><span class="sxs-lookup"><span data-stu-id="b4575-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="b4575-130">系統會忽略回應群組號碼上的繁忙選項設定;會允許多個同時通話。</span><span class="sxs-lookup"><span data-stu-id="b4575-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="b4575-131">在具有「忙碌選項」設定的 [代理程式] 中，目前的「在回應群組中顯示路由經驗將保持不變</span><span class="sxs-lookup"><span data-stu-id="b4575-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="b4575-132">從回應群組到回應群組代理程式的呼叫，將不會受到忙碌選項設定的限制，而且目前的 RGS 經驗也會維持下來。</span><span class="sxs-lookup"><span data-stu-id="b4575-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="b4575-133">對代理人的非 RGS 相關呼叫會受到其「忙碌選項」設定的認可。</span><span class="sxs-lookup"><span data-stu-id="b4575-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="b4575-134">小組通話</span><span class="sxs-lookup"><span data-stu-id="b4575-134">Team Call</span></span>
    
  - <span data-ttu-id="b4575-135">設定為小組通話之使用者的來電，將優先于「忙碌忙碌」和「在忙碌設定上的語音信箱」設定為「略過忙碌」。</span><span class="sxs-lookup"><span data-stu-id="b4575-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="b4575-136">目前的小組通話體驗將保持不變，並為使用者設定忙碌選項。</span><span class="sxs-lookup"><span data-stu-id="b4575-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="b4575-137">對這類使用者的非小組通話相關呼叫將會受到其「忙碌」選項設定的認可。</span><span class="sxs-lookup"><span data-stu-id="b4575-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="b4575-138">上司/系統管理員委派</span><span class="sxs-lookup"><span data-stu-id="b4575-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="b4575-139">設定為老闆/系統管理員委派的來電或系統管理員的來電，將優先于「忙碌」上的「忙碌」和「語音信箱開啟」設定。</span><span class="sxs-lookup"><span data-stu-id="b4575-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="b4575-140">目前的上司/系統管理員委派經驗將保持不變，並為系統管理員或上司設定忙碌選項。</span><span class="sxs-lookup"><span data-stu-id="b4575-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="b4575-141">與系統管理員相關的非老闆/系統管理員委派相關呼叫會受到其「忙碌選項」設定的認可。</span><span class="sxs-lookup"><span data-stu-id="b4575-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="b4575-142">共用線路外觀</span><span class="sxs-lookup"><span data-stu-id="b4575-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="b4575-143">已設定共用線路外觀之使用者帳戶的 [忙碌選項] 設定會被忽略。</span><span class="sxs-lookup"><span data-stu-id="b4575-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="b4575-144">共用線外觀的原生忙碌狀態和「忙碌的語音信箱」選項將會改為加以認可。</span><span class="sxs-lookup"><span data-stu-id="b4575-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="b4575-145">通話駐留服務</span><span class="sxs-lookup"><span data-stu-id="b4575-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="b4575-146">停用但因超時而被停用的來電，可讓使用者透過忙碌選項撥打通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="b4575-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="b4575-147">通話會議</span><span class="sxs-lookup"><span data-stu-id="b4575-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="b4575-148">會議呼叫中的使用者被視為忙碌狀態，且新的來電會以忙碌信號拒絕，或根據其忙碌選項設定轉寄給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b4575-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="b4575-149">會議中的使用者不會因忙碌選項而禁止撥打新通話或會議。</span><span class="sxs-lookup"><span data-stu-id="b4575-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="b4575-150">會議中的使用者仍可接收新的會議邀請，但根據其忙碌選項的設定，將拒絕新的對等通話。</span><span class="sxs-lookup"><span data-stu-id="b4575-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="b4575-151">同時震鈴和來電轉接</span><span class="sxs-lookup"><span data-stu-id="b4575-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="b4575-152">「忙碌忙碌」功能並非設計用來搭配同時震鈴和來電轉接。</span><span class="sxs-lookup"><span data-stu-id="b4575-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

