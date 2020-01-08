---
title: DNS 摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff58998ef9114baeb7dc7c6462ca0ebaae114f10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="fdfcf-102">在 Lync Server 2013 中的 DNS 摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟</span><span class="sxs-lookup"><span data-stu-id="fdfcf-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdfcf-103">_**主題上次修改日期：** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="fdfcf-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="fdfcf-104">若要為您的部署設定可擴展的訊息和目前狀態通訊協定（XMPP），您可以在外部 DNS 伺服器中建立兩個網域名稱系統（DNS）記錄，將記錄解析成 Edge 伺服器或 Edge 池的存取邊緣服務。</span><span class="sxs-lookup"><span data-stu-id="fdfcf-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="fdfcf-105">可擴展訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="fdfcf-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdfcf-106">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="fdfcf-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="fdfcf-107">稱</span><span class="sxs-lookup"><span data-stu-id="fdfcf-107">FQDN</span></span></th>
<th><span data-ttu-id="fdfcf-108">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="fdfcf-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="fdfcf-109">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="fdfcf-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdfcf-110">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="fdfcf-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="fdfcf-111">_xmpp-_tcp. .com</span><span class="sxs-lookup"><span data-stu-id="fdfcf-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fdfcf-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fdfcf-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fdfcf-113">XMPP [存取邊緣服務] 或 [Edge] 池中的 [proxy 外部介面]。在已啟用 Lync 功能的使用者中，針對所有內部 SIP 網域重複上述步驟，可透過全域原則、使用者所處的網站原則，或套用使用者原則來設定外部存取原則。啟用 Lync 的使用者。</span><span class="sxs-lookup"><span data-stu-id="fdfcf-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="fdfcf-114">您也必須在 XMPP 聯盟夥伴原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="fdfcf-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="fdfcf-115">如需其他詳細資料，請參閱另<strong>請</strong>參閱中的主題</span><span class="sxs-lookup"><span data-stu-id="fdfcf-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdfcf-116">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fdfcf-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fdfcf-117">xmpp.contoso.com （例如）</span><span class="sxs-lookup"><span data-stu-id="fdfcf-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="fdfcf-118">Edge 伺服器或邊緣池託管 XMPP proxy 的存取邊緣服務的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fdfcf-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="fdfcf-119">指向託管 XMPP proxy 服務的存取邊緣服務或 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="fdfcf-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="fdfcf-120">通常，您所建立的 SRV 記錄會指向這個主機（A 或 AAAA）記錄</span><span class="sxs-lookup"><span data-stu-id="fdfcf-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fdfcf-121">請參閱</span><span class="sxs-lookup"><span data-stu-id="fdfcf-121">See Also</span></span>


[<span data-ttu-id="fdfcf-122">在 Lync Server 2013 中設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="fdfcf-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="fdfcf-123">針對 Lync Server 2013 判定 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="fdfcf-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

