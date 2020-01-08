---
title: Lync Server 2013：設定控制同盟使用者存取的原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fb009561c36395ee31a49986f2db0103cbe096b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="c3121-102">在 Lync Server 2013 中設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="c3121-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3121-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="c3121-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="c3121-104">當您將原則設定為支援與同盟夥伴的通訊時，這些原則會套用至同盟網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3121-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="c3121-105">您可以設定一或多個外部使用者存取原則，以控制聯盟網域的使用者是否可與您的 Lync Server 2013 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="c3121-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="c3121-106">若要控制同盟使用者存取權，您可以在全域、網站和使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="c3121-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="c3121-107">在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="c3121-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c3121-108">Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="c3121-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c3121-109">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="c3121-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3121-110">您可以設定控制聯盟使用者存取的原則，即使您的組織未啟用同盟也一樣。</span><span class="sxs-lookup"><span data-stu-id="c3121-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="c3121-111">不過，您設定的原則只會在您的組織啟用同盟時生效。</span><span class="sxs-lookup"><span data-stu-id="c3121-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="c3121-112">如需啟用同盟的詳細資料，請參閱在部署檔或操作檔中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="c3121-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="c3121-113">此外，如果您指定要控制同盟使用者存取的使用者原則，原則只會套用到已啟用 Lync Server 2013 的使用者，並設定為使用原則。</span><span class="sxs-lookup"><span data-stu-id="c3121-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c3121-114">若要設定受同盟網域使用者支援存取的原則</span><span class="sxs-lookup"><span data-stu-id="c3121-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c3121-115">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c3121-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3121-116">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c3121-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c3121-117">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c3121-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c3121-118">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="c3121-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="c3121-119">在 [**外部存取原則**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c3121-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c3121-120">若要設定全域原則以支援同盟使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c3121-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="c3121-121">若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="c3121-121">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="c3121-122">在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c3121-122">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="c3121-123">若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="c3121-123">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="c3121-124">在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容（例如，為聯盟網域使用者啟用通訊的使用者原則**EnableFederatedUsers** ）。</span><span class="sxs-lookup"><span data-stu-id="c3121-124">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="c3121-125">若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c3121-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c3121-126">可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3121-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="c3121-127">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c3121-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="c3121-128">若要針對原則啟用聯盟使用者存取，請選取 [**啟用與同盟使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c3121-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="c3121-129">若要停用同盟使用者對原則的存取權，請清除 [**啟用與聯盟使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c3121-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="c3121-130">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3121-130">Click **Commit**.</span></span>

<span data-ttu-id="c3121-131">若要啟用聯盟使用者存取，您也必須在組織中啟用同盟的支援。</span><span class="sxs-lookup"><span data-stu-id="c3121-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="c3121-132">如需詳細資訊，請參閱[在 Lync Server 2013 中啟用或停用同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="c3121-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="c3121-133">如果這是使用者原則，您也必須將原則套用到您想要能夠與同盟使用者共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3121-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="c3121-134">如需詳細資訊，請參閱[在 Lync Server 2013 中將外部使用者存取原則指派給 lync 啟用的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c3121-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c3121-135">使用 Windows PowerShell 設定現有的原則以支援由聯盟網域的使用者存取</span><span class="sxs-lookup"><span data-stu-id="c3121-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c3121-136">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c3121-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3121-137">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="c3121-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c3121-138">在 Lync Server 管理命令介面中輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="c3121-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="c3121-139">這個範例命令會將同盟使用者存取的全域原則設定為 [已啟用]、[XMPP 網域存取]、[啟用]、[公用提供者存取]，並授與支援它的公用提供者使用音訊與影片的功能：</span><span class="sxs-lookup"><span data-stu-id="c3121-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c3121-140">[Lync Server 控制台] 中的 [EnablePublicCloudAudioVideoAccess] 參數沒有對應的選取專案</span><span class="sxs-lookup"><span data-stu-id="c3121-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c3121-141">使用 Windows PowerShell 建立新原則以支援由聯盟網域的使用者存取</span><span class="sxs-lookup"><span data-stu-id="c3121-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c3121-142">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c3121-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3121-143">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="c3121-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c3121-144">在 Lync Server 管理命令介面中輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="c3121-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="c3121-145">建立新網站原則的範例：</span><span class="sxs-lookup"><span data-stu-id="c3121-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c3121-146">使用 Windows PowerShell 刪除或重設原則，以支援由聯盟網域的使用者存取</span><span class="sxs-lookup"><span data-stu-id="c3121-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c3121-147">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c3121-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c3121-148">在 Lync Server 管理命令介面中輸入以下命令</span><span class="sxs-lookup"><span data-stu-id="c3121-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="c3121-149">重設全域原則（全域原則只能移除其設定）的範例。</span><span class="sxs-lookup"><span data-stu-id="c3121-149">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="c3121-150">無法刪除原則）：</span><span class="sxs-lookup"><span data-stu-id="c3121-150">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="c3121-151">若要移除網站原則，請輸入：</span><span class="sxs-lookup"><span data-stu-id="c3121-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="c3121-152">刪除網站原則雷德蒙。</span><span class="sxs-lookup"><span data-stu-id="c3121-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="c3121-153">若要刪除名為 UserEAPPolicy 的使用者原則，請輸入：</span><span class="sxs-lookup"><span data-stu-id="c3121-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3121-154">請參閱</span><span class="sxs-lookup"><span data-stu-id="c3121-154">See Also</span></span>


[<span data-ttu-id="c3121-155">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="c3121-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="c3121-156">在 Lync Server 2013 中將外部使用者存取原則指派給擁有 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="c3121-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="c3121-157">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="c3121-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="c3121-158">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="c3121-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="c3121-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3121-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="c3121-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3121-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="c3121-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3121-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="c3121-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3121-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="c3121-163">授與 CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c3121-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

