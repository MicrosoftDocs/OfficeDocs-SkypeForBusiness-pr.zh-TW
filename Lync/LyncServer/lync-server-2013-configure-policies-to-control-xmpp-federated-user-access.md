---
title: Lync Server 2013：設定原則以控制 XMPP 同盟使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ec90a1b079935713ce6f13e7b74763e7004dedf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="16205-102">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="16205-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16205-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="16205-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="16205-104">這是初步檔，可能會變更。</span><span class="sxs-lookup"><span data-stu-id="16205-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="16205-105">空白主題是以預留位置形式提供。</span><span class="sxs-lookup"><span data-stu-id="16205-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="16205-106">當您針對可擴展訊息和目前狀態通訊協定（XMPP）同盟合作夥伴支援策略時，這些原則會套用至 XMPP 聯盟網域的使用者，但不會套用至會話初始通訊協定（SIP）立即訊息（IM）服務提供者的使用者（例如，Windows Live）或 SIP 聯盟網域。</span><span class="sxs-lookup"><span data-stu-id="16205-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="16205-107">您可以針對每個 XMPP 聯盟網域設定**XMPP 聯盟夥伴**，以允許使用者新增連絡人並與之通訊。</span><span class="sxs-lookup"><span data-stu-id="16205-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="16205-108">XMPP 聯盟夥伴原則只能在單一範圍內提供，但不是定義為全域原則，充當全域原則。</span><span class="sxs-lookup"><span data-stu-id="16205-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="16205-109">若要為 XMPP 同盟夥伴定義全域、網站或使用者原則，您必須先建立及設定您所需範圍的外部存取原則，以設定原則範圍。</span><span class="sxs-lookup"><span data-stu-id="16205-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="16205-110">如需有關您可以針對外部存取與同盟設定的原則類型的詳細資訊，請參閱在作業檔中[管理 Lync Server 2013 的同盟和外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="16205-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16205-111">所有<STRONG>同盟和外部存取</STRONG>原則都是透過頻帶內配來套用。</span><span class="sxs-lookup"><span data-stu-id="16205-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="16205-112">在登入期間，適用于使用者、屬於網站或全域在範圍內的原則會傳遞給用戶端。</span><span class="sxs-lookup"><span data-stu-id="16205-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="16205-113">您可以設定原則來控制 XMPP 聯盟夥伴的存取權，即使您的組織未啟用 XMPP 聯盟也一樣。</span><span class="sxs-lookup"><span data-stu-id="16205-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="16205-114">不過，您設定的原則只有在您的組織部署、啟用並設定 XMPP 合作夥伴同盟時才會生效。</span><span class="sxs-lookup"><span data-stu-id="16205-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="16205-115">如需有關部署和設定 XMPP 合作夥伴同盟的詳細資訊，請參閱部署檔中的 Lync Server 2013 中的 [設定<A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">SIP 同盟]、[XMPP 聯盟] 和 [公用立即訊息</A>]。</span><span class="sxs-lookup"><span data-stu-id="16205-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="16205-116">此外，如果您在外部存取原則中指定使用者原則來控制 XMPP 聯盟夥伴，則原則只適用于已啟用 Lync Server 2013 且設定為使用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="16205-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="16205-117">編輯 XMPP 聯盟合作夥伴的全域原則</span><span class="sxs-lookup"><span data-stu-id="16205-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="16205-118">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="16205-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16205-119">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="16205-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="16205-120">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="16205-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="16205-121">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="16205-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="16205-122">在 [**外部存取原則**] 頁面上，針對全域原則執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="16205-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="16205-123">按一下全域原則，按一下 [**編輯**]，然後按一下 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="16205-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="16205-124">提供全域原則的描述（選用）。</span><span class="sxs-lookup"><span data-stu-id="16205-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="16205-125">選取 [**啟用與聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="16205-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="16205-126">選取 [**啟用與 XMPP 聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="16205-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="16205-127">按一下 [**認可**]，儲存您對全域原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="16205-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="16205-128">若要為 XMPP 聯盟合作夥伴建立網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="16205-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="16205-129">按一下 [**新增**]，然後按一下 [**網站原則**] 或 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="16205-129">Click **New**, and then click **Site policy** or **User policy**.</span></span> <span data-ttu-id="16205-130">在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="16205-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="16205-131">提供網站原則的描述（選用）。</span><span class="sxs-lookup"><span data-stu-id="16205-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="16205-132">在網站或使用者原則中，選取 [**啟用與聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="16205-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="16205-133">選取 [**啟用與 XMPP 聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="16205-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="16205-134">按一下 [**認可**]，儲存您對網站或使用者原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="16205-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="16205-135">編輯 XMPP 聯盟合作夥伴的現有原則</span><span class="sxs-lookup"><span data-stu-id="16205-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="16205-136">若要變更現有的原則，請在清單中選取適當的原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="16205-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="16205-137">變更或更新原則的描述（選用）。</span><span class="sxs-lookup"><span data-stu-id="16205-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="16205-138">選取或取消選取 [**啟用與聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="16205-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="16205-139">選取或取消選取 [**啟用與 XMPP 聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="16205-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="16205-140">按一下 [**認可**]，儲存您對原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="16205-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="16205-141">使用 Windows PowerShell 編輯 XMPP 聯盟夥伴的現有原則</span><span class="sxs-lookup"><span data-stu-id="16205-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="16205-142">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="16205-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16205-143">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="16205-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="16205-144">在 Lync Server 管理命令介面中輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="16205-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="16205-145">將同盟使用者存取權設定為 True （啟用），並將網域存取 XMPP 為 True （啟用）的全域原則的範例命令：</span><span class="sxs-lookup"><span data-stu-id="16205-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="16205-146">使用 Windows PowerShell 建立 XMPP 聯盟夥伴的網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="16205-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="16205-147">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="16205-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16205-148">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="16205-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="16205-149">在 Lync Server 管理命令介面中輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="16205-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="16205-150">將同盟使用者存取權的 [雷德蒙] 網站的網站原則設定為 [已啟用] 並 XMPP [網域存取] 的範例命令：</span><span class="sxs-lookup"><span data-stu-id="16205-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="16205-151">使用 Windows PowerShell 刪除 XMPP 聯盟夥伴的現有原則</span><span class="sxs-lookup"><span data-stu-id="16205-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="16205-152">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="16205-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16205-153">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="16205-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="16205-154">在 Lync Server 管理命令介面中輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="16205-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="16205-155">將會刪除使用者原則的範例命令：</span><span class="sxs-lookup"><span data-stu-id="16205-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="16205-156">將全域原則重設為預設值的範例命令：</span><span class="sxs-lookup"><span data-stu-id="16205-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16205-157">請參閱</span><span class="sxs-lookup"><span data-stu-id="16205-157">See Also</span></span>


[<span data-ttu-id="16205-158">在 Lync Server 2013 中將外部使用者存取原則指派給擁有 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="16205-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="16205-159">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="16205-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="16205-160">在 Lync Server 2013 中管理 XMPP 同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="16205-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="16205-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16205-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="16205-162">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16205-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="16205-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16205-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="16205-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16205-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="16205-165">授與 CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="16205-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

