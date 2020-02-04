---
title: Lync Server 2013：監視行動性以提高效能
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
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="2878c-102">在 Lync Server 2013 中監控行動能力以提高效能</span><span class="sxs-lookup"><span data-stu-id="2878c-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2878c-103">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="2878c-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="2878c-104">Lync Server 行動服務（Mcx）和整合通訊網頁 API （UCWA）會增加前端伺服器和前端池的負載。</span><span class="sxs-lookup"><span data-stu-id="2878c-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="2878c-105">即使在行動應用程式已最小化（例如 Android 2010 和執行 Lync 2013 Mobile 的 Apple 裝置，以及執行 Lync 行動裝置的 Android 和 Apple 裝置等），仍會維持伺服器連線的行動裝置，以及執行 Lync 行動裝置的 Android 和 Apple 裝置所強加的負載比當行動應用程式最小化時，中斷與伺服器的連線。</span><span class="sxs-lookup"><span data-stu-id="2878c-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="2878c-106">隨著行動使用量的增加，您必須監視行動效能，以判斷何時需要增加您的容量。</span><span class="sxs-lookup"><span data-stu-id="2878c-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="2878c-107">數個限制會影響行動效能：</span><span class="sxs-lookup"><span data-stu-id="2878c-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="2878c-108">可用記憶體</span><span class="sxs-lookup"><span data-stu-id="2878c-108">Available memory</span></span>

  - <span data-ttu-id="2878c-109">要求佇列限制</span><span class="sxs-lookup"><span data-stu-id="2878c-109">Request queue limit</span></span>

  - <span data-ttu-id="2878c-110">併發連接</span><span class="sxs-lookup"><span data-stu-id="2878c-110">Concurrent connections</span></span>

  - <span data-ttu-id="2878c-111">IIS 佇列長度</span><span class="sxs-lookup"><span data-stu-id="2878c-111">IIS queue length</span></span>

<span data-ttu-id="2878c-112">可能影響行動效能之伺服器的其他限制，最多可以有十二個併發登入、驗證、會話重新啟用和終止。</span><span class="sxs-lookup"><span data-stu-id="2878c-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="2878c-113">對於大部分的部署而言，不需要修改這些最大的。</span><span class="sxs-lookup"><span data-stu-id="2878c-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2878c-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="2878c-114">In This Section</span></span>

  - [<span data-ttu-id="2878c-115">監視 Lync Server 2013 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="2878c-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="2878c-116">在 Lync Server 2013 中監控行動服務與 UCWA 使用量</span><span class="sxs-lookup"><span data-stu-id="2878c-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="2878c-117">在 Lync Server 2013 中設定行動服務以取得高效能</span><span class="sxs-lookup"><span data-stu-id="2878c-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="2878c-118">在 Lync Server 2013 中監視 IIS 要求追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="2878c-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="2878c-119">Lync Server 2013 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="2878c-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

