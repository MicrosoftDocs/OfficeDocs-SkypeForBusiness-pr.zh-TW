---
title: Lync Server 2013：設定行動服務以取得高效能
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
ms.openlocfilehash: 9d587444dfd1fbe4fae8898438a51bc9cfb2b5ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526950"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="e8dba-102">在 Lync Server 2013 中設定高效能的行動服務</span><span class="sxs-lookup"><span data-stu-id="e8dba-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8dba-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="e8dba-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e8dba-104">本主題只適用于 Lync Server 2013 行動服務 (Mcx) ，而且不會套用至「整合通訊 Web API (UCWA) ，但在 Lync Server 2013 的累計更新中已傳遞：2月2013。</span><span class="sxs-lookup"><span data-stu-id="e8dba-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="e8dba-105">當您在網際網路資訊服務 (IIS) 7.5 上安裝行動服務 (Mcx) 時，行動性服務安裝程式會在前端伺服器上設定某些效能設定。</span><span class="sxs-lookup"><span data-stu-id="e8dba-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="e8dba-106">建議您使用 IIS 7.5 以用於行動性。</span><span class="sxs-lookup"><span data-stu-id="e8dba-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="e8dba-107">這些設定會影響並行使用者要求數目上限，以及行動性服務所允許的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="e8dba-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="e8dba-108">效能設定如下：</span><span class="sxs-lookup"><span data-stu-id="e8dba-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="e8dba-109">IIS 7.5 上的 Mcx 設定</span><span class="sxs-lookup"><span data-stu-id="e8dba-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="e8dba-110">**maxConcurrentThreadsPerCPU** 設定為零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="e8dba-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="e8dba-111">**maxConcurrentRequestsPerCPU** 設定為零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="e8dba-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="e8dba-112">ASP.NET 進程模型設定為僅) IIS 7.5 的自動設定 (。</span><span class="sxs-lookup"><span data-stu-id="e8dba-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="e8dba-113">HTTP.sys 佇列限制預設設定為 1000 () 。</span><span class="sxs-lookup"><span data-stu-id="e8dba-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

