---
title: 規劃商務用 Skype Server 的繁忙選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 瞭解商務用 Skype Server 中的 [忙碌選項] 功能。
ms.openlocfilehash: 8e88b4bf3b92c7fea9bcf79822e2711ff3bee7de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187789"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="f1a9d-103">規劃商務用 Skype Server 的繁忙選項</span><span class="sxs-lookup"><span data-stu-id="f1a9d-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="f1a9d-104">瞭解商務用 Skype Server 中的 [忙碌選項] 功能。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="f1a9d-105">[忙碌選項] 是一種新的語音策略, 在2016年7月累計更新中引進, 可讓您設定當使用者已在通話或會議中, 或有通話處於保留狀態時, 如何處理撥入通話。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="f1a9d-106">您可以使用占線信號或轉接至語音信箱來拒絕新的或來電的通話。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="f1a9d-107">[Busy] 選項原則支援在成對的前端池與 Survivable 分支伺服器 (SBS) 上進行容錯移轉和災害復原。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="f1a9d-108">本主題描述 [忙碌] 選項的功能。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="f1a9d-109">如需如何安裝及設定 Busy 選項的相關資訊, 請參閱[安裝和設定商務用 Skype Server 的 Busy 選項](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="f1a9d-110">配置選項</span><span class="sxs-lookup"><span data-stu-id="f1a9d-110">Configuration options</span></span>

<span data-ttu-id="f1a9d-111">如果針對組織啟用 [忙碌] 選項, 組織中的所有使用者 (企業語音和非企業語音使用者) 都可以使用下列功能:</span><span class="sxs-lookup"><span data-stu-id="f1a9d-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="f1a9d-112">繁忙-在此情況下, 如果使用者太忙, 就會拒絕新的傳入通話。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="f1a9d-113">占線時的語音信箱-當使用者忙碌時, 會將新的撥入電話轉寄到語音信箱。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="f1a9d-114">[忙碌選項] 功能提供容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="f1a9d-115">如果發生問題, 且使用者已容錯移轉至另一個前端伺服器或商務用 Skype Server 中的另一個池, 其 [忙碌] 選項設定將會保留。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="f1a9d-116">不論其忙碌選項的設定方式為何, 通話或會議中的使用者, 或通話保持通話的使用者, 都不會被禁止開始新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="f1a9d-117">設定完成後, [Busy] 選項設定就會在所有使用者的商務用 Skype 通話裝置和用戶端上生效。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="f1a9d-118">根據使用者的 [忙碌選項] 設定, 拒絕或傳送至語音信箱的通話不會在使用者的任何電話裝置上響鈴, 包括使用者已登入的 Macintosh、Windows 桌面、行動用戶端或 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="f1a9d-119">使用者會在其商務用 Skype 用戶端和裝置上看到未接來電通知, 而且他們也會收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="f1a9d-120">呼叫因忙碌而遭到拒絕的呼叫者, 會在其商務用 Skype 用戶端中看到通知, 指出他們嘗試達到的使用者正在進行其他通話。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="f1a9d-121">您可以使用商務用 Skype PowerShell Cmdlet 設定 [忙碌選項] 功能, 以進行下列作業:</span><span class="sxs-lookup"><span data-stu-id="f1a9d-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="f1a9d-122">啟用或停用企業的 [忙碌] 選項語音原則。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="f1a9d-123">針對企業中的所有使用者, 在忙碌或繁忙的語音信箱上管理忙碌狀態。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="f1a9d-124">針對駐留在特定前端池中的所有使用者, 管理忙碌的繁忙或語音信箱等功能。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="f1a9d-125">在使用者清單中, 管理忙碌的繁忙或語音信箱占線。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="f1a9d-126">針對單一使用者, 管理忙碌的繁忙或語音信箱占線。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="f1a9d-127">與語音應用程式的互通性</span><span class="sxs-lookup"><span data-stu-id="f1a9d-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="f1a9d-128">[忙碌] 選項可讓您在商務用 Skype 中與下列語音應用程式進行交互操作:</span><span class="sxs-lookup"><span data-stu-id="f1a9d-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="f1a9d-129">回應群組 (RGS)</span><span class="sxs-lookup"><span data-stu-id="f1a9d-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="f1a9d-130">系統會忽略回應群組編號上設定的 [忙碌] 選項;將允許多個併發通話。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="f1a9d-131">對於 [忙碌] 選項設定, 回應群組中的目前行事片路由體驗將保持不變。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="f1a9d-132">從回應群組傳送給屬於回應群組代理的使用者, 將不會受到 [忙碌選項] 設定的限制, 且會維持目前的 RGS 體驗。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="f1a9d-133">與 Agent 的非 RGS 相關呼叫將由其 [忙碌] 選項設定所接受。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f1a9d-134">團隊通話</span><span class="sxs-lookup"><span data-stu-id="f1a9d-134">Team Call</span></span>
    
  - <span data-ttu-id="f1a9d-135">將呼叫設定為小組通話的使用者, 會將優先順序設為 [忽略繁忙的使用者] 和 [忙碌的語音信箱] 設定。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="f1a9d-136">目前的團隊通話體驗將會保持不變, 並為使用者設定忙碌選項。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="f1a9d-137">與這些使用者的非小組通話相關呼叫將由其 [忙碌] 選項設定所接受。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f1a9d-138">老闆/系統管理員委派</span><span class="sxs-lookup"><span data-stu-id="f1a9d-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="f1a9d-139">將來電或系統管理員設定為老闆/管理員委派的使用者, 將會優先處理 [在繁忙時忽略忙] 和 [占線] 設定上的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="f1a9d-140">目前的老闆/系統管理員委派經驗將保持不變, 並為系統管理員或老闆設定忙碌選項。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="f1a9d-141">與系統管理員的非老闆/Admin 委派相關呼叫將由其 [忙碌] 選項設定所接受。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="f1a9d-142">共用線外觀</span><span class="sxs-lookup"><span data-stu-id="f1a9d-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="f1a9d-143">針對共用線外觀設定的使用者帳戶上的 [忙碌選項] 設定將會被忽略。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="f1a9d-144">[共用線外觀] 的原生繁忙狀態和 [忙碌] 選項上的 [語音信箱] 都將生效。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="f1a9d-145">通話停用服務</span><span class="sxs-lookup"><span data-stu-id="f1a9d-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="f1a9d-146">停用未檢索到且因超時而響鈴的通話, 將會被視為由繁忙選項停用通話的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="f1a9d-147">通話會議</span><span class="sxs-lookup"><span data-stu-id="f1a9d-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="f1a9d-148">電話會議中的使用者被認為是繁忙的, 新的來電將會遭到繁忙的信號, 或根據其繁忙選項設定轉寄到語音信箱。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="f1a9d-149">不會阻止會議中的使用者使用 [忙碌] 選項來啟動新的通話或會議。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="f1a9d-150">會議中的使用者仍然可以接收新的會議邀請, 但新的對等呼叫將會根據其繁忙選項設定而遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="f1a9d-151">同時撥打及來電轉接</span><span class="sxs-lookup"><span data-stu-id="f1a9d-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="f1a9d-152">[忙碌] 的 [忙碌] 功能並非設計用於同時撥打和來電轉接。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

