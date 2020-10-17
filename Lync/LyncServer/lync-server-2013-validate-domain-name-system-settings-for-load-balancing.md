---
title: Lync Server 2013：驗證負載平衡的網域名稱系統設定
description: Lync Server 2013：驗證負載平衡的網域名稱系統設定。
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
ms.openlocfilehash: a218a79a541e9c9705a8403146fe7e134e8ed827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547229"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="f6786-103">在 Lync Server 2013 中驗證負載平衡的網域名稱系統設定</span><span class="sxs-lookup"><span data-stu-id="f6786-103">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6786-104">_**主題上次修改日期：** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="f6786-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="f6786-p101">若要支援 DNS 負載平衡所使用的 FQDN，您必須佈建 DNS，以將集區 FQDN (如 pool01.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。您應該只包含目前部署之伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f6786-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="f6786-107">此外，如果您要對 Edge 集區使用 DNS 負載平衡，則需要下列 DNS 專案：</span><span class="sxs-lookup"><span data-stu-id="f6786-107">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="f6786-108">對於 Lync Server Access Edge service，集區中的每一部伺服器都必須有一個專案。</span><span class="sxs-lookup"><span data-stu-id="f6786-108">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f6786-109">每個專案都必須解析 Lync Server Access Edge service (的 FQDN，例如，sip.contoso.com) 到集區中某一部 Edge Server 上的 Lync Server Access Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f6786-109">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f6786-110">對於 Lync Server Web 會議 Edge service，集區中的每一部伺服器都必須有一個專案。</span><span class="sxs-lookup"><span data-stu-id="f6786-110">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f6786-111">每個專案都必須解析 Lync Server Web 會議 Edge service (的 FQDN，例如，webconf.contoso.com) 到集區中某一部 Edge Server 上的 Lync Server Web 會議 Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f6786-111">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f6786-112">對於 Lync Server Audio/Video Edge service，集區中的每一部伺服器都必須有一個專案。</span><span class="sxs-lookup"><span data-stu-id="f6786-112">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f6786-113">每個專案都必須解析 Lync Server Audio/Video Edge service 的 FQDN (例如，av.contoso.com) 至集區中某一部 Edge Server 上的 Lync Server Audio/Video Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f6786-113">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f6786-114">如果您想要在 Edge 集區的內部介面上使用 DNS 負載平衡，您必須新增一個 DNS 記錄，以將 Edge 集區的內部 FQDN 解析為集區中每一部伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f6786-114">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="f6786-115">若要確認 DNS 是否傳回 DNS 負載平衡的正確值，您應該使用 nslookup 工具。</span><span class="sxs-lookup"><span data-stu-id="f6786-115">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="f6786-116">若要傳回具有 nslookup 之 DNS 記錄的所有值，您應該執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f6786-116">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="f6786-117">您可以針對 DNS 負載平衡設定中所用的每個 FQDN，執行此命令，以確認 DNS 負載平衡的每一筆記錄都傳回所有正確的專案。</span><span class="sxs-lookup"><span data-stu-id="f6786-117">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

