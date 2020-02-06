---
title: 透過商務用 Skype Server 中的工作部署通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：瞭解如何在商務用 Skype Server 中針對部分或所有使用者部署通話。
ms.openlocfilehash: 9b77207d6618e4a869ae369697bc8395aba81673
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791081"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="872c3-103">透過商務用 Skype Server 中的工作部署通話</span><span class="sxs-lookup"><span data-stu-id="872c3-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="872c3-104">**摘要：** 瞭解如何透過商務用 Skype Server 中的工作，為部分或所有使用者部署通話。</span><span class="sxs-lookup"><span data-stu-id="872c3-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="872c3-105">使用這些步驟來為您的使用者部署通話。</span><span class="sxs-lookup"><span data-stu-id="872c3-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="872c3-106">規劃[使用商務用 Skype Server 中的工作來進行通話](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="872c3-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="872c3-107">在舊版 Lync Server 遠端通話控制中，這項功能可讓使用者使用 Lync Server 控制其 PBX 手機。</span><span class="sxs-lookup"><span data-stu-id="872c3-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="872c3-108">在商務用 Skype Server 中，此功能已由 [透過工作通話] 取代。</span><span class="sxs-lookup"><span data-stu-id="872c3-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="872c3-109">透過工作進行通話的先決條件</span><span class="sxs-lookup"><span data-stu-id="872c3-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="872c3-110">[透過公司通話] 使用整合通訊 Web API （UCWA），它會自動安裝在所有商務用 Skype Server 前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="872c3-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="872c3-111">若要讓使用者能夠透過公司通話，您也必須準備好下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="872c3-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="872c3-112">您必須部署中繼伺服器，要麼是作為前端伺服器的一部分，要麼是獨立角色。</span><span class="sxs-lookup"><span data-stu-id="872c3-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="872c3-113">您也必須部署 IP PBX 閘道。</span><span class="sxs-lookup"><span data-stu-id="872c3-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="872c3-114">所有將透過工作啟用呼叫的使用者，都必須在 PBX 電話系統上進行直接撥出（已執行）。</span><span class="sxs-lookup"><span data-stu-id="872c3-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="872c3-115">您必須透過企業語音的工作使用者來啟用所有通話。</span><span class="sxs-lookup"><span data-stu-id="872c3-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="872c3-116">當您這麼做時，必須針對對應的 PBX 電話系統，將每個使用者的商務用 Skype 的號碼設定為相對應的號碼。</span><span class="sxs-lookup"><span data-stu-id="872c3-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="872c3-117">在其商務用 Skype 用戶端的 [**高級**連線] 選項中，所有將透過工作使用呼叫的使用者，都必須已選取 [**自動**設定]。</span><span class="sxs-lookup"><span data-stu-id="872c3-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="872c3-118">這可讓用戶端探索 UCWA Url。</span><span class="sxs-lookup"><span data-stu-id="872c3-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="872c3-119">[**自動**設定] 是預設的選取專案。</span><span class="sxs-lookup"><span data-stu-id="872c3-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="872c3-120">針對每個使用者的呼叫，請啟用來電轉接及同時撥打。</span><span class="sxs-lookup"><span data-stu-id="872c3-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="872c3-121">針對每個工作使用者的通話，請確定已啟用電話撥入式會議和會議撥出功能。</span><span class="sxs-lookup"><span data-stu-id="872c3-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="872c3-122">這可讓這些使用者進入和登出商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="872c3-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="872c3-123">確保透過工作使用者針對每個通話停用委派、小組通話及回應群組。</span><span class="sxs-lookup"><span data-stu-id="872c3-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="872c3-124">部署從公司撥號功能</span><span class="sxs-lookup"><span data-stu-id="872c3-124">Deploy Call Via Work</span></span>

<span data-ttu-id="872c3-125">在先決條件就緒之後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="872c3-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="872c3-126">為您的部署建立全域電話號碼，該商務用 Skype 會在 PBX 來電者 ID 上顯示的是透過工作通話撥打的使用者。</span><span class="sxs-lookup"><span data-stu-id="872c3-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="872c3-127">透過工作原則建立一或多個通話</span><span class="sxs-lookup"><span data-stu-id="872c3-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="872c3-128">將 [透過工作原則撥打電話] 指派給每個將可透過工作通話的使用者</span><span class="sxs-lookup"><span data-stu-id="872c3-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="872c3-129">透過公司全球電話號碼建立通話</span><span class="sxs-lookup"><span data-stu-id="872c3-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="872c3-130">輸入下列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="872c3-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="872c3-131">例如，下列 Cmdlet 會將全域電話號碼設定為1-555-123-4567。</span><span class="sxs-lookup"><span data-stu-id="872c3-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="872c3-132">透過工作原則建立通話</span><span class="sxs-lookup"><span data-stu-id="872c3-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="872c3-133">輸入下列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="872c3-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="872c3-134">例如，下列 Cmdlet 會透過名為 ContosoUser1CvWP 的工作原則建立通話，要求使用者使用系統管理員回撥號碼，並將該回撥號碼設定為1-555-789-1234。</span><span class="sxs-lookup"><span data-stu-id="872c3-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="872c3-135">透過工作原則指派通話給使用者</span><span class="sxs-lookup"><span data-stu-id="872c3-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="872c3-136">輸入下列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="872c3-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="872c3-137">例如，下列 Cmdlet 會透過工作原則 "ContosoUser1CvWP" 將呼叫指派給名為**ContosoUser1**的使用者。</span><span class="sxs-lookup"><span data-stu-id="872c3-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="872c3-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="872c3-138">See also</span></span>

[<span data-ttu-id="872c3-139">透過商務用 Skype Server 中的工作規劃通話</span><span class="sxs-lookup"><span data-stu-id="872c3-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

