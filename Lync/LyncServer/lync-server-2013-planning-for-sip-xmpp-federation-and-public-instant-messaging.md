---
title: 規劃 SIP、XMPP 同盟和公用立即訊息
description: 規劃 SIP、XMPP 同盟和公用立即訊息。
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
ms.openlocfilehash: 4c28c9c75310c884ea00117be2458384d408daae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564059"
---
# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="7eb4f-103">在 Lync Server 2013 中規劃 SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="7eb4f-103">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eb4f-104">_**主題上次修改日期：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="7eb4f-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="7eb4f-105">您可以設定 Edge Server，以允許您的內部和外部使用者存取夥伴組織或服務上的連絡人。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-105">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="7eb4f-106">這些合作夥伴合約稱為「同盟」，可提供貴組織的連絡人對合作夥伴同盟，或者合作夥伴同盟的連絡人對貴組織，下列任一或所有的功能：</span><span class="sxs-lookup"><span data-stu-id="7eb4f-106">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="7eb4f-107">立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="7eb4f-107">Instant messaging and presence</span></span>

  - <span data-ttu-id="7eb4f-108">共同作業和會議，例如：Web 會議</span><span class="sxs-lookup"><span data-stu-id="7eb4f-108">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="7eb4f-109">音訊會議、視訊會議，或兩者</span><span class="sxs-lookup"><span data-stu-id="7eb4f-109">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="7eb4f-110">在某些情況下，通訊（如立即訊息 (IM) 和目前狀態）與 Microsoft Lync Server 2013 及可延伸的訊息和顯示狀態通訊協定之間的狀態， (XMPP) 連絡人，僅支援您和同盟協力廠商的連絡人。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-110">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="7eb4f-111">在其他情況下，例如 Lync Server、Lync Server 2010 to Lync Server 2013 同盟，可邀請多位參與者加入交談。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-111">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="7eb4f-112">Lync Server 和 Office 通訊伺服器同盟</span><span class="sxs-lookup"><span data-stu-id="7eb4f-112">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="7eb4f-113">Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間的同盟可支援對等與多方通訊。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-113">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="7eb4f-114">對等交談可以呈報給多方交談，以允許點對點會議。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-114">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="7eb4f-115">會議– Web 會議或音訊/視頻/視覺會議–可以排定在組織內的連絡人，以及您同盟的夥伴中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-115">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="7eb4f-116">同盟會先出現在 Microsoft Office Live 通訊伺服器2005中，並支援一種同盟、直接同盟。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-116">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="7eb4f-117">直接同盟需要您知道同盟協力廠商的會話初始通訊協定 (SIP) 網域和夥伴的 Edge Server 的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-117">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="7eb4f-118">Live 通訊伺服器2005與 SP1 引進其他的同盟類型，所有必要的網域名稱系統都 (DNS) 可供同盟協力廠商用來找到其 Edge Server 的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-118">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="7eb4f-119">該版本的術語如下：</span><span class="sxs-lookup"><span data-stu-id="7eb4f-119">The terminology for that release was:</span></span>

  - <span data-ttu-id="7eb4f-120">*開啟增強型同盟*：接受任何 SIP 功能變數名稱，並使用 DNS SRV 尋找合作夥伴 Edge Server</span><span class="sxs-lookup"><span data-stu-id="7eb4f-120">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="7eb4f-121">*增強型同盟*：將合作者的 SIP 功能變數名稱設定為組織的同盟夥伴，並使用 DNS SRV 尋找合作夥伴 Edge Server</span><span class="sxs-lookup"><span data-stu-id="7eb4f-121">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="7eb4f-122">*直接同盟*：設定夥伴的 SIP 功能變數名稱和 FQDN 至夥伴的 Edge Server</span><span class="sxs-lookup"><span data-stu-id="7eb4f-122">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="7eb4f-123">*伺服器允許清單*：接受任何網域，使用 DNS SRV 尋找主機服務或公用立即訊息 (IM) 連線提供者的 Edge Server</span><span class="sxs-lookup"><span data-stu-id="7eb4f-123">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="7eb4f-124">Microsoft Office 通訊伺服器2007引進同盟類型的更新命名，以更好地定義每個同盟類型實際完成的專案：</span><span class="sxs-lookup"><span data-stu-id="7eb4f-124">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="7eb4f-125">開啟增強型同盟成為所謂的已 *探索夥伴網域*</span><span class="sxs-lookup"><span data-stu-id="7eb4f-125">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="7eb4f-126">增強型同盟成為所謂的 *允許夥伴網域*</span><span class="sxs-lookup"><span data-stu-id="7eb4f-126">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="7eb4f-127">直接同盟成為所謂的 *允許夥伴伺服器*</span><span class="sxs-lookup"><span data-stu-id="7eb4f-127">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="7eb4f-128">伺服器允許清單被稱為「*裝載提供者*」和「*公用 IM 提供者*」</span><span class="sxs-lookup"><span data-stu-id="7eb4f-128">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="7eb4f-129">Microsoft Lync Server 2010 會依照 Microsoft Lync Online 2010 和 Microsoft Office 365 引進主機提供者較窄的定義，也就是遵守允許的協力廠商域同盟類型所定義的相同允許清單。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-129">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="7eb4f-130">在 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間啟用同盟，即可使用 Edge server 和反向 proxy 來強制執行所定義的規則及允許的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-130">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="7eb4f-131">從規劃的觀點來看，與其他 Lync Server 同盟，Office 通訊伺服器需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="7eb4f-131">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="7eb4f-132">在拓撲產生器中啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-132">Enable federation in Topology Builder.</span></span> <span data-ttu-id="7eb4f-133">如需詳細資訊，請參閱部署主題設定 [SIP 同盟、XMPP 同盟和 public 立即訊息 In Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-133">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="7eb4f-134">決定同盟網域探索的需求：</span><span class="sxs-lookup"><span data-stu-id="7eb4f-134">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="7eb4f-135">若要手動設定同盟，您必須具有夥伴之 Edge Server 和功能變數名稱（或線上功能變數名稱）的功能變數名稱 (FQDN) ，該名稱會在 Lync Server 控制台、 **同盟及外部存取**、 **SIP 同盟網域**中輸入。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-135">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="7eb4f-136">建立 **新** 原則或 **編輯** 現有原則，以允許或封鎖 FQDN 的網域。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-136">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="7eb4f-137">當夥伴變更其 Edge Server 的 IP 位址時，同盟協力廠商的 Edge Server 的手動設定便很容易失敗。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-137">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="7eb4f-138">若為 <STRONG>新的 SIP 同盟網域</STRONG>，您必須提供 <STRONG>功能變數名稱 (或 FQDN) </STRONG> ，以供 Microsoft Lync Online 和 microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-138">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7eb4f-139">針對 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器，您也必須提供 <STRONG>Access Edge service (FQDN) </STRONG></span><span class="sxs-lookup"><span data-stu-id="7eb4f-139">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="7eb4f-140">在已探索的夥伴同盟中，協力廠商可以探索您的 Edge Server，您可以在外部 DNS sipfederationtls 中建立 SRV 記錄 \_ 。 \_tcp.contoso.com –哪些指向埠5061，而主機 (Edge Server 的) 記錄</span><span class="sxs-lookup"><span data-stu-id="7eb4f-140">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="7eb4f-141">如果您要在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 裝置上支援 Microsoft Lync 行動用戶端，且使用推播通知服務或推播通知服務，您必須規劃 _sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-141">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="7eb4f-142">&lt;&gt;您擁有 Lync Mobile 用戶端之每個 sip 網域的 SIP 網域 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-142">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="7eb4f-143">Android 和 Nokia Symbian Lync Mobile 不會使用推播通知，也不會受到此項需求的制約。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-143">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="7eb4f-144">設定外部使用者存取原則以支援同盟網域</span><span class="sxs-lookup"><span data-stu-id="7eb4f-144">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="7eb4f-145">針對會話初始通訊協定開啟防火牆埠 (SIP) 、web 會議與音訊/視覺效果，以容納您要啟用的同盟或連絡人。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-145">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="7eb4f-146">如需詳細資訊，請參閱： [判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="7eb4f-146">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="7eb4f-147">下列資訊可協助您為與 Microsoft Lync Server 2013 和 Lync Server 2010 的同盟定義憑證、埠/通訊協定和 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-147">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="7eb4f-148">若您已規劃或部署 Microsoft Lync Server 2013 Edge server，則規劃憑證、防火牆及埠/通訊協定需求和 DNS 需求通常是直接的向前處理。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-148">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="7eb4f-149">因為同盟是另一個使用現有 Edge Server 的功能，所以 Edge Server 規劃及部署一般會滿足規劃需求。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-149">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="7eb4f-150">您應該使用下表來判斷是否符合您的需求，並對埠/通訊協定和 DNS 作出適當的變更。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-150">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="7eb4f-151">如果您有一部 Edge server 集區，且與 Lync Server 2013 或 Lync Server 2010 合作夥伴同盟，您可以在 Edge server 的內部及外部方端上使用 DNS 負載平衡或硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-151">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="7eb4f-152">如果您與 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 同盟，硬體負載平衡會在 Edge Server 的事件中提供容錯移轉支援。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-152">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="7eb4f-153">Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 不是 DNS 負載平衡感知。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-153">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="7eb4f-154">夥伴 Edge Server 會與集區中的第一個 Edge Server 進行通訊，以進行回應。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-154">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="7eb4f-155">如果該 Edge Server 失敗，通訊不會自動容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-155">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="7eb4f-156">憑證需求通常是透過規劃您所選 Edge Server 或集區 Edge Server 計畫的憑證所獲得。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-156">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="7eb4f-157">公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="7eb4f-157">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="7eb4f-158">公用立即訊息連線是同盟的類別，設定為允許您的內部及外部 Lync Server 2013 使用者從下列任何專案新增連絡人：</span><span class="sxs-lookup"><span data-stu-id="7eb4f-158">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="7eb4f-159">信使連絡人</span><span class="sxs-lookup"><span data-stu-id="7eb4f-159">Messenger contacts</span></span>

  - <span data-ttu-id="7eb4f-160">雅虎\!</span><span class="sxs-lookup"><span data-stu-id="7eb4f-160">Yahoo\!</span></span> <span data-ttu-id="7eb4f-161">接觸</span><span class="sxs-lookup"><span data-stu-id="7eb4f-161">contacts</span></span>

  - <span data-ttu-id="7eb4f-162">北美線上 (AOL) 連絡人</span><span class="sxs-lookup"><span data-stu-id="7eb4f-162">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="7eb4f-163">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 (PIC USL) 已不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-163">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="7eb4f-164">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="7eb4f-164">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="7eb4f-165">信使直到服務關閉日期 (確切日期仍會決定，但不會早于2013年6月的) 。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-165">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="7eb4f-166">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的每一使用者、每月訂閱授權。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-166">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="7eb4f-167">信使。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-167">Messenger.</span></span> <span data-ttu-id="7eb4f-168">Microsoft 提供此服務的能力已因 Yahoo！的支援而產生，不會更新的基準合約。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-168">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="7eb4f-169">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-169">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7eb4f-170">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-170">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="7eb4f-171">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以透過 IM 和語音來抵達數百個人的人員。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-171">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="7eb4f-172">這個同盟類別需要下列規劃考慮：</span><span class="sxs-lookup"><span data-stu-id="7eb4f-172">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="7eb4f-173">Windows Live Messenger 使用者除了立即訊息之外，還可以與 Lync Server 2013 使用者進行對等音訊/視覺通訊。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-173">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="7eb4f-174">您的 Edge Server 必須符合特定埠和通訊協定的需求。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-174">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="7eb4f-175">如需詳細資訊，請參閱 [決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-175">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="7eb4f-176">在規劃及部署提供同盟之典型 Edge Server 的情況下，Yahoo 立即訊息沒有獨特的需求。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-176">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="7eb4f-177">北美洲線上要求指派給 Access Edge service 的 Edge Server 憑證具有用戶端增強型金鑰使用方式 (EKU) 。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-177">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="7eb4f-178">可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟</span><span class="sxs-lookup"><span data-stu-id="7eb4f-178">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="7eb4f-179">舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和顯示狀態通訊協定 (XMPP) 閘道，可部署為個別的伺服器角色，以允許與 XMPP 部署同盟。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-179">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="7eb4f-180">在 Microsoft Lync Server 2013 中，可以將 XMPP 功能部署為功能。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-180">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="7eb4f-181">XMPP 功能是以兩個部分安裝：在 Edge Server 上執行的 XMPP proxy，以及在前端伺服器上執行的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-181">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="7eb4f-182">XMPP 的部署和設定涵蓋在 [Lync Server 2013 的部署外部使用者存取](lync-server-2013-deploying-external-user-access.md) 中，您可以在防火牆上定義埠和通訊協定規則、憑證的設定，以及新增 DNS 記錄，以支援組織中的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-182">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="7eb4f-183">本節中的下列主題摘要說明為您的部署成功規劃 XMPP 同盟時所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-183">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="7eb4f-184">Lync Server 2013 的 XMPP 功能會經過測試，並受 Microsoft 支援，以進行與 Google 交談的立即訊息同盟。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-184">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="7eb4f-185">對於任何其他 XMPP 系統，請聯繫協力廠商廠商，以確認其支援與 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-185">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="7eb4f-186">在 survivable branch 裝置上的使用者不支援 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-186">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="7eb4f-187">這適用于查看顯示狀態資訊和交換 IM 郵件。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-187">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="7eb4f-188">在下列主題中，會包含針對支援的同盟案例類型定義憑證、防火牆埠和 DNS 專案的指導方針。</span><span class="sxs-lookup"><span data-stu-id="7eb4f-188">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="7eb4f-189">Lync Server 2013 中的憑證摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="7eb4f-189">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="7eb4f-190">Lync Server 2013 中的埠摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="7eb4f-190">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="7eb4f-191">Lync Server 2013 中的 DNS 摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="7eb4f-191">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7eb4f-192">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7eb4f-192">See Also</span></span>


[<span data-ttu-id="7eb4f-193">在 Lync Server 2013 中設定控制同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="7eb4f-193">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="7eb4f-194">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="7eb4f-194">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="7eb4f-195">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</span><span class="sxs-lookup"><span data-stu-id="7eb4f-195">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="7eb4f-196">決定 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="7eb4f-196">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="7eb4f-197">在 Lync Server 2013 中管理組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="7eb4f-197">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="7eb4f-198">在 Lync Server 2013 中管理組織的 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="7eb4f-198">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="7eb4f-199">在 Lync Server 2013 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="7eb4f-199">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

