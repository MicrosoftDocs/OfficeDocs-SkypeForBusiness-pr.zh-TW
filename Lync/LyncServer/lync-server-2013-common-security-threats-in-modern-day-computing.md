---
title: 新式天運算 Lync Server 2013： 常見安全性威脅
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9869f3c903aa7b16529ed72c499a1cb41254634
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="66f5a-102">新式天運算的常見安全性威脅</span><span class="sxs-lookup"><span data-stu-id="66f5a-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66f5a-103">_**上次修改主題：** 2013年-09-10_</span><span class="sxs-lookup"><span data-stu-id="66f5a-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="66f5a-104">由於 Lync Server 2013 是企業層級通訊系統，您應該要知道其基礎結構和通訊可能會影響的常見安全性攻擊。</span><span class="sxs-lookup"><span data-stu-id="66f5a-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="66f5a-105">洩漏金鑰攻擊</span><span class="sxs-lookup"><span data-stu-id="66f5a-105">Compromised-Key Attack</span></span>

<span data-ttu-id="66f5a-106">金鑰是用來加密、解密或驗證秘密資訊的秘密代碼或數字。</span><span class="sxs-lookup"><span data-stu-id="66f5a-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="66f5a-107">有兩個機密機碼中使用中公開金鑰基礎結構 (PKI) 也必須納入考量:。</span><span class="sxs-lookup"><span data-stu-id="66f5a-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="66f5a-108">每個憑證持有者具有私密金鑰</span><span class="sxs-lookup"><span data-stu-id="66f5a-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="66f5a-109">工作階段識別碼，是使用後成功的識別資料及工作階段 exchange 通訊的協力廠商</span><span class="sxs-lookup"><span data-stu-id="66f5a-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="66f5a-110">當攻擊者判斷出私密金鑰或工作階段金鑰時，即發生洩漏金鑰攻擊。</span><span class="sxs-lookup"><span data-stu-id="66f5a-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="66f5a-111">當攻擊者成功判斷出金鑰後，就可以在傳送者不知情的情況下，使用金鑰將加密的資料解密。</span><span class="sxs-lookup"><span data-stu-id="66f5a-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="66f5a-112">Lync Server 2013 的 Windows Server 作業系統中使用 PKI 功能，來保護用於加密的傳輸層安全性 (TLS) 連線的索引鍵資料。</span><span class="sxs-lookup"><span data-stu-id="66f5a-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="66f5a-113">所用的媒體加密金鑰會透過 TLS 連線交換。</span><span class="sxs-lookup"><span data-stu-id="66f5a-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="66f5a-114">網路拒絕服務攻擊</span><span class="sxs-lookup"><span data-stu-id="66f5a-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="66f5a-115">一般網路使用與函式的有效使用者，可防止攻擊者時，就會發生*拒絕服務攻擊*。</span><span class="sxs-lookup"><span data-stu-id="66f5a-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="66f5a-116">這是當攻擊者塞爆使癱瘓使用服務的合法要求服務合法的使用者。</span><span class="sxs-lookup"><span data-stu-id="66f5a-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="66f5a-117">藉由使用拒絕服務攻擊，攻擊者可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="66f5a-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="66f5a-118">傳送無效的資料給受攻擊網路中執行的應用程式和服務，干擾其正常功能。</span><span class="sxs-lookup"><span data-stu-id="66f5a-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="66f5a-119">傳送大量流量使系統超載，直到系統停止回應或是對合法要求回應變慢。</span><span class="sxs-lookup"><span data-stu-id="66f5a-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="66f5a-120">隱藏攻擊證據。</span><span class="sxs-lookup"><span data-stu-id="66f5a-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="66f5a-121">阻止使用者存取網路資源。</span><span class="sxs-lookup"><span data-stu-id="66f5a-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="66f5a-122">竊聽 （竊聽，側錄）</span><span class="sxs-lookup"><span data-stu-id="66f5a-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="66f5a-123">當攻擊者後所提升的網路中的資料路徑的存取權，且能夠監視及讀取流量時，就會發生*竊聽*。</span><span class="sxs-lookup"><span data-stu-id="66f5a-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="66f5a-124">這也稱為*探查*或*側錄*。</span><span class="sxs-lookup"><span data-stu-id="66f5a-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="66f5a-125">如果流量是純文字，則攻擊者取得路徑存取權之後就可以讀取流量。</span><span class="sxs-lookup"><span data-stu-id="66f5a-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="66f5a-126">例如，控制資料路徑上的路由器，就是進行這類攻擊的方式。</span><span class="sxs-lookup"><span data-stu-id="66f5a-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="66f5a-127">Microsoft Lync Server 2013 內的流量的設定與預設的建議作法是使用相互 TLS (MTLS) 之間信任的伺服器與 TLS 從用戶端到伺服器。</span><span class="sxs-lookup"><span data-stu-id="66f5a-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="66f5a-128">此措施會使攻擊，很難或無法達到指定的交談會發生的期間內。</span><span class="sxs-lookup"><span data-stu-id="66f5a-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="66f5a-129">TLS 會驗證所有相關人員並加密所有流量。</span><span class="sxs-lookup"><span data-stu-id="66f5a-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="66f5a-130">雖然這無法阻止竊聽，卻能讓攻擊者無法讀取流量，除非加密被破解。</span><span class="sxs-lookup"><span data-stu-id="66f5a-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="66f5a-131">周遊使用轉送 NAT （開啟） 通訊協定並未受命進行加密的流量，它傳送資訊會受到訊息完整性。</span><span class="sxs-lookup"><span data-stu-id="66f5a-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="66f5a-132">雖然開啟竊聽，資訊它傳送直接透過只要查看封包的來源和目的地位址，則可以擷取 （也就是 IP 位址和連接埠）。</span><span class="sxs-lookup"><span data-stu-id="66f5a-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="66f5a-133">A / V Edge service 可確保資料是否有效，藉由使用衍生自幾項目，包括開啟密碼，永遠不會以純文字傳送的機碼檢查郵件訊息完整性。</span><span class="sxs-lookup"><span data-stu-id="66f5a-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="66f5a-134">如果使用安全即時通訊協定 (SRTP)，則也加密的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="66f5a-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="66f5a-135">身分詐騙 （IP 位址詐騙）</span><span class="sxs-lookup"><span data-stu-id="66f5a-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="66f5a-136">攻擊者決定並沒有正在授權使用 IP 位址為網路、 電腦或網路元件，若要這麼做時，就會發生*詐騙*。</span><span class="sxs-lookup"><span data-stu-id="66f5a-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="66f5a-137">成功的攻擊允許操作時是否攻擊者通常的 IP 位址所識別的實體攻擊者。</span><span class="sxs-lookup"><span data-stu-id="66f5a-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="66f5a-138">在 Microsoft Lync Server 2013 的內容，這種情況而重新列入播放只有當系統管理員已完成下列兩項：</span><span class="sxs-lookup"><span data-stu-id="66f5a-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="66f5a-139">設定支援僅傳輸控制通訊協定 (TCP) （這不建議使用，因為 TCP 通訊未經過加密） 的連線。</span><span class="sxs-lookup"><span data-stu-id="66f5a-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="66f5a-140">將這些連線的 IP 位址標記為信任的主機。</span><span class="sxs-lookup"><span data-stu-id="66f5a-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="66f5a-141">這是小於問題進行傳輸層安全性 (TLS) 連線，因為 TLS 驗證所有方並加密的所有流量。</span><span class="sxs-lookup"><span data-stu-id="66f5a-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="66f5a-142">使用 TLS，可防止攻擊者執行詐騙在某特定連線 （例如，相互 TLS 連線） 上的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="66f5a-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="66f5a-143">但攻擊者可能仍會詐騙的 Lync Server 2013 使用的 DNS 伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="66f5a-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="66f5a-144">不過，因為憑證執行 Lync 中的驗證，攻擊者將不會包含需要下列其中一個通訊中的各方負責詐騙的有效憑證。</span><span class="sxs-lookup"><span data-stu-id="66f5a-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="66f5a-145">攔截攻擊</span><span class="sxs-lookup"><span data-stu-id="66f5a-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="66f5a-146">攻擊變更路徑透過攻擊者電腦的兩個通訊使用者不知情的情況下的兩個使用者之間的通訊時發生攔截攻擊。</span><span class="sxs-lookup"><span data-stu-id="66f5a-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="66f5a-147">攻擊者可以監視及傳送入預定的收件者之前，請先閱讀流量。</span><span class="sxs-lookup"><span data-stu-id="66f5a-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="66f5a-148">通訊中的每位使用者不知情的情況下傳送的流量，並從攻擊者，所有時考慮進行通訊，但只會與預期的使用者接收流量。</span><span class="sxs-lookup"><span data-stu-id="66f5a-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="66f5a-149">如果攻擊者可以修改將他/她伺服器新增為信任的伺服器，或修改網域名稱系統 (DNS) 來取得用戶端能夠連線至伺服器的路上攻擊者透過 Active Directory 網域服務，這可能會發生。</span><span class="sxs-lookup"><span data-stu-id="66f5a-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="66f5a-150">攔截攻擊可能也會發生兩個用戶端之間的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="66f5a-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="66f5a-151">不過，在 [Microsoft Lync Server 2013 點對點音訊、 視訊及應用程式共用，資料流是使用 SRTP，使用交涉會使用透過 TLS 的工作階段初始通訊協定 (SIP) 對等之間的密碼編譯金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="66f5a-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="66f5a-152">例如 Group Chat 伺服器進行強化安全性的網頁流量使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="66f5a-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="66f5a-153">RTP 重播攻擊</span><span class="sxs-lookup"><span data-stu-id="66f5a-153">RTP Replay Attack</span></span>

<span data-ttu-id="66f5a-154">*重新執行攻擊*發生於兩方有效的媒體傳輸會攔截和重新傳輸的惡意的用途。</span><span class="sxs-lookup"><span data-stu-id="66f5a-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="66f5a-155">與安全信號通訊協定使用 SRTP 會重新執行攻擊傳輸保護藉由啟用維護已收到 RTP 封包的索引，並比較與索引中已列出每個新的封包收件者。</span><span class="sxs-lookup"><span data-stu-id="66f5a-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="66f5a-156">垃圾訊息</span><span class="sxs-lookup"><span data-stu-id="66f5a-156">Spim</span></span>

<span data-ttu-id="66f5a-157">*垃圾訊息*是來路不明的商業立即訊息或目前狀態訂閱要求。</span><span class="sxs-lookup"><span data-stu-id="66f5a-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="66f5a-158">而不是依本身，而危害的網路，請它很煩人中最少資源可用性和實際執行環境，可以減少，可能導致網路的危害。</span><span class="sxs-lookup"><span data-stu-id="66f5a-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="66f5a-159">例如，這是使用者 spimming 彼此藉由傳送要求。</span><span class="sxs-lookup"><span data-stu-id="66f5a-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="66f5a-160">使用者可以封鎖彼此避免發生這樣，但使用同盟時，如果在建立協調的垃圾攻擊時，這可能很難克服除非您停用同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="66f5a-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="66f5a-161">病毒和蠕蟲</span><span class="sxs-lookup"><span data-stu-id="66f5a-161">Viruses and Worms</span></span>

<span data-ttu-id="66f5a-162">*病毒*是程式碼的目的，是以重現額外類似的程式碼單位的單位。</span><span class="sxs-lookup"><span data-stu-id="66f5a-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="66f5a-163">病毒需要宿主才能運作，檔案、電子郵件或程式都可能成為宿主。</span><span class="sxs-lookup"><span data-stu-id="66f5a-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="66f5a-164">*蠕蟲*單位程式碼的目的，是以重現額外類似的程式碼單位，但它不需要主應用程式。</span><span class="sxs-lookup"><span data-stu-id="66f5a-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="66f5a-165">病毒和蠕蟲常出現在用戶端之間的檔案傳輸期間或是其他使用者送出的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="66f5a-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="66f5a-166">舉例來說，如果病毒存在您的電腦中，它就能夠使用您的身分識別並代您傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="66f5a-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="66f5a-167">個人識別資訊</span><span class="sxs-lookup"><span data-stu-id="66f5a-167">Personally Identifiable Information</span></span>

<span data-ttu-id="66f5a-168">Microsoft Lync Server 2013 有可能會透過公用網路，或許可以都連結至個人透露資訊。</span><span class="sxs-lookup"><span data-stu-id="66f5a-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="66f5a-169">資訊類型可以是分解以兩個特定類別：</span><span class="sxs-lookup"><span data-stu-id="66f5a-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="66f5a-170">**增強顯示狀態資料**增強顯示狀態資料是使用者可以選擇要共用的或不共用透過連結給同盟協力廠商或與組織內的連絡人的資訊。</span><span class="sxs-lookup"><span data-stu-id="66f5a-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="66f5a-171">此資料不會共用與公用 IM 網路上的使用者。</span><span class="sxs-lookup"><span data-stu-id="66f5a-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="66f5a-172">用戶端原則及其他用戶端組態可能會讓某些控制項與系統管理員。</span><span class="sxs-lookup"><span data-stu-id="66f5a-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="66f5a-173">在 Lync Server 2013 中，增強型目前狀態隱私權模式可針對個別使用者可防止不是在使用者的連絡人清單上的 Lync 使用者看見使用者的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="66f5a-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="66f5a-174">增強型目前狀態隱私權模式無法防止使用者的 Microsoft Office Communicator 2007 與 Microsoft Office Communicator 2007 R2 看見使用者的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="66f5a-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="66f5a-175">如需詳細資訊，請參閱[什麼是新的 Lync Server 2013 中的用戶端](lync-server-2013-what-s-new-for-clients.md)中的快速入門 > 文件和[Lync Server 2013 中設定增強的目前狀態隱私權模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)部署文件中。</span><span class="sxs-lookup"><span data-stu-id="66f5a-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="66f5a-176">**必要資料**必要資料是必要的伺服器或用戶端的正常運作，且無法控制的用戶端或系統管理。</span><span class="sxs-lookup"><span data-stu-id="66f5a-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="66f5a-177">這是所需的路由、 狀態維護的目的伺服器或網路層級和訊號的資訊。</span><span class="sxs-lookup"><span data-stu-id="66f5a-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="66f5a-178">下表列出公開在公用網路上的資料。</span><span class="sxs-lookup"><span data-stu-id="66f5a-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="66f5a-179">增強顯示狀態資料</span><span class="sxs-lookup"><span data-stu-id="66f5a-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66f5a-180">資料外洩</span><span class="sxs-lookup"><span data-stu-id="66f5a-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="66f5a-181">可能的設定</span><span class="sxs-lookup"><span data-stu-id="66f5a-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66f5a-182">個人資料</span><span class="sxs-lookup"><span data-stu-id="66f5a-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="66f5a-183">名稱、 職稱、 公司、 電子郵件地址、 時區</span><span class="sxs-lookup"><span data-stu-id="66f5a-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66f5a-184">電話號碼</span><span class="sxs-lookup"><span data-stu-id="66f5a-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="66f5a-185">工作、 手機、 住家</span><span class="sxs-lookup"><span data-stu-id="66f5a-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66f5a-186">行事曆資訊</span><span class="sxs-lookup"><span data-stu-id="66f5a-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="66f5a-187">空閒/忙碌，Out-Of-Town 通知、 會議詳細資料 （對象存取您行事曆）</span><span class="sxs-lookup"><span data-stu-id="66f5a-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66f5a-188">目前狀態</span><span class="sxs-lookup"><span data-stu-id="66f5a-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="66f5a-189">離開、 線上、 忙碌、 請勿打擾、 離線</span><span class="sxs-lookup"><span data-stu-id="66f5a-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="66f5a-190">必要資料</span><span class="sxs-lookup"><span data-stu-id="66f5a-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66f5a-191">資料外洩</span><span class="sxs-lookup"><span data-stu-id="66f5a-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="66f5a-192">範例資訊</span><span class="sxs-lookup"><span data-stu-id="66f5a-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66f5a-193">IP 位址</span><span class="sxs-lookup"><span data-stu-id="66f5a-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="66f5a-194">實際的電腦或經過 nat 處理地址的地址</span><span class="sxs-lookup"><span data-stu-id="66f5a-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66f5a-195">SIP URI</span><span class="sxs-lookup"><span data-stu-id="66f5a-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="66f5a-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="66f5a-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

