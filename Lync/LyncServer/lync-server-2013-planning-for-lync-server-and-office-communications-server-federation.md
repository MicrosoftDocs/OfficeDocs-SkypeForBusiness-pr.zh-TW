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
ms.openlocfilehash: dad03a196b6909d2657b7dbc8463653bb004a310
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="acd01-102">規劃 Lync Server 2013 和 Office 通訊伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="acd01-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acd01-103">_**主題上次修改日期：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="acd01-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="acd01-104">Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間的同盟可支援對等與多方通訊。</span><span class="sxs-lookup"><span data-stu-id="acd01-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="acd01-105">對等交談可以呈報給多方交談，以允許點對點會議。</span><span class="sxs-lookup"><span data-stu-id="acd01-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="acd01-106">會議– Web 會議或音訊/視頻/視覺會議–可以排定在組織內的連絡人，以及您同盟的夥伴中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="acd01-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="acd01-107">同盟會先出現在 Microsoft Office Live 通訊伺服器2005中，並支援一種同盟、直接同盟。</span><span class="sxs-lookup"><span data-stu-id="acd01-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="acd01-108">直接同盟需要您知道同盟協力廠商的會話初始通訊協定（SIP）網域，以及夥伴的 Edge Server 的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="acd01-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="acd01-109">Live 通訊伺服器2005與 SP1 引進其他的同盟類型，同盟協力廠商所需要的網域名稱系統（DNS） SRV 記錄，以找出其 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="acd01-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="acd01-110">該版本的術語如下：</span><span class="sxs-lookup"><span data-stu-id="acd01-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="acd01-111">*開啟增強型同盟*：接受任何 SIP 功能變數名稱，並使用 DNS SRV 尋找合作夥伴 Edge Server</span><span class="sxs-lookup"><span data-stu-id="acd01-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="acd01-112">*增強型同盟*：將合作者的 SIP 功能變數名稱設定為組織的同盟夥伴，並使用 DNS SRV 尋找合作夥伴 Edge Server</span><span class="sxs-lookup"><span data-stu-id="acd01-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="acd01-113">*直接同盟*：設定夥伴的 SIP 功能變數名稱和 FQDN 至夥伴的 Edge Server</span><span class="sxs-lookup"><span data-stu-id="acd01-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="acd01-114">*伺服器允許清單*：接受任何網域，使用 DNS SRV 尋找主機服務提供者或公用立即訊息（IM）連線提供者的 Edge Server</span><span class="sxs-lookup"><span data-stu-id="acd01-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="acd01-115">Microsoft Office 通訊伺服器2007引進同盟類型的更新命名，以更好地定義每個同盟類型實際完成的專案：</span><span class="sxs-lookup"><span data-stu-id="acd01-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="acd01-116">開啟增強型同盟成為所謂的已*探索夥伴網域*</span><span class="sxs-lookup"><span data-stu-id="acd01-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="acd01-117">增強型同盟成為所謂的*允許夥伴網域*</span><span class="sxs-lookup"><span data-stu-id="acd01-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="acd01-118">直接同盟成為所謂的*允許夥伴伺服器*</span><span class="sxs-lookup"><span data-stu-id="acd01-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="acd01-119">伺服器允許清單被稱為「*裝載提供者*」和「*公用 IM 提供者*」</span><span class="sxs-lookup"><span data-stu-id="acd01-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="acd01-120">Microsoft Lync Server 2010 會依照 Microsoft Lync Online 2010 和 Microsoft Office 365 引進主機提供者較窄的定義，也就是遵守允許的協力廠商域同盟類型所定義的相同允許清單。</span><span class="sxs-lookup"><span data-stu-id="acd01-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="acd01-121">在 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間啟用同盟，即可使用 Edge server 和反向 proxy 來強制執行所定義的規則及允許的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="acd01-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="acd01-122">從規劃的觀點來看，與其他 Lync Server 同盟，Office 通訊伺服器需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="acd01-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="acd01-123">在拓撲產生器中啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="acd01-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="acd01-124">如需詳細資訊，請參閱部署主題設定[SIP 同盟、XMPP 同盟和 public 立即訊息 In Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="acd01-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="acd01-125">決定同盟網域探索的需求：</span><span class="sxs-lookup"><span data-stu-id="acd01-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="acd01-126">若要手動設定同盟，您必須具有夥伴之 Edge Server 和功能變數名稱的完整功能變數名稱（FQDN），或在 Lync Server 控制台、**同盟和外部存取**（ **SIP 同盟網域**）中輸入的線上功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="acd01-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="acd01-127">建立**新**原則或**編輯**現有原則，以允許或封鎖 FQDN 的網域。</span><span class="sxs-lookup"><span data-stu-id="acd01-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="acd01-128">當夥伴變更其 Edge Server 的 IP 位址時，同盟協力廠商的 Edge Server 的手動設定便很容易失敗。</span><span class="sxs-lookup"><span data-stu-id="acd01-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="acd01-129">針對<STRONG>新的 SIP 同盟網域</STRONG>，您必須提供 Microsoft Lync Online 和 microsoft 365 或 Office 365 的<STRONG>功能變數名稱（或 FQDN）</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="acd01-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="acd01-130">針對 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器，您也必須提供<STRONG>Access Edge service （FQDN）</STRONG></span><span class="sxs-lookup"><span data-stu-id="acd01-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="acd01-131">在已探索的夥伴同盟中，協力廠商可以探索您的 Edge Server，您可以在外部 DNS sipfederationtls 中建立 SRV 記錄 \_ 。 \_tcp.contoso.com –哪些指向您 Edge Server 的埠5061和主機（A）記錄</span><span class="sxs-lookup"><span data-stu-id="acd01-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="acd01-132">如果您要在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 裝置上支援 Microsoft Lync 行動用戶端，且使用推播通知服務或推播通知服務，您必須規劃 _sipfederationtls。 _tcp。</span><span class="sxs-lookup"><span data-stu-id="acd01-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="acd01-133">&lt;&gt;您擁有 Lync Mobile 用戶端之每個 sip 網域的 SIP 網域 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="acd01-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="acd01-134">Android 和 Nokia Symbian Lync Mobile 不會使用推播通知，也不會受到此項需求的制約。</span><span class="sxs-lookup"><span data-stu-id="acd01-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="acd01-135">設定外部使用者存取原則以支援同盟網域</span><span class="sxs-lookup"><span data-stu-id="acd01-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="acd01-136">開啟防火牆埠的會話初始通訊協定（SIP）、web 會議與音訊/視覺效果，以容納您要啟用的同盟或連絡人。</span><span class="sxs-lookup"><span data-stu-id="acd01-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="acd01-137">如需詳細資訊，請參閱：[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="acd01-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="acd01-138">下列資訊可協助您為與 Microsoft Lync Server 2013 和 Lync Server 2010 的同盟定義憑證、埠/通訊協定和 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="acd01-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="acd01-139">若您已規劃或部署 Microsoft Lync Server 2013 Edge server，則規劃憑證、防火牆及埠/通訊協定需求和 DNS 需求通常是直接的向前處理。</span><span class="sxs-lookup"><span data-stu-id="acd01-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="acd01-140">因為同盟是另一個使用現有 Edge Server 的功能，所以 Edge Server 規劃及部署一般會滿足規劃需求。</span><span class="sxs-lookup"><span data-stu-id="acd01-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="acd01-141">您應該使用下表來判斷是否符合您的需求，並對埠/通訊協定和 DNS 作出適當的變更。</span><span class="sxs-lookup"><span data-stu-id="acd01-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="acd01-142">如果您有一部 Edge server 集區，且與 Lync Server 2013 或 Lync Server 2010 合作夥伴同盟，您可以在 Edge server 的內部及外部方端上使用 DNS 負載平衡或硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="acd01-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="acd01-143">如果您與 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 同盟，硬體負載平衡會在 Edge Server 的事件中提供容錯移轉支援。</span><span class="sxs-lookup"><span data-stu-id="acd01-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="acd01-144">Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 不是 DNS 負載平衡感知。</span><span class="sxs-lookup"><span data-stu-id="acd01-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="acd01-145">夥伴 Edge Server 會與集區中的第一個 Edge Server 進行通訊，以進行回應。</span><span class="sxs-lookup"><span data-stu-id="acd01-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="acd01-146">如果該 Edge Server 失敗，通訊不會自動容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="acd01-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="acd01-147">憑證需求通常是透過規劃您所選 Edge Server 或集區 Edge Server 計畫的憑證所獲得。</span><span class="sxs-lookup"><span data-stu-id="acd01-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="acd01-148">本章節內容</span><span class="sxs-lookup"><span data-stu-id="acd01-148">In This Section</span></span>

  - [<span data-ttu-id="acd01-149">Lync Server 2013 中的憑證摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="acd01-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="acd01-150">Lync Server 2013 中的埠摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="acd01-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="acd01-151">Lync Server 2013 中的 DNS 摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="acd01-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acd01-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="acd01-152">See Also</span></span>


[<span data-ttu-id="acd01-153">在 Lync Server 2013 中設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="acd01-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="acd01-154">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="acd01-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="acd01-155">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</span><span class="sxs-lookup"><span data-stu-id="acd01-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="acd01-156">決定 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="acd01-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="acd01-157">在 Lync Server 2013 中管理組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="acd01-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="acd01-158">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="acd01-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="acd01-159">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="acd01-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

