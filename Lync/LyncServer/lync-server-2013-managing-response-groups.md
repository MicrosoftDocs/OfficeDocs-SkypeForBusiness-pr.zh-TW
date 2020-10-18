---
title: Lync Server 2013：管理回應群組
description: Lync Server 2013：管理回應群組。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138ece386d55895893402e5a1fdead58790504f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572629"
---
# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="500ac-103">在 Lync Server 2013 中管理回應群組</span><span class="sxs-lookup"><span data-stu-id="500ac-103">Managing response groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="500ac-104">_**主題上次修改日期：** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="500ac-104">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="500ac-105">回應群組是一種通話管理功能，可讓您保留對特定區域所撥出的通話 (例如客服中心)，然後將這些通話路由傳送至指定的人員群組 (稱為 *「代理人」*)。</span><span class="sxs-lookup"><span data-stu-id="500ac-105">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="500ac-106">若要管理回應群組，請設定代理人群組、佇列及工作流程，藉以定義從通話保留至代理人應答這段期間對通話的處理方式。</span><span class="sxs-lookup"><span data-stu-id="500ac-106">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="500ac-107">如果您有超過300的工作流程在回應群組部署的單一集區中，最好是使用 Lync Server 管理命令介面 Cmdlet 來建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="500ac-107">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="500ac-108">如果您使用「回應群組設定工具」，為內含 300 多個工作流程的集區建立更多工作流程，該網頁需要一段時間載入。</span><span class="sxs-lookup"><span data-stu-id="500ac-108">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="500ac-109">透過佇列間接與工作流程相關聯的代理程式數目，在頁面載入時也會產生比例影響。</span><span class="sxs-lookup"><span data-stu-id="500ac-109">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="500ac-110">本節中的主題會針對您可以在部署中執行自訂及維護回應群組應用程式的工作，提供逐步程式。</span><span class="sxs-lookup"><span data-stu-id="500ac-110">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="500ac-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="500ac-111">In This Section</span></span>

  - [<span data-ttu-id="500ac-112">在 Lync Server 2013 中管理回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="500ac-112">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="500ac-113">在 Lync Server 2013 中管理回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="500ac-113">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="500ac-114">在 Lync Server 2013 中管理回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="500ac-114">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="500ac-115">在 Lync Server 2013 中管理應用層級回應群組設定</span><span class="sxs-lookup"><span data-stu-id="500ac-115">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="500ac-116">將回應群組移至 Lync Server 2013 中的新集區</span><span class="sxs-lookup"><span data-stu-id="500ac-116">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="500ac-117">在發生災難時在 Lync Server 2013 中管理回應群組</span><span class="sxs-lookup"><span data-stu-id="500ac-117">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

