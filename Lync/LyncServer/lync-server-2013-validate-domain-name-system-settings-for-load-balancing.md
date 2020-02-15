---
title: Lync Server 2013： 驗證網域名稱系統設定負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cc1766ad11a5a6b7933d95b2c3e1182ff8ffc6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="c5c72-102">驗證 Lync Server 2013 中的負載平衡的網域名稱系統設定</span><span class="sxs-lookup"><span data-stu-id="c5c72-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5c72-103">_**上次修改主題：** 2014年-05-02_</span><span class="sxs-lookup"><span data-stu-id="c5c72-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="c5c72-p101">若要支援 DNS 負載平衡所使用的 FQDN，您必須佈建 DNS，以將集區 FQDN (如 pool01.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。您應該只包含目前部署之伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c5c72-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="c5c72-106">此外使用 DNS 負載平衡 Edge 集區的下列 DNS 項目需要：</span><span class="sxs-lookup"><span data-stu-id="c5c72-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="c5c72-107">為 Lync Server Access Edge 服務] 中，您必須為每個伺服器的一個項目集區中。</span><span class="sxs-lookup"><span data-stu-id="c5c72-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="c5c72-108">每個項目必須解決的 FQDN，Lync Server Access Edge 服務 (例如 sip.contoso.com) 上下列其中一個 Edge Server 集區中的 Lync Server Access Edge 服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c5c72-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="c5c72-109">Lync Server Web Conferencing Edge service，您必須為每個伺服器的一個項目集區中。</span><span class="sxs-lookup"><span data-stu-id="c5c72-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="c5c72-110">每個項目必須解決的 FQDN，Lync Server Web Conferencing Edge service (例如，webconf.contoso.com) 上下列其中一個 Edge Server 集區中的 Lync Server Web 會議 Edge 服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c5c72-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="c5c72-111">Lync Server Audio/Video Edge service，您必須為每個伺服器的一個項目集區中。</span><span class="sxs-lookup"><span data-stu-id="c5c72-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="c5c72-112">每個項目必須為下列其中一個 Edge Server 集區中的 Lync Server Audio/Video Edge 服務 IP 位址解析 Lync Server Audio/Video Edge service (例如，av.contoso.com) 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5c72-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="c5c72-113">如果您想要使用 DNS 負載平衡 Edge 集區的內部介面上，您必須新增一個內部 Edge 集區 FQDN 解析為集區中每部伺服器的 IP 位址的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="c5c72-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="c5c72-114">若要確認 DNS 會傳回正確的值為 DNS 負載平衡您應該使用 nslookup 工具。</span><span class="sxs-lookup"><span data-stu-id="c5c72-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="c5c72-115">若要傳回所有具有 nslookup 的 DNS 記錄的值，您應該執行命令：</span><span class="sxs-lookup"><span data-stu-id="c5c72-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="c5c72-116">您可以執行此命令來確認每一筆記錄設定 DNS 負載平衡傳回所有的正確的項目使用 DNS 負載平衡組態中每個 fqdn。</span><span class="sxs-lookup"><span data-stu-id="c5c72-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

