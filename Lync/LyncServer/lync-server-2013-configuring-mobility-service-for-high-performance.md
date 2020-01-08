---
title: Lync Server 2013：針對高效能配置行動服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a1c9b901e9a861b40a5cfa8c2642e3e3e41ffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="9a240-102">在 Lync Server 2013 中設定行動服務以取得高效能</span><span class="sxs-lookup"><span data-stu-id="9a240-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a240-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="9a240-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a240-104">本主題僅適用于 Lync Server 2013 行動服務（Mcx），不適用於在 Lync Server 2013 的累積更新：年2月2013中提供的統一通訊 Web API （UCWA）。</span><span class="sxs-lookup"><span data-stu-id="9a240-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="9a240-105">當您在網際網路資訊服務（IIS）7.5 上安裝行動服務（Mcx）時，行動服務安裝程式會在前端伺服器上設定一些效能設定。</span><span class="sxs-lookup"><span data-stu-id="9a240-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="9a240-106">我們建議您使用 IIS 7.5 進行行動。</span><span class="sxs-lookup"><span data-stu-id="9a240-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="9a240-107">這些設定會影響並行使用者要求的數目上限，以及行動服務所允許的最大執行緒數。</span><span class="sxs-lookup"><span data-stu-id="9a240-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="9a240-108">以下是效能設定：</span><span class="sxs-lookup"><span data-stu-id="9a240-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="9a240-109">IIS 7.5 上的 Mcx 設定</span><span class="sxs-lookup"><span data-stu-id="9a240-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="9a240-110">**maxConcurrentThreadsPerCPU**已設定為零（0）。</span><span class="sxs-lookup"><span data-stu-id="9a240-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="9a240-111">**maxConcurrentRequestsPerCPU**已設定為零（0）。</span><span class="sxs-lookup"><span data-stu-id="9a240-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="9a240-112">ASP.NET 程式模型已設定為自動設定（僅適用于 IIS 7.5）。</span><span class="sxs-lookup"><span data-stu-id="9a240-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="9a240-113">Http.sys 佇列限制設定為1000（依預設）。</span><span class="sxs-lookup"><span data-stu-id="9a240-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

