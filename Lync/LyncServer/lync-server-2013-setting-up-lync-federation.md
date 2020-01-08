---
title: Lync Server 2013：設定 Lync 同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6dc0a2aeb39c86db54d21a2c4be5ff6c5be599
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="d48e7-102">在 Lync Server 2013 中設定 Lync 同盟</span><span class="sxs-lookup"><span data-stu-id="d48e7-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d48e7-103">_**主題上次修改日期：** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="d48e7-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="d48e7-104">如果您已經部署了 Edge 伺服器或伺服器，新增同盟案例功能就會是直向。</span><span class="sxs-lookup"><span data-stu-id="d48e7-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="d48e7-105">如果您沒有設定邊緣伺服器，您必須先執行此動作。</span><span class="sxs-lookup"><span data-stu-id="d48e7-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="d48e7-106">如需詳細資訊，請參閱：在[Lync server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)在 [部署] 檔中的 [規劃檔] 和 [在[lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d48e7-107">如果您想要設定 XMPP 同盟、Lync 同盟或公用立即訊息連線的任何組合，您可以同時部署它們或一次一個。</span><span class="sxs-lookup"><span data-stu-id="d48e7-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="d48e7-108">如果您是透過拓撲產生器和 Lync Server 管理命令介面設定選項，請在 Edge 伺服器上執行部署嚮導，然後再針對其中一個、兩個或全部三個同盟類型設定選項之後，您就可以減少所需的步驟數。</span><span class="sxs-lookup"><span data-stu-id="d48e7-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="d48e7-109">在拓撲建立器和 [部署嚮導] 中設定 Lync 同盟</span><span class="sxs-lookup"><span data-stu-id="d48e7-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="d48e7-110">在前端伺服器上，開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="d48e7-111">展開 [邊緣池]，然後以滑鼠右鍵按一下 Edge 伺服器或 Edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="d48e7-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="d48e7-112">選取 [編輯屬性]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="d48e7-113">在 [編輯屬性] 底下的 [一般] 底下，選取 [針對此 Edge 池啟用同盟（埠5061）]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="d48e7-114">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-114">Click OK.</span></span>

3.  <span data-ttu-id="d48e7-115">按一下 [動作]，選取 [拓撲]，選取 [發佈]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="d48e7-116">發佈拓撲時出現提示時，請按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="d48e7-117">發佈完成後，請按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="d48e7-118">在邊緣伺服器上，開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="d48e7-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="d48e7-119">按一下 [安裝或更新 Lync Server 系統]，然後按一下 [設定] 或 [移除 Lync Server 元件]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="d48e7-120">再次按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-120">Click Run Again.</span></span>

5.  <span data-ttu-id="d48e7-121">在安裝程式 Lync Server 元件上，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="d48e7-122">[摘要] 畫面會在執行時顯示動作。</span><span class="sxs-lookup"><span data-stu-id="d48e7-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="d48e7-123">完成部署之後，按一下 [查看記錄] 以查看可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d48e7-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="d48e7-124">按一下 [完成] 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="d48e7-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d48e7-125">您可以選取這個選項，但貴組織中只有一個邊界池或邊緣伺服器可以在外部針對同盟進行發佈。</span><span class="sxs-lookup"><span data-stu-id="d48e7-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="d48e7-126">同盟使用者的所有存取權，包括公用立即訊息（IM）使用者，請流覽相同的邊緣池或單層伺服器。</span><span class="sxs-lookup"><span data-stu-id="d48e7-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="d48e7-127">例如，如果您的部署包含在紐約部署的邊緣池或單層伺服器，且在倫敦部署，且您在紐約的邊緣池或單一邊緣伺服器上啟用同盟支援，則聯盟使用者的信號流量將會透過紐約進行。[邊緣] 池或 [單一邊緣] 伺服器。</span><span class="sxs-lookup"><span data-stu-id="d48e7-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="d48e7-128">儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="d48e7-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="d48e7-129">設定與合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="d48e7-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="d48e7-130">若要設定成功的同盟與另一個 Microsoft Lync Server 2013、Lync Server 2010、Office 通訊伺服器 2007 R2 或 Office Communicator 2007，請從下表中選取同盟類型，並定義 DNS SRV 記錄、DNS 主機（A 或 AAAA）。IPv6）並設定適用于同盟類型的原則：</span><span class="sxs-lookup"><span data-stu-id="d48e7-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d48e7-131">同盟類型</span><span class="sxs-lookup"><span data-stu-id="d48e7-131">Federation type</span></span></th>
    <th><span data-ttu-id="d48e7-132">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="d48e7-132">DNS Records</span></span></th>
    <th><span data-ttu-id="d48e7-133">原則定義</span><span class="sxs-lookup"><span data-stu-id="d48e7-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="d48e7-134">筆記</span><span class="sxs-lookup"><span data-stu-id="d48e7-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d48e7-135">已發現合作夥伴網域</span><span class="sxs-lookup"><span data-stu-id="d48e7-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="d48e7-136">設定 _sipfederationtls 格式的 SRV 記錄。 _tcp。&lt;外部功能變數名稱，&gt;其中 SRV 記錄的埠值是 TCP 5061，而<strong>提供此服務的主機</strong>定義為 sip。</span><span class="sxs-lookup"><span data-stu-id="d48e7-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="d48e7-137">&lt;外部功能變數名稱&gt; -您的存取邊緣服務的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d48e7-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="d48e7-138">如需建立 SRV 記錄的詳細資料，請參閱<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定 edge 支援 DNS</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="d48e7-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="d48e7-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中啟用或停用探索同盟協力廠商</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="d48e7-141">先前版本會參照此同盟類型，即<strong>開啟增強型同盟</strong>。</span><span class="sxs-lookup"><span data-stu-id="d48e7-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="d48e7-142">此類型的同盟需要建立 SRV 記錄，並允許其他夥伴探索您的同盟。</span><span class="sxs-lookup"><span data-stu-id="d48e7-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d48e7-143">允許的合作夥伴網域</span><span class="sxs-lookup"><span data-stu-id="d48e7-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="d48e7-144">設定 _sipfederationtls 格式的 SRV 記錄。 _tcp。&lt;外部功能變數名稱，&gt;其中 SRV 記錄的埠值是 TCP 5061，而<strong>提供此服務的主機</strong>定義為 sip。</span><span class="sxs-lookup"><span data-stu-id="d48e7-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="d48e7-145">&lt;外部功能變數名稱&gt; -您的存取邊緣服務的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d48e7-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="d48e7-146">如需建立 SRV 記錄的詳細資料，請參閱<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定 edge 支援 DNS</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="d48e7-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="d48e7-148">先前版本稱為此同盟類型為 [<strong>增強聯盟</strong>]。</span><span class="sxs-lookup"><span data-stu-id="d48e7-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="d48e7-149">對於這種類型的同盟而言，SRV 記錄的建立是選用的，而且是允許其他夥伴探索您的同盟。</span><span class="sxs-lookup"><span data-stu-id="d48e7-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="d48e7-150">當然，這是<strong>開啟的增強聯盟</strong>，或已<strong>發現的合作夥伴網域</strong></span><span class="sxs-lookup"><span data-stu-id="d48e7-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d48e7-151">允許的合作夥伴伺服器</span><span class="sxs-lookup"><span data-stu-id="d48e7-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="d48e7-152">在原則中將 SIP 功能變數名稱與夥伴邊緣伺服器 FQDN 設定為同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="d48e7-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="d48e7-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="d48e7-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">在 Lync Server 2013 中針對允許的外部網域設定支援</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="d48e7-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">在 Lync Server 2013 中為封鎖的外部網域設定支援</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="d48e7-156">此同盟類型是單一關聯的定義，不允許發現其他同盟夥伴。</span><span class="sxs-lookup"><span data-stu-id="d48e7-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="d48e7-157">每個同盟夥伴都是明確設定的。</span><span class="sxs-lookup"><span data-stu-id="d48e7-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="d48e7-158">在舊版中，這稱為<strong>直接同盟</strong></span><span class="sxs-lookup"><span data-stu-id="d48e7-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d48e7-159">主機服務提供者和公用 IM 提供者</span><span class="sxs-lookup"><span data-stu-id="d48e7-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="d48e7-160">此類型同盟沒有定義任何特定的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="d48e7-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="d48e7-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="d48e7-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="d48e7-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d48e7-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="d48e7-164">此同盟類型定義您想要為使用者設定的服務與主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="d48e7-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="d48e7-165">典型用途包括公用 IM 提供者的設定，例如 Windows Live Messenger、Yahoo！</span><span class="sxs-lookup"><span data-stu-id="d48e7-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="d48e7-166">與 AOL，以及主機服務提供者（例如 Lync Online 和 Office 365）</span><span class="sxs-lookup"><span data-stu-id="d48e7-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="d48e7-167">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="d48e7-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d48e7-168">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="d48e7-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d48e7-169">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="d48e7-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="d48e7-170">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="d48e7-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d48e7-171">已公佈。</span><span class="sxs-lookup"><span data-stu-id="d48e7-171">has been announced.</span></span> <span data-ttu-id="d48e7-172">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="d48e7-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d48e7-173">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="d48e7-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d48e7-174">名單.</span><span class="sxs-lookup"><span data-stu-id="d48e7-174">Messenger.</span></span> <span data-ttu-id="d48e7-175">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="d48e7-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d48e7-176">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="d48e7-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d48e7-177">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="d48e7-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d48e7-178">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="d48e7-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="d48e7-179">定義並設定任何必要的 DNS 主機（A 或 AAAA IPv6）和 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="d48e7-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="d48e7-180">使用 Lync Server [控制台] 或使用 Lync Server 管理命令介面和適當的 Cmdlet 來定義及設定任何原則。</span><span class="sxs-lookup"><span data-stu-id="d48e7-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="d48e7-181">如需 Lync Server 管理命令介面 Cmdlet 的詳細資料，請參閱[Lync server 2013 中的同盟與外部存取 Cmdlet](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="d48e7-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d48e7-182">Lync 會議室系統（LRS）不會針對聯盟 Lync 合作夥伴中的召集人所傳送的會議顯示 [加入] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d48e7-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="d48e7-183">若要在 LRS 上顯示會議加入連結，傳送組織必須使用下列 Cmdlet 來啟用 TNEF：</span><span class="sxs-lookup"><span data-stu-id="d48e7-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="d48e7-184">請注意，這不是 LRS 的特定功能。</span><span class="sxs-lookup"><span data-stu-id="d48e7-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="d48e7-185">在這種情況下，outlook 和 Lync 也不會顯示聯結連結，因為 MAPI 屬性不會傳輸，但在 Outlook 案例中，使用者可以開啟會議邀請，然後按一下會議 URL。</span><span class="sxs-lookup"><span data-stu-id="d48e7-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="d48e7-186">當 TNEFEnabled 設定為 true 時，Exchange 2013 不會去除 MAPI 屬性（包括 OnlineMeetingExternalLink），而且會在提醒上顯示 [加入] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d48e7-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d48e7-187">請參閱</span><span class="sxs-lookup"><span data-stu-id="d48e7-187">See Also</span></span>


[<span data-ttu-id="d48e7-188">在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="d48e7-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="d48e7-189">管理 Lync Server 2013 的同盟與外部存取</span><span class="sxs-lookup"><span data-stu-id="d48e7-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

