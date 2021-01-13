---
title: 在商務用 Skype Server 中啟用使用者的 Enterprise Voice
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 摘要：瞭解如何在商務用 Skype Server 中使用 Enterprise Voice，讓使用者能夠撥打和接聽電話。
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830873"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="3c5a7-103">在商務用 Skype Server 中啟用使用者的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3c5a7-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="3c5a7-104">**摘要：** 瞭解如何使用商務用 Skype Server 中的 Enterprise Voice，讓使用者能夠撥打和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="3c5a7-105">在您部署企業語音或呼叫透過工作之後，您可以使用下列程式，讓使用者使用 Enterprise Voice 進行呼叫：</span><span class="sxs-lookup"><span data-stu-id="3c5a7-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c5a7-106">在下列程式中，只有 first 可以使用商務用 Skype Server 控制台執行。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3c5a7-107">對於其餘的程式，您只能使用商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="3c5a7-108">啟用 Enterprise Voice 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="3c5a7-109"> (選用) 指派使用者特有的語音原則的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="3c5a7-110"> (選用) 指派使用者特定撥號對應表的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="3c5a7-111">啟用企業語音的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="3c5a7-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="3c5a7-112">以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="3c5a7-113">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3c5a7-114">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3c5a7-115">在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3c5a7-116">在表格中，按一下您要為 Enterprise Voice 啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="3c5a7-117">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="3c5a7-118">在 [ **編輯商務用 Skype 伺服器使用者** ] 頁面的 [ **電話** 語音] 下，按一下 [ **企業語音**]。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="3c5a7-119">按一下 [ **行 URI**]，然後輸入唯一的標準化電話號碼 (例如，電話： + 14255550200) 。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="3c5a7-120">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-120">Click **Commit**.</span></span>
    
<span data-ttu-id="3c5a7-121">若要完成為使用者啟用 Enterprise Voice，請確定使用者已獲指派語音原則和撥號對應表，不論是預設指派的全域 () 或使用者特有的。根據預設，會為所有使用者指派通用語音原則和撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="3c5a7-122">如果語音原則或撥號對應表存在於使用者帳戶所在網站的網站層級上，這些網站原則將會自動套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="3c5a7-123">若要將個別使用者的語音原則或撥號對應表套用至使用者，您必須執行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="3c5a7-124">如需詳細資訊，請參閱本主題中的下列程式。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="3c5a7-125">語音原則指派</span><span class="sxs-lookup"><span data-stu-id="3c5a7-125">Voice Policy Assignment</span></span>

<span data-ttu-id="3c5a7-126">全域與網站層級語音原則會自動指派給所有已啟用 Enterprise Voice 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="3c5a7-127">您也可以建立適用于特定使用者或群組的語音原則。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="3c5a7-128">這些每個使用者的原則都必須明確指派給使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="3c5a7-129">如果您想要針對所有已啟用 Enterprise Voice 的使用者使用全域或網站語音原則，您可以略過此區段，然後繼續本主題稍後的 [撥號對應表 [指派](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="3c5a7-130">指派使用者特有的語音原則</span><span class="sxs-lookup"><span data-stu-id="3c5a7-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="3c5a7-131">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c5a7-132">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3c5a7-133">若要將現有的使用者語音原則指派給使用者，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3c5a7-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="3c5a7-134">例如：</span><span class="sxs-lookup"><span data-stu-id="3c5a7-134">For example:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="3c5a7-135">在此範例中，具有顯示名稱小明凱利的使用者會被指派名稱為 **VoicePolicyJapan** 的語音原則。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="3c5a7-136">撥號對應表指派</span><span class="sxs-lookup"><span data-stu-id="3c5a7-136">Dial Plan Assignment</span></span>
<span data-ttu-id="3c5a7-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="3c5a7-137"><a name="BKMK_DialPlanAssignment"> </a></span></span>

<span data-ttu-id="3c5a7-138">若要為企業語音使用者或電話撥入式會議的使用者完成使用者帳戶設定，必須為使用者指定撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="3c5a7-139">當您未明確指派現有的個別使用者撥號對應表時，使用者帳戶會自動使用全域撥號對應表或網站層級撥號對應表（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="3c5a7-140">如果您想要針對所有已啟用 Enterprise Voice 的使用者使用全域或網站撥號對應表，您可以略過本節。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="3c5a7-141">指派使用者特有的撥號對應表</span><span class="sxs-lookup"><span data-stu-id="3c5a7-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="3c5a7-142">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3c5a7-143">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3c5a7-144">若要指派使用者特有的撥號對應表，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3c5a7-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="3c5a7-145">例如：</span><span class="sxs-lookup"><span data-stu-id="3c5a7-145">For example:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="3c5a7-146">在此範例中，具有顯示名稱小明凱利的使用者會被指派名稱為 **DialPlanJapan** 的使用者撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="3c5a7-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

