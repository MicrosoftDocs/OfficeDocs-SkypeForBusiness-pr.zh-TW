---
title: Lync Server 2013： 監控行動性效能
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
ms.openlocfilehash: 131a6a4dd6fffb3081ff2b1dee58318afd525eaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="1cc85-102">Lync Server 2013 的效能監控行動性</span><span class="sxs-lookup"><span data-stu-id="1cc85-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cc85-103">_**上次修改主題：** 2013年-02-14_</span><span class="sxs-lookup"><span data-stu-id="1cc85-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="1cc85-104">Lync Server 行動性服務 (Mcx) 和 Unified Communications Web API (UCWA) 增加前端伺服器和前端集區上的負載。</span><span class="sxs-lookup"><span data-stu-id="1cc85-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="1cc85-105">維護伺服器的連線，即使當行動應用程式最小化，例如 Android 和 Nokia 裝置執行 Lync 2010 Mobile，以及執行 Lync 2013 行動、 Android 和 Apple 裝置的行動裝置加諸更大的負載，比裝置，當行動應用程式最小化時，終止其連線至伺服器。</span><span class="sxs-lookup"><span data-stu-id="1cc85-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="1cc85-106">當您行動性使用情況增加時，您必須監視行動效能，以決定當您需要增加容量。</span><span class="sxs-lookup"><span data-stu-id="1cc85-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="1cc85-107">有多個限制會影響行動效能：</span><span class="sxs-lookup"><span data-stu-id="1cc85-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="1cc85-108">可用的記憶體</span><span class="sxs-lookup"><span data-stu-id="1cc85-108">Available memory</span></span>

  - <span data-ttu-id="1cc85-109">要求佇列限制</span><span class="sxs-lookup"><span data-stu-id="1cc85-109">Request queue limit</span></span>

  - <span data-ttu-id="1cc85-110">並行連線</span><span class="sxs-lookup"><span data-stu-id="1cc85-110">Concurrent connections</span></span>

  - <span data-ttu-id="1cc85-111">IIS 佇列長度</span><span class="sxs-lookup"><span data-stu-id="1cc85-111">IIS queue length</span></span>

<span data-ttu-id="1cc85-112">其他可能會影響行動效能的伺服器上的限制是最多 12 個並行登入、 驗證、 工作階段續訂和終止。</span><span class="sxs-lookup"><span data-stu-id="1cc85-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="1cc85-113">若要修改大部分的部署不需要這些最大值。</span><span class="sxs-lookup"><span data-stu-id="1cc85-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1cc85-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1cc85-114">In This Section</span></span>

  - [<span data-ttu-id="1cc85-115">監控的 Lync Server 2013 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="1cc85-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="1cc85-116">監控 Mobility Service 和 ucwa 的參考 Lync Server 2013 中的使用狀況</span><span class="sxs-lookup"><span data-stu-id="1cc85-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="1cc85-117">設定 Lync Server 2013 中的高效能的 Mobility Service</span><span class="sxs-lookup"><span data-stu-id="1cc85-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="1cc85-118">監控 IIS 要求在 Lync Server 2013 中的追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="1cc85-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="1cc85-119">Lync Server 2013 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="1cc85-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

