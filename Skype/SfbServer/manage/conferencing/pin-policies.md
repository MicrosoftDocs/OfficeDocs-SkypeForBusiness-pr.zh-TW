---
title: 為商務用 Skype Server 中的電話撥入式會議管理 PIN 碼原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 摘要：瞭解如何為商務用 Skype Server 中的電話撥入式會議管理 PIN 碼原則。
ms.openlocfilehash: 6544586071f1107537232a117de196dfbffeb4aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827949"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="04b48-103">為商務用 Skype Server 中的電話撥入式會議管理 PIN 碼原則</span><span class="sxs-lookup"><span data-stu-id="04b48-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="04b48-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="04b48-105">在您組織中 (AD DS) 認證的商務用 Skype 伺服器使用者，您可以使用個人識別碼 (PIN) ，將電話撥入式會議當作已驗證的使用者加入電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="04b48-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="04b48-106">PIN 原則可定義電話撥入式會議 PIN 的運作方式規則。</span><span class="sxs-lookup"><span data-stu-id="04b48-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="04b48-107">如果您要對整個組織使用相同的 PIN 原則，您可以使用全域 PIN 原則，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="04b48-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="04b48-108">全域 PIN 原則可在樹系層級上定義電話撥入式會議 PIN 的規則。</span><span class="sxs-lookup"><span data-stu-id="04b48-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="04b48-109">您可以修改全域 PIN 原則，但無法加以刪除。</span><span class="sxs-lookup"><span data-stu-id="04b48-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="04b48-110">如果您要將特定原則套用至網站或特定使用者群組，您可以建立新的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="04b48-111">對使用者套用 PIN 原則時，會優先套用最小的範圍。</span><span class="sxs-lookup"><span data-stu-id="04b48-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="04b48-112">如果您為使用者指派了使用者層級 PIN 原則，這些設定將會優先套用。</span><span class="sxs-lookup"><span data-stu-id="04b48-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="04b48-113">如果您未指派使用者原則，則會套用網站層級 PIN 原則 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="04b48-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="04b48-114">如果未套用使用者或網站原則，則會使用全域 PIN 原則的預設設定。</span><span class="sxs-lookup"><span data-stu-id="04b48-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="04b48-115">查看有關 PIN 原則的資訊</span><span class="sxs-lookup"><span data-stu-id="04b48-115">View information about PIN policies</span></span>

<span data-ttu-id="04b48-116">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面，查看 PIN 原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="04b48-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="04b48-117">使用商務用 Skype Server 控制台，查看 PIN 原則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="04b48-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="04b48-118">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="04b48-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="04b48-119">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="04b48-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="04b48-120">在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。</span><span class="sxs-lookup"><span data-stu-id="04b48-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="04b48-121">在 [ **PIN 原則** ] 頁面上，按一下您要查看的 PIN 原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="04b48-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="04b48-122">使用商務用 Skype Server 管理命令介面來查看 PIN 原則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="04b48-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="04b48-123">若要查看有關 PIN 原則的資訊，請使用 **Get-CsPinPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04b48-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="04b48-124">例如，下列命令會傳回 Identity 為 site： Redmond 的單一 PIN 原則資訊：</span><span class="sxs-lookup"><span data-stu-id="04b48-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="04b48-125">如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="04b48-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="04b48-126">修改通用 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-126">Modify the global PIN policy</span></span>

<span data-ttu-id="04b48-127">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面，修改全域 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="04b48-128">使用商務用 Skype Server 控制台修改全域電話撥入式會議 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="04b48-129">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="04b48-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="04b48-130">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="04b48-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="04b48-131">在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。</span><span class="sxs-lookup"><span data-stu-id="04b48-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="04b48-132">在 **[PIN 原則]** 頁面上，依序按一下 **[通用]** 原則、**[編輯]** 和 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="04b48-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="04b48-p105">在 **[編輯 PIN 原則]** 的 **[最小 PIN 長度]** 中，輸入或選取您要允許的最小 PIN 長度。預設的最小長度為五位數。</span><span class="sxs-lookup"><span data-stu-id="04b48-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="04b48-p106">若要能夠指定使用者遭鎖定前可嘗試登入的次數上限，請選取 **[指定登入嘗試次數上限]** 核取方塊。若未選取此選項，則會根據 PIN 長度自動指定允許的嘗試次數上限。依預設會自動指定嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="04b48-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="04b48-138">如果您選取了 **[指定登入嘗試次數上限]** 核取方塊，請在 **[登入嘗試次數上限]** 中輸入或選取您所要允許的登入嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="04b48-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="04b48-p107">若要讓 PIN 有期限，請選取 **[啟用 PIN 到期]** 核取方塊。若未選取此選項，PIN 將永不過期。根據預設，PIN 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="04b48-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="04b48-142">如果您選取了 **[啟用 PIN 到期]** 核取方塊，請在 **[PIN 於下列日數後到期]** 中輸入或選取 PIN 將在幾天之後到期。</span><span class="sxs-lookup"><span data-stu-id="04b48-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="04b48-p108">在 **[PIN 碼歷程記錄計數]** 中，輸入使用者必須在建立多少個 PIN 之後才可重複使用 PIN。根據預設，使用者可重複使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="04b48-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="04b48-p109">若要允許在 PIN 中使用共同模式的數字 (如連續數字與重複數字組)，請選取 **[允許共同模式]** 核取方塊。若未選取此選項，則只會允許複合模式的數字。依預設只會允許複合模式的數字。</span><span class="sxs-lookup"><span data-stu-id="04b48-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="04b48-148">基於安全性的考慮，Microsoft 建議您不要允許通用模式。</span><span class="sxs-lookup"><span data-stu-id="04b48-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="04b48-149">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="04b48-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="04b48-150">使用商務用 Skype Server 管理命令介面來修改全域電話撥入式會議 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="04b48-151">若要修改全域電話撥入式會議 PIN 原則，請使用 **Set-CsPinPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04b48-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="04b48-152">下列命令會變更所有設定供組織使用之 PIN 碼原則的 MinPasswordLength 值。</span><span class="sxs-lookup"><span data-stu-id="04b48-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="04b48-153">為達到此目的，命令會先呼叫不含任何參數的 **Get-CsPinPolicy** Cmdlet，以取回所有現有 PIN 碼原則的集合。</span><span class="sxs-lookup"><span data-stu-id="04b48-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="04b48-154">然後，該集合會管線傳送至 **Set-CsPinPolicy** Cmdlet，此 Cmdlet 會修改集合中每個原則的 MinPasswordLength 屬性值：</span><span class="sxs-lookup"><span data-stu-id="04b48-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="04b48-155">如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="04b48-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="04b48-156">建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="04b48-157">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來建立使用者或網站 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="04b48-158">使用商務用 Skype Server 控制台建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="04b48-159">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="04b48-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="04b48-160">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="04b48-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="04b48-161">在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。</span><span class="sxs-lookup"><span data-stu-id="04b48-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="04b48-162">在 [ **PIN 原則** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="04b48-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="04b48-163">若要建立使用者層級原則，請按一下 [ **使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="04b48-163">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="04b48-164">在 [ **新增 PIN 原則**] 的 [ **名稱**] 中，輸入描述原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="04b48-164">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="04b48-165">若要建立網站層級原則，請按一下 [ **網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="04b48-165">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="04b48-166">在 [ **選取網站** ] 搜尋欄位中，輸入您要建立原則的網站名稱全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="04b48-166">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="04b48-167">在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="04b48-167">In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="04b48-168">在 [ **描述** ] 欄位中，輸入 PIN 原則的描述。</span><span class="sxs-lookup"><span data-stu-id="04b48-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="04b48-169">在 [ **最小 PIN 碼長度** ] 欄位中，輸入或選取您想要允許的最小 pin 碼長度。</span><span class="sxs-lookup"><span data-stu-id="04b48-169">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="04b48-170">預設的最小長度為五位數。</span><span class="sxs-lookup"><span data-stu-id="04b48-170">The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="04b48-p114">若要能夠指定使用者遭鎖定前可嘗試登入的次數上限，請選取 **[指定登入嘗試次數上限]** 核取方塊。若未選取此選項，則會根據 PIN 長度自動指定允許的嘗試次數上限。依預設會自動指定嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="04b48-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="04b48-174">如果您選取了 **[指定登入嘗試次數上限]** 核取方塊，請在 **[登入嘗試次數上限]** 中輸入或選取您所要允許的登入嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="04b48-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="04b48-p115">若要讓 PIN 有期限，請選取 **[啟用 PIN 到期]** 核取方塊。若未選取此選項，PIN 將永不過期。根據預設，PIN 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="04b48-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="04b48-178">如果您選取了 **[啟用 PIN 到期]** 核取方塊，請在 **[PIN 於下列日數後到期]** 中輸入或選取 PIN 將在幾天之後到期。</span><span class="sxs-lookup"><span data-stu-id="04b48-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="04b48-p116">在 **[PIN 碼歷程記錄計數]** 中，輸入使用者必須在建立多少個 PIN 之後才可重複使用 PIN。根據預設，使用者可重複使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="04b48-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="04b48-p117">若要允許在 PIN 中使用共同模式的數字 (如連續數字與重複數字組)，請選取 **[允許共同模式]** 核取方塊。若未選取此選項，則只會允許複合模式的數字。依預設只會允許複合模式的數字。</span><span class="sxs-lookup"><span data-stu-id="04b48-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="04b48-184">基於安全性的考慮，Microsoft 建議您不要允許通用模式。</span><span class="sxs-lookup"><span data-stu-id="04b48-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="04b48-185">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="04b48-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="04b48-186">使用商務用 Skype Server 管理命令介面來建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="04b48-187">若要建立使用者或網站 PIN 原則，請使用 **get-cspinpolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04b48-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="04b48-188">下列命令會使用 Identity site： Redmond 建立新的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="04b48-189">這個命令只包含一個 optional 參數 MinPasswordLength，可用來將 MinPasswordLength 屬性設定為7。</span><span class="sxs-lookup"><span data-stu-id="04b48-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="04b48-190">所有剩餘的原則屬性都會以預設值進行設定。</span><span class="sxs-lookup"><span data-stu-id="04b48-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="04b48-191">如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="04b48-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="04b48-192">修改使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="04b48-193">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面，修改使用者或網站 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="04b48-194">使用商務用 Skype Server 控制台修改使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="04b48-195">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="04b48-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="04b48-196">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="04b48-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="04b48-197">在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。</span><span class="sxs-lookup"><span data-stu-id="04b48-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="04b48-198">在 [ **PIN 原則** ] 頁面上，按一下您要變更的 PIN 原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="04b48-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="04b48-199">在 [ **編輯 PIN 原則**] 中，修改原則名稱 (以外的任何原則設定，但無法修改) 。</span><span class="sxs-lookup"><span data-stu-id="04b48-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="04b48-200">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="04b48-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="04b48-201">使用商務用 Skype Server 管理命令介面來修改使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="04b48-202">若要修改電話撥入式會議 PIN 原則，請使用 **Set-CsPinPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04b48-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="04b48-203">下列命令會修改指派給 Redmond 網站的 PIN 碼原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="04b48-204">在此情況下，此命令會將 MinPasswordLength 屬性的值變更為10。這表示新 Pin 必須至少包含10位數：</span><span class="sxs-lookup"><span data-stu-id="04b48-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="04b48-205">如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="04b48-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="04b48-206">刪除使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="04b48-207">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來刪除使用者或網站 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="04b48-208">使用商務用 Skype Server 控制台刪除使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="04b48-209">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="04b48-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="04b48-210">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="04b48-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="04b48-211">在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。</span><span class="sxs-lookup"><span data-stu-id="04b48-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="04b48-212">在 [ **PIN 原則** ] 頁面上，按一下您要變更的 PIN 原則，按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="04b48-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="04b48-213">使用商務用 Skype Server 管理命令介面來刪除使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="04b48-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="04b48-214">若要刪除使用者或網站 PIN 原則，請使用 **get-cspinpolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04b48-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="04b48-215">下列命令會移除已在網站範圍設定的所有 PIN 碼原則。</span><span class="sxs-lookup"><span data-stu-id="04b48-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="04b48-216">若要這麼做，請使用 **Get-CsPinPolicy** Cmdlet 及 Filter 參數，傳回 Identity 以字元 "site：" 開頭的所有原則的集合。</span><span class="sxs-lookup"><span data-stu-id="04b48-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="04b48-217">然後，此集合會管線傳送至 **get-cspinpolicy** Cmdlet，以刪除集合中的每個原則：</span><span class="sxs-lookup"><span data-stu-id="04b48-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="04b48-218">如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Remove-get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="04b48-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

