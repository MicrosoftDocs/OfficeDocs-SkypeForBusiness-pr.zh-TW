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
ms.openlocfilehash: 3dd1aa5bdde1c94e3d0558be14c67cf62ec8142a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="54c4f-102">Lync Server 2013 的憑證基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="54c4f-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c4f-103">_**主題上次修改日期：** 2016年-06-23_</span><span class="sxs-lookup"><span data-stu-id="54c4f-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="54c4f-104">Lync Server 2013 需要公開金鑰基礎結構 (PKI) 來支援 TLS 和相互 TLS (MTLS) 連線。</span><span class="sxs-lookup"><span data-stu-id="54c4f-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="54c4f-105">Lync Server 會基於下列目的使用憑證：</span><span class="sxs-lookup"><span data-stu-id="54c4f-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="54c4f-106">用戶端及伺服器之間的 TLS 連線</span><span class="sxs-lookup"><span data-stu-id="54c4f-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="54c4f-107">伺服器之間的 MTLS 連線</span><span class="sxs-lookup"><span data-stu-id="54c4f-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="54c4f-108">使用自動探索協力廠商 DNS 的同盟連線</span><span class="sxs-lookup"><span data-stu-id="54c4f-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="54c4f-109">遠端使用者存取即時訊息 (IM)</span><span class="sxs-lookup"><span data-stu-id="54c4f-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="54c4f-110">外部使用者存取音訊/視訊 (A/V) 工作階段、應用程式共用及會議</span><span class="sxs-lookup"><span data-stu-id="54c4f-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="54c4f-111">使用 Web 服務自動探索的行動要求</span><span class="sxs-lookup"><span data-stu-id="54c4f-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="54c4f-112">Lync server，適用下列一般需求：</span><span class="sxs-lookup"><span data-stu-id="54c4f-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="54c4f-113">所有的伺服器憑證必須支援伺服器授權 (伺服器 EKU)。</span><span class="sxs-lookup"><span data-stu-id="54c4f-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="54c4f-114">所有的伺服器憑證必須包含一個 CRL 發佈點 (CDP)。</span><span class="sxs-lookup"><span data-stu-id="54c4f-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="54c4f-115">必須使用支援的作業系統簽署演算法簽署所有憑證。</span><span class="sxs-lookup"><span data-stu-id="54c4f-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="54c4f-116">Lync Server 2013 支援 sha-1 和摘要 sha-2 套件調整大小 （224 256、 384，512 位元），並使用符合或超過作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="54c4f-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="54c4f-117">如需作業系統支援，請參閱[https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002)。</span><span class="sxs-lookup"><span data-stu-id="54c4f-117">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c4f-118">使用 RSASSA PSS 簽章演算法是不受支援，並登入和來電轉接問題，請在其他問題可能會導致錯誤。</span><span class="sxs-lookup"><span data-stu-id="54c4f-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="54c4f-119">執行 Lync Server 的內部伺服器支援自動註冊。</span><span class="sxs-lookup"><span data-stu-id="54c4f-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="54c4f-120">Lync Server Edge Server 不支援自動註冊。</span><span class="sxs-lookup"><span data-stu-id="54c4f-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="54c4f-121">當您將 Web 憑證要求提交至 Windows Server 2003 CA 時，您必須從執行 Windows Server 2003 (SP2) 或 Windows XP 的電腦進行提交。</span><span class="sxs-lookup"><span data-stu-id="54c4f-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="54c4f-122">請注意，雖然 KB922706 可支援解決 Windows Server 2003 憑證服務的網頁註冊功能引發的網頁憑證註冊問題，但仍無法使用 Windows Server 2008、Windows Vista 或 Windows 7 向 Windows Server 2003 CA 要求憑證。</span><span class="sxs-lookup"><span data-stu-id="54c4f-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="54c4f-123">支援的加密金鑰長度為 1024年、 2048年和 4096。</span><span class="sxs-lookup"><span data-stu-id="54c4f-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="54c4f-124">建議的金鑰長度為 2048年和更新版本。</span><span class="sxs-lookup"><span data-stu-id="54c4f-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="54c4f-125">預設值之摘要，或雜湊簽章演算法是 RSA。</span><span class="sxs-lookup"><span data-stu-id="54c4f-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="54c4f-126">ECDH\_P256、 ECDH\_P384 和 ECDH\_也支援 P521 演算法。</span><span class="sxs-lookup"><span data-stu-id="54c4f-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="54c4f-127">本章節內容</span><span class="sxs-lookup"><span data-stu-id="54c4f-127">In This Section</span></span>

  - [<span data-ttu-id="54c4f-128">適用於 Lync Server 2013 中的內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="54c4f-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="54c4f-129">Lync Server 2013 中的外部使用者存取的憑證需求</span><span class="sxs-lookup"><span data-stu-id="54c4f-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - <span data-ttu-id="54c4f-130">[在 [Lync Server 2013 常設聊天室伺服器的憑證需求](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="54c4f-130">[Certificate requirements for Persistent Chat server in Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)</span></span>

  - [<span data-ttu-id="54c4f-131">Lync Server 2013 中的行動的憑證需求</span><span class="sxs-lookup"><span data-stu-id="54c4f-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

