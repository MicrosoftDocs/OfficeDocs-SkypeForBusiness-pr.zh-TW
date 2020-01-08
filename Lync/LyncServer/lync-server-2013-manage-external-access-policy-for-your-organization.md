---
title: Lync Server 2013：管理組織的外部使用存取原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="78d00-102">在 Lync Server 2013 中管理外部使用存取原則</span><span class="sxs-lookup"><span data-stu-id="78d00-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78d00-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="78d00-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="78d00-104">部署一或多個 Edge 伺服器之後，您必須啟用貴組織所支援的外部存取類型。</span><span class="sxs-lookup"><span data-stu-id="78d00-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="78d00-105">根據預設，沒有任何原則可設定支援外部使用者存取，包括遠端使用者存取、同盟使用者存取，即使您已為組織啟用外部使用者存取支援。</span><span class="sxs-lookup"><span data-stu-id="78d00-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="78d00-106">若要控制外部使用者存取的使用方式，您必須設定一或多個原則，以指定每個原則支援的外部使用者存取類型。</span><span class="sxs-lookup"><span data-stu-id="78d00-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="78d00-107">下列原則作用中可供建立及設定。</span><span class="sxs-lookup"><span data-stu-id="78d00-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="78d00-108">根據預設，會建立全域原則，但無法刪除。</span><span class="sxs-lookup"><span data-stu-id="78d00-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="78d00-109">**全域原則**   當您部署邊緣伺服器時，就會建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="78d00-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="78d00-110">根據預設，全域原則中不會啟用任何外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="78d00-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="78d00-111">若要支援全域層級的外部使用者存取，您可以將全域原則設定為支援一或多種類型的外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="78d00-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="78d00-112">全域原則會套用至貴組織中的所有使用者，但網站原則和使用者原則會覆寫全域原則。</span><span class="sxs-lookup"><span data-stu-id="78d00-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="78d00-113">如果您刪除全域原則，就不會將它移除。</span><span class="sxs-lookup"><span data-stu-id="78d00-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="78d00-114">相反地，您可以將其重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="78d00-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="78d00-115">**網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者存取特定網站的支援。</span><span class="sxs-lookup"><span data-stu-id="78d00-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="78d00-116">網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="78d00-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="78d00-117">例如，如果您在全域原則中啟用遠端使用者存取，您可以指定可停用特定網站之遠端使用者存取權的網站原則。</span><span class="sxs-lookup"><span data-stu-id="78d00-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="78d00-118">根據預設，網站原則會套用至該網站的所有使用者，但您可以將使用者原則指派給使用者，以覆寫網站原則設定。</span><span class="sxs-lookup"><span data-stu-id="78d00-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="78d00-119">**使用者原則**   您可以建立及設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取權的支援。</span><span class="sxs-lookup"><span data-stu-id="78d00-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="78d00-120">使用者原則中的設定會覆寫全域和網站原則，但只適用于指派使用者原則的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="78d00-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="78d00-121">例如，如果您在全域原則和網站原則中啟用遠端使用者存取，您可以指定可停用遠端使用者存取的使用者原則，然後將該使用者原則指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="78d00-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="78d00-122">如果您建立使用者原則，您必須先將其套用至一或多個使用者，才會生效。</span><span class="sxs-lookup"><span data-stu-id="78d00-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78d00-123">在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="78d00-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="78d00-124">Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="78d00-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="78d00-125">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="78d00-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="78d00-126">這些選項包括下列外部存取類型：</span><span class="sxs-lookup"><span data-stu-id="78d00-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="78d00-127">\*\*\*\*    如果您想要支援使用者存取聯盟夥伴網域，請啟用與同盟使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="78d00-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="78d00-128">此設定會設定使用者與其他 SIP 聯盟網域通訊的能力，以及 Microsoft Office 365 等主機提供者。</span><span class="sxs-lookup"><span data-stu-id="78d00-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="78d00-129">選取此設定可讓您選取允許與 XMPP 聯盟網域進行通訊的選項。</span><span class="sxs-lookup"><span data-stu-id="78d00-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="78d00-130">如果您先選取 [**啟用與聯盟使用者的通訊**]，您可以選取 [**啟用與 XMPP 聯盟夥伴的通訊**] 作為選項。</span><span class="sxs-lookup"><span data-stu-id="78d00-130">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**.</span></span> <span data-ttu-id="78d00-131">XMPP 同盟是與使用可擴展訊息和目前狀態通訊協定（XMPP）的組織進行同盟。</span><span class="sxs-lookup"><span data-stu-id="78d00-131">XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78d00-132">如果您啟用 XMPP 同盟，您也必須在拓撲建立器的 [Edge 池設定] 區段中，選取以部署<STRONG>XMPP 同盟</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="78d00-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="78d00-133">針對 XMPP 同盟進行設定，在 Edge 伺服器上部署 XMPP Proxy，並在前端伺服器上部署 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="78d00-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="78d00-134">\*\*\*\*    如果您想要在您的組織外的使用者（例如出差的遠端電腦）連線至 Lync Server，可以透過網際網路連線到遠端使用者，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="78d00-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="78d00-135">\*\*\*\*    如果您希望內部使用者能夠與公用 IM 提供者連絡人通訊（例如 Windows Live、Yahoo\!和美洲 Online （AOL）），請啟用此選項，以便與公用使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="78d00-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="78d00-136">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="78d00-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="78d00-137">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="78d00-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="78d00-138">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="78d00-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="78d00-139">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="78d00-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="78d00-140">已公佈。</span><span class="sxs-lookup"><span data-stu-id="78d00-140">has been announced.</span></span> <span data-ttu-id="78d00-141">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="78d00-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="78d00-142">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="78d00-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="78d00-143">名單.</span><span class="sxs-lookup"><span data-stu-id="78d00-143">Messenger.</span></span> <span data-ttu-id="78d00-144">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="78d00-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="78d00-145">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="78d00-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="78d00-146">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="78d00-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="78d00-147">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="78d00-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="78d00-148">除了啟用外部使用者存取支援之外，您也必須先設定原則，以控制在您的組織中使用外部使用者存取權，才能供使用者使用任何類型的外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="78d00-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="78d00-149">如需有關建立、設定及套用外部使用者存取原則的詳細資料，請參閱<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="78d00-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="78d00-150">**使用 Windows PowerShell Cmdlet 來查看外部存取原則**</span><span class="sxs-lookup"><span data-stu-id="78d00-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="78d00-151">您可以使用 Lync Server 管理命令介面和**CsExternalAccessPolicy** Cmdlet 來查看外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="78d00-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="78d00-152">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78d00-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="78d00-153">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="78d00-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="78d00-154">若要查看所有外部存取原則的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="78d00-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="78d00-155">這個命令會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="78d00-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="78d00-156">本節內容</span><span class="sxs-lookup"><span data-stu-id="78d00-156">In This Section</span></span>

  - [<span data-ttu-id="78d00-157">在 Lync Server 2013 中設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="78d00-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="78d00-158">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="78d00-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="78d00-159">在 Lync Server 2013 中設定原則以控制遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="78d00-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="78d00-160">在 Lync Server 2013 中設定原則以控制公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="78d00-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="78d00-161">在 Lync Server 2013 中將外部使用者存取原則指派給擁有 Lync 功能的使用者</span><span class="sxs-lookup"><span data-stu-id="78d00-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="78d00-162">在 Lync Server 2013 中重設或刪除外部使用者存取原則</span><span class="sxs-lookup"><span data-stu-id="78d00-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

