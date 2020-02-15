---
title: 'Lync Server 2013: Standard Edition server 的 DNS 需求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe05133865c0aecdb522e203c1ec2d39ff7b824d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="a368a-102">在 [Lync Server 2013 Standard Edition server 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="a368a-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a368a-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="a368a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a368a-104">本節說明 Standard Edition Server 部署所需的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="a368a-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="a368a-105">Standard Edition Server 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a368a-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="a368a-106">下表指定 Lync Server 2013 Standard Edition server 部署的 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="a368a-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a368a-107">部署案例</span><span class="sxs-lookup"><span data-stu-id="a368a-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="a368a-108">DNS 需求</span><span class="sxs-lookup"><span data-stu-id="a368a-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a368a-109">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="a368a-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="a368a-110">一筆內部 A 記錄，用來將伺服器的完整網域名稱 (FQDN) 解析為 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a368a-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a368a-111">自動用戶端登入</span><span class="sxs-lookup"><span data-stu-id="a368a-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="a368a-112">每個支援的 SIP 網域，_sipinternaltls._tcp 的 SRV 記錄。&lt;網域&gt;透過對應的 FQDN，Standard Edition server 的驗證，並將登入的用戶端要求重新導向至連接埠 5061。</span><span class="sxs-lookup"><span data-stu-id="a368a-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="a368a-113">如需詳細資訊，請參閱<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS 需求的用戶端自動登入 Lync Server 2013 中</a>。</span><span class="sxs-lookup"><span data-stu-id="a368a-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a368a-114">整合通訊 (UC) 裝置的裝置更新 Web 服務探索</span><span class="sxs-lookup"><span data-stu-id="a368a-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="a368a-115">一筆內部 A 記錄名稱 ucupdates-r2。&lt;SIP 網域&gt;，解析為 Standard Edition server 主控的裝置更新 Web 服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a368a-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="a368a-116">在 UC 裝置已開啟，但尚未有使用者登入裝置的情況下，此 A 記錄會允許裝置去探索裝載著裝置更新 Web 服務的伺服器並取得更新。</span><span class="sxs-lookup"><span data-stu-id="a368a-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="a368a-117">否則，裝置會透過使用者首次登入時的頻內佈建取得伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="a368a-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="a368a-118">如需詳細資訊，請參閱作業文件中的<a href="lync-server-2013-device-update-web-service.md">Lync Server 2013 中的裝置更新 Web 服務</a>。</span><span class="sxs-lookup"><span data-stu-id="a368a-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a368a-119">支援 HTTP 流量的反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="a368a-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="a368a-120">一筆外部 A 記錄，將外部 Web 伺服陣列 FQDN 解析為反向 Proxy 的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a368a-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="a368a-121">用戶端和 UC 裝置會使用這個記錄來連線至反向 Proxy。</span><span class="sxs-lookup"><span data-stu-id="a368a-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="a368a-122">如需詳細資訊，請參閱規劃文件中的<a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 的判斷 DNS 需求</a>。</span><span class="sxs-lookup"><span data-stu-id="a368a-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a368a-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a368a-123">See Also</span></span>


[<span data-ttu-id="a368a-124">DNS 需求的用戶端自動登入 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="a368a-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="a368a-125">決定針對 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="a368a-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="a368a-126">Lync Server 2013 中的裝置更新 Web 服務</span><span class="sxs-lookup"><span data-stu-id="a368a-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

