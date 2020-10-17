---
title: Lync Server 2013： TLS 和 MTLS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e22fcf910062df155bb62a9da183bbe6ad73e0f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503770"
---
# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="0cc3e-102">Lync Server 2013 的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="0cc3e-102">TLS and MTLS for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cc3e-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0cc3e-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0cc3e-104">傳輸層安全性 (TLS) 與相互傳輸層安全性 (MTLS) 通訊協定提供網際網路上的加密通訊和端點驗證。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="0cc3e-105">Microsoft Lync Server 2013 使用這兩種通訊協定建立信任的伺服器網路，並確保所有透過該網路的通訊都已加密。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="0cc3e-106">伺服器之間的所有 SIP 通訊都透過 MTLS 進行。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="0cc3e-107">從用戶端到伺服器的 SIP 通訊會透過 TLS 進行。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="0cc3e-108">TLS 可讓使用者透過用戶端軟體來驗證其所連接的 Lync Server 2013 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="0cc3e-109">在 TLS 連接上，用戶端會從伺服器要求有效的憑證。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="0cc3e-110">若是有效的，則憑證必須由用戶端也信任的 CA 所發出，而且伺服器的 DNS 名稱必須符合憑證上的 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="0cc3e-111">如果憑證有效，用戶端會使用憑證中的公開金鑰來加密要用於通訊的對稱加密金鑰，所以只有憑證的原始擁有者可以使用私密金鑰來解密通訊的內容。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="0cc3e-112">產生的連線是受信任的，而來自于其他受信任的伺服器或用戶端不會有任何挑戰。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="0cc3e-113">在此內容中，安全通訊端層 (SSL) （用於 Web 服務）可以與 TLS 基礎相關聯。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="0cc3e-114">伺服器對伺服器連線依賴 MTLS 進行相互驗證。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="0cc3e-115">在 MTLS 連線上，發起郵件的伺服器及接收它的伺服器會從相互信任的 CA 交換憑證。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="0cc3e-116">憑證會將每個伺服器的身分識別證明為另一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="0cc3e-117">在 Lync Server 2013 部署中，所有內部用戶端和伺服器皆會自動將由企業 CA 所簽發的憑證，而不是發行 CA 吊銷的憑證視為有效，因為 Active Directory 網域的所有成員都信任該網域中的企業 CA。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="0cc3e-118">在同盟案例中，雙方同盟協力廠商都必須信任發證 CA。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="0cc3e-119">如有需要，每個合作夥伴都可以使用不同的 CA，只要另一個夥伴也信任該 CA。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="0cc3e-120">當 Edge Server 具有夥伴的根 CA 憑證的根信任 Ca，或使用雙方所信任的協力廠商 CA 時，這項信任就會順利完成。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="0cc3e-121">TLS 和 MTLS 可協助防止偷聽和中間人攻擊。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="0cc3e-122">在中間人攻擊中，攻擊者會透過攻擊者的電腦重排兩個網路實體之間的通訊，而不需要任何一方的知識。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="0cc3e-123">TLS 和 Lync Server 2013 規格的受信任的伺服器 (僅限) 拓撲產生器中所指定的伺服器，但您可以使用兩個端點之間的公開金鑰密碼協調，以降低部分對應用程式層上之中間人攻擊的風險。而且，攻擊者必須具有對應私密金鑰的有效且受信任的憑證，而且會發佈給用戶端通訊的服務名稱，以解密通訊。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="0cc3e-124">不過，最後，您必須遵循網路基礎結構的最佳安全性作法， (在此案例中的公司 DNS) 。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="0cc3e-125">Lync Server 2013 假設 DNS 伺服器的信任方式與網域控制站和通用類別目錄的信任方式相同，但 DNS 確實會透過防止攻擊者的伺服器對哄騙名稱的要求作出回應，對 DNS 劫持攻擊提供保護層級。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="0cc3e-126">下圖顯示 Lync Server 2013 如何使用 MTLS 建立信任伺服器網路的高層級。</span><span class="sxs-lookup"><span data-stu-id="0cc3e-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="0cc3e-127">**Lync Server 網路中的信任連接**</span><span class="sxs-lookup"><span data-stu-id="0cc3e-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="0cc3e-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="0cc3e-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

