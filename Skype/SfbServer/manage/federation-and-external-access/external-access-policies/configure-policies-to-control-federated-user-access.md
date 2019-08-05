---
title: 設定控制同盟使用者存取的原則
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '當您將原則設定為支援與同盟夥伴的通訊時, 這些原則會套用至同盟網域的使用者。 '
ms.openlocfilehash: 00552dfd6e2cb92d1bd50cb851bfb8324122c5ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188851"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="ba39e-103">在商務用 Skype Server 中設定控制聯盟使用者存取權的原則</span><span class="sxs-lookup"><span data-stu-id="ba39e-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="ba39e-104">當您將原則設定為支援與同盟夥伴的通訊時, 這些原則會套用至同盟網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="ba39e-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="ba39e-105">您可以設定一或多個外部使用者存取原則, 以控制聯盟網域的使用者是否可與您的商務用 Skype 伺服器使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="ba39e-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="ba39e-106">若要控制同盟使用者存取權, 您可以在全域、網站和使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="ba39e-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="ba39e-107">在一個策略層級套用的商務用 Skype 伺服器原則設定, 可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="ba39e-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="ba39e-108">商務用 Skype Server 原則優先順序為: 使用者原則 (最具影響力) 會覆寫網站原則, 然後網站原則會覆寫全域原則 (最小的影響)。</span><span class="sxs-lookup"><span data-stu-id="ba39e-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="ba39e-109">這表示原則設定越接近策略設定的物件, 就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="ba39e-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="ba39e-110">您可以設定控制聯盟使用者存取的原則, 即使您的組織未啟用同盟也一樣。</span><span class="sxs-lookup"><span data-stu-id="ba39e-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="ba39e-111">不過, 您設定的原則只會在您的組織啟用同盟時生效。</span><span class="sxs-lookup"><span data-stu-id="ba39e-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="ba39e-112">如需啟用同盟的詳細資料, 請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ba39e-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="ba39e-113">此外, 如果您指定要控制同盟使用者存取權的使用者原則, 原則只適用于已啟用商務用 Skype Server 且設定為使用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="ba39e-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="ba39e-114">若要設定受同盟網域使用者支援存取的原則</span><span class="sxs-lookup"><span data-stu-id="ba39e-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="ba39e-115">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ba39e-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba39e-116">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ba39e-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="ba39e-117">在左側導覽列中, 按一下 [**外部使用者存取**], 然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="ba39e-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="ba39e-118">在 [**外部存取原則**] 頁面上, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="ba39e-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ba39e-119">若要設定全域原則以支援同盟使用者存取, 請按一下全域原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ba39e-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="ba39e-120">若要建立新的網站原則, 請按一下 [**新增**], 然後按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="ba39e-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="ba39e-121">在 [**選取網站**] 中, 從清單中按一下適當的網站, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ba39e-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="ba39e-122">若要建立新的使用者原則, 請按一下 [**新增**], 然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="ba39e-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="ba39e-123">在**新的外部存取原則**中, 在 [name] (**名稱**) 欄位中建立唯一的名稱, 以指出使用者原則所涵蓋的內容 (例如, 為聯盟網域使用者啟用通訊的使用者原則**EnableFederatedUsers** )。</span><span class="sxs-lookup"><span data-stu-id="ba39e-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="ba39e-124">若要變更現有的原則, 請按一下表格中所列的適當原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ba39e-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ba39e-125">可選如果您想要新增或編輯描述, 請在 [**描述**] 中指定原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="ba39e-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="ba39e-126">請執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="ba39e-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="ba39e-127">若要針對原則啟用聯盟使用者存取, 請選取 [**啟用與同盟使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ba39e-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="ba39e-128">若要停用同盟使用者對原則的存取權, 請清除 [**啟用與聯盟使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ba39e-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="ba39e-129">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ba39e-129">Click **Commit**.</span></span>

<span data-ttu-id="ba39e-130">若要啟用聯盟使用者存取, 您也必須在組織中啟用同盟的支援。</span><span class="sxs-lookup"><span data-stu-id="ba39e-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="ba39e-131">如需詳細資訊, 請參閱[啟用或停用同盟與公用 IM](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="ba39e-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="ba39e-132">如果這是使用者原則, 您也必須將原則套用到您想要能夠與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="ba39e-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="ba39e-133">如需詳細資訊, 請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="ba39e-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="ba39e-134">使用 Windows PowerShell 設定現有的原則以支援由聯盟網域的使用者存取</span><span class="sxs-lookup"><span data-stu-id="ba39e-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="ba39e-135">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ba39e-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba39e-136">啟動名片伺服器管理命令介面的 Skype: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype**Server], 然後按一下 [商務用**skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ba39e-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="ba39e-137">在商務用 Skype Server Management 命令介面中輸入下列專案:</span><span class="sxs-lookup"><span data-stu-id="ba39e-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="ba39e-138">[商務用 Skype 伺服器] 控制台中的參數 "EnablePublicCloudAudioVideoAccess" 沒有對應的選取專案</span><span class="sxs-lookup"><span data-stu-id="ba39e-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="ba39e-139">使用 Windows PowerShell 建立新原則以支援由聯盟網域的使用者存取</span><span class="sxs-lookup"><span data-stu-id="ba39e-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="ba39e-140">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ba39e-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba39e-141">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server**], 然後按一下 [**商務用 skype server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="ba39e-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="ba39e-142">在商務用 Skype Server Management 命令介面中輸入下列專案:</span><span class="sxs-lookup"><span data-stu-id="ba39e-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="ba39e-143">建立新網站原則的範例:</span><span class="sxs-lookup"><span data-stu-id="ba39e-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="ba39e-144">使用 Windows PowerShell 刪除或重設原則, 以支援由聯盟網域的使用者存取</span><span class="sxs-lookup"><span data-stu-id="ba39e-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="ba39e-145">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ba39e-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba39e-146">在商務用 Skype Server Management 命令介面中輸入以下命令</span><span class="sxs-lookup"><span data-stu-id="ba39e-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="ba39e-147">重設全域原則 (全域原則只能移除其設定) 的範例。</span><span class="sxs-lookup"><span data-stu-id="ba39e-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="ba39e-148">無法刪除原則):</span><span class="sxs-lookup"><span data-stu-id="ba39e-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="ba39e-149">若要移除網站原則, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="ba39e-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="ba39e-150">刪除網站原則雷德蒙。</span><span class="sxs-lookup"><span data-stu-id="ba39e-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="ba39e-151">若要刪除名為 UserEAPPolicy 的使用者原則, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="ba39e-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="ba39e-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="ba39e-152">See Also</span></span>


[<span data-ttu-id="ba39e-153">啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="ba39e-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="ba39e-154">指派外部使用者存取原則</span><span class="sxs-lookup"><span data-stu-id="ba39e-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="ba39e-155">管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="ba39e-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="ba39e-156">管理貴組織的 SIP 聯盟提供者</span><span class="sxs-lookup"><span data-stu-id="ba39e-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="ba39e-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="ba39e-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="ba39e-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="ba39e-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="ba39e-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="ba39e-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="ba39e-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="ba39e-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="ba39e-161">授與 CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="ba39e-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

