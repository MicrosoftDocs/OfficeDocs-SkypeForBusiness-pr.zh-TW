---
title: Lync Server 2013：現代計算中常見的安全性威脅
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
ms.openlocfilehash: 60197a65bb0362b1bbdcf3fee779ed503af00eb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526130"
---
# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="e5b6f-102">現代的日期計算中的常見安全性威脅</span><span class="sxs-lookup"><span data-stu-id="e5b6f-102">Common security threats in modern day computing</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5b6f-103">_**主題上次修改日期：** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="e5b6f-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="e5b6f-104">因為 Lync Server 2013 是企業級的通訊系統，所以應注意可能影響其基礎結構和通訊的常見安全性攻擊。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="e5b6f-105">洩漏金鑰攻擊</span><span class="sxs-lookup"><span data-stu-id="e5b6f-105">Compromised-Key Attack</span></span>

<span data-ttu-id="e5b6f-106">金鑰是用來加密、解密或驗證秘密資訊的秘密代碼或數字。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="e5b6f-107">在公開金鑰基礎結構中使用的機密機碼有兩個 (必須考慮的 PKI) ：。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="e5b6f-108">每個憑證持有者所擁有的私密金鑰</span><span class="sxs-lookup"><span data-stu-id="e5b6f-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="e5b6f-109">通訊夥伴成功識別與會話金鑰交換之後所使用的工作階段金鑰</span><span class="sxs-lookup"><span data-stu-id="e5b6f-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="e5b6f-110">當攻擊者判斷出私密金鑰或工作階段金鑰時，即發生洩漏金鑰攻擊。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="e5b6f-111">當攻擊者成功判斷出金鑰後，就可以在傳送者不知情的情況下，使用金鑰將加密的資料解密。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="e5b6f-112">Lync Server 2013 使用 Windows Server 作業系統中的 PKI 功能來保護用於加密傳輸層安全性 (TLS) 連線的金鑰資料。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="e5b6f-113">媒體加密所用的按鍵會透過 TLS 連接進行交換。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="e5b6f-114">網路拒絕服務攻擊</span><span class="sxs-lookup"><span data-stu-id="e5b6f-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="e5b6f-115">當攻擊者禁止正常網路使用和有效使用者運作時，就會發生 *拒絕服務攻擊* 。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="e5b6f-116">當攻擊者利用合法的使用者利用服務的合法要求來淹沒服務時，這是很好的做法。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="e5b6f-117">攻擊者使用拒絕服務攻擊可執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e5b6f-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="e5b6f-118">傳送無效的資料給受攻擊網路中執行的應用程式和服務，干擾其正常功能。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="e5b6f-119">傳送大量流量使系統超載，直到系統停止回應或是對合法要求回應變慢。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="e5b6f-120">隱藏攻擊證據。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="e5b6f-121">阻止使用者存取網路資源。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="e5b6f-122">偷聽 (探查、窺探) </span><span class="sxs-lookup"><span data-stu-id="e5b6f-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="e5b6f-123">當攻擊者存取網路中的資料路徑，並且具備監控和讀取流量的能力時，可能會發生*偷聽*。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="e5b6f-124">這也稱為 *嗅探* 或 *窺探*。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="e5b6f-125">如果流量是純文字，則攻擊者取得路徑存取權之後就可以讀取流量。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="e5b6f-126">例如，控制資料路徑上的路由器，就是進行這類攻擊的方式。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="e5b6f-127">Microsoft Lync Server 2013 內之流量的預設建議和設定是使用來自用戶端與伺服器之間的信任伺服器與 TLS 之間的相互 TLS (MTLS) 。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="e5b6f-128">這項保護措施會使攻擊非常困難，甚至無法在指定交談發生的時段內達到。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="e5b6f-129">TLS 會驗證所有相關人員並加密所有流量。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="e5b6f-130">雖然這無法阻止竊聽，卻能讓攻擊者無法讀取流量，除非加密被破解。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="e5b6f-131">使用轉送 NAT 的遍歷 (關閉) 通訊協定不會要求加密流量，而且傳送的資訊會受到郵件完整性的保護。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="e5b6f-132">雖然它是開放的，但是它所傳送的資訊 (也就是說，您只需查看封包的來源和目的地位址，即可直接解壓縮 IP 位址和通訊埠) 。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="e5b6f-133">A/V Edge service 會使用衍生自少數專案的金鑰（包括密碼，也就是永不以明文形式傳送）來檢查郵件的郵件完整性，以確保資料有效。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="e5b6f-134">如果使用安全即時通訊協定 (SRTP) ，媒體流量也會加密。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="e5b6f-135">身分識別哄騙 (IP 位址欺騙) </span><span class="sxs-lookup"><span data-stu-id="e5b6f-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="e5b6f-136">當攻擊者判斷並使用網路、電腦或網路元件的 IP 位址但未獲授權時，就會發生*欺騙*。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="e5b6f-137">成功的攻擊可讓攻擊者像是由 IP 位址一般識別的實體一樣運作。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="e5b6f-138">在 Microsoft Lync Server 2013 的內容中，只有當系統管理員已執行下列兩項作業時，才會進入播放狀態：</span><span class="sxs-lookup"><span data-stu-id="e5b6f-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="e5b6f-139">設定只支援傳輸控制通訊協定 (TCP)  (但不建議使用的連線，因為 TCP 通訊未加密) 。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="e5b6f-140">將那些連線的 IP 位址標記為受信任的主機。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="e5b6f-141">這不是傳輸層安全性 (TLS) 連線的問題，因為 TLS 會驗證所有的各方，並加密所有流量。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="e5b6f-142">使用 TLS 可防止攻擊者在特定的連接上執行 IP 位址欺騙 (例如，相互 TLS 連線) 。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="e5b6f-143">但是，攻擊者仍然可以哄騙 Lync Server 2013 所用的 DNS 伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="e5b6f-144">不過，因為 Lync 的驗證是以憑證執行，所以攻擊者不會有必要的有效憑證，以哄騙通訊中的一方。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="e5b6f-145">干預中間人攻擊</span><span class="sxs-lookup"><span data-stu-id="e5b6f-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="e5b6f-146">當攻擊者透過攻擊者的電腦來重排兩位使用者之間的通訊時，就會發生中間人攻擊，而不會知道兩個通訊使用者的知識。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="e5b6f-147">攻擊者可以在將流量傳送給預定收件者之前，監控並讀取流量。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="e5b6f-148">通訊中的每一位使用者都會在不知情的情況下傳送流量，並接收來自攻擊者的流量，所有的情況都是在思考他們只與預定的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="e5b6f-149">如果攻擊者可以修改 Active Directory 網域服務，將其伺服器新增為受信任的伺服器或修改網域名稱系統 (DNS) ，以取得用戶端透過攻擊者以其方式連線至伺服器，便會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="e5b6f-150">在兩個用戶端間的媒體流量也會發生中間人攻擊。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="e5b6f-151">不過，在 Microsoft Lync Server 2013 點對點音訊、影片和應用程式共用中，資料流程會以 SRTP 加密，使用在使用會話初始通訊協定的對等 (SIP) over TLS 之間協商的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="e5b6f-152">群組聊天等伺服器會使用 HTTPS，以加強網頁流量的安全性。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="e5b6f-153">RTP 重放攻擊</span><span class="sxs-lookup"><span data-stu-id="e5b6f-153">RTP Replay Attack</span></span>

<span data-ttu-id="e5b6f-154">當雙方之間的有效媒體傳輸因惡意目的而截取和重新傳輸時，就會發生重新顯示 *攻擊* 。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="e5b6f-155">SRTP 與安全信號通訊協定搭配使用，可讓接收器維護已接收的 RTP 封包的索引，並將每個新的資料包與索引中已列出的資料包進行比較，以保護傳輸免受重新顯示攻擊。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="e5b6f-156">Spim</span><span class="sxs-lookup"><span data-stu-id="e5b6f-156">Spim</span></span>

<span data-ttu-id="e5b6f-157">*Spim* 是未經要求的商業立即訊息或顯示狀態訂閱要求。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="e5b6f-158">雖然它本身不是網路遭到損害，但卻令人討厭的是，它可能會降低資源的可用性和生產，而且可能會導致網路受損。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="e5b6f-159">例如，使用者會傳送要求來 spimming 對方。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="e5b6f-160">使用者可以彼此封鎖，以防止發生這種情況，但在同盟中，如果已建立協調的 spim 攻擊，則除非您停用夥伴的同盟，否則這可能會很難克服。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="e5b6f-161">病毒和蠕蟲</span><span class="sxs-lookup"><span data-stu-id="e5b6f-161">Viruses and Worms</span></span>

<span data-ttu-id="e5b6f-162">*病毒*是其用途的程式碼單位，可再現其他類似的代碼單位。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="e5b6f-163">病毒需要宿主才能運作，檔案、電子郵件或程式都可能成為宿主。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="e5b6f-164">*Worm*是一個程式碼單位，其用途是複製其他類似的代碼單位，但不需要主機。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="e5b6f-165">病毒和蠕蟲常出現在用戶端之間的檔案傳輸期間或是其他使用者送出的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="e5b6f-166">舉例來說，如果病毒存在您的電腦中，它就能夠使用您的身分識別並代您傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="e5b6f-167">個人身分識別資訊</span><span class="sxs-lookup"><span data-stu-id="e5b6f-167">Personally Identifiable Information</span></span>

<span data-ttu-id="e5b6f-168">Microsoft Lync Server 2013 可能會透過可以連結到個人的公用網路洩漏資訊。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="e5b6f-169">資訊類型可分為兩個特定類別：</span><span class="sxs-lookup"><span data-stu-id="e5b6f-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="e5b6f-170">**增強顯示狀態資料** 增強型顯示狀態資料是使用者可選擇共用或不共用的資訊，供同盟合作夥伴或組織內的連絡人連結。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="e5b6f-171">此資料與公用 IM 網路上的使用者不共用。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="e5b6f-172">用戶端原則和其他用戶端設定可能會對系統管理員帶來一些控制權。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="e5b6f-173">在 Lync Server 2013 中，可為個別使用者設定增強的目前狀態隱私權模式，以避免使用者的連絡人清單中的 Lync 使用者看到使用者的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="e5b6f-174">增強型目前狀態隱私權模式不會防止 Microsoft Office Communicator 2007 和 Microsoft Office Communicator 2007 R2 的使用者看到使用者的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="e5b6f-175">如需詳細資訊，請參閱部署檔中的「入門檔」和「[在 Lync server 2013 中設定增強型目前狀態隱私權」模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)中的[客戶2013端新增功能](lync-server-2013-what-s-new-for-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="e5b6f-176">**必要資料** 必要的資料是伺服器或用戶端的適當運作所需的，且不受用戶端或系統管理的控制。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="e5b6f-177">這是伺服器或網路層級必要的資訊，目的是用於路由、狀態維護和信號。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="e5b6f-178">下表列出透過公用網路公開的資料。</span><span class="sxs-lookup"><span data-stu-id="e5b6f-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="e5b6f-179">增強顯示狀態資料</span><span class="sxs-lookup"><span data-stu-id="e5b6f-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5b6f-180">資料洩漏</span><span class="sxs-lookup"><span data-stu-id="e5b6f-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="e5b6f-181">可能的設定</span><span class="sxs-lookup"><span data-stu-id="e5b6f-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5b6f-182">個人資料</span><span class="sxs-lookup"><span data-stu-id="e5b6f-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="e5b6f-183">名稱、職稱、公司、電子郵件地址、時區</span><span class="sxs-lookup"><span data-stu-id="e5b6f-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5b6f-184">電話號碼</span><span class="sxs-lookup"><span data-stu-id="e5b6f-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="e5b6f-185">Work，Mobile，Home</span><span class="sxs-lookup"><span data-stu-id="e5b6f-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5b6f-186">行事曆資訊</span><span class="sxs-lookup"><span data-stu-id="e5b6f-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="e5b6f-187">Free/Busy、不在城鎮的通知、會議詳細資料 (有權存取您的行事曆) </span><span class="sxs-lookup"><span data-stu-id="e5b6f-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5b6f-188">顯示狀態</span><span class="sxs-lookup"><span data-stu-id="e5b6f-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="e5b6f-189">離開，可用，忙碌，請勿打擾，離線</span><span class="sxs-lookup"><span data-stu-id="e5b6f-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="e5b6f-190">必要資料</span><span class="sxs-lookup"><span data-stu-id="e5b6f-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5b6f-191">資料洩漏</span><span class="sxs-lookup"><span data-stu-id="e5b6f-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="e5b6f-192">範例資訊</span><span class="sxs-lookup"><span data-stu-id="e5b6f-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5b6f-193">IP 位址</span><span class="sxs-lookup"><span data-stu-id="e5b6f-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="e5b6f-194">電腦或 NATed 位址的實際位址</span><span class="sxs-lookup"><span data-stu-id="e5b6f-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5b6f-195">SIP URI</span><span class="sxs-lookup"><span data-stu-id="e5b6f-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="e5b6f-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e5b6f-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

