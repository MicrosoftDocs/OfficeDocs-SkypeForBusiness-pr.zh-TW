---
title: 指派語音路由策略
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '摘要: 請閱讀本主題, 以瞭解如何在 Office 365 中使用電話系統以內部部署 PSTN 連線來指派語音原則。'
ms.openlocfilehash: 0d310378b77c09b427836f0d9bceb60a14982071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192602"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="b08e7-103">指派語音路由策略</span><span class="sxs-lookup"><span data-stu-id="b08e7-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="b08e7-104">**摘要:** 請閱讀本主題, 以瞭解如何在 Office 365 中使用電話系統與內部部署 PSTN 連線來指派語音原則。</span><span class="sxs-lookup"><span data-stu-id="b08e7-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="b08e7-105">一旦使用者位於商務用 Skype Online, 且使用 Office 365 中的電話系統與內部部署 PSTN 連線, 就會套用兩個語音原則。</span><span class="sxs-lookup"><span data-stu-id="b08e7-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="b08e7-106">一個是您將在內部部署指派的內部部署語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="b08e7-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="b08e7-107">這個原則可以是全域或使用者專用的, 並定義哪些 PSTN 使用記錄與使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="b08e7-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="b08e7-108">本主題說明如何指派此原則。</span><span class="sxs-lookup"><span data-stu-id="b08e7-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="b08e7-109">其他語音原則定義使用者可以使用的通話功能。此語音原則是由 Microsoft 定義, 且與內部部署 PSTN 連線使用者在 Office 365 中的所有電話系統都是相同的。</span><span class="sxs-lookup"><span data-stu-id="b08e7-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="b08e7-110">系統會自動將它指派給 Office 365 使用者中的 [電話系統]。</span><span class="sxs-lookup"><span data-stu-id="b08e7-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="b08e7-111">**內部部署使用者**</span><span class="sxs-lookup"><span data-stu-id="b08e7-111">**On-premises user**</span></span>|<span data-ttu-id="b08e7-112">**Office 365 中的電話系統與內部部署 PSTN 連線使用者**</span><span class="sxs-lookup"><span data-stu-id="b08e7-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b08e7-113">中定義的通話功能</span><span class="sxs-lookup"><span data-stu-id="b08e7-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="b08e7-114">語音原則</span><span class="sxs-lookup"><span data-stu-id="b08e7-114">Voice policy</span></span>  <br/> |<span data-ttu-id="b08e7-115">預先定義的語音原則, 在使用者使用 Office 365 中的電話系統授權時自動指派。</span><span class="sxs-lookup"><span data-stu-id="b08e7-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="b08e7-116">關聯的 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="b08e7-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="b08e7-117">語音原則</span><span class="sxs-lookup"><span data-stu-id="b08e7-117">Voice policy</span></span>  <br/> |<span data-ttu-id="b08e7-118">語音路由策略, 在使用者仍在內部部署時指派。</span><span class="sxs-lookup"><span data-stu-id="b08e7-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="b08e7-119">您可以使用內部部署部署執行下列步驟, 而使用者仍在內部部署的部署中。</span><span class="sxs-lookup"><span data-stu-id="b08e7-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="b08e7-120">使用全域語音路由策略</span><span class="sxs-lookup"><span data-stu-id="b08e7-120">Using a global voice routing policy</span></span>

<span data-ttu-id="b08e7-121">您必須先將 PSTN 使用記錄新增至原則, 才能在 Office 365 中的電話系統中使用全域語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="b08e7-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="b08e7-122">將 PSTN 使用記錄指派給全域語音路由策略</span><span class="sxs-lookup"><span data-stu-id="b08e7-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="b08e7-123">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b08e7-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b08e7-124">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="b08e7-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b08e7-125">將 PSTN 使用記錄新增至原則:</span><span class="sxs-lookup"><span data-stu-id="b08e7-125">Add the PSTN usage records to the policy:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="b08e7-126">例如：</span><span class="sxs-lookup"><span data-stu-id="b08e7-126">For example:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="b08e7-127">建立新的語音路由策略</span><span class="sxs-lookup"><span data-stu-id="b08e7-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="b08e7-128">若要建立新的語音路由策略</span><span class="sxs-lookup"><span data-stu-id="b08e7-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="b08e7-129">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b08e7-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b08e7-130">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="b08e7-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b08e7-131">建立新的語音路由策略:</span><span class="sxs-lookup"><span data-stu-id="b08e7-131">Create a new voice routing policy:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="b08e7-132">例如：</span><span class="sxs-lookup"><span data-stu-id="b08e7-132">For example:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="b08e7-133">這個範例會建立名為 HybridVoice 的新語音路由策略, 其中有兩個與它相關聯的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="b08e7-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="b08e7-134">指派語音路由策略</span><span class="sxs-lookup"><span data-stu-id="b08e7-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="b08e7-135">不論您使用的是全域語音路由策略, 還是使用者專用的, 請使用下列步驟將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b08e7-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="b08e7-136">指派語音路由策略</span><span class="sxs-lookup"><span data-stu-id="b08e7-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="b08e7-137">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b08e7-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b08e7-138">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="b08e7-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b08e7-139">將現有的語音原則指派給使用者:</span><span class="sxs-lookup"><span data-stu-id="b08e7-139">Assign an existing voice policy to a user:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="b08e7-140">例如：</span><span class="sxs-lookup"><span data-stu-id="b08e7-140">For example:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="b08e7-141">在這個範例中, 將顯示名稱 Bob 凱利的使用者指派給先前建立的名稱為 HybridVoice 的語音原則。</span><span class="sxs-lookup"><span data-stu-id="b08e7-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="b08e7-142">如需有關語音路由策略的詳細資訊, 請參閱[建立或修改語音原則, 以及在商務用 Skype 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、[新-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)及[贈與 CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)中設定 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="b08e7-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

