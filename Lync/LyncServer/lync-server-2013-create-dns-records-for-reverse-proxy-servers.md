---
title: Lync Server 2013：建立反向 Proxy 伺服器的 DNS 記錄
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
ms.openlocfilehash: 0f85b222688dcefd45030f2c05f7b59ce45ec0ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="2ac31-102">在 Lync Server 2013 中建立反向 Proxy 伺服器的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2ac31-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ac31-103">_**主題上次修改日期：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="2ac31-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="2ac31-104">針對[Lync Server 2013 中的 [設定 DNS 以取得 edge 支援](lync-server-2013-configure-dns-for-edge-support.md)] 中所述，建立外部 DNS A 指向 Microsoft 網際網路安全性與加速（ISA） server 2006 2010 SP1 的公用外部介面的記錄。</span><span class="sxs-lookup"><span data-stu-id="2ac31-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="2ac31-105">您需要針對每個池、Director （或主管池）及每個簡單的 URL 的外部 Web 服務 Fqdn 的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ac31-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="2ac31-106">用戶端解析到反向 proxy 的最小 DNS 記錄，必須建立下列記錄：</span><span class="sxs-lookup"><span data-stu-id="2ac31-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="2ac31-107">為控制器和控制器池定義已發佈的外部 web 服務的主機（A）記錄（例如， **webdirext.contoso.com**）</span><span class="sxs-lookup"><span data-stu-id="2ac31-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="2ac31-108">針對任何前端池和標準版伺服器角色（例如**webext.contoso.com**）所裝載之外部 web 服務的主機（A）記錄定義已發佈的外部 web 服務</span><span class="sxs-lookup"><span data-stu-id="2ac31-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="2ac31-109">簡單 Url 的主機（A）記錄（例如**dialin.contoso.com**和**meet.contoso.com**）</span><span class="sxs-lookup"><span data-stu-id="2ac31-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="2ac31-110">Lync 探索外部記錄的主機（A）記錄，也提供所有 Web 應用程式的自動探索的指標，包括 Lync Web App、排程及行動性（例如， **lyncdiscover.contoso.com**）</span><span class="sxs-lookup"><span data-stu-id="2ac31-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="2ac31-111">Office Web Apps Server URL 的主機（A）記錄（例如**officewebapp01.contoso.com**）</span><span class="sxs-lookup"><span data-stu-id="2ac31-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="2ac31-112">如需詳細資訊，請參閱[Lync Server 2013 中的 [DNS 摘要-反向 proxy](lync-server-2013-dns-summary-reverse-proxy.md)]。</span><span class="sxs-lookup"><span data-stu-id="2ac31-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

