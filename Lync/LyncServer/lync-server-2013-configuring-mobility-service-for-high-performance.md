---
title: Lync Server 2013： 設定高效能的 Mobility Service
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d09fb2ab6a122e8d25902bdc156f3870714f8dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="a3a9b-102">設定 Lync Server 2013 中的高效能的 Mobility Service</span><span class="sxs-lookup"><span data-stu-id="a3a9b-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3a9b-103">_**上次修改主題：** 2013年-02-17_</span><span class="sxs-lookup"><span data-stu-id="a3a9b-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3a9b-104">本主題僅適用於 Lync Server 2013 行動性服務 (Mcx)，並不會套用至 Unified Communications Web API (UCWA)、 為 Lync Server 2013 累計更新中傳遞： 2 月 2013年。</span><span class="sxs-lookup"><span data-stu-id="a3a9b-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="a3a9b-105">當您安裝 Mobility Service (Mcx) 網際網路資訊服務 (IIS) 7.5 上時，Mobility Service 安裝程式會在前端伺服器上設定一些效能設定。</span><span class="sxs-lookup"><span data-stu-id="a3a9b-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="a3a9b-106">建議您使用 IIS 7.5 以用於行動性。</span><span class="sxs-lookup"><span data-stu-id="a3a9b-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="a3a9b-107">設定會影響最大並行使用者要求數目與所允許的 Mobility Service 的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="a3a9b-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="a3a9b-108">以下是效能設定：</span><span class="sxs-lookup"><span data-stu-id="a3a9b-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="a3a9b-109">在 IIS 7.5 Mcx 設定</span><span class="sxs-lookup"><span data-stu-id="a3a9b-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="a3a9b-110">**maxConcurrentThreadsPerCPU**設為零 (0)。</span><span class="sxs-lookup"><span data-stu-id="a3a9b-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="a3a9b-111">**maxConcurrentRequestsPerCPU**設為零 (0)。</span><span class="sxs-lookup"><span data-stu-id="a3a9b-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="a3a9b-112">ASP.NET 處理序模型設為自動設定 （適用於僅使用 IIS 7.5)。</span><span class="sxs-lookup"><span data-stu-id="a3a9b-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="a3a9b-113">HTTP.sys 佇列限制設為 1000 （預設）。</span><span class="sxs-lookup"><span data-stu-id="a3a9b-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

