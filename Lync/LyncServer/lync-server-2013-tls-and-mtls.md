---
title: 'Lync Server 2013: TLS 和 MTLS'
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
ms.openlocfilehash: 39c3d9dbaeb4c630445b832ab8f220c209461837
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="7321b-102">Lync Server 2013 的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="7321b-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7321b-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="7321b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7321b-104">傳輸層安全性 (TLS) 和相互傳輸層安全性 (MTLS) 通訊協定會提供加密的通訊和端點驗證在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="7321b-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="7321b-105">Microsoft Lync Server 2013 使用這些兩個通訊協定，若要建立受信任伺服器的網路，並確保該網路上的所有通訊會都加密。</span><span class="sxs-lookup"><span data-stu-id="7321b-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="7321b-106">透過 MTLS 發生伺服器之間的所有 SIP 通訊。</span><span class="sxs-lookup"><span data-stu-id="7321b-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="7321b-107">從用戶端到伺服器的 SIP 通訊發生透過 TLS。</span><span class="sxs-lookup"><span data-stu-id="7321b-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="7321b-108">TLS 可讓使用者，透過其用戶端軟體，驗證使用者連線的 Lync Server 2013 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7321b-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="7321b-109">在 TLS 連線，用戶端向伺服器要求的有效憑證。</span><span class="sxs-lookup"><span data-stu-id="7321b-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="7321b-110">若要有效，憑證必須有已由 CA 發行也信任由用戶端和伺服器的 DNS 名稱必須符合憑證上的 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="7321b-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="7321b-111">如果憑證是否有效中加密的對稱式加密憑證, 的公開金鑰的按鍵來進行通訊，使用用戶端使用，只讓憑證的原始擁有者可以使用其私密金鑰解密的通訊內容。</span><span class="sxs-lookup"><span data-stu-id="7321b-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="7321b-112">產生的連線受到信任，因此由其他受信任的伺服器或用戶端不挑戰從該點。</span><span class="sxs-lookup"><span data-stu-id="7321b-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="7321b-113">在此情況下，Secure Sockets Layer (SSL) 用於 Web 服務可以做為 TLS 型相關聯。</span><span class="sxs-lookup"><span data-stu-id="7321b-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="7321b-114">伺服器對伺服器的連線自信地仰賴 MTLS 相互驗證。</span><span class="sxs-lookup"><span data-stu-id="7321b-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="7321b-115">MTLS 連線時，原始郵件伺服器和伺服器接收其 exchange 從相互信任的 CA 的憑證。</span><span class="sxs-lookup"><span data-stu-id="7321b-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="7321b-116">憑證證明其他每個伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="7321b-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="7321b-117">在 Lync Server 2013 部署中，企業 CA 所發出的憑證期間及未撤銷由發行 CA 其有效性的自動視為有效所有內部用戶端和伺服器因為 Active Directory 網域中的所有成員信任的網域中的企業 CA。</span><span class="sxs-lookup"><span data-stu-id="7321b-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="7321b-118">在同盟案例中，必須由這兩個同盟協力廠商信任發出憑證的 CA。</span><span class="sxs-lookup"><span data-stu-id="7321b-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="7321b-119">每個合作夥伴可以使用不同的 CA，如有需要，只要其他協力廠商也信任的 CA。</span><span class="sxs-lookup"><span data-stu-id="7321b-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="7321b-120">Edge Server 需要合作夥伴的根 CA 憑證在其受信任的根 Ca，或使用協力廠商 CA 所信任的雙方，是最容易達成此信任。</span><span class="sxs-lookup"><span data-stu-id="7321b-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="7321b-121">TLS 和 MTLS 協助防止竊聽和人在中間攻擊。</span><span class="sxs-lookup"><span data-stu-id="7321b-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="7321b-122">在攔截攻擊，攻擊者變更路徑透過任一廠商不知情的攻擊者電腦的兩個網路實體之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="7321b-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="7321b-123">TLS 和受信任的伺服器 （僅限那些拓撲產生器中指定） 的 Lync Server 2013 規格減輕部分上應用程式層人在中間攻擊的風險使用國際使用公開金鑰加密的端對端加密兩個端點，之間和攻擊者必須有對應的私用金鑰和發行的通訊用戶端解密通訊的服務名稱有效且受信任憑證。</span><span class="sxs-lookup"><span data-stu-id="7321b-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="7321b-124">最後，不過，您必須遵循最佳安全性作法與您的網路基礎結構 (在此情況下公司 DNS)。</span><span class="sxs-lookup"><span data-stu-id="7321b-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="7321b-125">Lync Server 2013 假設 DNS 伺服器的信任的網域控制站和通用類別目錄是受信任，但 DNS 藉由防止攻擊者的伺服器已成功回應提供針對 DNS 挾攻擊的保護層級的相同方式要求的詐騙的名稱。</span><span class="sxs-lookup"><span data-stu-id="7321b-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="7321b-126">下圖顯示高層級的 Lync Server 2013 如何使用 MTLS 建立受信任伺服器的網路。</span><span class="sxs-lookup"><span data-stu-id="7321b-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="7321b-127">**Lync Server 網路中的信任的連線**</span><span class="sxs-lookup"><span data-stu-id="7321b-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="7321b-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="7321b-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

