---
title: Lync Server 2013：外部使用者存取的部署檢查表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c8831e8bd94040095fabd9fb335113b62b5287b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="f2592-102">Lync Server 2013 中外部使用者存取的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="f2592-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2592-103">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="f2592-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="f2592-104">您必須先部署 Microsoft Lync Server 2013 內部伺服器（包括前端池或標準版伺服器），才能部署周邊網路並實現外部使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="f2592-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="f2592-105">如果您打算在內部網路中部署選用的控制器，您也應該在部署邊緣伺服器之前先進行部署。</span><span class="sxs-lookup"><span data-stu-id="f2592-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="f2592-106">如需主管部署程式的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="f2592-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="f2592-107">Microsoft Lync Server 2013 包含協助規劃及部署內部伺服器與邊緣伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="f2592-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="f2592-108">拓撲完成後，將產生的拓撲定義發佈到您的生產環境。</span><span class="sxs-lookup"><span data-stu-id="f2592-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="f2592-109">若要這樣做，您必須是 [**網域管理員**] 群組和 [ **RTCUniversalServerAdmins** ] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f2592-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="f2592-110">**規劃工具**   Office 通訊伺服器 2007 R2 包含規劃工具和 Edge 規劃工具，您可以用來協助引導拓撲設計。</span><span class="sxs-lookup"><span data-stu-id="f2592-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="f2592-111">在 Lync Server 2010 中，這兩個工具已結合成單一規劃工具，其中有其他功能，例如收集已規劃的使用者數目、語音需求、外部使用者存取類型，以及同盟選項。</span><span class="sxs-lookup"><span data-stu-id="f2592-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="f2592-112">此外，您也可以規劃基礎結構的網路參數，例如 IP 位址、負載平衡器類型及其他周邊網路考慮。</span><span class="sxs-lookup"><span data-stu-id="f2592-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="f2592-113">**拓撲**   建立程式 Lync Server 2013 拓撲建立器可協助您定義拓撲與元件。</span><span class="sxs-lookup"><span data-stu-id="f2592-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="f2592-114">若要部署執行 Lync Server 2013 的伺服器，拓撲建立器是必要的。</span><span class="sxs-lookup"><span data-stu-id="f2592-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="f2592-115">[拓撲建立器] 會將結果發佈到中央管理儲存區，用來設定貴組織中所有執行 Lync Server 2013 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f2592-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="f2592-116">您無法在伺服器上安裝 Lync Server 2013，不需要使用拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="f2592-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="f2592-117">如果您是在規劃流程中設計邊緣拓撲，包括執行拓撲建立器以定義邊緣拓撲，您可以使用這些結果來啟動 Edge 伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="f2592-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="f2592-118">如果您之前沒有完成建立邊緣拓撲，或者想要變更您先前指定的資訊，您必須先完成執行拓撲建立器，然後再繼續進行其他部署步驟。</span><span class="sxs-lookup"><span data-stu-id="f2592-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="f2592-119">如需如何建立拓撲的詳細資料，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f2592-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="f2592-120">如需規劃工具與拓撲建立器的詳細資料，請參閱規劃檔中的[Lync Server 2013 規劃程式](lync-server-2013-beginning-the-planning-process.md)。</span><span class="sxs-lookup"><span data-stu-id="f2592-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="f2592-121">下表提供 Edge 伺服器部署程式的概覽。</span><span class="sxs-lookup"><span data-stu-id="f2592-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="f2592-122">若要查看部署外部使用者存取之前必須做出的規劃決定，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f2592-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f2592-123">下表中的資訊將重點放在新的部署上。</span><span class="sxs-lookup"><span data-stu-id="f2592-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="f2592-124">如果您已在 Lync Server 2010、Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007環境中部署 Edge 伺服器，請參閱<A href="migration.md">遷移</A>以取得遷移至 Lync Server 2013 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f2592-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="f2592-125">Office 通訊伺服器 2007 R2 之前的任何版本都不支援 [遷移]，包括 Office 通訊伺服器2007、[即時通訊伺服器 2005]，以及 [即時通訊伺服器] 2003。</span><span class="sxs-lookup"><span data-stu-id="f2592-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="f2592-126">為了加強邊緣伺服器的效能與安全性，以及協助部署，請在部署周邊網路和 Edge 伺服器時，套用下列最佳做法：</span><span class="sxs-lookup"><span data-stu-id="f2592-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="f2592-127">只有在貴組織內部已測試並驗證 Lync Server 2013 的操作後，才會部署 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f2592-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="f2592-128">我們建議您將 Edge 伺服器部署在工作組中，而非網域中。</span><span class="sxs-lookup"><span data-stu-id="f2592-128">We recommend that you deploy Edge Servers in a workgroup rather than a domain.</span></span> <span data-ttu-id="f2592-129">如此一來簡化安裝，並將 Active Directory 網域服務（AD DS）從周邊網路中保留。</span><span class="sxs-lookup"><span data-stu-id="f2592-129">Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network.</span></span> <span data-ttu-id="f2592-130">在周邊網路中尋找 AD DS 可能會帶來巨大的安全性風險。</span><span class="sxs-lookup"><span data-stu-id="f2592-130">Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="f2592-131">支援將 Edge 伺服器加入完全位於周邊網路的網域，但不建議這樣做。</span><span class="sxs-lookup"><span data-stu-id="f2592-131">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended.</span></span> <span data-ttu-id="f2592-132">在內部網域中，邊緣伺服器違反受信任的網路界限，且網際網路最小信任、周邊網路比網際網路更受信任，且內部網路最受信任。</span><span class="sxs-lookup"><span data-stu-id="f2592-132">An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted.</span></span> <span data-ttu-id="f2592-133">作為網域成員的邊緣伺服器會自動成為最受信任網路的一部分，但位於較不信任的網路（週邊）中。</span><span class="sxs-lookup"><span data-stu-id="f2592-133">An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="f2592-134">Edge 伺服器的部署程式</span><span class="sxs-lookup"><span data-stu-id="f2592-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2592-135">分</span><span class="sxs-lookup"><span data-stu-id="f2592-135">Phase</span></span></th>
<th><span data-ttu-id="f2592-136">步驟</span><span class="sxs-lookup"><span data-stu-id="f2592-136">Steps</span></span></th>
<th><span data-ttu-id="f2592-137">許可權</span><span class="sxs-lookup"><span data-stu-id="f2592-137">Permissions</span></span></th>
<th><span data-ttu-id="f2592-138">文件</span><span class="sxs-lookup"><span data-stu-id="f2592-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2592-139">建立適當的邊緣拓撲，並判斷適當的元件。</span><span class="sxs-lookup"><span data-stu-id="f2592-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2592-140">執行拓撲建立器以設定 Edge 伺服器設定，並建立和發佈拓撲，然後使用 Lync Server 管理命令介面匯出拓撲設定檔。</span><span class="sxs-lookup"><span data-stu-id="f2592-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f2592-141">[<strong>網域管理員</strong>] 群組和 [ <strong>RTCUniversalServerAdmins</strong> ] 或 [ <strong>CsAdmins</strong> ] 群組</span><span class="sxs-lookup"><span data-stu-id="f2592-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f2592-142">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但發佈拓朴需要<STRONG>網域系統管理員</STRONG>群組和 [ <STRONG>RTCUniversalServerAdmins</STRONG> ] 群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f2592-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="f2592-143">在部署檔的<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 中建立邊緣與控制器拓撲</a></span><span class="sxs-lookup"><span data-stu-id="f2592-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2592-144">準備進行設定。</span><span class="sxs-lookup"><span data-stu-id="f2592-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f2592-145">確保已滿足系統先決條件。</span><span class="sxs-lookup"><span data-stu-id="f2592-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="f2592-146">針對每個 Edge 伺服器上的內部和公開的網路介面，設定 IP 位址（IPv4 和 IPv6，如果是使用）。</span><span class="sxs-lookup"><span data-stu-id="f2592-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f2592-147">設定內部和外部 DNS 記錄（IPv4 和 IPv6 的主機 A 和 AAAA），包括在電腦上設定要部署為邊緣伺服器的 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="f2592-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f2592-148">可選建立及安裝公用憑證。</span><span class="sxs-lookup"><span data-stu-id="f2592-148">(Optional) Create and install public certificates.</span></span> <span data-ttu-id="f2592-149">取得憑證所需的時間取決於憑證授權單位（CA）所頒發的憑證。</span><span class="sxs-lookup"><span data-stu-id="f2592-149">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="f2592-150">如果您目前不執行此步驟，您必須在 Edge 伺服器安裝期間執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="f2592-150">If you do not perform this step at this point, you must do it during Edge Server installation.</span></span> <span data-ttu-id="f2592-151">在取得並安裝證書之前，無法啟動 Edge 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="f2592-151">The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="f2592-152">如果您的部署是要支援與 Windows Live、AOL 或 Yahoo！的通訊，請為公用 IM 連線提供支援</span><span class="sxs-lookup"><span data-stu-id="f2592-152">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo!</span></span> <span data-ttu-id="f2592-153">使用者.</span><span class="sxs-lookup"><span data-stu-id="f2592-153">users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f2592-154">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="f2592-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f2592-155">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="f2592-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f2592-156">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="f2592-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="f2592-157">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="f2592-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f2592-158">已公佈。</span><span class="sxs-lookup"><span data-stu-id="f2592-158">has been announced.</span></span> <span data-ttu-id="f2592-159">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="f2592-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="f2592-160">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="f2592-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f2592-161">名單.</span><span class="sxs-lookup"><span data-stu-id="f2592-161">Messenger.</span></span> <span data-ttu-id="f2592-162">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="f2592-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="f2592-163">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="f2592-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f2592-164">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="f2592-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f2592-165">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="f2592-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="f2592-166">針對 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 合作夥伴的 XMPP 及同盟支援提供支援，如果您的部署將使用這些</span><span class="sxs-lookup"><span data-stu-id="f2592-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="f2592-167">設定防火牆。</span><span class="sxs-lookup"><span data-stu-id="f2592-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f2592-168">視您的組織而定</span><span class="sxs-lookup"><span data-stu-id="f2592-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="f2592-169">在部署檔中<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">針對 Lync Server 2013 的周邊網路安裝伺服器的準備</a></span><span class="sxs-lookup"><span data-stu-id="f2592-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2592-170">設定反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="f2592-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2592-171">在周邊網路中設定反向 proxy （例如，針對 Microsoft Forefront 威脅管理閘道2010或 Microsoft Internet 安全性及加速（ISA） Server），取得必要的公用憑證，並將反向 proxy 伺服器上的 web 發佈規則。</span><span class="sxs-lookup"><span data-stu-id="f2592-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="f2592-172">如果您已規劃行動，且正在部署前端池或標準版伺服器上的行動服務，請準備行動服務的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="f2592-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f2592-173"><strong>管理員</strong>群組或反向 Proxy 管理員</span><span class="sxs-lookup"><span data-stu-id="f2592-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="f2592-174">在部署檔中<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</a></span><span class="sxs-lookup"><span data-stu-id="f2592-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2592-175">設定導演（選用）。</span><span class="sxs-lookup"><span data-stu-id="f2592-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f2592-176">可選在內部網路中安裝並設定一或多個控制器。</span><span class="sxs-lookup"><span data-stu-id="f2592-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f2592-177">[<strong>管理員</strong>] 群組</span><span class="sxs-lookup"><span data-stu-id="f2592-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="f2592-178">在部署檔的<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 中設定導演</a></span><span class="sxs-lookup"><span data-stu-id="f2592-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2592-179">設定邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="f2592-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f2592-180">安裝必備軟體。</span><span class="sxs-lookup"><span data-stu-id="f2592-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="f2592-181">將匯出的拓撲設定檔案傳輸到每個邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="f2592-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f2592-182">在每個邊緣伺服器上安裝 Lync Server 2013 軟體。</span><span class="sxs-lookup"><span data-stu-id="f2592-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f2592-183">設定邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="f2592-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="f2592-184">針對每個 Edge 伺服器要求並安裝證書。</span><span class="sxs-lookup"><span data-stu-id="f2592-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="f2592-185">啟動 Edge 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="f2592-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f2592-186">[<strong>管理員</strong>] 群組</span><span class="sxs-lookup"><span data-stu-id="f2592-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="f2592-187">在部署檔的<a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 中設定 Edge 伺服器</a></span><span class="sxs-lookup"><span data-stu-id="f2592-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2592-188">設定外部使用者存取的部署。</span><span class="sxs-lookup"><span data-stu-id="f2592-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f2592-189">使用 Lync Server [控制台] 來設定下列各項的支援（如果適用）：</span><span class="sxs-lookup"><span data-stu-id="f2592-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="f2592-190">媒體轉送</span><span class="sxs-lookup"><span data-stu-id="f2592-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="f2592-191">同盟路由</span><span class="sxs-lookup"><span data-stu-id="f2592-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="f2592-192">遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="f2592-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="f2592-193">使用 Lync Server、Office 通訊伺服器與即時通訊伺服器的同盟</span><span class="sxs-lookup"><span data-stu-id="f2592-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="f2592-194">公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f2592-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="f2592-195">XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="f2592-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="f2592-196">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="f2592-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="f2592-197">針對遠端使用者存取、同盟、公用 IM 連線、XMPP 與匿名使用者支援（如果適用的話），設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f2592-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f2592-198">指派給<strong>CSAdministrator</strong>角色的<strong>RTCUniversalServerAdmins</strong>群組或使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="f2592-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="f2592-199">在部署檔中設定<a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 中的外部使用者存取支援</a></span><span class="sxs-lookup"><span data-stu-id="f2592-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2592-200">驗證 Edge 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="f2592-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f2592-201">驗證服務器連線並從內部伺服器複製配置資料。</span><span class="sxs-lookup"><span data-stu-id="f2592-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="f2592-202">針對您的部署，確認外部使用者可以連線，包括遠端使用者、聯盟網域中的使用者、公用 IM 使用者以及匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="f2592-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="f2592-203">使用 Lync Server 遠端連線分析程式驗證設定和通訊<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="f2592-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="f2592-204">疑難排解配置和通訊問題</span><span class="sxs-lookup"><span data-stu-id="f2592-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f2592-205">針對已指派給<strong>CSAdministrator</strong>角色的複製、 <strong>RTCUniversalServerAdmins</strong>群組或使用者帳戶進行驗證</span><span class="sxs-lookup"><span data-stu-id="f2592-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="f2592-206">針對使用者連線驗證，您支援的每個外部使用者存取類型的使用者</span><span class="sxs-lookup"><span data-stu-id="f2592-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="f2592-207">遠端使用者</span><span class="sxs-lookup"><span data-stu-id="f2592-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="f2592-208">在部署檔中<a href="lync-server-2013-verifying-your-edge-deployment.md">驗證 Lync Server 2013 中的 edge 部署</a></span><span class="sxs-lookup"><span data-stu-id="f2592-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

