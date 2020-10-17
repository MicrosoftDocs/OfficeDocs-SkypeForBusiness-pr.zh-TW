---
title: Lync Server 2013： DNS 基礎結構支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed40fb498b93f0c6f3b1a8d32c7642f7714998ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528940"
---
# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="6a24c-102">Lync Server 2013 中的 DNS 基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="6a24c-102">DNS infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a24c-103">_**主題上次修改日期：** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="6a24c-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="6a24c-104">Lync Server 2013 需要網域名稱系統 (DNS) ，並以下列方式使用：</span><span class="sxs-lookup"><span data-stu-id="6a24c-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="6a24c-105">探索內部伺服器或集區以進行伺服器對伺服器的通訊。</span><span class="sxs-lookup"><span data-stu-id="6a24c-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="6a24c-106">讓用戶端可探索用於各種 SIP 交易的前端集區或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="6a24c-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="6a24c-107">將會議的簡單 URL 與裝載這些會議的伺服器產生關聯。</span><span class="sxs-lookup"><span data-stu-id="6a24c-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="6a24c-108">讓外部伺服器與用戶端可連線至 Edge Server 或 HTTP 反向 Proxy 以進行立即訊息 (IM) 或會議。</span><span class="sxs-lookup"><span data-stu-id="6a24c-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="6a24c-109">讓未登入的整合通訊 (UC) 裝置可探索執行裝置更新 Web 服務的前端集區或 Standard Edition Server 以取得更新以及傳送記錄檔。</span><span class="sxs-lookup"><span data-stu-id="6a24c-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="6a24c-110">讓行動用戶端能自動探索 Web 服務資源，而不需使用者手動在裝置設定中輸入 URL。</span><span class="sxs-lookup"><span data-stu-id="6a24c-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="6a24c-111">進行 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="6a24c-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a24c-112">Lync Server 2013 不支援 (Idn) 中的國際化功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="6a24c-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6a24c-113">您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。</span><span class="sxs-lookup"><span data-stu-id="6a24c-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="6a24c-114">根據預設，未加入網域的電腦，其電腦名稱是簡短名稱，而不是完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="6a24c-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="6a24c-115">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="6a24c-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6a24c-116">因此，在未加入網域但要部署為 Edge Server 電腦的電腦名稱中，您必須設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="6a24c-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="6a24c-117">當您為 Lync Server、Edge Server 以及集區指派 FQDN 時，只能使用標準字元<STRONG></STRONG> (包括 A–Z、a–z、0–9 與連字號)。</span><span class="sxs-lookup"><span data-stu-id="6a24c-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="6a24c-118">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="6a24c-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6a24c-119">也就是當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="6a24c-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

