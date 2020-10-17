---
title: Lync Server 2013：每日工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 777d0fdfc8857022c0a54fcb1cd237b90f68d9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516640"
---
# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="93cc1-102">Lync Server 2013 中的日常工作</span><span class="sxs-lookup"><span data-stu-id="93cc1-102">Daily tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93cc1-103">_**主題上次修改日期：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="93cc1-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="93cc1-104">為了協助確保 Lync Server 2013 部署的可用性和可靠性，您應該是日常例行監控和測試元素的一部分，這些元素對系統的運作（包括實體平臺、作業系統和所有重要的 Lync Server 2013 服務）很重要。</span><span class="sxs-lookup"><span data-stu-id="93cc1-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="93cc1-105">預防性維護和主動監控會協助您找出可能會對 Lync Server 2013 部署造成不良影響的潛在錯誤及問題。</span><span class="sxs-lookup"><span data-stu-id="93cc1-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="93cc1-106">監視 Lync Server 2013 部署包括檢查連線、服務、伺服器資源和系統資源的問題。</span><span class="sxs-lookup"><span data-stu-id="93cc1-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="93cc1-107">Windows Server 作業系統（搭配 System Center Operations Manager 和 Lync Server）可提供許多監視工具和服務，以協助確保 Lync Server 組織順利運作。</span><span class="sxs-lookup"><span data-stu-id="93cc1-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="93cc1-108">當這些技術共同實施時，系統管理員將可以在發生問題時或之前收到警示。</span><span class="sxs-lookup"><span data-stu-id="93cc1-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="93cc1-109">每日監控的主要優點如下：</span><span class="sxs-lookup"><span data-stu-id="93cc1-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="93cc1-110">滿足定義之 Sla 的效能與可用性需求。</span><span class="sxs-lookup"><span data-stu-id="93cc1-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="93cc1-111">順利完成特定的系統管理工作，例如每日備份作業，以及檢查伺服器健康情況。</span><span class="sxs-lookup"><span data-stu-id="93cc1-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="93cc1-112">偵測和解決問題，例如伺服器效能中的瓶頸，或在影響到生產力之前需要額外資源。</span><span class="sxs-lookup"><span data-stu-id="93cc1-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="93cc1-113">每日維護工作可協助系統管理小組為組織內的一般系統作業定義或建立準則或基準，並偵測任何不正常的活動。</span><span class="sxs-lookup"><span data-stu-id="93cc1-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="93cc1-114">請務必執行這些日常維護工作，讓系統管理小組能夠捕獲和維護 Lync Server 2013 基礎結構的相關資料，例如流量層級、可能的性能瓶頸，以及系統管理變更。</span><span class="sxs-lookup"><span data-stu-id="93cc1-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="93cc1-115">若要協助組織日常工作的效能，請使用 [每日工作檢查清單](lync-server-2013-operations-checklists.md)。</span><span class="sxs-lookup"><span data-stu-id="93cc1-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="93cc1-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="93cc1-116">See Also</span></span>


[<span data-ttu-id="93cc1-117">每日工作檢查清單</span><span class="sxs-lookup"><span data-stu-id="93cc1-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

