---
title: Lync Server 2013：現代的日期計算中的常見安全性威脅
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
ms.openlocfilehash: 99e17f9f6dbba30697c72fecf77fbff4bfbdc003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="c689f-102">現代的日期計算中的常見安全性威脅</span><span class="sxs-lookup"><span data-stu-id="c689f-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c689f-103">_**主題上次修改日期：** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="c689f-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="c689f-104">由於 Lync Server 2013 是企業級通訊系統，因此您應該注意到可能會影響其基礎結構和通訊的常見安全性攻擊。</span><span class="sxs-lookup"><span data-stu-id="c689f-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="c689f-105">受害金鑰攻擊</span><span class="sxs-lookup"><span data-stu-id="c689f-105">Compromised-Key Attack</span></span>

<span data-ttu-id="c689f-106">金鑰是用來加密、解密或驗證機密資訊的秘密代碼或數位。</span><span class="sxs-lookup"><span data-stu-id="c689f-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="c689f-107">在公開金鑰基礎結構（PKI）中，有兩個要使用的機密金鑰必須考慮：。</span><span class="sxs-lookup"><span data-stu-id="c689f-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="c689f-108">每個證書持有者所擁有的私人金鑰</span><span class="sxs-lookup"><span data-stu-id="c689f-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="c689f-109">通訊合作夥伴成功識別與會話金鑰交換之後所使用的工作階段金鑰</span><span class="sxs-lookup"><span data-stu-id="c689f-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="c689f-110">當攻擊者決定私密金鑰或工作階段金鑰時，就會發生受害金鑰攻擊。</span><span class="sxs-lookup"><span data-stu-id="c689f-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="c689f-111">當攻擊者成功判斷金鑰之後，攻擊者就可以使用金鑰來解密加密的資料，而不需要寄件者的知識。</span><span class="sxs-lookup"><span data-stu-id="c689f-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="c689f-112">Lync Server 2013 使用 Windows Server 作業系統中的 PKI 功能，來保護用於傳輸層安全性（TLS）連線之加密的金鑰資料。</span><span class="sxs-lookup"><span data-stu-id="c689f-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="c689f-113">媒體加密所用的金鑰會經由 TLS 連線進行交換。</span><span class="sxs-lookup"><span data-stu-id="c689f-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="c689f-114">網路拒絕服務攻擊</span><span class="sxs-lookup"><span data-stu-id="c689f-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="c689f-115">當攻擊者防止正常網路使用及由有效的使用者運作時，就會發生*拒絕服務攻擊*。</span><span class="sxs-lookup"><span data-stu-id="c689f-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="c689f-116">當攻擊者利用合法的使用者大量使用服務的合法要求時，就會完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="c689f-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="c689f-117">攻擊者可以使用拒絕服務攻擊來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c689f-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="c689f-118">傳送不正確資料給受攻擊的網路中執行的應用程式和服務，以中斷其正常運作。</span><span class="sxs-lookup"><span data-stu-id="c689f-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="c689f-119">傳送大量的流量，在系統停止回應或緩慢回應合法要求之前，將系統超載。</span><span class="sxs-lookup"><span data-stu-id="c689f-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="c689f-120">隱藏攻擊的證據。</span><span class="sxs-lookup"><span data-stu-id="c689f-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="c689f-121">防止使用者存取網路資源。</span><span class="sxs-lookup"><span data-stu-id="c689f-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="c689f-122">竊聽（嗅探、窺探）</span><span class="sxs-lookup"><span data-stu-id="c689f-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="c689f-123">*竊聽*可能會在攻擊者取得網路中資料路徑的存取權，並具備監視及讀取流量的能力時發生。</span><span class="sxs-lookup"><span data-stu-id="c689f-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="c689f-124">這也稱為*嗅探*或*窺探*。</span><span class="sxs-lookup"><span data-stu-id="c689f-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="c689f-125">如果流量是純文字，攻擊者就可以在取得路徑存取權時，閱讀流量。</span><span class="sxs-lookup"><span data-stu-id="c689f-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="c689f-126">例如，您可以透過控制資料路徑上的路由器來執行攻擊。</span><span class="sxs-lookup"><span data-stu-id="c689f-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="c689f-127">在 Microsoft Lync Server 2013 中，針對通訊的預設建議和設定是在受信任的伺服器之間使用相互 TLS （MTLS），而從用戶端到伺服器的 TLS 則是。</span><span class="sxs-lookup"><span data-stu-id="c689f-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="c689f-128">這個保護措施會使攻擊在指定交談發生的時段內變得非常困難或無法完成。</span><span class="sxs-lookup"><span data-stu-id="c689f-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="c689f-129">TLS 會驗證所有雙方，並加密所有通訊。</span><span class="sxs-lookup"><span data-stu-id="c689f-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="c689f-130">這不會防止竊聽，但除非加密遭到破壞，否則攻擊者無法讀取流量。</span><span class="sxs-lookup"><span data-stu-id="c689f-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="c689f-131">使用中繼 NAT （TURN）通訊協定的遍歷不會要求加密通信量，且傳送的資訊會受到郵件完整性的保護。</span><span class="sxs-lookup"><span data-stu-id="c689f-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="c689f-132">雖然它是以竊聽的方式開啟，但是它所傳送的資訊（也就是 IP 位址和埠）可以直接提取，只要查看資料包的來源和目的地位址即可。</span><span class="sxs-lookup"><span data-stu-id="c689f-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="c689f-133">A/V Edge 服務使用從幾個專案衍生的金鑰來檢查郵件的完整性，以確保資料有效，包括 [密碼]，此密碼決不會以明文傳送。</span><span class="sxs-lookup"><span data-stu-id="c689f-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="c689f-134">如果使用安全即時通訊協定（SRTP），媒體流量也會經過加密。</span><span class="sxs-lookup"><span data-stu-id="c689f-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="c689f-135">身分識別欺騙（IP 位址欺騙）</span><span class="sxs-lookup"><span data-stu-id="c689f-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="c689f-136">如果攻擊者決定並使用網路、電腦或網路元件的 IP 位址，而不需要執行此動作，就會發生*哄騙*情況。</span><span class="sxs-lookup"><span data-stu-id="c689f-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="c689f-137">成功的攻擊可讓攻擊者進行操作，就像是 IP 位址通常會識別的實體一樣。</span><span class="sxs-lookup"><span data-stu-id="c689f-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="c689f-138">在 Microsoft Lync Server 2013 的內容中，只有當系統管理員已完成下列兩項作業時，才會播放此情況：</span><span class="sxs-lookup"><span data-stu-id="c689f-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="c689f-139">已設定僅支援傳輸控制通訊協定（TCP）的連線（不建議使用），因為 TCP 通訊未加密。</span><span class="sxs-lookup"><span data-stu-id="c689f-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="c689f-140">已將這些連線的 IP 位址標示為受信任的主機。</span><span class="sxs-lookup"><span data-stu-id="c689f-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="c689f-141">這不是傳輸層安全性（TLS）連線的問題，因為 TLS 會驗證所有參與方，並加密所有通訊。</span><span class="sxs-lookup"><span data-stu-id="c689f-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="c689f-142">使用 TLS 可防止攻擊者在特定連線（例如相互 TLS 連線）上執行 IP 位址欺騙。</span><span class="sxs-lookup"><span data-stu-id="c689f-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="c689f-143">但是，攻擊者仍可欺騙 Lync Server 2013 使用的 DNS 伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="c689f-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="c689f-144">不過，因為 Lync 中的驗證是透過憑證來執行，所以攻擊者沒有假冒通訊中的其中一個參與方所需的有效證書。</span><span class="sxs-lookup"><span data-stu-id="c689f-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="c689f-145">中間人攻擊（中間人）</span><span class="sxs-lookup"><span data-stu-id="c689f-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="c689f-146">當攻擊者透過攻擊者的電腦傳送兩個使用者之間的通訊時，就會發生中間人攻擊，而不需要兩個通訊使用者的知識。</span><span class="sxs-lookup"><span data-stu-id="c689f-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="c689f-147">攻擊者可以在將通信量傳送給預定的收件者前，進行監控並閱讀。</span><span class="sxs-lookup"><span data-stu-id="c689f-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="c689f-148">通訊中的每位使用者都會在不知情的情況下傳送流量，並接收來自攻擊者的流量，同時認為他們只與預期的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="c689f-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="c689f-149">如果攻擊者可以修改 Active Directory 網域服務將其伺服器作為受信任的伺服器加入，或修改網域名稱系統（DNS），以讓用戶端透過攻擊者連線到伺服器，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="c689f-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="c689f-150">中間人攻擊也會在兩個用戶端之間的媒體流量中發生。</span><span class="sxs-lookup"><span data-stu-id="c689f-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="c689f-151">不過，在 Microsoft Lync Server 2013 的點對端音訊、影片和應用程式共用中，資料流程是使用 SRTP 來加密的，這些金鑰是在使用經由 TLS 的會話初始通訊協定（SIP）的對等。</span><span class="sxs-lookup"><span data-stu-id="c689f-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="c689f-152">伺服器（例如群組聊天）使用 HTTPS 來加強網頁流量的安全性。</span><span class="sxs-lookup"><span data-stu-id="c689f-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="c689f-153">RTP 重播攻擊</span><span class="sxs-lookup"><span data-stu-id="c689f-153">RTP Replay Attack</span></span>

<span data-ttu-id="c689f-154">當雙方之間的有效媒體傳輸遭到攔截並重新傳輸以進行惡意時，就會發生*重播攻擊*。</span><span class="sxs-lookup"><span data-stu-id="c689f-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="c689f-155">SRTP 與安全的信號通訊協定搭配使用，可讓接收器維持已收到的 RTP 資料包的索引，並將每個新的資料包與已列在索引中的新資料包加以比較，以保護傳輸。</span><span class="sxs-lookup"><span data-stu-id="c689f-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="c689f-156">Spim</span><span class="sxs-lookup"><span data-stu-id="c689f-156">Spim</span></span>

<span data-ttu-id="c689f-157">*Spim*是未經請求的商業立即訊息或目前狀態訂閱要求。</span><span class="sxs-lookup"><span data-stu-id="c689f-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="c689f-158">雖然不只是網路遭到破壞，但卻不令人討厭，但可能會降低資源的可用性與生產，而且可能會造成網路遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="c689f-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="c689f-159">例如，使用者可以傳送要求來 spimming 對方。</span><span class="sxs-lookup"><span data-stu-id="c689f-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="c689f-160">使用者可以彼此封鎖來避免這種情況，但使用同盟時，如果已建立共同的 spim 攻擊，除非您為合作夥伴停用同盟，否則可能難以解決。</span><span class="sxs-lookup"><span data-stu-id="c689f-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="c689f-161">病毒與蠕蟲</span><span class="sxs-lookup"><span data-stu-id="c689f-161">Viruses and Worms</span></span>

<span data-ttu-id="c689f-162">[*病毒*] 是一個程式碼單位，其目的是要再現其他類似的代碼單位。</span><span class="sxs-lookup"><span data-stu-id="c689f-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="c689f-163">若要發揮作用，病毒需要有主機（例如檔案、電子郵件或程式）。</span><span class="sxs-lookup"><span data-stu-id="c689f-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="c689f-164">*蠕蟲*是一種程式碼單位，其用途是要再現其他類似的程式碼單位，但不需要主機。</span><span class="sxs-lookup"><span data-stu-id="c689f-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="c689f-165">病毒和蠕蟲主要會在用戶端之間的檔案傳輸期間，或從其他使用者傳送 Url 時顯示。</span><span class="sxs-lookup"><span data-stu-id="c689f-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="c689f-166">例如，如果您的電腦上有病毒，就可以使用您的身分識別和代表您傳送即時消息。</span><span class="sxs-lookup"><span data-stu-id="c689f-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="c689f-167">個人辨識資訊</span><span class="sxs-lookup"><span data-stu-id="c689f-167">Personally Identifiable Information</span></span>

<span data-ttu-id="c689f-168">Microsoft Lync Server 2013 有可能在可連結至個人的公用網路上洩漏資訊。</span><span class="sxs-lookup"><span data-stu-id="c689f-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="c689f-169">資訊類型可以分為兩個特定類別：</span><span class="sxs-lookup"><span data-stu-id="c689f-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="c689f-170">**增強的目前狀態資料**[增強的目前狀態資料] 是使用者可以選擇共用或不共用至同盟夥伴或組織內部連絡人之連結的資訊。</span><span class="sxs-lookup"><span data-stu-id="c689f-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="c689f-171">此資料不會與公用 IM 網路上的使用者共用。</span><span class="sxs-lookup"><span data-stu-id="c689f-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="c689f-172">用戶端原則和其他用戶端設定可能會讓系統管理員進行一些控制。</span><span class="sxs-lookup"><span data-stu-id="c689f-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="c689f-173">在 Lync Server 2013 中，您可以針對個別使用者設定增強的目前狀態隱私權模式，避免 Lync 使用者不在使用者的連絡人清單中，而不會看到使用者的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="c689f-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="c689f-174">增強的目前狀態隱私權模式不會防止 Microsoft Office Communicator 2007 和 Microsoft Office Communicator 2007 R2 的使用者看到使用者的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="c689f-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="c689f-175">如需詳細資訊，請參閱適用[于 Lync server 2013 中的用戶端的新功能](lync-server-2013-what-s-new-for-clients.md)在「快速入門」檔中，以及在 [部署] 檔的 [ [lync server 2013]](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)中設定增強的目前狀態隱私權</span><span class="sxs-lookup"><span data-stu-id="c689f-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="c689f-176">**強制資料**伺服器或用戶端的正常運作需要必要的資料，而且不受用戶端或系統管理的控制。</span><span class="sxs-lookup"><span data-stu-id="c689f-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="c689f-177">這是伺服器或網路層級所需的資訊，用於路由、狀態維護和傳送信號。</span><span class="sxs-lookup"><span data-stu-id="c689f-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="c689f-178">下表列出在公用網路公開的資料。</span><span class="sxs-lookup"><span data-stu-id="c689f-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="c689f-179">增強的目前狀態資料</span><span class="sxs-lookup"><span data-stu-id="c689f-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c689f-180">已披露資料</span><span class="sxs-lookup"><span data-stu-id="c689f-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="c689f-181">可能的設定</span><span class="sxs-lookup"><span data-stu-id="c689f-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c689f-182">個人資料</span><span class="sxs-lookup"><span data-stu-id="c689f-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="c689f-183">名稱、標題、公司、電子郵件地址、時區</span><span class="sxs-lookup"><span data-stu-id="c689f-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c689f-184">電話號碼</span><span class="sxs-lookup"><span data-stu-id="c689f-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="c689f-185">公司、行動裝置、家用版</span><span class="sxs-lookup"><span data-stu-id="c689f-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c689f-186">行事曆資訊</span><span class="sxs-lookup"><span data-stu-id="c689f-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="c689f-187">空閒/忙碌、不在城鎮通知、會議詳細資料（針對有權存取您行事曆的人員）</span><span class="sxs-lookup"><span data-stu-id="c689f-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c689f-188">目前狀態</span><span class="sxs-lookup"><span data-stu-id="c689f-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="c689f-189">離開、可用、忙碌、[請勿打擾]、[離線]</span><span class="sxs-lookup"><span data-stu-id="c689f-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="c689f-190">強制資料</span><span class="sxs-lookup"><span data-stu-id="c689f-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c689f-191">已披露資料</span><span class="sxs-lookup"><span data-stu-id="c689f-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="c689f-192">範例資訊</span><span class="sxs-lookup"><span data-stu-id="c689f-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c689f-193">IP 位址</span><span class="sxs-lookup"><span data-stu-id="c689f-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="c689f-194">電腦或 NATed 位址的實際位址</span><span class="sxs-lookup"><span data-stu-id="c689f-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c689f-195">SIP URI</span><span class="sxs-lookup"><span data-stu-id="c689f-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="c689f-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c689f-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

