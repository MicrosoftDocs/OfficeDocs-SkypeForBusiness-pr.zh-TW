---
title: Lync Server 2013：建立反向 proxy 伺服器的 DNS 記錄
description: Lync Server 2013：建立反向 proxy 伺服器的 DNS 記錄。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef785ebbd7160274b631a2d2b6b1f1dcc866e5fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562279"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="c1e37-103">在 Lync Server 2013 中建立反向 proxy 伺服器的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="c1e37-103">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1e37-104">_**主題上次修改日期：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="c1e37-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="c1e37-105">建立外部 DNS A 記錄，指向 Microsoft Internet 安全性和加速度的公用外部介面 (ISA) Server 2006 SP1、Forefront 威脅管理閘道2010伺服器或網際網路資訊伺服器應用程式要求路由，如在 [Lync Server 2013 中設定 edge 支援的 DNS](lync-server-2013-configure-dns-for-edge-support.md)所述。</span><span class="sxs-lookup"><span data-stu-id="c1e37-105">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="c1e37-106">您需要每個集區的外部 Web 服務 Fqdn 的 DNS 記錄、Director (或 Director 集區) ，以及每個簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="c1e37-106">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="c1e37-107">用戶端解析為反向 proxy 的最低 DNS 記錄，必須建立下列記錄：</span><span class="sxs-lookup"><span data-stu-id="c1e37-107">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="c1e37-108">Host () record (s) ，可定義 Director 及 Director 集區的已發佈外部 web 服務 (例如， **webdirext.contoso.com**) </span><span class="sxs-lookup"><span data-stu-id="c1e37-108">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="c1e37-109">Host () record (s) ，它會為主控于任何前端集區和 Standard Edition server role 上的外部 web 服務定義發佈的外部 web 服務 (例如， **webext.contoso.com**) </span><span class="sxs-lookup"><span data-stu-id="c1e37-109">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="c1e37-110">主機 (簡單 URLs (的) 記錄，例如 **dialin.contoso.com** 和 **meet.contoso.com**) </span><span class="sxs-lookup"><span data-stu-id="c1e37-110">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="c1e37-111">主機 (Lync 探索外部記錄的) 記錄，也提供所有 Web 應用程式的 AutoDiscover 指標，包括 Lync Web App、排程器和行動性 (例如， **lyncdiscover.contoso.com**) </span><span class="sxs-lookup"><span data-stu-id="c1e37-111">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="c1e37-112">主機 (Office Web Apps Server URL 的) 記錄， (例如 **officewebapp01.contoso.com**) </span><span class="sxs-lookup"><span data-stu-id="c1e37-112">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="c1e37-113">如需詳細資訊，請參閱 [Lync Server 2013 中的 DNS 摘要-反向 proxy](lync-server-2013-dns-summary-reverse-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e37-113">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

