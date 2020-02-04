---
title: 規劃 Lync Server 和 Office 通訊伺服器同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 015f824ff2b8510559a7bd4910be76321d44d242
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="37f1f-102">規劃 Lync Server 2013 與 Office 通訊伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="37f1f-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37f1f-103">_**主題上次修改日期：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="37f1f-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="37f1f-104">Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間的同盟支援對等與多方通訊。</span><span class="sxs-lookup"><span data-stu-id="37f1f-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="37f1f-105">對等交談可以上報給多個參與方交談，以便進行即席會議。</span><span class="sxs-lookup"><span data-stu-id="37f1f-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="37f1f-106">[會議-網路會議] 或 [音訊/視覺會議]-可安排在您的組織內加入連絡人，以及與您聯盟的合作夥伴中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="37f1f-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="37f1f-107">同盟會先出現在 Microsoft Office Live 迅 Server 2005 中，並且支援一種類型的同盟（直接聯盟）。</span><span class="sxs-lookup"><span data-stu-id="37f1f-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="37f1f-108">直接同盟需要您知道同盟夥伴的會話初始通訊協定（SIP）網域以及合作夥伴邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="37f1f-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="37f1f-109">即時通訊伺服器2005（含 SP1）引進了其他聯合體類型，聯盟夥伴必須發佈所有需要的網域名稱系統（DNS） SRV 記錄，才能找出其 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="37f1f-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="37f1f-110">該版本的術語為：</span><span class="sxs-lookup"><span data-stu-id="37f1f-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="37f1f-111">*開啟加強聯盟*：接受任何 SIP 功能變數名稱，並使用 DNS SRV 來尋找合作夥伴邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="37f1f-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="37f1f-112">*增強聯盟*：將合作夥伴的 SIP 功能變數名稱設定為貴組織的同盟夥伴，並使用 DNS SRV 尋找合作夥伴邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="37f1f-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="37f1f-113">*直接聯盟*：將合作夥伴的 SIP 功能變數名稱和 FQDN 設定為合作夥伴的邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="37f1f-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="37f1f-114">*伺服器允許清單*：接受任何網域，請使用 DNS SRV 來尋找主機服務提供者或公用立即訊息（IM）連線提供者的邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="37f1f-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="37f1f-115">Microsoft Office 通訊伺服器2007引進了同盟類型的更新命名，以更好地定義每個同盟類型實際完成的專案：</span><span class="sxs-lookup"><span data-stu-id="37f1f-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="37f1f-116">開啟的加強聯盟稱為「已*探索夥伴網域*」</span><span class="sxs-lookup"><span data-stu-id="37f1f-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="37f1f-117">增強聯盟成為「*允許的夥伴網域*」</span><span class="sxs-lookup"><span data-stu-id="37f1f-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="37f1f-118">直接同盟成為「*允許的合作夥伴伺服器*」</span><span class="sxs-lookup"><span data-stu-id="37f1f-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="37f1f-119">伺服器允許清單已成為*託管提供者*和*公用 IM 提供者*</span><span class="sxs-lookup"><span data-stu-id="37f1f-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="37f1f-120">Microsoft Lync Server 2010 會根據 Microsoft Lync Online 2010 和 Microsoft Office 365，以較窄的方式定義主機服務提供者，同時也使其遵守允許的合作夥伴網域同盟類型所定義的同一個允許清單。</span><span class="sxs-lookup"><span data-stu-id="37f1f-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="37f1f-121">在 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間啟用同盟，就會使用 Edge 伺服器和反向代理伺服器來強制執行您定義的規則及允許的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="37f1f-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="37f1f-122">從規劃的角度來看，與其他 Lync 伺服器進行聯盟，Office 通訊伺服器需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="37f1f-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="37f1f-123">在拓撲建立器中啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="37f1f-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="37f1f-124">如需詳細資訊，請參閱[在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及公用立即訊息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)的部署主題。</span><span class="sxs-lookup"><span data-stu-id="37f1f-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="37f1f-125">判斷您的聯盟網域探索需求：</span><span class="sxs-lookup"><span data-stu-id="37f1f-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="37f1f-126">如需手動設定聯盟，您必須具備合作夥伴的邊緣伺服器和功能變數名稱的完整功能變數名稱（FQDN），或是在 Lync Server 控制台、**同盟及外部存取**、 **SIP 聯盟網域**中輸入的線上功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="37f1f-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="37f1f-127">建立**新**原則，或**編輯**現有的原則，以允許或封鎖 FQDN 的網域。</span><span class="sxs-lookup"><span data-stu-id="37f1f-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="37f1f-128">如果合作夥伴變更其 Edge 伺服器的 IP 位址，則聯盟夥伴的邊緣伺服器的手動設定就很容易失敗。</span><span class="sxs-lookup"><span data-stu-id="37f1f-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="37f1f-129">針對<STRONG>新的 SIP 聯盟網域</STRONG>，您必須提供 Microsoft Lync Online、microsoft Office 365 的<STRONG>功能變數名稱（或 FQDN）</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="37f1f-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="37f1f-130">針對 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器，您也必須提供<STRONG>存取邊緣服務（FQDN）</STRONG></span><span class="sxs-lookup"><span data-stu-id="37f1f-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="37f1f-131">針對已探索的合作夥伴同盟，合作夥伴可以在其中探索您的 Edge 伺服器，您可以在外部 DNS \_sipfederationtls 中建立 SRV 記錄。\_tcp.contoso.com –哪些指向邊緣伺服器的埠5061和主機（A）記錄</span><span class="sxs-lookup"><span data-stu-id="37f1f-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="37f1f-132">如果您在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 裝置上支援 Microsoft Lync Mobile 用戶端，且使用推播通知服務或推播通知服務，您必須規劃 _sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="37f1f-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="37f1f-133">&lt;您擁有&gt; Lync 行動用戶端之每個 SIP 網域的 SIP 網域 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="37f1f-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="37f1f-134">Android 和 Nokia Symbian Lync Mobile 不使用推播通知，也不受此需求。</span><span class="sxs-lookup"><span data-stu-id="37f1f-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="37f1f-135">設定外部使用者存取原則以支援聯盟網域</span><span class="sxs-lookup"><span data-stu-id="37f1f-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="37f1f-136">開啟 [會話初始化通訊協定] （SIP）、[web 會議] 和 [音訊/視覺] 的防火牆埠，以適應您要啟用的同盟或連絡人。</span><span class="sxs-lookup"><span data-stu-id="37f1f-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="37f1f-137">如需詳細資訊，請參閱：[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="37f1f-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="37f1f-138">下列資訊將協助您針對使用 Microsoft Lync Server 2013 和 Lync Server 2010 的同盟定義憑證、埠/通訊協定及 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="37f1f-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="37f1f-139">如果您已規劃或部署 Microsoft Lync Server 2013 Edge 伺服器，則規劃憑證、防火牆和埠/通訊協定需求以及 DNS 需求通常是一個直接的轉寄程式。</span><span class="sxs-lookup"><span data-stu-id="37f1f-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="37f1f-140">因為同盟是使用現有邊緣伺服器的其他功能，所以 Edge 伺服器規劃和部署通常都能滿足規劃需求。</span><span class="sxs-lookup"><span data-stu-id="37f1f-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="37f1f-141">您應該使用下清單格來判斷符合您的需求，並據此變更埠/通訊協定及 DNS。</span><span class="sxs-lookup"><span data-stu-id="37f1f-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="37f1f-142">如果您有一個 Edge 伺服器池，且正在與 Lync Server 2013 或 Lync Server 2010 合作夥伴進行聯盟，則您可以在邊緣伺服器的內部和外部方端上使用 DNS 負載平衡或硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="37f1f-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="37f1f-143">如果您是使用 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 進行聯盟，則硬體負載平衡將在 Edge 伺服器的事件中提供容錯移轉支援。</span><span class="sxs-lookup"><span data-stu-id="37f1f-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="37f1f-144">Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 不是 DNS 負載平衡感知。</span><span class="sxs-lookup"><span data-stu-id="37f1f-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="37f1f-145">夥伴邊緣伺服器會與您在池中回應的第一個邊緣伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="37f1f-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="37f1f-146">如果該 Edge 伺服器發生故障，通訊就不會自動進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="37f1f-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="37f1f-147">證書需求通常是透過針對您所選的邊緣伺服器或彙集邊緣伺服器方案的憑證規劃來達到。</span><span class="sxs-lookup"><span data-stu-id="37f1f-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37f1f-148">本節內容</span><span class="sxs-lookup"><span data-stu-id="37f1f-148">In This Section</span></span>

  - [<span data-ttu-id="37f1f-149">認證摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="37f1f-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="37f1f-150">埠摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="37f1f-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="37f1f-151">DNS 摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="37f1f-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="37f1f-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="37f1f-152">See Also</span></span>


[<span data-ttu-id="37f1f-153">在 Lync Server 2013 中設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="37f1f-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="37f1f-154">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="37f1f-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="37f1f-155">決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求</span><span class="sxs-lookup"><span data-stu-id="37f1f-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="37f1f-156">針對 Lync Server 2013 判定 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="37f1f-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="37f1f-157">在 Lync Server 2013 中管理組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="37f1f-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="37f1f-158">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="37f1f-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="37f1f-159">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="37f1f-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

