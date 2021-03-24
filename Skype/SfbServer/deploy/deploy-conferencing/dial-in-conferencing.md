---
title: 設定商務用 Skype Server 中的電話撥入式會議
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
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中設定電話撥入式會議。
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103849"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="336b9-103">設定商務用 Skype Server 中的電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="336b9-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="336b9-104">**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="336b9-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="336b9-105">在您建立包含會議工作負載的拓撲，以及所選的電話撥入式會議之後，您必須執行額外的步驟來設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="336b9-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="336b9-106">在閱讀本主題之前，請確定您已在商務用 skype server 中的 [電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)、 [硬體和軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)，以及 [電話撥入式會議的部署流程圖及檢查清單](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)中，進行了閱讀計畫。</span><span class="sxs-lookup"><span data-stu-id="336b9-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="336b9-107">若要設定電話撥入式會議，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="336b9-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="336b9-108">設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="336b9-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="336b9-109">設定電話撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="336b9-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="336b9-110">設定撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="336b9-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="336b9-111">設定會議原則</span><span class="sxs-lookup"><span data-stu-id="336b9-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="336b9-112">將行 URI 指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="336b9-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="336b9-113">此外，您也可以執行下列選擇性工作。</span><span class="sxs-lookup"><span data-stu-id="336b9-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="336b9-114">如需這些選用任務的詳細資訊，請參閱 [在商務用 Skype Server 中管理電話撥入式會議](../../manage/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="336b9-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="336b9-115">管理電話撥入式會議的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="336b9-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="336b9-116">管理 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="336b9-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="336b9-117">建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="336b9-117">Create conference directories</span></span>
    
- <span data-ttu-id="336b9-118">管理會議加入和離開宣告</span><span class="sxs-lookup"><span data-stu-id="336b9-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="336b9-119">測試電話撥入式會議設定</span><span class="sxs-lookup"><span data-stu-id="336b9-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="336b9-120">傳送歡迎使用郵件給撥入使用者</span><span class="sxs-lookup"><span data-stu-id="336b9-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="336b9-121">設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="336b9-121">Configure dial plans</span></span>
<span data-ttu-id="336b9-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="336b9-122"><a name="BKMK_ConfigureDialPlans"> </a></span></span>

<span data-ttu-id="336b9-123">當您部署電話撥入式會議時，您必須建立或修改一或多個用於路由撥入存取電話號碼的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="336b9-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="336b9-124">您也必須確定每個撥號對應表至少包含一個正規化規則，此規則會將電話分機分機以 e.164 格式轉換成完整的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="336b9-125">使用電話撥入式會議加入會議的使用者，將其個人身分識別號碼 (PIN) 和其電話號碼輸入，以供已驗證的企業使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="336b9-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="336b9-126">您需要正規化規則，將分機轉換成完整的電話號碼，讓使用者在輸入電話分機時可驗證。</span><span class="sxs-lookup"><span data-stu-id="336b9-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="336b9-127">若要設定電話撥入式會議的撥號對應表：</span><span class="sxs-lookup"><span data-stu-id="336b9-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="336b9-128">不論您是部署企業語音，請修改全域撥號對應表，以加入電話撥入式會議區域，並確定正規化規則正確地轉換您的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="336b9-129">如需詳細指示，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。</span><span class="sxs-lookup"><span data-stu-id="336b9-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="336b9-130">如果您未部署企業語音，請建立電話撥入式會議存取號碼的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="336b9-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="336b9-131">請務必加入電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="336b9-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="336b9-132">如需詳細指示，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。</span><span class="sxs-lookup"><span data-stu-id="336b9-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="336b9-133">如果您部署了企業語音，請視需要修改 Enterprise Voice 撥號對應表，以包含地區，並使用適當的正規化規則來撥打撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="336b9-134">您也可以建立專用的撥號對應表，只用于撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="336b9-135">如需詳細指示，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。</span><span class="sxs-lookup"><span data-stu-id="336b9-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="336b9-136">如需建立正規化規則的詳細資訊，請參閱 [在商務用 Skype 中建立或修改正規化規則](../../deploy/deploy-enterprise-voice/normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="336b9-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="336b9-137">設定電話撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="336b9-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="336b9-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="336b9-138"><a name="BKMK_ConfigureDialInRegions"> </a></span></span>

<span data-ttu-id="336b9-139">設定撥號對應表時，您會指定適用於該撥號對應表的電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="336b9-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="336b9-140">電話撥入式會議區域會將電話撥入式會議存取號碼與適當的撥號對應表產生關聯。</span><span class="sxs-lookup"><span data-stu-id="336b9-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="336b9-141">當您建立撥入存取號碼時，請選取相關聯的撥號對應表的存取號碼相關聯的地區。</span><span class="sxs-lookup"><span data-stu-id="336b9-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="336b9-142">由於為所有的撥號對應表指定區域很重要，因此建議您確認所有的撥號對應表都有會議地區。</span><span class="sxs-lookup"><span data-stu-id="336b9-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="336b9-143">若要確認是否已設定所有電話撥入式會議撥號對應表的區域，請使用 **Get-CsDialPlan** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="336b9-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="336b9-144">如果撥號對應表缺少區域，您可以使用 **Set-CsDialPlan** Cmdlet 來設定區域。</span><span class="sxs-lookup"><span data-stu-id="336b9-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="336b9-145">您也可以使用商務用 Skype Server 控制台更新現有撥號對應表中的區域。</span><span class="sxs-lookup"><span data-stu-id="336b9-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="336b9-146">如需使用商務用 Skype Server 控制台的詳細資訊，請參閱 [在商務用 Skype server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。</span><span class="sxs-lookup"><span data-stu-id="336b9-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="336b9-147">若要確認撥號對應表是否已設定區域屬性</span><span class="sxs-lookup"><span data-stu-id="336b9-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="336b9-148">以 RTCUniversalServerAdmins 群組成員或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="336b9-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="336b9-149">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="336b9-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="336b9-150">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="336b9-150">Run the following at the command prompt:</span></span>
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="336b9-151">例如：</span><span class="sxs-lookup"><span data-stu-id="336b9-151">For example:</span></span>
    
   ```powershell
   Get-CsDialPlan
   ```

   <span data-ttu-id="336b9-152">在此範例中，會傳回組織中所有已設定的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="336b9-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="336b9-153">檢閱傳回的撥號對應表，檢查是否有任何一項缺少電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="336b9-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="336b9-154">如需詳細資訊，請參閱 [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="336b9-154">For more information, see [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="336b9-155">若要設定撥號對應表的區域屬性</span><span class="sxs-lookup"><span data-stu-id="336b9-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="336b9-156">以 RTCUniversalServerAdmins 群組成員或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="336b9-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="336b9-157">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="336b9-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="336b9-158">針對任何缺少電話撥入式會議區域的撥號對應表，執行：</span><span class="sxs-lookup"><span data-stu-id="336b9-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="336b9-159">例如：</span><span class="sxs-lookup"><span data-stu-id="336b9-159">For example:</span></span>
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="336b9-160">在此範例中，將修改識別為 Redmond 的撥號對應表，以將其 DialinConferencingRegion 屬性設為 "US West Coast"。</span><span class="sxs-lookup"><span data-stu-id="336b9-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="336b9-161">如需詳細資訊，請參閱 [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="336b9-161">For more information, see [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="336b9-162">設定撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="336b9-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="336b9-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="336b9-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span></span>

<span data-ttu-id="336b9-164">當您部署電話撥入式會議時，您必須設定使用者可以從公用交換電話網路 (PSTN) 撥打的電話號碼，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="336b9-164">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="336b9-165">這些撥入存取號碼會顯示在會議邀請和電話撥入式會議設定網頁上。</span><span class="sxs-lookup"><span data-stu-id="336b9-165">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="336b9-166">在您可以建立撥入存取號碼之前，您必須先規劃撥入式會議區域，然後使用地區設定撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="336b9-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="336b9-167">如需地區的詳細資訊，請參閱 [在商務用 Skype Server 中規劃撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="336b9-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="336b9-168">如需設定電話撥入式會議的撥號對應表的詳細資訊，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。</span><span class="sxs-lookup"><span data-stu-id="336b9-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="336b9-169">您無法使用新的撥入存取號碼，除非 Active Directory 網域服務 (AD DS) 該存取號碼的複寫已完成。</span><span class="sxs-lookup"><span data-stu-id="336b9-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="336b9-170">複寫可能需要數小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="336b9-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="336b9-171">在您建立撥入存取號碼之後，您可以修改 Active Directory 連絡人物件的顯示名稱，讓使用者可以更輕鬆地識別正確的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="336b9-172">若要修改顯示名稱，請使用 [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="336b9-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="336b9-173">您不應該手動修改 Active Directory 物件。</span><span class="sxs-lookup"><span data-stu-id="336b9-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="336b9-174">若要建立撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="336b9-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="336b9-175">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="336b9-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="336b9-176">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="336b9-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="336b9-177">在左導覽列中，按一下 **[會議]**，然後按一下 **[撥入存取號碼]**。</span><span class="sxs-lookup"><span data-stu-id="336b9-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="336b9-178">在 **[撥入存取號碼]** 頁面中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="336b9-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="336b9-179">按一下 **[新增]** 以開啟 **[新增撥入存取號碼]**。</span><span class="sxs-lookup"><span data-stu-id="336b9-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="336b9-180">按一下清單中的其中一個撥入存取號碼，按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="336b9-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="336b9-p114">使用搜尋欄位來搜尋撥入存取號碼清單中可能無法產生預期結果的欄內容。請依照您想要的欄排序此清單，找出您想檢視或變更的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-p114">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="336b9-183">在 [ **顯示號碼**] 中，輸入公用交換電話網路 (PSTN) 電話使用者撥號以加入會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="336b9-184">此號碼會顯示在會議邀請中和電話撥入式會議設定網頁上。</span><span class="sxs-lookup"><span data-stu-id="336b9-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="336b9-185">在 [ **顯示名稱**] 中，輸入撥入存取號碼的描述。</span><span class="sxs-lookup"><span data-stu-id="336b9-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="336b9-186">這是商務用 Skype 搜尋結果中與撥入存取號碼相關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="336b9-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="336b9-187">當使用者呼叫存取號碼時，此名稱會顯示在用戶端中。</span><span class="sxs-lookup"><span data-stu-id="336b9-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="336b9-188">在 [ **行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 e.164 號碼，包含號碼前面的 + 符號，並排除空格。</span><span class="sxs-lookup"><span data-stu-id="336b9-188">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="336b9-189">例如電話： + 14255550200。</span><span class="sxs-lookup"><span data-stu-id="336b9-189">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="336b9-190">其他電話撥入式會議存取號碼無法重複使用相同的列 URI。</span><span class="sxs-lookup"><span data-stu-id="336b9-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="336b9-191">在 [ **SIP URI**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="336b9-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="336b9-192">在文字方塊中，輸入此撥入式會議存取號碼的唯一 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="336b9-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="336b9-193">這種 SIP URI 會顯示在不同的位置，包括（但不限於）來電通知訊息和舊版的 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="336b9-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="336b9-194">其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="336b9-194">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="336b9-195">建立存取號碼之後，便無法修改 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="336b9-195">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="336b9-196">變更 SIP URI 的唯一方法是刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-196">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="336b9-197">在下拉式清單方塊中，按一下支援此撥入存取號碼之會議應答應用程式的網域。</span><span class="sxs-lookup"><span data-stu-id="336b9-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="336b9-198">在 [ **集** 區] 中，按一下執行支援此撥入存取號碼之會議助理實例的集區。</span><span class="sxs-lookup"><span data-stu-id="336b9-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="336b9-199">如果您在建立存取號碼之後需要變更集區，則必須使用 [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) Cmdlet，或刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="336b9-200">在 [ **主要語言**] 中，按一下為此撥入存取號碼播放提示時所使用的語言。</span><span class="sxs-lookup"><span data-stu-id="336b9-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="336b9-201">主要語言是會議助理用來接聽通話的語言。</span><span class="sxs-lookup"><span data-stu-id="336b9-201">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="336b9-202">在 [電話撥入式會議設定] 網頁上的每一個存取電話號碼旁會顯示支援的語言。</span><span class="sxs-lookup"><span data-stu-id="336b9-202">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="336b9-203"> (選用) 在 **次要語言中 (最多四個)**，請按一下 [ **新增**]，選取您要支援的來電者撥打此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="336b9-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="336b9-204">您最多可以為每個撥入存取號碼選擇四種次要語言。</span><span class="sxs-lookup"><span data-stu-id="336b9-204">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="336b9-205">使用者在撥入會議時，可以先選取次要語言，再進入會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-205">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="336b9-206">若要新增撥入存取號碼的地區，請在 [ **關聯的地區**] 下，按一下 [ **新增**]，然後按一下與此撥入存取號碼的撥號對應表相關聯的一個或多個地區，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="336b9-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="336b9-207">若要從撥入存取號碼中刪除地區，請在 [ **關聯的地區**] 下，按一下您要刪除的地區，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="336b9-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="336b9-208">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="336b9-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="336b9-209">設定會議原則</span><span class="sxs-lookup"><span data-stu-id="336b9-209">Configure conferencing policies</span></span>
<span data-ttu-id="336b9-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="336b9-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span></span>

<span data-ttu-id="336b9-211">會議原則是一種使用者帳戶設定，可指定參與者的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="336b9-211">Conferencing policy is a user account setting that specifies the conferencing experience for participants.</span></span> <span data-ttu-id="336b9-212">您可以建立具有網站範圍或使用者範圍的會議原則。</span><span class="sxs-lookup"><span data-stu-id="336b9-212">You can create conferencing policies with a site scope or a user scope.</span></span> <span data-ttu-id="336b9-213">會議原則設定涵蓋許多會議排程和參與的層面。</span><span class="sxs-lookup"><span data-stu-id="336b9-213">Conferencing policy settings encompass many aspects of conference scheduling and participation.</span></span> <span data-ttu-id="336b9-214">數個會議原則設定支援參與者的電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="336b9-214">Several conferencing policy settings support dial-in conferencing for participants.</span></span> <span data-ttu-id="336b9-215">當您設定電話撥入式會議時，應確認您的組織已正確設定這些欄位，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="336b9-215">When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="336b9-216">如需設定會議原則的詳細資訊，請參閱 [在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="336b9-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="336b9-217">將行 URI 指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="336b9-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="336b9-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="336b9-218"><a name="BKMK_AssignaLineURI"> </a></span></span>

<span data-ttu-id="336b9-219">撥入使用者輸入他們的電話號碼或分機號碼，以及將會議加入已驗證使用者的 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="336b9-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="336b9-220">驗證需要在商務用 Skype Server 使用者帳戶上指定的電話語音 **行 URI** 。</span><span class="sxs-lookup"><span data-stu-id="336b9-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="336b9-221">本主題中的程式說明如何為單一使用者帳戶指派 **行 URI** 。</span><span class="sxs-lookup"><span data-stu-id="336b9-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="336b9-222">如果您需要為多個使用者帳戶指派 **行 URI** ，您可以建立使用 **Set-CsUser** Cmdlet 的腳本。</span><span class="sxs-lookup"><span data-stu-id="336b9-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="336b9-223">如需使用範例腳本將 **行 URI** 指派給多個使用者帳戶的詳細資訊，請參閱 [指派行 URIs 給多位使用者](https://go.microsoft.com/fwlink/p/?linkId=196945)。</span><span class="sxs-lookup"><span data-stu-id="336b9-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="336b9-224">以 RTCUniversalServerAdmins 群組成員的身分，或是 **Cs-UserAdministrator** 或 **CsAdministrator** 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="336b9-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="336b9-225">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="336b9-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="336b9-226">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="336b9-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="336b9-227">在 [搜尋] 欄位中，輸入您要設定電話撥入式會議的使用者名稱，或按一下 [ **新增篩選** ] 以指定搜尋欄位，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="336b9-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="336b9-228">連按兩下使用者名稱，以開啟 [ **編輯商務用 Skype Server 使用者** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="336b9-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="336b9-229">在 [ **電話語音**] 下的 [ **線路 URI** ] 欄位中，輸入唯一且正規化的電話號碼 (例如電話： + 14255550200) 。</span><span class="sxs-lookup"><span data-stu-id="336b9-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="336b9-230">只有在 **電話語音** 設定為 **僅限 pc 對電腦**、 **Enterprise Voice**、**遠端呼叫控制** 或 **遠端呼叫控制** 時，您才可以指定 **行 URI** 。</span><span class="sxs-lookup"><span data-stu-id="336b9-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="336b9-231">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="336b9-231">Click **Commit**.</span></span>
