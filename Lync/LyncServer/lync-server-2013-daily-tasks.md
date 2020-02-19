---
title: Lync Server 2013： 每日工作
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
ms.openlocfilehash: 59204fab5a1df067668f73ca4752033b64326a2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="aea96-102">Lync Server 2013 中的每日工作</span><span class="sxs-lookup"><span data-stu-id="aea96-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aea96-103">_**主題上次修改日期：** 2015年-01-26_</span><span class="sxs-lookup"><span data-stu-id="aea96-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="aea96-104">為了協助確保 Lync Server 2013 部署的可靠性與可用性，您應每日例行監視器] 及 [系統，包括實體平台、 作業系統的運作非常重要的測試元素的一部分，所有重要的 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="aea96-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="aea96-105">預防性維護和主動式監控可協助您找出可能的錯誤和可能有不利的影響 Lync Server 2013 部署的問題。</span><span class="sxs-lookup"><span data-stu-id="aea96-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="aea96-106">監控的 Lync Server 2013 部署牽涉到檢查連線、 服務、 伺服器資源，以及系統資源的問題。</span><span class="sxs-lookup"><span data-stu-id="aea96-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="aea96-107">Windows Server 作業系統，以及 System Center Operations Manager 和 Lync Server 提供許多監控工具和服務，以協助確保組織可以順利執行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="aea96-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="aea96-108">這些技術會實作時在一起，系統管理員將能夠接收提醒時，或之前發生問題。</span><span class="sxs-lookup"><span data-stu-id="aea96-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="aea96-109">每日監控的主要優點如下：</span><span class="sxs-lookup"><span data-stu-id="aea96-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="aea96-110">會議定義 Sla 效能及可用性需求。</span><span class="sxs-lookup"><span data-stu-id="aea96-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="aea96-111">成功完成特定的系統管理工作，例如每日備份作業，以及檢查伺服器健康狀況。</span><span class="sxs-lookup"><span data-stu-id="aea96-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="aea96-112">偵測和解決問題，例如中伺服器的效能或其他資源需求的瓶頸，避免其影響生產力。</span><span class="sxs-lookup"><span data-stu-id="aea96-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="aea96-113">每日維護工作協助管理小組，以定義或建立準則或一般系統作業在組織內，並偵測任何異常活動的比較基準。</span><span class="sxs-lookup"><span data-stu-id="aea96-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="aea96-114">請務必實作這些每日維護工作，以便管理小組可以擷取及維護的 Lync Server 2013 基礎結構，例如使用量等級、 可能的效能瓶頸和系統管理變更的相關資料。</span><span class="sxs-lookup"><span data-stu-id="aea96-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="aea96-115">若要協助組織每日工作的效能，請使用[每日工作檢查清單](lync-server-2013-operations-checklists.md)。</span><span class="sxs-lookup"><span data-stu-id="aea96-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="aea96-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aea96-116">See Also</span></span>


[<span data-ttu-id="aea96-117">每日工作檢查清單</span><span class="sxs-lookup"><span data-stu-id="aea96-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

