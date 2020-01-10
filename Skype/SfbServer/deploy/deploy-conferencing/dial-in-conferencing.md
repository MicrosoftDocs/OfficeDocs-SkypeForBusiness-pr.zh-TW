---
title: 在商務用 Skype Server 中設定電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 摘要：請閱讀本主題，以瞭解如何在商務用 Skype Server 中設定電話撥入式會議。
ms.openlocfilehash: ff04637cf077bae4c1408a48a487582a04123b54
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002923"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="c8eab-103">在商務用 Skype Server 中設定電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="c8eab-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="c8eab-104">**摘要：** 若要瞭解如何在商務用 Skype Server 中設定電話撥入式會議，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="c8eab-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="c8eab-105">在您建立包含會議工作負荷與已選取電話撥入式會議的拓撲之後，您必須執行其他步驟來設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="c8eab-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="c8eab-106">在您閱讀本主題之前，請確定您已閱讀商務用 Skype server 的[電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)、[商務用 skype server 的硬體及軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)，以及[電話撥入式會議的部署流程圖與檢查清單](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="c8eab-107">若要設定電話撥入式會議，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c8eab-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="c8eab-108">設定撥號方案</span><span class="sxs-lookup"><span data-stu-id="c8eab-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="c8eab-109">設定電話撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="c8eab-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="c8eab-110">設定撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="c8eab-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="c8eab-111">設定會議原則</span><span class="sxs-lookup"><span data-stu-id="c8eab-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="c8eab-112">將行 URI 指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="c8eab-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="c8eab-113">此外，您也可以執行下列選用的工作。</span><span class="sxs-lookup"><span data-stu-id="c8eab-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="c8eab-114">如需這些選用工作的詳細資訊，請參閱[管理商務用 Skype Server 中的電話撥入式會議](../../manage/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="c8eab-115">管理電話撥入式會議的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="c8eab-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="c8eab-116">管理 DTMF 命令的金鑰組應</span><span class="sxs-lookup"><span data-stu-id="c8eab-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="c8eab-117">建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="c8eab-117">Create conference directories</span></span>
    
- <span data-ttu-id="c8eab-118">管理會議加入與離開宣告</span><span class="sxs-lookup"><span data-stu-id="c8eab-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="c8eab-119">測試電話撥入式會議設定</span><span class="sxs-lookup"><span data-stu-id="c8eab-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="c8eab-120">傳送歡迎郵件給撥入使用者</span><span class="sxs-lookup"><span data-stu-id="c8eab-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="c8eab-121">設定撥號方案</span><span class="sxs-lookup"><span data-stu-id="c8eab-121">Configure dial plans</span></span>
<span data-ttu-id="c8eab-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="c8eab-122"></span></span>

<span data-ttu-id="c8eab-123">當您部署電話撥入式會議時，您需要建立或修改路由撥入存取電話號碼的一個或多個撥號方案。</span><span class="sxs-lookup"><span data-stu-id="c8eab-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="c8eab-124">您也必須確認每個撥號方案都至少包含一個標準化規則，這項規則會將電話分機轉換成以164格式的完整電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c8eab-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="c8eab-125">電話撥入式會議以已驗證的企業使用者身分加入會議的使用者，只要輸入其個人識別碼（PIN）及他們的電話號碼即可。</span><span class="sxs-lookup"><span data-stu-id="c8eab-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="c8eab-126">您需要正常化規則，將延伸轉換成完整的電話號碼，讓使用者在輸入電話分機時就能進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c8eab-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="c8eab-127">若要為電話撥入式會議設定撥號方案，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c8eab-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="c8eab-128">不論是否要部署企業語音，請修改全域撥號方案以新增電話撥入式會議區域，並確認正常化規則正確地轉換您的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c8eab-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="c8eab-129">如需詳細指示，請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="c8eab-130">如果您沒有部署企業語音，請為電話撥入式會議存取號碼建立撥號方案。</span><span class="sxs-lookup"><span data-stu-id="c8eab-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="c8eab-131">請務必包含電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="c8eab-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="c8eab-132">如需詳細指示，請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="c8eab-133">如果您已部署企業語音，請根據需要修改企業語音撥號方案，以加入地區，並針對撥入存取號碼使用適當的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="c8eab-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="c8eab-134">您也可以建立只用于撥入存取號碼的專用撥號方案。</span><span class="sxs-lookup"><span data-stu-id="c8eab-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="c8eab-135">如需詳細指示，請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="c8eab-136">如需建立正常化規則的詳細資料，請參閱[在商務用 Skype 中建立或修改正常化規則](../../deploy/deploy-enterprise-voice/normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="c8eab-137">設定電話撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="c8eab-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="c8eab-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="c8eab-138"></span></span>

<span data-ttu-id="c8eab-139">當您設定撥號方案時，請指定適用于該撥號方案的電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="c8eab-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="c8eab-140">電話撥入式會議區域會將電話撥入式會議存取號碼與適當的撥號方案進行關聯。</span><span class="sxs-lookup"><span data-stu-id="c8eab-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="c8eab-141">當您建立撥入存取號碼時，請選取將存取號碼與適當的撥號方案相關聯的地區。</span><span class="sxs-lookup"><span data-stu-id="c8eab-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="c8eab-142">因為為所有撥號方案指定區域很重要，所以建議您確認所有撥號方案都有會議區域。</span><span class="sxs-lookup"><span data-stu-id="c8eab-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="c8eab-143">若要驗證是否已針對所有電話撥入式會議撥號方案設定區域，請使用**CsDialPlan** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8eab-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="c8eab-144">如果撥號方案中的區域遺失，您可以使用**CsDialPlan** Cmdlet 來設定區域。</span><span class="sxs-lookup"><span data-stu-id="c8eab-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="c8eab-145">您也可以使用商務用 Skype Server 的 [控制台] 來更新現有撥號方案中的區域。</span><span class="sxs-lookup"><span data-stu-id="c8eab-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="c8eab-146">如需使用商務用 Skype Server [控制台] 的詳細資料，請參閱[在商務用 Skype server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="c8eab-147">驗證撥號方案是否已設定 region 屬性</span><span class="sxs-lookup"><span data-stu-id="c8eab-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="c8eab-148">以 RTCUniversalServerAdmins 群組的成員或**cs-VoiceAdministrator**、 **cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="c8eab-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="c8eab-149">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c8eab-150">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c8eab-150">Run the following at the command prompt:</span></span>
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="c8eab-151">例如：</span><span class="sxs-lookup"><span data-stu-id="c8eab-151">For example:</span></span>
    
   ```powershell
   Get-CsDialPlan
   ```

   <span data-ttu-id="c8eab-152">在這個範例中，會傳回為貴組織設定的所有撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="c8eab-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="c8eab-153">查看傳回的撥號方案，以找出遺失電話撥入式會議區域的任何專案。</span><span class="sxs-lookup"><span data-stu-id="c8eab-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="c8eab-154">如需詳細資訊，請參閱[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="c8eab-155">若要設定撥號方案的 region 屬性</span><span class="sxs-lookup"><span data-stu-id="c8eab-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="c8eab-156">以 RTCUniversalServerAdmins 群組的成員或**cs-VoiceAdministrator**、 **cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="c8eab-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="c8eab-157">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c8eab-158">針對遺失電話撥入式會議區域的任何撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="c8eab-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="c8eab-159">例如：</span><span class="sxs-lookup"><span data-stu-id="c8eab-159">For example:</span></span>
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="c8eab-160">在這個範例中，會修改具有雷德蒙者身分識別的撥號計畫，以將 DialinConferencingRegion 屬性設為 "US West Coast"。</span><span class="sxs-lookup"><span data-stu-id="c8eab-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="c8eab-161">如需詳細資訊，請參閱[設定 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="c8eab-162">設定撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="c8eab-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="c8eab-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="c8eab-163"></span></span>

<span data-ttu-id="c8eab-164">當您部署電話撥入式會議時，您必須設定使用者可從公用交換電話網絡（PSTN）撥打電話的電話號碼，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="c8eab-164">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="c8eab-165">這些撥入存取號碼會出現在會議邀請和 [電話撥入式會議設定] 網頁上。</span><span class="sxs-lookup"><span data-stu-id="c8eab-165">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="c8eab-166">您必須先規劃撥入式會議區域，然後設定與地區的撥號方案，才能建立撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="c8eab-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="c8eab-167">如需地區的詳細資料，請參閱[在商務用 Skype 伺服器中規劃電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="c8eab-168">如需有關設定電話撥入式會議的撥號方案的詳細資訊，請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8eab-169">在該存取號碼的 Active Directory 網域服務（AD DS）複製完成之前，您無法使用新的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c8eab-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="c8eab-170">複製可能需要幾個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="c8eab-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c8eab-171">在您建立撥入存取號碼之後，您可以修改 Active Directory 連絡人物件的顯示名稱，讓使用者能更輕鬆地識別正確的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c8eab-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="c8eab-172">若要修改顯示名稱，請使用[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8eab-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="c8eab-173">您不應該手動修改 Active Directory 物件。</span><span class="sxs-lookup"><span data-stu-id="c8eab-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="c8eab-174">建立撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="c8eab-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="c8eab-175">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c8eab-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c8eab-176">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c8eab-177">在左側導覽列中，按一下 [**會議**]，然後按一下 [**撥入存取號碼**]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="c8eab-178">在 [**撥入存取號碼**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c8eab-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="c8eab-179">按一下 [**新增**] 以開啟**新的撥入存取號碼**。</span><span class="sxs-lookup"><span data-stu-id="c8eab-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="c8eab-180">按一下清單中的其中一個撥入存取號碼，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="c8eab-181">使用 [搜尋] 欄位來搜尋撥入存取號碼清單中的欄內容，可能不會產生您預期的結果。</span><span class="sxs-lookup"><span data-stu-id="c8eab-181">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="c8eab-182">您可以改為依您想要查看或變更的撥入存取號碼來排序清單。</span><span class="sxs-lookup"><span data-stu-id="c8eab-182">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="c8eab-183">在 [**顯示號碼**] 中，輸入「公用交換電話網絡（PSTN）電話撥打電話給」加入會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c8eab-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="c8eab-184">這個數位會顯示在 [會議邀請] 和 [電話撥入式會議設定] 網頁上。</span><span class="sxs-lookup"><span data-stu-id="c8eab-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="c8eab-185">在 [**顯示名稱**] 中，輸入撥入存取號碼的描述。</span><span class="sxs-lookup"><span data-stu-id="c8eab-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="c8eab-186">這是與商務用 Skype 搜尋結果中的撥入存取號碼相關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="c8eab-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="c8eab-187">當使用者呼叫存取號碼時，此名稱就會顯示在用戶端中。</span><span class="sxs-lookup"><span data-stu-id="c8eab-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="c8eab-188">在 [**行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 E. 164 個數字，包括數位前面的 + 符號，不含空格。</span><span class="sxs-lookup"><span data-stu-id="c8eab-188">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="c8eab-189">例如，電話： + 14255550200。</span><span class="sxs-lookup"><span data-stu-id="c8eab-189">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8eab-190">其他電話撥入式會議存取號碼無法重複使用相同的行 URI。</span><span class="sxs-lookup"><span data-stu-id="c8eab-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="c8eab-191">在**SIP URI**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c8eab-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="c8eab-192">在文字方塊中，輸入此電話撥入式會議存取號碼的唯一 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c8eab-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="c8eab-193">此 SIP URI 會顯示在不同的位置，包括但不限於呼叫通知訊息及舊版 Lync 用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="c8eab-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="c8eab-194">其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c8eab-194">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="c8eab-195">在建立存取號碼之後，便無法修改 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c8eab-195">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="c8eab-196">變更 SIP URI 的唯一方式是刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c8eab-196">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="c8eab-197">在下拉式清單方塊中，按一下支援此撥入存取號碼之會議助理應用程式的網域。</span><span class="sxs-lookup"><span data-stu-id="c8eab-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="c8eab-198">在 [Pool] （**池**）中，按一下執行支援此撥入存取號碼之會議助理實例的池。</span><span class="sxs-lookup"><span data-stu-id="c8eab-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8eab-199">如果您在建立存取號碼後需要變更池，您必須使用[CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) Cmdlet，或刪除並重新建立存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c8eab-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="c8eab-200">在**主要語言**中，按一下針對此撥入存取號碼播放提示的語言。</span><span class="sxs-lookup"><span data-stu-id="c8eab-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="c8eab-201">主要語言是會議助理用來接聽通話的語言。</span><span class="sxs-lookup"><span data-stu-id="c8eab-201">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="c8eab-202">支援的語言會顯示在電話撥入式會議設定網頁上的每個存取電話號碼旁邊。</span><span class="sxs-lookup"><span data-stu-id="c8eab-202">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="c8eab-203">可選在**次要語言（最多四個）** 中，按一下 [**新增**]，選取您想要支援來電者至此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c8eab-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="c8eab-204">您最多可以為每個撥入存取號碼選擇四個次要語言。</span><span class="sxs-lookup"><span data-stu-id="c8eab-204">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="c8eab-205">使用者在撥入會議時，輸入會議 ID 前，就可以選取次要語言。</span><span class="sxs-lookup"><span data-stu-id="c8eab-205">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="c8eab-206">若要新增撥入存取號碼的地區，請在 [**相關區域**] 底下，按一下 [**新增**]，按一下與此撥入存取號碼的撥號方案相關聯的一個或多個區域，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c8eab-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="c8eab-207">若要從撥入存取號碼刪除區域，請在 [**相關區域**] 底下，按一下您要刪除的區域，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="c8eab-208">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8eab-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="c8eab-209">設定會議原則</span><span class="sxs-lookup"><span data-stu-id="c8eab-209">Configure conferencing policies</span></span>
<span data-ttu-id="c8eab-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="c8eab-210"></span></span>

<span data-ttu-id="c8eab-211">[會議原則] 是一個使用者帳戶設定，可為參與者指定會議體驗。</span><span class="sxs-lookup"><span data-stu-id="c8eab-211">Conferencing policy is a user account setting that specifies the conferencing experience for participants.</span></span> <span data-ttu-id="c8eab-212">您可以使用網站範圍或使用者範圍建立會議原則。</span><span class="sxs-lookup"><span data-stu-id="c8eab-212">You can create conferencing policies with a site scope or a user scope.</span></span> <span data-ttu-id="c8eab-213">會議原則設定涵蓋了會議排程與參與的許多方面。</span><span class="sxs-lookup"><span data-stu-id="c8eab-213">Conferencing policy settings encompass many aspects of conference scheduling and participation.</span></span> <span data-ttu-id="c8eab-214">幾個會議原則設定支援參與者的電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="c8eab-214">Several conferencing policy settings support dial-in conferencing for participants.</span></span> <span data-ttu-id="c8eab-215">當您設定電話撥入式會議時，應確認這些欄位已針對您的組織進行適當的設定，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="c8eab-215">When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="c8eab-216">如需有關設定會議原則的詳細資訊，請參閱[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="c8eab-217">將行 URI 指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="c8eab-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="c8eab-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="c8eab-218"></span></span>

<span data-ttu-id="c8eab-219">[撥入使用者] 輸入他們的電話號碼或分機，以及將會議加入為經過驗證的使用者的 PIN。</span><span class="sxs-lookup"><span data-stu-id="c8eab-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="c8eab-220">在商務用 Skype Server 使用者帳戶上指定的電話**線路 URI**是驗證所必需的。</span><span class="sxs-lookup"><span data-stu-id="c8eab-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="c8eab-221">本主題中的程式說明如何為單一使用者帳戶指派**行 URI** 。</span><span class="sxs-lookup"><span data-stu-id="c8eab-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="c8eab-222">如果您需要為多個使用者帳戶指派**行 URI** ，您可以建立使用**move-csuser** Cmdlet 的腳本。</span><span class="sxs-lookup"><span data-stu-id="c8eab-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="c8eab-223">如需使用範例腳本將**行 URI**指派給多個使用者帳戶的詳細資料，請參閱[將行 Uri 指派給多個使用者](https://go.microsoft.com/fwlink/p/?linkId=196945)。</span><span class="sxs-lookup"><span data-stu-id="c8eab-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="c8eab-224">以 RTCUniversalServerAdmins 群組的成員或**Cs-UserAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="c8eab-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="c8eab-225">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c8eab-226">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c8eab-227">在 [搜尋] 欄位中，輸入您要為電話撥入式會議設定的使用者名稱，或按一下 [**新增篩選**] 以指定搜尋欄位，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="c8eab-228">按兩下使用者名稱以開啟 [**編輯商務用 Skype 伺服器使用者**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c8eab-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="c8eab-229">在 [**電話**] 底下的 [**行 URI** ] 欄位中，輸入唯一的、標準化的電話號碼（例如電話： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="c8eab-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8eab-230">只有將**電話**設定為 [**僅電腦至電腦**]、[**企業語音**]、[**遠端通話控制**] 或 [**遠端通話控制**] 時，才能指定 [**行 URI** ]。</span><span class="sxs-lookup"><span data-stu-id="c8eab-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="c8eab-231">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8eab-231">Click **Commit**.</span></span>
    

