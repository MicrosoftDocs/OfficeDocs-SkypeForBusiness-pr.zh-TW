---
title: Lync Server 2013 憑證基礎結構需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="48af5-102">Lync Server 2013 的憑證基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="48af5-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48af5-103">_**主題上次修改日期：** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="48af5-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="48af5-104">Lync Server 2013 需要公開金鑰基礎結構（PKI）來支援 TLS 和相互 TLS （MTLS）連線。</span><span class="sxs-lookup"><span data-stu-id="48af5-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="48af5-105">Lync Server 使用憑證的目的如下：</span><span class="sxs-lookup"><span data-stu-id="48af5-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="48af5-106">用戶端與伺服器之間的 TLS 連接</span><span class="sxs-lookup"><span data-stu-id="48af5-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="48af5-107">伺服器之間的 MTLS 連線</span><span class="sxs-lookup"><span data-stu-id="48af5-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="48af5-108">使用合作夥伴自動 DNS 探索的同盟</span><span class="sxs-lookup"><span data-stu-id="48af5-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="48af5-109">立即訊息（IM）的遠端使用者存取權</span><span class="sxs-lookup"><span data-stu-id="48af5-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="48af5-110">外部使用者存取音訊/視頻（A/V）會話、應用程式共用和會議</span><span class="sxs-lookup"><span data-stu-id="48af5-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="48af5-111">使用自動探索 Web 服務的行動要求</span><span class="sxs-lookup"><span data-stu-id="48af5-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="48af5-112">對於 Lync Server，請遵循下列常見需求：</span><span class="sxs-lookup"><span data-stu-id="48af5-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="48af5-113">所有伺服器憑證都必須支援伺服器授權（伺服器 EKU）。</span><span class="sxs-lookup"><span data-stu-id="48af5-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="48af5-114">所有伺服器憑證都必須包含 CRL 發佈點（CDP）。</span><span class="sxs-lookup"><span data-stu-id="48af5-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="48af5-115">所有憑證都必須使用作業系統支援的簽名演算法進行簽署。</span><span class="sxs-lookup"><span data-stu-id="48af5-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="48af5-116">Lync Server 2013 支援 SHA-1 和 SHA-1 組成的摘要式大小（224、256、384和512），並符合或超過作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="48af5-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="48af5-117">如需作業系統支援，請[http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)參閱。</span><span class="sxs-lookup"><span data-stu-id="48af5-117">For operating system support, see [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48af5-118">不支援使用 RSASSA-PSS 簽章演算法，而且可能會導致登入和來電轉接問題等錯誤，以及其他問題。</span><span class="sxs-lookup"><span data-stu-id="48af5-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="48af5-119">運行 Lync Server 的內部伺服器支援自動註冊。</span><span class="sxs-lookup"><span data-stu-id="48af5-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="48af5-120">Lync Server Edge 伺服器不支援自動註冊。</span><span class="sxs-lookup"><span data-stu-id="48af5-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="48af5-121">當您將 web 型證書申請提交至 Windows Server 2003 CA 時，您必須從執行 Windows Server 2003 的電腦，以 SP2 或 Windows XP 提交。</span><span class="sxs-lookup"><span data-stu-id="48af5-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="48af5-122">請注意，雖然 KB922706 提供支援，以解決針對 Windows Server 2003 憑證服務 web 登記註冊 web 憑證的問題，但它不能使用 Windows Server 2008、Windows Vista 或 Windows 7 來要求進行來自 Windows Server 2003 CA 的憑證。</span><span class="sxs-lookup"><span data-stu-id="48af5-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="48af5-123">支援1024、2048和4096的加密金鑰長度。</span><span class="sxs-lookup"><span data-stu-id="48af5-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="48af5-124">建議使用2048和更大的金鑰長度。</span><span class="sxs-lookup"><span data-stu-id="48af5-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="48af5-125">預設摘要（即雜湊簽章）演算法是 RSA。</span><span class="sxs-lookup"><span data-stu-id="48af5-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="48af5-126">還支援\_ecdh P256、\_ecdh P384 和 ECDH\_P521 演算法。</span><span class="sxs-lookup"><span data-stu-id="48af5-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="48af5-127">本節內容</span><span class="sxs-lookup"><span data-stu-id="48af5-127">In This Section</span></span>

  - [<span data-ttu-id="48af5-128">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="48af5-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="48af5-129">Lync Server 2013 中的外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="48af5-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="48af5-130">Lync Server 2013 中的常設聊天室伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="48af5-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="48af5-131">Lync Server 2013 中的行動憑證需求</span><span class="sxs-lookup"><span data-stu-id="48af5-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

