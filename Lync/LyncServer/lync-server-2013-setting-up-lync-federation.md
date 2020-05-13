---
title: Lync Server 2013：設定 Lync federation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b955def7b7648f274125353673d6973afb59b7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="f0231-102">在 Lync Server 2013 中設定 Lync 同盟</span><span class="sxs-lookup"><span data-stu-id="f0231-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0231-103">_**主題上次修改日期：** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="f0231-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="f0231-104">如果您已經部署一或多部 Edge Server，就可以直接新增同盟案例功能。</span><span class="sxs-lookup"><span data-stu-id="f0231-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="f0231-105">如果您尚未設定 Edge Server，則必須先進行設定。</span><span class="sxs-lookup"><span data-stu-id="f0231-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="f0231-106">如需詳細資訊，請參閱部署檔中的規劃檔及[部署 [Lync server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)] 中的 [在[lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0231-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0231-p102">如果您想要設定任何 XMPP 同盟、Lync 同盟或 Public Instant Messaging Connectivity 的組合，您可以同時部署它們，或者一次部署一個。如果您透過拓撲產生器和 Lync Server 管理命令介面設定選項，接著在設定一個、兩個或三個同盟類型的選項之後，於 Edge Server 上執行部署精靈，則您可以減少必要的步驟數。</span><span class="sxs-lookup"><span data-stu-id="f0231-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="f0231-109">在拓撲產生器和部署精靈中設定 Lync 同盟</span><span class="sxs-lookup"><span data-stu-id="f0231-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="f0231-p103">在前端伺服器上，開啟 [拓撲產生器]。展開 Edge 集區，然後按一下您的 Edge Server 或 Edge Server 集區。選取 [編輯內容]。</span><span class="sxs-lookup"><span data-stu-id="f0231-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="f0231-p104">在 [編輯內容] 的 [一般] 下方，選取 [啟用此 Edge 集區的同盟 (連接埠 5061)]。按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="f0231-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="f0231-p105">按一下 [動作]，然後依序選取 [拓撲] 和 [發行]。出現發行拓撲的提示時，按 [下一步]。完成發行時，按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="f0231-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="f0231-p106">在 Edge Server 上，開啟 [Lync Server 部署精靈]。按一下 [安裝或更新 Lync Server 系統]，然後按一下 [安裝或移除 Lync Server 元件]。按一下 [再執行一次]。</span><span class="sxs-lookup"><span data-stu-id="f0231-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="f0231-p107">在 [安裝 Lync Server 元件] 上，按 [下一步]。摘要畫面將顯示它們執行的動作。部署完成之後，按一下 [檢視記錄] 以檢視可用的記錄檔。按一下 [完成] 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="f0231-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f0231-p108">您可以選取此選項，但是只能將組織中的一個 Edge 集區或 Edge Server 發行到外部，以進行同盟。所有由同盟使用者 (包括公用立即訊息 (IM) 使用者) 進行的存取都會通過相同的 Edge 集區或單一 Edge Server。例如，如果您的部署範圍包括分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。</span><span class="sxs-lookup"><span data-stu-id="f0231-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="f0231-129">設定與協力廠商同盟</span><span class="sxs-lookup"><span data-stu-id="f0231-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="f0231-130">若要設定與其他 Microsoft Lync Server 2013、Lync Server 2010、Office 通訊伺服器 2007 R2 或 Office Communicator 2007 的成功同盟，請選取下表的同盟類型及定義 DNS SRV 記錄、DNS 主機（A 或 AAAA 用於 IPv6）及設定適用于同盟類型的原則：</span><span class="sxs-lookup"><span data-stu-id="f0231-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="f0231-131">同盟類型</span><span class="sxs-lookup"><span data-stu-id="f0231-131">Federation type</span></span></th>
    <th><span data-ttu-id="f0231-132">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="f0231-132">DNS Records</span></span></th>
    <th><span data-ttu-id="f0231-133">原則定義</span><span class="sxs-lookup"><span data-stu-id="f0231-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="f0231-134">附註</span><span class="sxs-lookup"><span data-stu-id="f0231-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="f0231-135">探索到的協力廠商網域</span><span class="sxs-lookup"><span data-stu-id="f0231-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="f0231-136">設定 _sipfederationtls 格式的 SRV 記錄。 _tcp。 &lt;外部功能變數名稱 &gt; ，其中 SRV 記錄的埠值為 TCP 5061，而<strong>提供此服務的主機</strong>是定義為 sip。</span><span class="sxs-lookup"><span data-stu-id="f0231-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="f0231-137">&lt;外部功能變數名稱 &gt; – Access Edge service 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f0231-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="f0231-138">如需建立 SRV 記錄的詳細資訊，請參閱<a href="lync-server-2013-configure-dns-for-edge-support.md">CONFIGURE DNS for edge support In Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="f0231-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="f0231-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="f0231-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f0231-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中啟用或停用同盟協力廠商的探索</a></span><span class="sxs-lookup"><span data-stu-id="f0231-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="f0231-p110">舊版將此類型的同盟稱為<strong>「開放式增強型同盟」</strong>。您必須針對此類型的同盟建立 SRV 記錄，以允許其他協力廠商探索您的同盟。</span><span class="sxs-lookup"><span data-stu-id="f0231-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="f0231-143">允許的協力廠商網域</span><span class="sxs-lookup"><span data-stu-id="f0231-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="f0231-144">設定 _sipfederationtls 格式的 SRV 記錄。 _tcp。 &lt;外部功能變數名稱 &gt; ，其中 SRV 記錄的埠值為 TCP 5061，而<strong>提供此服務的主機</strong>是定義為 sip。</span><span class="sxs-lookup"><span data-stu-id="f0231-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="f0231-145">&lt;外部功能變數名稱 &gt; – Access Edge service 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f0231-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="f0231-146">如需建立 SRV 記錄的詳細資訊，請參閱<a href="lync-server-2013-configure-dns-for-edge-support.md">CONFIGURE DNS for edge support In Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="f0231-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="f0231-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="f0231-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="f0231-148">先前版本稱為這類同盟為<strong>增強型同盟</strong>。</span><span class="sxs-lookup"><span data-stu-id="f0231-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="f0231-149">您可以選擇性地針對此類型的同盟建立 SRV 記錄，以允許其他協力廠商探索您的同盟。</span><span class="sxs-lookup"><span data-stu-id="f0231-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="f0231-150">當然，這就是<strong>「開放式增強型同盟」</strong>或<strong>「探索到的協力廠商網域」</strong>.</span><span class="sxs-lookup"><span data-stu-id="f0231-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="f0231-151">允許的協力廠商伺服器</span><span class="sxs-lookup"><span data-stu-id="f0231-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="f0231-152">將 SIP 功能變數名稱和協力廠商 Edge Server FQDN 設定為原則中的同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="f0231-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="f0231-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="f0231-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f0231-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">在 Lync Server 2013 中為允許的外部網域設定支援</a></span><span class="sxs-lookup"><span data-stu-id="f0231-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f0231-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">在 Lync Server 2013 中為封鎖的外部網域設定支援</a></span><span class="sxs-lookup"><span data-stu-id="f0231-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="f0231-p113">此同盟類型為一對一關聯性的定義，不允許其他同盟協力廠商進行探索。每個同盟協力廠商都已明確設定。在舊版中，這稱為<strong>「直接同盟」</strong></span><span class="sxs-lookup"><span data-stu-id="f0231-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="f0231-159">裝載提供者和公用 IM 提供者</span><span class="sxs-lookup"><span data-stu-id="f0231-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="f0231-160">未針對此類型的同盟定義任何特定的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="f0231-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="f0231-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></span><span class="sxs-lookup"><span data-stu-id="f0231-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f0231-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</a></span><span class="sxs-lookup"><span data-stu-id="f0231-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f0231-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0231-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="f0231-164">此同盟類型定義您要為使用者設定的服務和裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="f0231-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="f0231-165">一般用法包含針對像是 Windows Live Messenger、Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f0231-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="f0231-166">和 AOL，以及主控服務提供者（如 Lync Online 和 Microsoft 365）</span><span class="sxs-lookup"><span data-stu-id="f0231-166">and AOL, as well as hosting providers such as Lync Online and Microsoft 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="f0231-167">從2012年9月1日起，Microsoft Lync 公開 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="f0231-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f0231-168">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="f0231-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f0231-169">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="f0231-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="f0231-170">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="f0231-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f0231-171">已宣告。</span><span class="sxs-lookup"><span data-stu-id="f0231-171">has been announced.</span></span> <span data-ttu-id="f0231-172">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="f0231-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f0231-173">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="f0231-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f0231-174">信使。</span><span class="sxs-lookup"><span data-stu-id="f0231-174">Messenger.</span></span> <span data-ttu-id="f0231-175">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="f0231-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f0231-176">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="f0231-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f0231-177">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="f0231-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f0231-178">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="f0231-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="f0231-179">定義和設定任何必要的 DNS 主機 (適用於 IPv6 的 A 或 AAAA) 和 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="f0231-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="f0231-180">使用 Lync Server 控制台或使用 Lync Server 管理命令介面及適當的指令程式，來定義及設定任何原則。</span><span class="sxs-lookup"><span data-stu-id="f0231-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="f0231-181">如需 Lync Server 管理命令介面 Cmdlet 的詳細資訊，請參閱[Lync server 2013 中的同盟和外部訪問 Cmdlet](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="f0231-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0231-182">Lync 會議室系統（LRS）不會顯示同盟 Lync 合作夥伴中召集人所傳送之會議的 [加入] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f0231-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="f0231-183">若要在 LRS 上顯示會議加入連結，傳送組織必須使用下列 Cmdlet 來啟用 TNEF：</span><span class="sxs-lookup"><span data-stu-id="f0231-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="f0231-184">請注意，這不是 LRS 特定的。</span><span class="sxs-lookup"><span data-stu-id="f0231-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="f0231-185">在此情況下，outlook 和 Lync 也不會顯示聯接連結，因為 MAPI 屬性並未傳輸，但是在 Outlook 案例中，使用者可以開啟會議邀請，然後按一下會議 URL。</span><span class="sxs-lookup"><span data-stu-id="f0231-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="f0231-186">當 TNEFEnabled 設定為 true Exchange 2013 時，不會去除 MAPI 屬性包含 OnlineMeetingExternalLink，而且會在提醒上顯示 [加入] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="f0231-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0231-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f0231-187">See Also</span></span>


[<span data-ttu-id="f0231-188">在 Lync Server 2013 中規劃 SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="f0231-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="f0231-189">管理 Lync Server 2013 的同盟與外部存取</span><span class="sxs-lookup"><span data-stu-id="f0231-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

