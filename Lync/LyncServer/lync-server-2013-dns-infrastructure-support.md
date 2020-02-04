---
title: Lync Server 2013：DNS 基礎結構支援
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
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="845c8-102">Lync Server 2013 中的 DNS 基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="845c8-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="845c8-103">_**主題上次修改日期：** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="845c8-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="845c8-104">Lync Server 2013 需要網域名稱系統（DNS），並以下列方式使用：</span><span class="sxs-lookup"><span data-stu-id="845c8-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="845c8-105">探索內部伺服器或池以進行伺服器間的通訊。</span><span class="sxs-lookup"><span data-stu-id="845c8-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="845c8-106">使用戶端能夠探索用於各種 SIP 事務的前端池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="845c8-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="845c8-107">若要將會議的簡單 Url 與主持這些會議的伺服器產生關聯。</span><span class="sxs-lookup"><span data-stu-id="845c8-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="845c8-108">若要讓外部伺服器和用戶端連線到 Edge 伺服器或 HTTP 反向 proxy 以進行立即訊息（IM）或會議。</span><span class="sxs-lookup"><span data-stu-id="845c8-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="845c8-109">若要啟用未登入的整合通訊（UC）裝置，以探索執行裝置更新 Web 服務的前端池或標準版伺服器，請取得更新並傳送記錄。</span><span class="sxs-lookup"><span data-stu-id="845c8-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="845c8-110">若要讓行動用戶端能夠自動探索 Web 服務資源，而不需要使用者在裝置設定中手動輸入 Url。</span><span class="sxs-lookup"><span data-stu-id="845c8-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="845c8-111">針對 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="845c8-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="845c8-112">Lync Server 2013 不支援國際化功能變數名稱（IDNs）。</span><span class="sxs-lookup"><span data-stu-id="845c8-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="845c8-113">您指定的名稱必須與伺服器上設定的電腦名稱相同。</span><span class="sxs-lookup"><span data-stu-id="845c8-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="845c8-114">根據預設，未加入網域之電腦的電腦名稱稱就是簡稱，不是完全合格的功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="845c8-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="845c8-115">拓撲產生器會使用 FQDN，而非簡稱。</span><span class="sxs-lookup"><span data-stu-id="845c8-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="845c8-116">因此，您必須在要部署為邊緣伺服器且未加入網域的電腦名稱稱上設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="845c8-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="845c8-117">在指派 Lync Server、Edge 伺服器和池的 Fqdn 時，<STRONG>只使用標準字元</STRONG>（包括 a-z、A 至 z、0–9和連字號）。</span><span class="sxs-lookup"><span data-stu-id="845c8-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="845c8-118">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="845c8-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="845c8-119">外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（也就是當 FQDN 必須指派給憑證中的 SN）時。</span><span class="sxs-lookup"><span data-stu-id="845c8-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

