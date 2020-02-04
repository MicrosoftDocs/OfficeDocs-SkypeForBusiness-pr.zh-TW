---
title: 規劃 SIP、XMPP 同盟及公用立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 994a1395363c28976c8bbfe325edae99e97cdc48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="825e9-102">在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="825e9-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="825e9-103">_**主題上次修改日期：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="825e9-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="825e9-104">您可以將 Edge 伺服器設定為允許您的內部與外部使用者存取合作夥伴組織或服務的連絡人。</span><span class="sxs-lookup"><span data-stu-id="825e9-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="825e9-105">同盟（因為這些合作夥伴協定是已知的）可將下列任何或所有專案提供給您組織中的連絡人，或是合作夥伴同盟中的連絡人：</span><span class="sxs-lookup"><span data-stu-id="825e9-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="825e9-106">立即訊息與顯示狀態</span><span class="sxs-lookup"><span data-stu-id="825e9-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="825e9-107">共同作業與會議，例如網路會議</span><span class="sxs-lookup"><span data-stu-id="825e9-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="825e9-108">音訊會議、視訊會議或兩者</span><span class="sxs-lookup"><span data-stu-id="825e9-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="825e9-109">在某些情況下，通訊（例如立即訊息（IM），以及在 Microsoft Lync Server 2013 與可擴展的訊息和目前狀態通訊協定（XMPP）連絡人之間的狀態，只支援對等使用者以及同盟中的連絡人partner.</span><span class="sxs-lookup"><span data-stu-id="825e9-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="825e9-110">在其他情況下（例如 Lync 伺服器），Lync server 2010 to Lync Server 2013 同盟，可邀請多個參與者加入交談。</span><span class="sxs-lookup"><span data-stu-id="825e9-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="825e9-111">Lync Server 和 Office 通訊伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="825e9-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="825e9-112">Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間的同盟支援對等與多方通訊。</span><span class="sxs-lookup"><span data-stu-id="825e9-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="825e9-113">對等交談可以上報給多個參與方交談，以便進行即席會議。</span><span class="sxs-lookup"><span data-stu-id="825e9-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="825e9-114">[會議-網路會議] 或 [音訊/視覺會議]-可安排在您的組織內加入連絡人，以及與您聯盟的合作夥伴中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="825e9-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="825e9-115">同盟會先出現在 Microsoft Office Live 迅 Server 2005 中，並且支援一種類型的同盟（直接聯盟）。</span><span class="sxs-lookup"><span data-stu-id="825e9-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="825e9-116">直接同盟需要您知道同盟夥伴的會話初始通訊協定（SIP）網域以及合作夥伴邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="825e9-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="825e9-117">即時通訊伺服器2005（含 SP1）引進了其他聯合體類型，聯盟夥伴必須發佈所有需要的網域名稱系統（DNS） SRV 記錄，才能找出其 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="825e9-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="825e9-118">該版本的術語為：</span><span class="sxs-lookup"><span data-stu-id="825e9-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="825e9-119">*開啟加強聯盟*：接受任何 SIP 功能變數名稱，並使用 DNS SRV 來尋找合作夥伴邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="825e9-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="825e9-120">*增強聯盟*：將合作夥伴的 SIP 功能變數名稱設定為貴組織的同盟夥伴，並使用 DNS SRV 尋找合作夥伴邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="825e9-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="825e9-121">*直接聯盟*：將合作夥伴的 SIP 功能變數名稱和 FQDN 設定為合作夥伴的邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="825e9-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="825e9-122">*伺服器允許清單*：接受任何網域，請使用 DNS SRV 來尋找主機服務提供者或公用立即訊息（IM）連線提供者的邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="825e9-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="825e9-123">Microsoft Office 通訊伺服器2007引進了同盟類型的更新命名，以更好地定義每個同盟類型實際完成的專案：</span><span class="sxs-lookup"><span data-stu-id="825e9-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="825e9-124">開啟的加強聯盟稱為「已*探索夥伴網域*」</span><span class="sxs-lookup"><span data-stu-id="825e9-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="825e9-125">增強聯盟成為「*允許的夥伴網域*」</span><span class="sxs-lookup"><span data-stu-id="825e9-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="825e9-126">直接同盟成為「*允許的合作夥伴伺服器*」</span><span class="sxs-lookup"><span data-stu-id="825e9-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="825e9-127">伺服器允許清單已成為*託管提供者*和*公用 IM 提供者*</span><span class="sxs-lookup"><span data-stu-id="825e9-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="825e9-128">Microsoft Lync Server 2010 會根據 Microsoft Lync Online 2010 和 Microsoft Office 365，以較窄的方式定義主機服務提供者，同時也使其遵守允許的合作夥伴網域同盟類型所定義的同一個允許清單。</span><span class="sxs-lookup"><span data-stu-id="825e9-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="825e9-129">在 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間啟用同盟，就會使用 Edge 伺服器和反向代理伺服器來強制執行您定義的規則及允許的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="825e9-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="825e9-130">從規劃的角度來看，與其他 Lync 伺服器進行聯盟，Office 通訊伺服器需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="825e9-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="825e9-131">在拓撲建立器中啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="825e9-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="825e9-132">如需詳細資訊，請參閱[在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及公用立即訊息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)的部署主題。</span><span class="sxs-lookup"><span data-stu-id="825e9-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="825e9-133">判斷您的聯盟網域探索需求：</span><span class="sxs-lookup"><span data-stu-id="825e9-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="825e9-134">如需手動設定聯盟，您必須具備合作夥伴的邊緣伺服器和功能變數名稱的完整功能變數名稱（FQDN），或是在 Lync Server 控制台、**同盟及外部存取**、 **SIP 聯盟網域**中輸入的線上功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="825e9-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="825e9-135">建立**新**原則，或**編輯**現有的原則，以允許或封鎖 FQDN 的網域。</span><span class="sxs-lookup"><span data-stu-id="825e9-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="825e9-136">如果合作夥伴變更其 Edge 伺服器的 IP 位址，則聯盟夥伴的邊緣伺服器的手動設定就很容易失敗。</span><span class="sxs-lookup"><span data-stu-id="825e9-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="825e9-137">針對<STRONG>新的 SIP 聯盟網域</STRONG>，您必須提供 Microsoft Lync Online、microsoft Office 365 的<STRONG>功能變數名稱（或 FQDN）</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="825e9-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="825e9-138">針對 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器，您也必須提供<STRONG>存取邊緣服務（FQDN）</STRONG></span><span class="sxs-lookup"><span data-stu-id="825e9-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="825e9-139">針對已探索的合作夥伴同盟，合作夥伴可以在其中探索您的 Edge 伺服器，您可以在外部 DNS \_sipfederationtls 中建立 SRV 記錄。\_tcp.contoso.com –哪些指向邊緣伺服器的埠5061和主機（A）記錄</span><span class="sxs-lookup"><span data-stu-id="825e9-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="825e9-140">如果您在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 裝置上支援 Microsoft Lync Mobile 用戶端，且使用推播通知服務或推播通知服務，您必須規劃 _sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="825e9-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="825e9-141">&lt;您擁有&gt; Lync 行動用戶端之每個 SIP 網域的 SIP 網域 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="825e9-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="825e9-142">Android 和 Nokia Symbian Lync Mobile 不使用推播通知，也不受此需求。</span><span class="sxs-lookup"><span data-stu-id="825e9-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="825e9-143">設定外部使用者存取原則以支援聯盟網域</span><span class="sxs-lookup"><span data-stu-id="825e9-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="825e9-144">開啟 [會話初始化通訊協定] （SIP）、[web 會議] 和 [音訊/視覺] 的防火牆埠，以適應您要啟用的同盟或連絡人。</span><span class="sxs-lookup"><span data-stu-id="825e9-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="825e9-145">如需詳細資訊，請參閱：[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="825e9-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="825e9-146">下列資訊將協助您針對使用 Microsoft Lync Server 2013 和 Lync Server 2010 的同盟定義憑證、埠/通訊協定及 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="825e9-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="825e9-147">如果您已規劃或部署 Microsoft Lync Server 2013 Edge 伺服器，則規劃憑證、防火牆和埠/通訊協定需求以及 DNS 需求通常是一個直接的轉寄程式。</span><span class="sxs-lookup"><span data-stu-id="825e9-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="825e9-148">因為同盟是使用現有邊緣伺服器的其他功能，所以 Edge 伺服器規劃和部署通常都能滿足規劃需求。</span><span class="sxs-lookup"><span data-stu-id="825e9-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="825e9-149">您應該使用下清單格來判斷符合您的需求，並據此變更埠/通訊協定及 DNS。</span><span class="sxs-lookup"><span data-stu-id="825e9-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="825e9-150">如果您有一個 Edge 伺服器池，且正在與 Lync Server 2013 或 Lync Server 2010 合作夥伴進行聯盟，則您可以在邊緣伺服器的內部和外部方端上使用 DNS 負載平衡或硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="825e9-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="825e9-151">如果您是使用 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 進行聯盟，則硬體負載平衡將在 Edge 伺服器的事件中提供容錯移轉支援。</span><span class="sxs-lookup"><span data-stu-id="825e9-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="825e9-152">Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 不是 DNS 負載平衡感知。</span><span class="sxs-lookup"><span data-stu-id="825e9-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="825e9-153">夥伴邊緣伺服器會與您在池中回應的第一個邊緣伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="825e9-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="825e9-154">如果該 Edge 伺服器發生故障，通訊就不會自動進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="825e9-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="825e9-155">證書需求通常是透過針對您所選的邊緣伺服器或彙集邊緣伺服器方案的憑證規劃來達到。</span><span class="sxs-lookup"><span data-stu-id="825e9-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="825e9-156">公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="825e9-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="825e9-157">公用立即訊息連線是一種聯盟類別，並設定為允許您的內部和外部 Lync Server 2013 使用者從下列任何專案新增連絡人：</span><span class="sxs-lookup"><span data-stu-id="825e9-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="825e9-158">信使連絡人</span><span class="sxs-lookup"><span data-stu-id="825e9-158">Messenger contacts</span></span>

  - <span data-ttu-id="825e9-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="825e9-159">Yahoo\!</span></span> <span data-ttu-id="825e9-160">聯絡</span><span class="sxs-lookup"><span data-stu-id="825e9-160">contacts</span></span>

  - <span data-ttu-id="825e9-161">美洲線上（AOL）連絡人</span><span class="sxs-lookup"><span data-stu-id="825e9-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="825e9-162">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（PIC USL）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="825e9-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="825e9-163">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="825e9-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="825e9-164">信使，直到服務關閉日期（確切日期仍會決定，但不會早于6月2013）。</span><span class="sxs-lookup"><span data-stu-id="825e9-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="825e9-165">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟所需的每個使用者、每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="825e9-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="825e9-166">名單.</span><span class="sxs-lookup"><span data-stu-id="825e9-166">Messenger.</span></span> <span data-ttu-id="825e9-167">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，不會更新的底層合約。</span><span class="sxs-lookup"><span data-stu-id="825e9-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="825e9-168">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="825e9-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="825e9-169">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="825e9-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="825e9-170">Skype 同盟將會新增到此清單，讓 Lync 使用者能夠透過 IM 和語音來取得成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="825e9-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="825e9-171">此同盟類別需要下列規劃考慮：</span><span class="sxs-lookup"><span data-stu-id="825e9-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="825e9-172">除了立即訊息之外，Windows Live Messenger 使用者也可以與 Lync Server 2013 使用者進行對等音訊/視覺通訊。</span><span class="sxs-lookup"><span data-stu-id="825e9-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="825e9-173">您的邊緣伺服器必須符合特定的埠和通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="825e9-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="825e9-174">如需詳細資訊，請參閱[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="825e9-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="825e9-175">Yahoo [立即訊息] 沒有任何獨特的需求，除了在提供同盟的一般邊緣伺服器規劃和部署中通常所使用的情況。</span><span class="sxs-lookup"><span data-stu-id="825e9-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="825e9-176">美洲線上要求指派給存取邊緣服務的 Edge 伺服器憑證具有用戶端增強型金鑰用法（EKU）。</span><span class="sxs-lookup"><span data-stu-id="825e9-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="825e9-177">可擴展訊息和目前狀態通訊協定（XMPP）同盟</span><span class="sxs-lookup"><span data-stu-id="825e9-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="825e9-178">舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和目前狀態通訊協定（XMPP）閘道，可將其部署為個別的伺服器角色，以允許與 XMPP 部署進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="825e9-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="825e9-179">在 Microsoft Lync Server 2013 中，您可以將 XMPP 功能部署為功能。</span><span class="sxs-lookup"><span data-stu-id="825e9-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="825e9-180">XMPP 功能是由兩個部分所安裝：在 Edge 伺服器上執行的 XMPP proxy，以及在前端伺服器上執行的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="825e9-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="825e9-181">XMPP 的部署與設定在[Lync Server 2013 中的 [部署外部使用者存取權](lync-server-2013-deploying-external-user-access.md)] 中，您打算在防火牆上定義埠和通訊協定規則、設定憑證的設定，以及新增 DNS 記錄，以規劃支援組織中的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="825e9-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="825e9-182">本節中的下列主題摘要說明為您的部署順利規劃 XMPP 同盟時所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="825e9-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="825e9-183">Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。</span><span class="sxs-lookup"><span data-stu-id="825e9-183">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="825e9-184">針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="825e9-184">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="825e9-185">託管在 survivable 分支裝置上的使用者不支援 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="825e9-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="825e9-186">這適用于查看目前狀態資訊和交換 IM 訊息。</span><span class="sxs-lookup"><span data-stu-id="825e9-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="825e9-187">下列主題包含針對支援的同盟情況類型定義憑證、防火牆埠及 DNS 專案的指導方針。</span><span class="sxs-lookup"><span data-stu-id="825e9-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="825e9-188">認證摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="825e9-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="825e9-189">埠摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="825e9-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="825e9-190">DNS 摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="825e9-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="825e9-191">請參閱</span><span class="sxs-lookup"><span data-stu-id="825e9-191">See Also</span></span>


[<span data-ttu-id="825e9-192">在 Lync Server 2013 中設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="825e9-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="825e9-193">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="825e9-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="825e9-194">決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求</span><span class="sxs-lookup"><span data-stu-id="825e9-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="825e9-195">針對 Lync Server 2013 判定 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="825e9-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="825e9-196">在 Lync Server 2013 中管理組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="825e9-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="825e9-197">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="825e9-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="825e9-198">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="825e9-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

