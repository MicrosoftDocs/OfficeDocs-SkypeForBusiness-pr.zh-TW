---
title: Lync Server 2013：監控行動性以取得效能
description: Lync Server 2013：監控行動性以取得效能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562899"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="8aadd-103">在 Lync Server 2013 中監控行動性以取得效能</span><span class="sxs-lookup"><span data-stu-id="8aadd-103">Monitoring mobility for performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aadd-104">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="8aadd-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="8aadd-105">Lync Server 行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 提高前端伺服器和前端集區的負載。</span><span class="sxs-lookup"><span data-stu-id="8aadd-105">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="8aadd-106">即使在行動應用程式最小化時，也會維持伺服器連線的行動裝置，例如執行 Lync 2010 Mobile 的 Android 和 Nokia 裝置，以及執行 Lync 2013 Mobile 之 Android 和 Apple 裝置的負載，會比裝置在最小化行動電話應用程式時終止其連線的裝置的負載更大。</span><span class="sxs-lookup"><span data-stu-id="8aadd-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="8aadd-107">隨著行動使用量的增加，您必須監視行動性效能，以決定何時需要增加容量。</span><span class="sxs-lookup"><span data-stu-id="8aadd-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="8aadd-108">一些限制會影響行動效能：</span><span class="sxs-lookup"><span data-stu-id="8aadd-108">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="8aadd-109">可用記憶體</span><span class="sxs-lookup"><span data-stu-id="8aadd-109">Available memory</span></span>

  - <span data-ttu-id="8aadd-110">要求佇列限制</span><span class="sxs-lookup"><span data-stu-id="8aadd-110">Request queue limit</span></span>

  - <span data-ttu-id="8aadd-111">同時連接</span><span class="sxs-lookup"><span data-stu-id="8aadd-111">Concurrent connections</span></span>

  - <span data-ttu-id="8aadd-112">IIS 佇列長度</span><span class="sxs-lookup"><span data-stu-id="8aadd-112">IIS queue length</span></span>

<span data-ttu-id="8aadd-113">可影響行動效能的伺服器上的其他限制，最多可有十二個同時登入、驗證性、會話續訂及終止。</span><span class="sxs-lookup"><span data-stu-id="8aadd-113">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="8aadd-114">在大多數的部署中，不需要修改這些最大值。</span><span class="sxs-lookup"><span data-stu-id="8aadd-114">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8aadd-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="8aadd-115">In This Section</span></span>

  - [<span data-ttu-id="8aadd-116">在 Lync Server 2013 中監控伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="8aadd-116">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="8aadd-117">在 Lync Server 2013 中監控行動服務和 UCWA 使用狀況</span><span class="sxs-lookup"><span data-stu-id="8aadd-117">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="8aadd-118">在 Lync Server 2013 中設定高效能的行動服務</span><span class="sxs-lookup"><span data-stu-id="8aadd-118">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="8aadd-119">在 Lync Server 2013 中監控 IIS 要求的追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="8aadd-119">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="8aadd-120">Lync Server 2013 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="8aadd-120">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

