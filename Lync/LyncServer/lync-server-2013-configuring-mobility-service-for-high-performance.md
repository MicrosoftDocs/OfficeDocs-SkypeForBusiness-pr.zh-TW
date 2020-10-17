---
title: Lync Server 2013：設定行動服務以取得高效能
description: Lync Server 2013：設定行動性服務以取得高效能。
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
ms.openlocfilehash: 4732d9f6a92c383a105a6f0d7162c9b6c798de24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556979"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="86943-103">在 Lync Server 2013 中設定高效能的行動服務</span><span class="sxs-lookup"><span data-stu-id="86943-103">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86943-104">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="86943-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86943-105">本主題只適用于 Lync Server 2013 行動服務 (Mcx) ，而且不會套用至「整合通訊 Web API (UCWA) ，但在 Lync Server 2013 的累計更新中已傳遞：2月2013。</span><span class="sxs-lookup"><span data-stu-id="86943-105">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="86943-106">當您在網際網路資訊服務 (IIS) 7.5 上安裝行動服務 (Mcx) 時，行動性服務安裝程式會在前端伺服器上設定某些效能設定。</span><span class="sxs-lookup"><span data-stu-id="86943-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="86943-107">建議您使用 IIS 7.5 以用於行動性。</span><span class="sxs-lookup"><span data-stu-id="86943-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="86943-108">這些設定會影響並行使用者要求數目上限，以及行動性服務所允許的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="86943-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="86943-109">效能設定如下：</span><span class="sxs-lookup"><span data-stu-id="86943-109">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="86943-110">IIS 7.5 上的 Mcx 設定</span><span class="sxs-lookup"><span data-stu-id="86943-110">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="86943-111">**maxConcurrentThreadsPerCPU** 設定為零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="86943-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="86943-112">**maxConcurrentRequestsPerCPU** 設定為零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="86943-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="86943-113">ASP.NET 進程模型設定為僅) IIS 7.5 的自動設定 (。</span><span class="sxs-lookup"><span data-stu-id="86943-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="86943-114">HTTP.sys 佇列限制預設設定為 1000 () 。</span><span class="sxs-lookup"><span data-stu-id="86943-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

