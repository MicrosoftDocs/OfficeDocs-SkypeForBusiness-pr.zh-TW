---
title: Lync Server 2013：每日工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4375b11511d3b2c88222ea36575c18ca6fcc7dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="676ac-102">Lync Server 2013 中的每日工作</span><span class="sxs-lookup"><span data-stu-id="676ac-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="676ac-103">_**主題上次修改日期：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="676ac-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="676ac-104">若要協助確保 Lync Server 2013 部署的可用性與可靠性，您應該是每日例行監視器和測試元素的一部分，這些專案對於系統的運作（包括物理平臺、作業系統及所有重要的 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="676ac-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="676ac-105">預防性維護與前瞻性監視可協助您找出可能會對 Lync Server 2013 部署造成負面影響的可能錯誤與問題。</span><span class="sxs-lookup"><span data-stu-id="676ac-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="676ac-106">監視 Lync Server 2013 部署涉及檢查連線、服務、伺服器資源和系統資源的問題。</span><span class="sxs-lookup"><span data-stu-id="676ac-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="676ac-107">Windows Server 作業系統與 System Center Operations Manager 及 Lync Server 提供了許多監視工具與服務，協助確保 Lync 伺服器組織順利執行。</span><span class="sxs-lookup"><span data-stu-id="676ac-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="676ac-108">將這些技術一起實作之後，系統管理員就會在發生問題當下或之前收到警示。</span><span class="sxs-lookup"><span data-stu-id="676ac-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="676ac-109">每日監控的主要優點如下：</span><span class="sxs-lookup"><span data-stu-id="676ac-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="676ac-110">滿足已定義 SLA 的效能和可用性需求。</span><span class="sxs-lookup"><span data-stu-id="676ac-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="676ac-111">順利完成特定系統管理工作，例如每日備份作業和檢查伺服器狀況。</span><span class="sxs-lookup"><span data-stu-id="676ac-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="676ac-112">偵測和解決問題，例如伺服器效能中的瓶頸，或在這些瓶頸影響產能之前需要額外資源。</span><span class="sxs-lookup"><span data-stu-id="676ac-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="676ac-113">每日維護工作可協助系統管理團隊在組織內部定義或建立正常系統作業的準則或基準，並協助偵測任何異常活動。</span><span class="sxs-lookup"><span data-stu-id="676ac-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="676ac-114">必須執行這些日常維護工作，才能讓系統管理小組捕獲並維護 Lync Server 2013 基礎結構的相關資料，例如使用等級、可能的效能瓶頸，以及系統管理變更。</span><span class="sxs-lookup"><span data-stu-id="676ac-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="676ac-115">若要協助整理每日工作的效能，請使用[每日工作檢查清單](lync-server-2013-operations-checklists.md)。</span><span class="sxs-lookup"><span data-stu-id="676ac-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="676ac-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="676ac-116">See Also</span></span>


[<span data-ttu-id="676ac-117">每日工作檢查清單</span><span class="sxs-lookup"><span data-stu-id="676ac-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

