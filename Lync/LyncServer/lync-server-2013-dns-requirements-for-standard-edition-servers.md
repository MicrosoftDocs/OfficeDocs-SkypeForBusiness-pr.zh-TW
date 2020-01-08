---
title: Lync Server 2013：標準版伺服器的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5e04f23428b073e544b040ed07dc852f1da4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="01dde-102">Lync Server 2013 中標準版伺服器的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="01dde-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01dde-103">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="01dde-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="01dde-104">本節說明部署標準版伺服器所需的網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="01dde-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="01dde-105">標準版伺服器的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="01dde-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="01dde-106">下表指定 Lync Server 2013 標準版伺服器部署的 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="01dde-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="01dde-107">標準版伺服器的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="01dde-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01dde-108">部署案例</span><span class="sxs-lookup"><span data-stu-id="01dde-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="01dde-109">DNS 需求</span><span class="sxs-lookup"><span data-stu-id="01dde-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01dde-110">標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="01dde-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="01dde-111">將伺服器的完整功能變數名稱（FQDN）解析成其 IP 位址的內部 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="01dde-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01dde-112">自動用戶端登入</span><span class="sxs-lookup"><span data-stu-id="01dde-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="01dde-113">針對每個支援的 SIP 網域，_sipinternaltls _tcp 的 SRV 記錄。&lt;經由&gt;埠5061的網域，會對應到標準版 server 的 FQDN，該伺服器會將登入的用戶端要求驗證並重新導向。</span><span class="sxs-lookup"><span data-stu-id="01dde-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="01dde-114">如需詳細資訊，請參閱<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自動用戶端登入 DNS 需求</a>。</span><span class="sxs-lookup"><span data-stu-id="01dde-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01dde-115">透過整合通訊（UC）裝置進行的裝置更新 Web 服務探索</span><span class="sxs-lookup"><span data-stu-id="01dde-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="01dde-116">含 name ucupdates-r2 的內部 A 記錄。&lt;可解析&gt;為標準版伺服器託管裝置更新 Web 服務之 IP 位址的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="01dde-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="01dde-117">在已開啟 UC 裝置，但使用者從未登入裝置的情況下，A 記錄可讓裝置探索託管裝置更新 Web 服務的伺服器，並取得更新。</span><span class="sxs-lookup"><span data-stu-id="01dde-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="01dde-118">否則，在使用者第一次登入時，裝置會透過頻帶內的設定來取得伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="01dde-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01dde-119">支援 HTTP 流量的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="01dde-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="01dde-120">外部 A 記錄，可將外部 web farm FQDN 解析成反向 proxy 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="01dde-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="01dde-121">用戶端和 UC 裝置使用此記錄連線到反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="01dde-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="01dde-122">如需詳細資訊，請參閱在規劃檔中<a href="lync-server-2013-determine-dns-requirements.md">判斷 Lync Server 2013 的 DNS 需求</a>。</span><span class="sxs-lookup"><span data-stu-id="01dde-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

