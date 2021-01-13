---
title: 透過商務用 Skype Server 中的工作部署通話
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要：瞭解如何在部分或所有使用者的商務用 Skype Server 中部署呼叫。
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825003"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="b68ed-103">透過商務用 Skype Server 中的工作部署通話</span><span class="sxs-lookup"><span data-stu-id="b68ed-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="b68ed-104">**摘要：** 瞭解如何在部分或所有使用者的商務用 Skype Server 中，部署通話的功能。</span><span class="sxs-lookup"><span data-stu-id="b68ed-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="b68ed-105">使用下列步驟，為您的使用者部署「透過運作」的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b68ed-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="b68ed-106">規劃透過 [商務用 Skype Server 中的工作進行通話](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="b68ed-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="b68ed-107">在舊版的 Lync Server 遠端呼叫控制中，有一個功能可讓使用者透過 Lync Server 控制其 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="b68ed-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="b68ed-108">在商務用 Skype Server 中，此功能已由「透過公司來電」取代。</span><span class="sxs-lookup"><span data-stu-id="b68ed-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="b68ed-109">從公司通話的必要條件</span><span class="sxs-lookup"><span data-stu-id="b68ed-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="b68ed-110">「透過公司通話」使用整合通訊網頁 API (UCWA) ，它會自動安裝在所有商務用 Skype Server 前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="b68ed-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="b68ed-111">若要讓使用者能夠透過公司通話，您也必須具備下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="b68ed-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="b68ed-112">您必須已部署轉送伺服器，既可以作為前端伺服器的一部分，也可以是獨立的角色。</span><span class="sxs-lookup"><span data-stu-id="b68ed-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="b68ed-113">您也必須部署 IP-PBX 閘道。</span><span class="sxs-lookup"><span data-stu-id="b68ed-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="b68ed-114">所有可透過工作進行呼叫的使用者，都必須在 PBX 電話系統上) 直接向內撥號 (。</span><span class="sxs-lookup"><span data-stu-id="b68ed-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="b68ed-115">您必須啟用透過企業語音之工作使用者的所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="b68ed-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="b68ed-116">當您執行此動作時，您必須將每位使用者的商務用 Skype 的號碼，設定為對應之 PBX 電話系統的對應號碼。</span><span class="sxs-lookup"><span data-stu-id="b68ed-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="b68ed-117">所有將使用「從公司撥號」的使用者，都必須在其 [商務用 Skype] 用戶端的 [ **Advanced Connections** ] 選項中，選取 [**自動** 設定]。</span><span class="sxs-lookup"><span data-stu-id="b68ed-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="b68ed-118">這可讓用戶端探索 UCWA URLs。</span><span class="sxs-lookup"><span data-stu-id="b68ed-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="b68ed-119">[**自動** 設定] 是預設的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="b68ed-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="b68ed-120">針對每位使用者的通話，啟用來電轉接和同時響鈴。</span><span class="sxs-lookup"><span data-stu-id="b68ed-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="b68ed-121">針對透過工作使用者的每一個呼叫，請確定已啟用電話撥入式會議和會議撥出功能。</span><span class="sxs-lookup"><span data-stu-id="b68ed-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="b68ed-122">這可讓這些使用者進入及離開商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="b68ed-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="b68ed-123">確定已透過工作使用者的每一個呼叫停用委派、小組通話及回應群組。</span><span class="sxs-lookup"><span data-stu-id="b68ed-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="b68ed-124">部署從公司撥號功能</span><span class="sxs-lookup"><span data-stu-id="b68ed-124">Deploy Call Via Work</span></span>

<span data-ttu-id="b68ed-125">準備好必要條件後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b68ed-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="b68ed-126">為您的部署建立全域電話號碼，商務用 Skype 會顯示在透過通話通話之使用者的 PBX 來電者 ID 上。</span><span class="sxs-lookup"><span data-stu-id="b68ed-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="b68ed-127">透過工作原則建立一或多個通話</span><span class="sxs-lookup"><span data-stu-id="b68ed-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="b68ed-128">將「透過工作原則的來電」指派給將啟用透過工作呼叫的每位使用者</span><span class="sxs-lookup"><span data-stu-id="b68ed-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="b68ed-129">透過工作通用電話號碼建立通話</span><span class="sxs-lookup"><span data-stu-id="b68ed-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="b68ed-130">輸入下列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b68ed-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="b68ed-131">例如，下列 Cmdlet 會將全域電話號碼設定為1-555-123-4567。</span><span class="sxs-lookup"><span data-stu-id="b68ed-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="b68ed-132">通過工作原則建立通話</span><span class="sxs-lookup"><span data-stu-id="b68ed-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="b68ed-133">輸入下列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b68ed-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="b68ed-134">例如，下列 Cmdlet 會透過名為 ContosoUser1CvWP 的工作原則建立呼叫，要求使用者使用系統管理員回撥號碼，並將該回撥號碼設定為1-555-789-1234。</span><span class="sxs-lookup"><span data-stu-id="b68ed-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="b68ed-135">將透過工作原則的呼叫指派給使用者</span><span class="sxs-lookup"><span data-stu-id="b68ed-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="b68ed-136">輸入下列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b68ed-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="b68ed-137">例如，下列 Cmdlet 會將呼叫從工作原則 "ContosoUser1CvWP" 指派給名為 **ContosoUser1** 的使用者。</span><span class="sxs-lookup"><span data-stu-id="b68ed-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="b68ed-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b68ed-138">See also</span></span>

[<span data-ttu-id="b68ed-139">透過商務用 Skype Server 中的工作規劃通話</span><span class="sxs-lookup"><span data-stu-id="b68ed-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

