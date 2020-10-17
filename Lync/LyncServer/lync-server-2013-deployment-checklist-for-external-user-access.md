---
title: Lync Server 2013：外部使用者存取的部署檢查表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 010d4437f2eb90d596ace15cc392690dba5544d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522770"
---
# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="76b9e-102">Lync Server 2013 中外部使用者存取的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="76b9e-102">Deployment checklist for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76b9e-103">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="76b9e-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="76b9e-104">在您部署周邊網路並為外部使用者執行支援之前，您必須已部署 Microsoft Lync Server 2013 內部伺服器，包括前端集區或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="76b9e-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="76b9e-105">如果您打算在內部網路中部署選用的 Director，您也應該在部署 Edge Server 之前加以部署。</span><span class="sxs-lookup"><span data-stu-id="76b9e-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="76b9e-106">如需 Director 部署程式的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md) 。</span><span class="sxs-lookup"><span data-stu-id="76b9e-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="76b9e-107">Microsoft Lync Server 2013 包含一些工具，可協助您規劃及部署內部伺服器和 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="76b9e-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="76b9e-108">拓撲完成之後，將產生的拓撲定義發行至生產環境。</span><span class="sxs-lookup"><span data-stu-id="76b9e-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="76b9e-109">若要進行這項作業，您必須是 **Domain Admins** 群組及 **RTCUniversalServerAdmins** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="76b9e-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="76b9e-110">**規劃工具**    Office 通訊伺服器 2007 R2 包含規劃工具和 Edge 計畫工具，可讓您用來協助指導拓撲設計。</span><span class="sxs-lookup"><span data-stu-id="76b9e-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="76b9e-111">在 Lync Server 2010 中，這兩個工具合併成單一計畫工具，具有其他功能，例如收集已規劃的使用者計數、語音需求、外部使用者存取類型及同盟選項。</span><span class="sxs-lookup"><span data-stu-id="76b9e-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="76b9e-112">此外，還可以規劃基礎結構的網路參數，例如 IP 位址、負載平衡器類型，以及其他周邊網路考量。</span><span class="sxs-lookup"><span data-stu-id="76b9e-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="76b9e-113">**拓撲產生器**    Lync Server 2013 拓撲產生器可協助您定義拓撲和元件。</span><span class="sxs-lookup"><span data-stu-id="76b9e-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="76b9e-114">拓撲產生器對部署執行 Lync Server 2013 的伺服器而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="76b9e-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="76b9e-115">拓撲產生器會將結果發佈至中央管理存放區，以用於設定組織中所有執行 Lync Server 2013 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="76b9e-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="76b9e-116">您無法在不使用拓撲產生器的伺服器上安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="76b9e-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="76b9e-117">如果您在規劃程式期間設計了 edge 拓撲，包括執行拓撲產生器以定義 edge 拓撲，則可以使用這些結果來開始 Edge Server 部署。</span><span class="sxs-lookup"><span data-stu-id="76b9e-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="76b9e-118">如果您先前未完成建立 edge 拓撲，或想變更您先前所指定的資訊，必須先完成執行拓撲產生器，再繼續進行其他部署步驟。</span><span class="sxs-lookup"><span data-stu-id="76b9e-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="76b9e-119">如需如何建立拓撲的詳細資訊，請參閱 [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="76b9e-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="76b9e-120">如需規劃工具和拓撲產生器的詳細資訊，請參閱規劃檔中的 [開始進行 Lync Server 2013 的規劃程式](lync-server-2013-beginning-the-planning-process.md) 。</span><span class="sxs-lookup"><span data-stu-id="76b9e-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="76b9e-121">下表提供 Edge Server 部署程序的概觀。</span><span class="sxs-lookup"><span data-stu-id="76b9e-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="76b9e-122">若要查看部署外部使用者存取之前必須進行的規劃決策，請參閱 [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="76b9e-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="76b9e-123">下表的資訊以全新部署為主。</span><span class="sxs-lookup"><span data-stu-id="76b9e-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="76b9e-124">如果您已在 Lync Server 2010、Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007環境中部署 Edge Server，請參閱 <A href="migration.md">遷移</A> 以瞭解遷移至 Lync Server 2013 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="76b9e-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="76b9e-125">Office 通訊伺服器 2007 R2 之前的任何版本都不支援遷移，包括 Office 通訊伺服器2007、即時通訊伺服器2005和即時通訊伺服器2003。</span><span class="sxs-lookup"><span data-stu-id="76b9e-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="76b9e-126">為了提升 Edge Server 效能與安全性，以及協助部署順利進行，請在部署周邊網路和 Edge Server 時套用下列最佳作法：</span><span class="sxs-lookup"><span data-stu-id="76b9e-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="76b9e-127">只有在組織內已測試並驗證 Lync Server 2013 的作業之後，才部署 Edge server。</span><span class="sxs-lookup"><span data-stu-id="76b9e-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="76b9e-p108">建議您在工作群組 (而不是網域) 中部署 Edge Server。這麼做可簡化安裝程序，同時將 Active Directory 網域服務 (AD DS) 置於周邊網路之外。將 AD DS 設置在周邊網路中，可能帶來重大的安全風險。</span><span class="sxs-lookup"><span data-stu-id="76b9e-p108">We recommend that you deploy Edge Servers in a workgroup rather than a domain. Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network. Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="76b9e-p109">可支援將 Edge Server 加入完全位於周邊網路中的網域，但不建議使用。 Edge Server 作為內部網域的一部分違反了信任網路界限 (其中網際網路最不受信任，周邊網路比網際網路更受信任，而內部網路最受信任)。Edge Server 作為網域的成員會自動成為最受信任網路的一部分，卻位於較不受信任的網路中 (周邊網路)。</span><span class="sxs-lookup"><span data-stu-id="76b9e-p109">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended. An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted. An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="76b9e-134">Edge Server 部署程序</span><span class="sxs-lookup"><span data-stu-id="76b9e-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76b9e-135">階段</span><span class="sxs-lookup"><span data-stu-id="76b9e-135">Phase</span></span></th>
<th><span data-ttu-id="76b9e-136">步驟</span><span class="sxs-lookup"><span data-stu-id="76b9e-136">Steps</span></span></th>
<th><span data-ttu-id="76b9e-137">權限</span><span class="sxs-lookup"><span data-stu-id="76b9e-137">Permissions</span></span></th>
<th><span data-ttu-id="76b9e-138">文件</span><span class="sxs-lookup"><span data-stu-id="76b9e-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76b9e-139">建立適當的 Edge 拓撲，並決定適當的元件。</span><span class="sxs-lookup"><span data-stu-id="76b9e-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="76b9e-140">執行拓撲產生器以設定 Edge Server 設定，以及建立及發行拓撲，然後使用 Lync Server 管理命令介面來匯出拓撲設定檔。</span><span class="sxs-lookup"><span data-stu-id="76b9e-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="76b9e-141"><strong>Domain Admins</strong> 群組和 <strong>RTCUniversalServerAdmins</strong> 或 <strong>CsAdmins</strong> 群組</span><span class="sxs-lookup"><span data-stu-id="76b9e-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="76b9e-142">您可以使用本機使用者群組的成員帳戶來定義拓撲，但發行拓撲需要以 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組的成員帳戶進行。</span><span class="sxs-lookup"><span data-stu-id="76b9e-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="76b9e-143">在部署檔中的<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 中建立 edge 和 Director 拓撲</a></span><span class="sxs-lookup"><span data-stu-id="76b9e-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b9e-144">準備進行安裝。</span><span class="sxs-lookup"><span data-stu-id="76b9e-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="76b9e-145">確定已符合系統先決條件。</span><span class="sxs-lookup"><span data-stu-id="76b9e-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-146">在每部 Edge Server 上，設定內部與公開網路介面的 IP 位址 (IPv4 和 IPv6，如果使用的話)。</span><span class="sxs-lookup"><span data-stu-id="76b9e-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-147">設定內部與外部 DNS 記錄 (IPv4 和 IPv6 的主機 A 和 AAAA)，包括在要部署為 Edge Server 的電腦上設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="76b9e-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-p110">(選用) 建立並安裝公用憑證。取得憑證所需的時間，視發出憑證的憑證授權單位 (CA) 而定。如果您此時不執行這個步驟，也必須在 Edge Server 安裝期間執行。未取得並安裝憑證前，Edge Server Service 無法啟動。</span><span class="sxs-lookup"><span data-stu-id="76b9e-p110">(Optional) Create and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. If you do not perform this step at this point, you must do it during Edge Server installation. The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-p111">佈建公用 IM 連線的支援 (如果您的部署是要支援與 Windows Live、AOL 或 Yahoo! 使用者的通訊)。</span><span class="sxs-lookup"><span data-stu-id="76b9e-p111">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo! users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="76b9e-154">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="76b9e-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="76b9e-155">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="76b9e-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="76b9e-156">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="76b9e-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="76b9e-157">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="76b9e-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="76b9e-158">已宣告。</span><span class="sxs-lookup"><span data-stu-id="76b9e-158">has been announced.</span></span> <span data-ttu-id="76b9e-159">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="76b9e-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="76b9e-160">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="76b9e-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="76b9e-161">信使。</span><span class="sxs-lookup"><span data-stu-id="76b9e-161">Messenger.</span></span> <span data-ttu-id="76b9e-162">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="76b9e-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="76b9e-163">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="76b9e-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="76b9e-164">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="76b9e-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="76b9e-165">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="76b9e-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="76b9e-166">若您的部署會使用這些服務，請提供 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 合作夥伴的 XMPP 和同盟支援的支援</span><span class="sxs-lookup"><span data-stu-id="76b9e-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="76b9e-167">設定防火牆。</span><span class="sxs-lookup"><span data-stu-id="76b9e-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="76b9e-168">視組織而定</span><span class="sxs-lookup"><span data-stu-id="76b9e-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="76b9e-169">在部署檔中<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">準備安裝 Lync Server 2013 的周邊網路伺服器</a></span><span class="sxs-lookup"><span data-stu-id="76b9e-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b9e-170">設定反向 Proxy。</span><span class="sxs-lookup"><span data-stu-id="76b9e-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="76b9e-171">設定反向 proxy (例如，針對 Microsoft Forefront 威脅管理閘道2010或 Microsoft Internet Security and 加速 (ISA) Server Service Pack 1) 在周邊網路中，取得必要的公用憑證，並在反向 proxy 伺服器上設定網頁發行規則。</span><span class="sxs-lookup"><span data-stu-id="76b9e-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="76b9e-172">如果已為行動性做規劃，並且要在前端集區或 Standard Edition Server 上部署行動性服務，請準備好行動性服務的反向 Proxy。</span><span class="sxs-lookup"><span data-stu-id="76b9e-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="76b9e-173"><strong>Administrators</strong> 群組或反向 Proxy 管理員</span><span class="sxs-lookup"><span data-stu-id="76b9e-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="76b9e-174">在部署檔中<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</a></span><span class="sxs-lookup"><span data-stu-id="76b9e-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b9e-175">安裝 Director (選用)。</span><span class="sxs-lookup"><span data-stu-id="76b9e-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="76b9e-176">(選用) 在內部網路安裝並設定一個或多個 Director。</span><span class="sxs-lookup"><span data-stu-id="76b9e-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="76b9e-177"><strong>Administrators</strong> 群組</span><span class="sxs-lookup"><span data-stu-id="76b9e-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="76b9e-178">部署檔中的<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 設定 Director</a></span><span class="sxs-lookup"><span data-stu-id="76b9e-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b9e-179">設定 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="76b9e-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="76b9e-180">安裝必要軟體。</span><span class="sxs-lookup"><span data-stu-id="76b9e-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-181">將匯出的拓撲組態檔傳輸給每部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="76b9e-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-182">在每一部 Edge Server 上安裝 Lync Server 2013 軟體。</span><span class="sxs-lookup"><span data-stu-id="76b9e-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-183">設定 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="76b9e-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-184">為每一部 Edge Server 要求並安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="76b9e-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-185">啟動 Edge Server 服務。</span><span class="sxs-lookup"><span data-stu-id="76b9e-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="76b9e-186"><strong>Administrators</strong> 群組</span><span class="sxs-lookup"><span data-stu-id="76b9e-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="76b9e-187">部署檔中的<a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 設定 Edge</a> server</span><span class="sxs-lookup"><span data-stu-id="76b9e-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b9e-188">設定部署以進行外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="76b9e-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="76b9e-189">使用 Lync Server 控制台，設定下列每個 (的支援（如適用）) ：</span><span class="sxs-lookup"><span data-stu-id="76b9e-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="76b9e-190">媒體中繼</span><span class="sxs-lookup"><span data-stu-id="76b9e-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="76b9e-191">同盟路由</span><span class="sxs-lookup"><span data-stu-id="76b9e-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="76b9e-192">遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="76b9e-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="76b9e-193">與 Lync Server、Office 通訊伺服器和即時通訊伺服器的同盟</span><span class="sxs-lookup"><span data-stu-id="76b9e-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="76b9e-194">公共 IM 連線</span><span class="sxs-lookup"><span data-stu-id="76b9e-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="76b9e-195">XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="76b9e-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="76b9e-196">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="76b9e-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="76b9e-197">設定使用者帳戶以進行遠端使用者存取、同盟、公用 IM 連線、XMPP 和匿名使用者支援 (若適用)</span><span class="sxs-lookup"><span data-stu-id="76b9e-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="76b9e-198">指派給 <strong>CSAdministrator</strong> 角色的 <strong>RTCUniversalServerAdmins</strong> 群組或使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="76b9e-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="76b9e-199">在部署檔中設定<a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 中外部使用者存取的支援</a></span><span class="sxs-lookup"><span data-stu-id="76b9e-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b9e-200">驗證您的 Edge Server 設定。</span><span class="sxs-lookup"><span data-stu-id="76b9e-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="76b9e-201">驗證伺服器連線以及內部伺服器組態資料的複寫是否正確。</span><span class="sxs-lookup"><span data-stu-id="76b9e-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-202">驗證外部使用者 (包括遠端使用者、同盟網域的使用者、公用 IM 使用者和匿名使用者，視您的部署而定) 是否能連線。</span><span class="sxs-lookup"><span data-stu-id="76b9e-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="76b9e-203">使用 Lync Server Remote Connectivity Analyzer 驗證設定和通訊 <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="76b9e-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="76b9e-204">疑難排解設定及通訊問題</span><span class="sxs-lookup"><span data-stu-id="76b9e-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="76b9e-205">若為驗證複寫，為指派給 <strong>CSAdministrator</strong> 角色的 <strong>RTCUniversalServerAdmins</strong> 群組或使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="76b9e-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="76b9e-206">若為驗證使用者連線，則為您支援之每種外部使用者存取類型的使用者</span><span class="sxs-lookup"><span data-stu-id="76b9e-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="76b9e-207">遠端使用者</span><span class="sxs-lookup"><span data-stu-id="76b9e-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="76b9e-208">在部署檔中<a href="lync-server-2013-verifying-your-edge-deployment.md">驗證 Lync Server 2013 中的 edge 部署</a></span><span class="sxs-lookup"><span data-stu-id="76b9e-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

