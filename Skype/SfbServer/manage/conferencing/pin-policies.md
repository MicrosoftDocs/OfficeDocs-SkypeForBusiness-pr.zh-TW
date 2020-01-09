---
title: 在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 摘要：瞭解如何在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則。
ms.openlocfilehash: f5ffef4af17a4337fe600b2059aab1ea106235ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992290"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="888af-103">在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="888af-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="888af-105">在貴組織中擁有 Active Directory 網域服務（AD DS）認證的商務用 Skype 伺服器使用者可以使用個人識別碼（PIN），將電話撥入式會議加入為已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="888af-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="888af-106">PIN 原則定義電話撥入式會議 Pin 如何運作的規則。</span><span class="sxs-lookup"><span data-stu-id="888af-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="888af-107">如果您想要為您的整個組織使用相同的 PIN 原則，您可以使用全域 PIN 原則，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="888af-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="888af-108">全域 PIN 原則會定義目錄林層級電話撥入式會議 Pin 的規則。</span><span class="sxs-lookup"><span data-stu-id="888af-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="888af-109">您可以修改全域 PIN 原則，但無法將其刪除。</span><span class="sxs-lookup"><span data-stu-id="888af-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="888af-110">如果您想要將特定原則套用至網站或特定使用者群組，您可以建立新的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="888af-111">PIN 原則適用于最窄範圍的使用者到最廣泛的範圍。</span><span class="sxs-lookup"><span data-stu-id="888af-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="888af-112">如果您將使用者層級的 PIN 原則指派給使用者，這些設定就會優先。</span><span class="sxs-lookup"><span data-stu-id="888af-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="888af-113">如果您沒有指派使用者原則，就會套用網站層級的 PIN 原則（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="888af-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="888af-114">如果沒有適用的使用者或網站原則，全域 PIN 原則就會提供預設設定。</span><span class="sxs-lookup"><span data-stu-id="888af-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="888af-115">查看 PIN 原則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="888af-115">View information about PIN policies</span></span>

<span data-ttu-id="888af-116">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面，查看 PIN 原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="888af-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="888af-117">使用商務用 Skype Server [控制台] 來查看 PIN 原則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="888af-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="888af-118">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="888af-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="888af-119">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="888af-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="888af-120">在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="888af-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="888af-121">在 [ **PIN 原則**] 頁面上，按一下您要查看的 PIN 原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="888af-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="888af-122">使用商務用 Skype Server Management Shell 來查看 PIN 原則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="888af-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="888af-123">若要查看 PIN 原則的相關資訊，請使用**CsPinPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="888af-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="888af-124">例如，下列命令會傳回具有身分識別網站的單一 PIN 原則的相關資訊：雷德蒙：</span><span class="sxs-lookup"><span data-stu-id="888af-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="888af-125">如需詳細資訊（包括完整的語法描述及參數清單），請參閱[CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="888af-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="888af-126">修改全域 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-126">Modify the global PIN policy</span></span>

<span data-ttu-id="888af-127">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來修改全域 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="888af-128">使用商務用 Skype Server [控制台] 修改全域電話撥入式會議 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="888af-129">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="888af-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="888af-130">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="888af-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="888af-131">在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="888af-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="888af-132">在 [ **PIN 原則**] 頁面上，按一下 [**全域**原則]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="888af-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="888af-133">在 [**編輯 Pin 原則**] 的 [**最小 pin 長度**] 中，輸入或選取您要允許的最小 pin 長度。</span><span class="sxs-lookup"><span data-stu-id="888af-133">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="888af-134">預設的最小長度為5位數。</span><span class="sxs-lookup"><span data-stu-id="888af-134">The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="888af-135">若要在封鎖使用者之前，能夠指定最大的登入嘗試次數，請選取 [**指定最大登入嘗試**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="888af-135">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="888af-136">如果您沒有選取此選項，則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="888af-136">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="888af-137">根據預設，會自動決定最大嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="888af-137">By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="888af-138">如果您已選取 [**指定最大登入嘗試**] 核取方塊，請在 [**最大登入次數**] 中，輸入或選取您要允許的最大登入嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="888af-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="888af-139">若要讓 Pin 到期，請選取 [**啟用 PIN 到期**日] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="888af-139">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="888af-140">如果您沒有選取此選項，針腳將永不過期。</span><span class="sxs-lookup"><span data-stu-id="888af-140">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="888af-141">根據預設，Pin 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="888af-141">By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="888af-142">如果您已選取 [**啟用 PIN 到期**日] 核取方塊，請在 **[PIN 到期日之後（天數）**] 中，輸入或選取 pin 到期前的天數。</span><span class="sxs-lookup"><span data-stu-id="888af-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="888af-143">在 [ **PIN 記錄計數**] 中，輸入使用者必須建立才能重複使用 pin 的 pin 數。</span><span class="sxs-lookup"><span data-stu-id="888af-143">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="888af-144">根據預設，使用者可以重複使用他們的 Pin。</span><span class="sxs-lookup"><span data-stu-id="888af-144">By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="888af-145">若要在 Pin 中允許通用位數（例如順序編號和重複的數位組），請選取 [**允許常見模式**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="888af-145">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="888af-146">如果您沒有選取此選項，則只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="888af-146">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="888af-147">根據預設，只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="888af-147">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="888af-148">出於安全性考慮，Microsoft 建議您不要允許常見模式。</span><span class="sxs-lookup"><span data-stu-id="888af-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="888af-149">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="888af-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="888af-150">使用商務用 Skype Server Management Shell 來修改全域電話撥入式會議 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="888af-151">若要修改全域電話撥入式會議 PIN 原則，請使用**CsPinPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="888af-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="888af-152">下列命令會變更在組織中設定為使用的所有 PIN 原則的 MinPasswordLength 值。</span><span class="sxs-lookup"><span data-stu-id="888af-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="888af-153">若要這樣做，命令會先呼叫**CsPinPolicy Cmdlet （** 不含任何參數），才能檢索所有現有的 PIN 原則集合。</span><span class="sxs-lookup"><span data-stu-id="888af-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="888af-154">然後，該集合會以管道傳送給**CsPinPolicy** Cmdlet，以修改集合中每個原則的 MinPasswordLength 屬性值：</span><span class="sxs-lookup"><span data-stu-id="888af-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="888af-155">如需詳細資訊（包括完整的語法描述及參數清單），請參閱[設定 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="888af-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="888af-156">建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="888af-157">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來建立使用者或網站 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="888af-158">使用商務用 Skype Server [控制台] 建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="888af-159">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="888af-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="888af-160">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="888af-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="888af-161">在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="888af-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="888af-162">在 [ **PIN 原則**] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="888af-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="888af-163">若要建立使用者層級原則，按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="888af-163">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="888af-164">在 [**新 PIN 原則**] 的 [**名稱**] 中，輸入描述原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="888af-164">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="888af-165">若要建立網站層級原則，按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="888af-165">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="888af-166">在 [**選取網站**搜尋] 欄位中，輸入您要為其建立原則之網站的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="888af-166">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="888af-167">在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="888af-167">In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="888af-168">在 [**描述**] 欄位中，輸入 PIN 原則的描述。</span><span class="sxs-lookup"><span data-stu-id="888af-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="888af-169">在 [**最小 pin 長度**] 欄位中，輸入或選取您要允許的最小 PIN 長度。</span><span class="sxs-lookup"><span data-stu-id="888af-169">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="888af-170">預設的最小長度為5位數。</span><span class="sxs-lookup"><span data-stu-id="888af-170">The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="888af-171">若要在封鎖使用者之前，能夠指定最大的登入嘗試次數，請選取 [**指定最大登入嘗試**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="888af-171">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="888af-172">如果您沒有選取此選項，則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="888af-172">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="888af-173">根據預設，會自動決定最大嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="888af-173">By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="888af-174">如果您已選取 [**指定最大登入嘗試**] 核取方塊，請在 [**最大登入次數**] 中，輸入或選取您要允許的最大登入嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="888af-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="888af-175">若要讓 Pin 到期，請選取 [**啟用 PIN 到期**日] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="888af-175">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="888af-176">如果您沒有選取此選項，針腳將永不過期。</span><span class="sxs-lookup"><span data-stu-id="888af-176">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="888af-177">根據預設，Pin 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="888af-177">By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="888af-178">如果您已選取 [**啟用 PIN 到期**日] 核取方塊，請在 **[PIN 到期日之後（天數）**] 中，輸入或選取 pin 到期前的天數。</span><span class="sxs-lookup"><span data-stu-id="888af-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="888af-179">在 [ **PIN 記錄計數**] 中，輸入使用者必須建立才能重複使用 pin 的 pin 數。</span><span class="sxs-lookup"><span data-stu-id="888af-179">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="888af-180">根據預設，使用者可以重複使用他們的 Pin。</span><span class="sxs-lookup"><span data-stu-id="888af-180">By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="888af-181">若要在 Pin 中允許通用位數（例如順序編號和重複的數位組），請選取 [**允許常見模式**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="888af-181">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="888af-182">如果您沒有選取此選項，則只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="888af-182">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="888af-183">根據預設，只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="888af-183">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="888af-184">出於安全性考慮，Microsoft 建議您不要允許常見模式。</span><span class="sxs-lookup"><span data-stu-id="888af-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="888af-185">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="888af-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="888af-186">使用商務用 Skype Server Management Shell 來建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="888af-187">若要建立使用者或網站 PIN 原則，請使用**CsPinPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="888af-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="888af-188">下列命令會建立具有身分識別網站：雷德蒙的新 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="888af-189">這個命令只包含一個選用參數 MinPasswordLength，可用於將 MinPasswordLength 屬性設為7。</span><span class="sxs-lookup"><span data-stu-id="888af-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="888af-190">所有剩餘的原則屬性都將使用預設值進行設定。</span><span class="sxs-lookup"><span data-stu-id="888af-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="888af-191">如需詳細資訊（包括完整的語法描述及參數清單），請參閱[新 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="888af-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="888af-192">修改使用者或網站的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="888af-193">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面來修改使用者或網站的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="888af-194">使用商務用 Skype Server [控制台] 修改使用者或網站的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="888af-195">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="888af-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="888af-196">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="888af-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="888af-197">在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="888af-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="888af-198">在 [ **PIN 原則**] 頁面上，按一下您要變更的固定原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="888af-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="888af-199">在 [**編輯 PIN 原則**] 中，修改任何原則設定（除了不能修改的原則名稱之外）。</span><span class="sxs-lookup"><span data-stu-id="888af-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="888af-200">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="888af-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="888af-201">使用商務用 Skype Server Management Shell 來修改使用者或網站的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="888af-202">若要修改電話撥入式會議 PIN 原則，請使用**CsPinPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="888af-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="888af-203">下列命令會修改指派給雷德蒙者網站的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="888af-204">在這種情況下，該命令會將 MinPasswordLength 屬性的值變更為 10;這表示新的 Pin 必須至少包含10個數字：</span><span class="sxs-lookup"><span data-stu-id="888af-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="888af-205">如需詳細資訊（包括完整的語法描述及參數清單），請參閱[設定 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="888af-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="888af-206">刪除使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="888af-207">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面，刪除使用者或網站的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="888af-208">使用商務用 Skype Server [控制台] 刪除使用者或網站的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="888af-209">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="888af-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="888af-210">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="888af-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="888af-211">在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="888af-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="888af-212">在 [ **PIN 原則**] 頁面上，按一下您要變更的固定原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="888af-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="888af-213">使用商務用 Skype Server Management 命令介面刪除使用者或網站的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="888af-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="888af-214">若要刪除使用者或網站 PIN 原則，請使用**CsPinPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="888af-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="888af-215">下列命令會移除已在網站範圍中設定的所有 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="888af-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="888af-216">若要這樣做，請使用**CsPinPolicy** Cmdlet 與 Filter 參數，以傳回以「site：」字元打頭之身分識別的所有原則集合。</span><span class="sxs-lookup"><span data-stu-id="888af-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="888af-217">然後將此集合輸送為**CsPinPolicy** Cmdlet，這會刪除集合中的每個原則：</span><span class="sxs-lookup"><span data-stu-id="888af-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="888af-218">如需詳細資訊（包括完整的語法描述及參數清單），請參閱[移除-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="888af-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

