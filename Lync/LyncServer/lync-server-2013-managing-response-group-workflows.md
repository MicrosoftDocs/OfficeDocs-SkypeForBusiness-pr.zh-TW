---
title: Lync Server 2013：管理回應群組工作流程
description: Lync Server 2013：管理回應群組工作流程。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group workflows
ms:assetid: 42cfccdd-2844-4875-b4e3-813e1df15f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520986(v=OCS.15)
ms:contentKeyID: 48183974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2223fed2b5b030a2c92e0b958ae8545a7717f848
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560409"
---
# <a name="managing-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="1b77b-103">在 Lync Server 2013 中管理回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="1b77b-103">Managing Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b77b-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1b77b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1b77b-105">「回應群組」工作流程會定義呼叫的行為，從電話響到代理人接聽通話的時間。</span><span class="sxs-lookup"><span data-stu-id="1b77b-105">A Response Group workflow defines the behavior of a call from the time that the phone rings to the time that an agent answers the call.</span></span> <span data-ttu-id="1b77b-106">工作流程包括佇列和路由資訊，也包括群組搜尋或互動語音回應 (IVR) 資訊。</span><span class="sxs-lookup"><span data-stu-id="1b77b-106">The workflow includes queue and routing information, and includes either hunt group or interactive voice response (IVR) information.</span></span>

<span data-ttu-id="1b77b-107">本節主題，識別 IVR 工作流程設計的最佳作法，並解說如何建立、自訂營業時間與假日集、如何建立或修改工作流程，以及如何刪除工作群組。</span><span class="sxs-lookup"><span data-stu-id="1b77b-107">Topics in this section identify best practices for designing IVR workflows, and explain how to create customized business hours and holiday sets, how to create or modify workflows, and how to delete workgroups.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1b77b-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1b77b-108">In This Section</span></span>

  - [<span data-ttu-id="1b77b-109">在 Lync Server 2013 中設計互動語音回應通話流程</span><span class="sxs-lookup"><span data-stu-id="1b77b-109">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="1b77b-110"> (選用) 在 Lync Server 2013 中定義回應群組上班時間</span><span class="sxs-lookup"><span data-stu-id="1b77b-110">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="1b77b-111"> (選用) 在 Lync Server 2013 中定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="1b77b-111">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="1b77b-112">在 Lync Server 2013 中建立或修改工作流程</span><span class="sxs-lookup"><span data-stu-id="1b77b-112">Create or modify a workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-workflow.md)

  - [<span data-ttu-id="1b77b-113">在 Lync Server 2013 中刪除工作流程</span><span class="sxs-lookup"><span data-stu-id="1b77b-113">Delete a workflow in Lync Server 2013</span></span>](lync-server-2013-delete-a-workflow.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

