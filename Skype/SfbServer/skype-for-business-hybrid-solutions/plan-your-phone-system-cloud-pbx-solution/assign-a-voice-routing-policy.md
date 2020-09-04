---
title: 指派語音路由原則
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 摘要：閱讀此主題以瞭解如何使用具有內部部署 PSTN 連線功能的電話系統，為使用者指派語音原則。
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359319"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="dc0b8-103">指派語音路由原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="dc0b8-104">在2021年7月31日之後，商務用 Skype Online 將會停用，在此之後將無法再存取服務。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="dc0b8-105">此外，您的內部部署環境之間的 PSTN 連線，不論是透過商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype Online，都將不再支援。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="dc0b8-106">瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="dc0b8-107">**摘要：** 閱讀此主題以瞭解如何使用具有內部部署 PSTN 連線功能的電話系統，為使用者指派語音原則。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="dc0b8-108">一旦使用者位於商務用 Skype Online，並使用具有內部部署 PSTN 連線的電話系統，就會將兩個語音原則套用至他們。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="dc0b8-109">一個是內部部署語音路由原則，您將會指派給內部部署。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="dc0b8-110">這個原則可以是全域或使用者特有的，也可以定義哪些 PSTN 使用方式記錄與使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="dc0b8-111">本主題說明如何指派此原則。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="dc0b8-112">其他語音原則定義使用者可以使用哪些通話功能;這個語音原則是由 Microsoft 所定義，而且對於具有內部部署 PSTN 連線使用者的所有電話系統都是相同的。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="dc0b8-113">它會自動指派給電話系統使用者。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="dc0b8-114">**內部部署使用者**</span><span class="sxs-lookup"><span data-stu-id="dc0b8-114">**On-premises user**</span></span>|<span data-ttu-id="dc0b8-115">**使用內部部署 PSTN 連線使用者的電話系統**</span><span class="sxs-lookup"><span data-stu-id="dc0b8-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dc0b8-116">通話中定義的功能</span><span class="sxs-lookup"><span data-stu-id="dc0b8-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="dc0b8-117">語音原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-117">Voice policy</span></span>  <br/> |<span data-ttu-id="dc0b8-118">預先定義的語音原則，會在使用者授權給電話系統時自動指派。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="dc0b8-119">關聯的 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="dc0b8-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="dc0b8-120">語音原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-120">Voice policy</span></span>  <br/> |<span data-ttu-id="dc0b8-121">語音路由原則，已指派使用者仍在內部部署。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="dc0b8-122">您可以執行下列步驟使用內部部署，而使用者仍是位於內部部署中。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="dc0b8-123">使用全域語音路由原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-123">Using a global voice routing policy</span></span>

<span data-ttu-id="dc0b8-124">在使用具有內部部署 PSTN 連線使用者的電話系統全域語音路由原則之前，您必須將 PSTN 使用方式記錄新增至原則。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="dc0b8-125">將 PSTN 使用方式記錄指派給全域語音路由原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="dc0b8-126">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dc0b8-127">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dc0b8-128">將 PSTN 使用方式記錄新增至原則：</span><span class="sxs-lookup"><span data-stu-id="dc0b8-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="dc0b8-129">例如：</span><span class="sxs-lookup"><span data-stu-id="dc0b8-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="dc0b8-130">建立新的語音路由原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="dc0b8-131">若要建立新的語音路由原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="dc0b8-132">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dc0b8-133">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dc0b8-134">建立新的語音路由原則：</span><span class="sxs-lookup"><span data-stu-id="dc0b8-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="dc0b8-135">例如：</span><span class="sxs-lookup"><span data-stu-id="dc0b8-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="dc0b8-136">此範例會建立名為 HybridVoice 的新語音路由原則，該原則有兩個相關聯的 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="dc0b8-137">指派語音路由原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="dc0b8-138">不論您使用的是通用語音路由原則還是特定使用者，請使用下列步驟將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="dc0b8-139">指派語音路由原則</span><span class="sxs-lookup"><span data-stu-id="dc0b8-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="dc0b8-140">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dc0b8-141">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dc0b8-142">將現有的語音原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="dc0b8-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="dc0b8-143">例如：</span><span class="sxs-lookup"><span data-stu-id="dc0b8-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="dc0b8-144">在此範例中，具有顯示名稱小明凱利的使用者會指派給先前建立的語音原則，名稱為 HybridVoice。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="dc0b8-145">如需語音路由原則的詳細資訊，請參閱 [建立或修改語音原則及設定 PSTN 使用方式記錄 In 商務用 Skype 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)及 [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

