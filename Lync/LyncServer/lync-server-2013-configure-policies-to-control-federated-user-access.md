---
title: Lync Server 2013：設定控制同盟使用者存取的原則
description: Lync Server 2013：設定控制同盟使用者存取的原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d69f35baa16086b0c4e93a2a015474f87e08b736
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548739"
---
# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="d9973-103">在 Lync Server 2013 中設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="d9973-103">Configure policies to control federated user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9973-104">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d9973-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d9973-105">當您設定原則以支援與同盟協力廠商的通訊時，這些原則會套用至同盟網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="d9973-105">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="d9973-106">您可以設定一或多個外部使用者存取原則，以控制同盟網域的使用者是否可以與您的 Lync Server 2013 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="d9973-106">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="d9973-107">若要控制同盟使用者存取，請在全域、網站與使用者層級設定相關原則。</span><span class="sxs-lookup"><span data-stu-id="d9973-107">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="d9973-108">套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="d9973-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d9973-109">Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。</span><span class="sxs-lookup"><span data-stu-id="d9973-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d9973-110">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="d9973-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9973-111">即便您並未對所屬組織啟用同盟，仍舊可以設定原則來控制同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="d9973-111">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="d9973-112">不過，只有當您為組織啟用同盟時，所設定的原則才會生效。</span><span class="sxs-lookup"><span data-stu-id="d9973-112">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="d9973-113">如需啟用同盟的詳細資訊，請參閱部署檔或作業檔中的 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A> 。</span><span class="sxs-lookup"><span data-stu-id="d9973-113">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="d9973-114">此外，如果您指定用來控制同盟使用者存取的使用者原則，此原則只適用于已啟用 Lync Server 2013 的使用者，且設定為使用原則。</span><span class="sxs-lookup"><span data-stu-id="d9973-114">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="d9973-115">若要設定原則以支援同盟網域使用者存取</span><span class="sxs-lookup"><span data-stu-id="d9973-115">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="d9973-116">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d9973-116">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9973-117">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d9973-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9973-118">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d9973-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9973-119">在左導覽列中，依序按一下 [外部使用者存取]\*\*\*\* 及 [外部存取原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9973-119">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="d9973-120">在 **[外部存取原則]** 頁面中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d9973-120">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d9973-121">若要設定全域原則以支援同盟使用者存取，依序按一下全域原則、**[編輯]** 以及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="d9973-121">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="d9973-p104">若要建立新的網站原則，請按一下 **[新增]**，然後按一下 **[站台原則]**。在 **[選取網站]** 的清單中按一下適當網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d9973-p104">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="d9973-p105">若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。在 **[新的外部存取原則]** 中，於 **[名稱]** 欄位中建立唯一名稱以代表使用者原則的涵蓋範圍 (例如，建立 **EnableFederatedUsers** 的使用者原則以啟用同盟網域使用者的通訊功能)。</span><span class="sxs-lookup"><span data-stu-id="d9973-p105">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="d9973-126">若要變更現有原則，按一下表中所列之適當原則，然後按一下 **[編輯]**，接著按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="d9973-126">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d9973-127">(選用) 如果您想要新增或編輯說明，請在 [說明]\*\*\*\* 中指定原則資訊。</span><span class="sxs-lookup"><span data-stu-id="d9973-127">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="d9973-128">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="d9973-128">Do one of the following:</span></span>
    
      - <span data-ttu-id="d9973-129">若要啟用原則的同盟使用者存取功能，請選取 **[啟用與同盟使用者的通訊]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d9973-129">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="d9973-130">若要停用原則的同盟使用者存取功能，請清除 **[啟用與同盟使用者的通訊]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d9973-130">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="d9973-131">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="d9973-131">Click **Commit**.</span></span>

<span data-ttu-id="d9973-132">若要啟用同盟使用者存取，您也必須在組織中啟用同盟支援。</span><span class="sxs-lookup"><span data-stu-id="d9973-132">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="d9973-133">如需詳細資訊，請參閱 [Enable or disable federation and PUBLIC IM connectivity In Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="d9973-133">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="d9973-134">如果這是使用者原則，則您也必須將該原則套用至您希望能與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="d9973-134">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="d9973-135">如需詳細資訊，請參閱 [將外部使用者存取原則指派給 Lync Server 2013 中啟用 Lync 功能的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d9973-135">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="d9973-136">使用 Windows PowerShell 設定現有原則，以支援同盟網域使用者的存取</span><span class="sxs-lookup"><span data-stu-id="d9973-136">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="d9973-137">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d9973-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9973-138">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d9973-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d9973-139">在 Lync Server 管理命令介面中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d9973-139">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="d9973-140">一個命令範例，會將適用於同盟使用者存取的全域原則設定為啟用、將 XMPP 網域存取設定為啟用、將遠端使用者存取設定為啟用、將公用提供者存取設定為啟用，以及為支援它的公用提供者授與使用音訊和視訊的能力：</span><span class="sxs-lookup"><span data-stu-id="d9973-140">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d9973-141">在 Lync Server 控制台中，參數「EnablePublicCloudAudioVideoAccess」沒有對應的選取範圍</span><span class="sxs-lookup"><span data-stu-id="d9973-141">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="d9973-142">使用 Windows PowerShell 建立新原則，以支援同盟網域使用者的存取</span><span class="sxs-lookup"><span data-stu-id="d9973-142">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="d9973-143">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d9973-143">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9973-144">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d9973-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d9973-145">在 Lync Server 管理命令介面中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d9973-145">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="d9973-146">建立新網站原則的範例：</span><span class="sxs-lookup"><span data-stu-id="d9973-146">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="d9973-147">使用 Windows PowerShell 刪除或重設原則，以支援同盟網域使用者的存取</span><span class="sxs-lookup"><span data-stu-id="d9973-147">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="d9973-148">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d9973-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9973-149">在 Lync Server 管理命令介面中輸入下列命令</span><span class="sxs-lookup"><span data-stu-id="d9973-149">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="d9973-p108">重設全域原則的範例 (全域原則只能移除它的設定。無法刪除原則)：</span><span class="sxs-lookup"><span data-stu-id="d9973-p108">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="d9973-152">若要移除網站原則，請輸入：</span><span class="sxs-lookup"><span data-stu-id="d9973-152">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="d9973-153">刪除網站原則 Redmond。</span><span class="sxs-lookup"><span data-stu-id="d9973-153">Deletes the site policy Redmond.</span></span> <span data-ttu-id="d9973-154">若要刪除名為 UserEAPPolicy 的使用者原則，請輸入：</span><span class="sxs-lookup"><span data-stu-id="d9973-154">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9973-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d9973-155">See Also</span></span>


[<span data-ttu-id="d9973-156">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="d9973-156">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="d9973-157">在 Lync Server 2013 中將外部使用者存取原則指派給啟用 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="d9973-157">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="d9973-158">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="d9973-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="d9973-159">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="d9973-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="d9973-160">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="d9973-160">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="d9973-161">新 Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="d9973-161">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="d9973-162">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="d9973-162">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="d9973-163">Remove-Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="d9973-163">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="d9973-164">授與 Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="d9973-164">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

