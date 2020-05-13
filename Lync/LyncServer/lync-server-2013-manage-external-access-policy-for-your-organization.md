---
title: Lync Server 2013：管理組織的外部存取原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afc2b1599551cfc3b7ee7341e441946610166ba0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="98139-102">在 Lync Server 2013 中管理外部存取原則</span><span class="sxs-lookup"><span data-stu-id="98139-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98139-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="98139-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="98139-104">部署一或多部 Edge Server 之後，您必須為組織啟用將支援的外部存取類型。</span><span class="sxs-lookup"><span data-stu-id="98139-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="98139-p101">依預設，不會將任何原則設定為支援外部使用者存取 (包括遠端使用者存取、同盟網域使用者存取)，即使您已經為組織啟用外部使用者存取支援也一樣。若要控制外部使用者存取的使用，您必須設定一或多個原則，並為每個原則指定支援的外部使用者存取類型。您可以使用下列原則範圍來進行建立和設定。預設會建立全域原則，但無法加以刪除。</span><span class="sxs-lookup"><span data-stu-id="98139-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="98139-109">**全域原則**   全域原則是在您部署 Edge Server 時建立。</span><span class="sxs-lookup"><span data-stu-id="98139-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="98139-110">根據預設，全域原則中不會啟用任何外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="98139-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="98139-111">若要在全域層級支援外部使用者存取，您可以設定全域原則來支援一或多個類型的外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="98139-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="98139-112">全域原則適用於組織中的所有使用者，但是網站原則和使用者原則會覆寫全域原則。</span><span class="sxs-lookup"><span data-stu-id="98139-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="98139-113">如果您刪除全域原則，不會將它移除。</span><span class="sxs-lookup"><span data-stu-id="98139-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="98139-114">而是會將它重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="98139-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="98139-115">**網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者對特定網站存取的支援。</span><span class="sxs-lookup"><span data-stu-id="98139-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="98139-116">網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="98139-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="98139-117">例如，如果您在全域原則中啟用了遠端使用者存取，您可以指定網站原則以對特定網站停用遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="98139-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="98139-118">根據預設，網站原則會套用至該網站的所有使用者，但您可以指派使用者原則給個別使用者，以覆寫網站原則設定。</span><span class="sxs-lookup"><span data-stu-id="98139-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="98139-119">**使用者原則**   您可以建立並設定一或多個使用者原則，以限制遠端使用者對特定網站存取的支援。</span><span class="sxs-lookup"><span data-stu-id="98139-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="98139-120">使用者原則中的設定會覆寫全域與網站原則，但僅限於該使用者原則指派的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="98139-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="98139-121">例如，如果您在全域原則和網站原則中啟用了遠端使用者存取，您可以指定使用者原則以停用遠端使用者存取，然後將該使用者原則指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="98139-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="98139-122">如果您建立使用者原則，必須將其套用至一或多個使用者，該原則才能生效。</span><span class="sxs-lookup"><span data-stu-id="98139-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98139-123">套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="98139-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="98139-124">Lync Server 原則優先順序是：使用者原則（影響最大）會覆寫網站原則，然後網站原則會覆寫全域原則（影響最小）。</span><span class="sxs-lookup"><span data-stu-id="98139-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="98139-125">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="98139-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="98139-126">這些選項包括下列類型的外部存取：</span><span class="sxs-lookup"><span data-stu-id="98139-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="98139-127">**啟用與同盟使用者的通訊**   如果您想要支援使用者對同盟合作夥伴網域的存取，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="98139-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="98139-128">此設定會設定使用者與其他 SIP 同盟網域通訊的能力，以及託管的提供者，如 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="98139-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365.</span></span> <span data-ttu-id="98139-129">選取此設定可讓您選取允許與 XMPP 同盟網域進行通訊的選項。</span><span class="sxs-lookup"><span data-stu-id="98139-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="98139-p107">做為選項，如果您先選取 **[啟用與同盟使用者的通訊]**，則可選取 **[啟用與 XMPP 同盟協力廠商的通訊]**。XMPP 同盟是與使用 Extensible Messaging and Presence Protocol (XMPP) 的組織同盟。</span><span class="sxs-lookup"><span data-stu-id="98139-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98139-132">如果您啟用 XMPP 同盟，您也必須在拓撲產生器的 [Edge 集區] 設定區段中，選取 [部署<STRONG>XMPP 同盟</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="98139-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="98139-133">針對 XMPP 同盟進行設定會在 Edge Server 上部署 XMPP Proxy，並在前端伺服器上部署 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="98139-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="98139-134">**啟用與遠端使用者**     的通訊如果您想要在您的組織中的使用者（例如出差的遠端辦公和使用者）可以透過網際網路連線至 Lync Server，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="98139-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="98139-135">**啟用與公用使用者**     的通訊如果您希望內部使用者能夠與公用 IM 提供者連絡人（如 Windows Live、Yahoo \! 和北美線上（AOL）等）進行通訊，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="98139-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="98139-136">從2012年9月1日起，Microsoft Lync 公開 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="98139-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="98139-137">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="98139-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="98139-138">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="98139-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="98139-139">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="98139-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="98139-140">已宣告。</span><span class="sxs-lookup"><span data-stu-id="98139-140">has been announced.</span></span> <span data-ttu-id="98139-141">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="98139-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="98139-142">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="98139-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="98139-143">信使。</span><span class="sxs-lookup"><span data-stu-id="98139-143">Messenger.</span></span> <span data-ttu-id="98139-144">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="98139-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="98139-145">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="98139-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="98139-146">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="98139-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="98139-147">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="98139-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="98139-148">除了啟用外部使用者存取支援，您還必須設定相關原則以控制組織外部使用者存取的使用，接著再為使用者提供任何類型的外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="98139-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="98139-149">如需建立、設定及套用外部使用者存取原則的詳細資訊，請參閱<A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="98139-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="98139-150">**使用 Windows PowerShell Cmdlet 來檢視外部存取原則**</span><span class="sxs-lookup"><span data-stu-id="98139-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="98139-151">您可以使用 Lync Server 管理命令介面和**Get-CsExternalAccessPolicy** Cmdlet 來查看外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="98139-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="98139-152">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98139-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="98139-153">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="98139-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="98139-154">若要檢視關於您所有外部存取原則的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="98139-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="98139-155">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="98139-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="98139-156">本章節內容</span><span class="sxs-lookup"><span data-stu-id="98139-156">In This Section</span></span>

  - [<span data-ttu-id="98139-157">在 Lync Server 2013 中設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="98139-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="98139-158">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="98139-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="98139-159">在 Lync Server 2013 中設定控制遠端使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="98139-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="98139-160">在 Lync Server 2013 中設定原則以控制公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="98139-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="98139-161">在 Lync Server 2013 中將外部使用者存取原則指派給啟用 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="98139-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="98139-162">在 Lync Server 2013 中重設或刪除外部使用者存取原則</span><span class="sxs-lookup"><span data-stu-id="98139-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

