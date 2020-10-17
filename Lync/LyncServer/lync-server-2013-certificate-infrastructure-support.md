---
title: Lync Server 2013 憑證基礎結構支援
description: Lync Server 2013 憑證基礎結構支援。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc08719e5b1c58a4dc3c1cab07db5e9842d46d5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544229"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="baf01-103">Lync Server 2013 中的憑證基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="baf01-103">Certificate infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baf01-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="baf01-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="baf01-105">Lync Server 2013 需要公開金鑰基礎結構 (PKI) ，以支援傳輸層安全性 (TLS) 及相互 TLS (MTLS) 連線。</span><span class="sxs-lookup"><span data-stu-id="baf01-105">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="baf01-106">根據預設，Lync Server 2013 設定為使用 TLS 進行用戶端對伺服器連線。</span><span class="sxs-lookup"><span data-stu-id="baf01-106">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="baf01-107">MTLS 是用於伺服器之間的連線。</span><span class="sxs-lookup"><span data-stu-id="baf01-107">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="baf01-108">MTLS 憑證必須由受信任的憑證授權單位單位所發出 () Lync Server 2013 的 CAs。</span><span class="sxs-lookup"><span data-stu-id="baf01-108">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="baf01-109">Lync Server 支援從下列 Ca 發出的憑證：</span><span class="sxs-lookup"><span data-stu-id="baf01-109">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="baf01-110">內部 CA 發行的憑證：</span><span class="sxs-lookup"><span data-stu-id="baf01-110">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="baf01-111">Windows Server 2003 作業系統 CA</span><span class="sxs-lookup"><span data-stu-id="baf01-111">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="baf01-112">Windows Server 2008 作業系統 CA</span><span class="sxs-lookup"><span data-stu-id="baf01-112">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="baf01-113">Windows Server 2008 R2 作業系統 CA</span><span class="sxs-lookup"><span data-stu-id="baf01-113">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="baf01-114">Windows Server 2012 作業系統 CA</span><span class="sxs-lookup"><span data-stu-id="baf01-114">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="baf01-115">Windows Server 2012 R2 作業系統 CA</span><span class="sxs-lookup"><span data-stu-id="baf01-115">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="baf01-116">公用 CA 發行的憑證</span><span class="sxs-lookup"><span data-stu-id="baf01-116">Certificates issued from a public CA</span></span>

<span data-ttu-id="baf01-117">與其他應用程式和伺服器進行通訊，例如 Exchange 2013，需要另一個應用程式和產品所支援的憑證。</span><span class="sxs-lookup"><span data-stu-id="baf01-117">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="baf01-118">針對2013版本，Lync Server 2013 和其他 Microsoft server 產品（包括 Exchange 2013 和 SharePoint 伺服器）都支援「開放授權」 (OAuth 伺服器對伺服器驗證和授權的) 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="baf01-118">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="baf01-119">如需詳細資訊，請參閱部署檔或作業檔中的 [管理 Lync server 2013 中的伺服器對伺服器驗證 (OAuth) 和夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 。</span><span class="sxs-lookup"><span data-stu-id="baf01-119">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="baf01-120">針對來自執行 Windows 7 作業系統、Windows Server 2008 R2 作業系統和 Microsoft Office Communicator 2007 Phone Edition 之用戶端的連線，Lync Server 2013 包含對 (的支援，但不需要使用 SHA-256 加密雜湊函數簽署) 憑證。</span><span class="sxs-lookup"><span data-stu-id="baf01-120">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="baf01-121">為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。</span><span class="sxs-lookup"><span data-stu-id="baf01-121">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="baf01-122">如需憑證需求的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 的憑證基礎結構需求](lync-server-2013-certificate-infrastructure-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="baf01-122">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="baf01-123">如需使用萬用字元搭配憑證的詳細資訊，請參閱支援檔中的 [通配憑證支援（Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="baf01-123">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

