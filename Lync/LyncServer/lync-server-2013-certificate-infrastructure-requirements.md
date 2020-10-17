---
title: Lync Server 2013 憑證基礎結構需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18666f33becabcbdf61370a32900ae7a4819e0cb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508020"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="98976-102">Lync Server 2013 的憑證基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="98976-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98976-103">_**主題上次修改日期：** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="98976-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="98976-104">Lync Server 2013 需要公開金鑰基礎結構 (PKI) ，以支援 TLS 和相互 TLS (MTLS) 連線。</span><span class="sxs-lookup"><span data-stu-id="98976-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="98976-105">Lync Server 會出於下列目的使用憑證：</span><span class="sxs-lookup"><span data-stu-id="98976-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="98976-106">用戶端及伺服器之間的 TLS 連線</span><span class="sxs-lookup"><span data-stu-id="98976-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="98976-107">伺服器之間的 MTLS 連線</span><span class="sxs-lookup"><span data-stu-id="98976-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="98976-108">使用自動探索協力廠商 DNS 的同盟連線</span><span class="sxs-lookup"><span data-stu-id="98976-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="98976-109">遠端使用者存取即時訊息 (IM)</span><span class="sxs-lookup"><span data-stu-id="98976-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="98976-110">外部使用者存取音訊/視訊 (A/V) 工作階段、應用程式共用及會議</span><span class="sxs-lookup"><span data-stu-id="98976-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="98976-111">使用 Web 服務自動探索的行動要求</span><span class="sxs-lookup"><span data-stu-id="98976-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="98976-112">對於 Lync Server，適用下列一般需求：</span><span class="sxs-lookup"><span data-stu-id="98976-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="98976-113">所有的伺服器憑證必須支援伺服器授權 (伺服器 EKU)。</span><span class="sxs-lookup"><span data-stu-id="98976-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="98976-114">所有的伺服器憑證必須包含一個 CRL 發佈點 (CDP)。</span><span class="sxs-lookup"><span data-stu-id="98976-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="98976-115">所有憑證必須使用作業系統支援的簽署演算法進行簽署。</span><span class="sxs-lookup"><span data-stu-id="98976-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="98976-116">Lync Server 2013 支援摘要大小的 SHA-1 和 SHA-2 套件， (224、256、384和512位) ，以及符合或超過作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="98976-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="98976-117">如需作業系統支援，請參閱 [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) 。</span><span class="sxs-lookup"><span data-stu-id="98976-117">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98976-118">不支援使用 RSASSA-PSS 簽名演算法，而且可能會導致登入和來電轉接問題的錯誤，以及其他問題。</span><span class="sxs-lookup"><span data-stu-id="98976-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="98976-119">執行 Lync Server 的內部伺服器支援自動註冊。</span><span class="sxs-lookup"><span data-stu-id="98976-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="98976-120">Lync Server Edge Server 不支援自動註冊。</span><span class="sxs-lookup"><span data-stu-id="98976-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="98976-121">當您將 Web 憑證要求提交至 Windows Server 2003 CA 時，您必須從執行 Windows Server 2003 (SP2) 或 Windows XP 的電腦進行提交。</span><span class="sxs-lookup"><span data-stu-id="98976-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="98976-122">請注意，雖然 KB922706 可支援解決 Windows Server 2003 憑證服務的網頁註冊功能引發的網頁憑證註冊問題，但仍無法使用 Windows Server 2008、Windows Vista 或 Windows 7 向 Windows Server 2003 CA 要求憑證。</span><span class="sxs-lookup"><span data-stu-id="98976-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="98976-123">支援加密金鑰長度（1024、2048及4096）。</span><span class="sxs-lookup"><span data-stu-id="98976-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="98976-124">建議使用的金鑰長度2048和更大。</span><span class="sxs-lookup"><span data-stu-id="98976-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="98976-125">預設摘要（或雜湊簽署）演算法為 RSA。</span><span class="sxs-lookup"><span data-stu-id="98976-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="98976-126">\_也支援 ecdh P256、ecdh \_ P384 和 ECDH \_ P521 演算法。</span><span class="sxs-lookup"><span data-stu-id="98976-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="98976-127">本章節內容</span><span class="sxs-lookup"><span data-stu-id="98976-127">In This Section</span></span>

  - [<span data-ttu-id="98976-128">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="98976-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="98976-129">Lync Server 2013 中外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="98976-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="98976-130">Lync Server 2013 中 Persistent Chat server 的憑證需求</span><span class="sxs-lookup"><span data-stu-id="98976-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="98976-131">Lync Server 2013 中行動的憑證需求</span><span class="sxs-lookup"><span data-stu-id="98976-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

