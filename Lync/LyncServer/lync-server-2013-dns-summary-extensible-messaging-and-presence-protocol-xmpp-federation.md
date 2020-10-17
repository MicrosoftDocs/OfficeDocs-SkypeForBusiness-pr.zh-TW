---
title: DNS 摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟
description: DNS 摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b8088e30c93faa52c575fefa97e572ed20b6ad9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544799"
---
# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="059dc-103">Lync Server 2013 中的 DNS 摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟</span><span class="sxs-lookup"><span data-stu-id="059dc-103">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="059dc-104">_**主題上次修改日期：** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="059dc-104">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="059dc-105">若要為您的部署設定可延伸的訊息和顯示狀態通訊協定 (XMPP) ，您可以在外部 DNS 伺服器中建立兩個網域名稱系統 (DNS) 記錄，以將記錄解析為 Edge Server 或 Edge 集區的 Access Edge service。</span><span class="sxs-lookup"><span data-stu-id="059dc-105">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="059dc-106">可延伸訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="059dc-106">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="059dc-107">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="059dc-107">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="059dc-108">FQDN</span><span class="sxs-lookup"><span data-stu-id="059dc-108">FQDN</span></span></th>
<th><span data-ttu-id="059dc-109">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="059dc-109">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="059dc-110">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="059dc-110">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="059dc-111">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="059dc-111">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="059dc-112">_xmpp-server._tcp .com</span><span class="sxs-lookup"><span data-stu-id="059dc-112">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="059dc-113">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="059dc-113">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="059dc-114">Access Edge service 或 Edge 集區上的 XMPP proxy 外部介面。針對所有內部 SIP 網域，針對所有內部 SIP 網域，依需要重複此步驟：透過全域原則、使用者所在的網站原則，或套用到啟用 Lync 功能之使用者的使用者原則，可透過外部存取原則的設定允許與 XMPP 聯繫。</span><span class="sxs-lookup"><span data-stu-id="059dc-114">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="059dc-115">您也必須在 XMPP 同盟協力廠商原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="059dc-115">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="059dc-116">如需其他詳細資料，請參閱另 <strong>請</strong> 參閱主題</span><span class="sxs-lookup"><span data-stu-id="059dc-116">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="059dc-117">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="059dc-117">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="059dc-118">xmpp.contoso.com (範例)</span><span class="sxs-lookup"><span data-stu-id="059dc-118">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="059dc-119">Edge Server 或 Edge 集區上主控 XMPP proxy 的 Access Edge service 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="059dc-119">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="059dc-120">指向主控 XMPP proxy 服務的 Access Edge service 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="059dc-120">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="059dc-121">一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</span><span class="sxs-lookup"><span data-stu-id="059dc-121">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="059dc-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="059dc-122">See Also</span></span>


[<span data-ttu-id="059dc-123">在 Lync Server 2013 中設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="059dc-123">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="059dc-124">決定 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="059dc-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

