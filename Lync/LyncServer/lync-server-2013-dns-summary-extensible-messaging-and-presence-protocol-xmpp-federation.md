---
title: DNS 摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟
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
ms.openlocfilehash: cb892d973a8da1bb7b3ea66e10082504342483b5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="a4154-102">DNS 摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="a4154-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4154-103">_**上次修改主題：** 2014年-04-08_</span><span class="sxs-lookup"><span data-stu-id="a4154-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="a4154-104">若要設定可延伸訊息和顯示狀態通訊協定 (XMPP) 部署，您可以建立兩個網域名稱系統 (DNS) 記錄會將記錄解析至 Edge Server 或 Edge 集區的 [Access Edge service 的外部 DNS 伺服器中。</span><span class="sxs-lookup"><span data-stu-id="a4154-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="a4154-105">可延伸訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="a4154-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4154-106">位置/類型/連接埠</span><span class="sxs-lookup"><span data-stu-id="a4154-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="a4154-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="a4154-107">FQDN</span></span></th>
<th><span data-ttu-id="a4154-108">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="a4154-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="a4154-109">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="a4154-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4154-110">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="a4154-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="a4154-111">_xmpp server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4154-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a4154-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4154-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a4154-113">XMPP proxy 外部介面的 Access Edge 服務或 Edge 集區。視您的 Lync 所有內部 SIP 網域重複啟用與 XMPP 連絡人的連絡人允許透過全域原則、 使用者所在的網站原則或使用者原則套用到的外部存取原則設定的位置的使用者啟用 Lync 功能的使用者。</span><span class="sxs-lookup"><span data-stu-id="a4154-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="a4154-114">允許的 XMPP 網域也必須設定 XMPP 同盟協力廠商原則中。</span><span class="sxs-lookup"><span data-stu-id="a4154-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="a4154-115">請參閱如需詳細資訊<strong>請參閱</strong>主題</span><span class="sxs-lookup"><span data-stu-id="a4154-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4154-116">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="a4154-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a4154-117">xmpp.contoso.com (範例)</span><span class="sxs-lookup"><span data-stu-id="a4154-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="a4154-118">IP 位址的 Access Edge service 上您的 Edge Server 或 Edge 集區裝載 XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="a4154-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="a4154-119">指向 Access Edge service 或裝載 XMPP proxy 服務的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="a4154-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="a4154-120">一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</span><span class="sxs-lookup"><span data-stu-id="a4154-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a4154-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a4154-121">See Also</span></span>


[<span data-ttu-id="a4154-122">設定 Lync Server 2013 中的 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="a4154-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="a4154-123">決定針對 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="a4154-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

