---
title: Lync Server 2013： 管理回應群組
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
ms.openlocfilehash: ee9ee5808263f1e10489a09a711c60f93a13429d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="acb17-102">管理 Lync Server 2013 中的回應群組</span><span class="sxs-lookup"><span data-stu-id="acb17-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acb17-103">_**主題上次修改日期：** 2018年-02-01_</span><span class="sxs-lookup"><span data-stu-id="acb17-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="acb17-104">回應群組是一種通話管理功能，可讓您保留對特定區域所撥出的通話 (例如客服中心)，然後將這些通話路由傳送至指定的人員群組 (稱為 *「代理人」*)。</span><span class="sxs-lookup"><span data-stu-id="acb17-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="acb17-105">若要管理回應群組，請設定代理人群組、佇列及工作流程，藉以定義從通話保留至代理人應答這段期間對通話的處理方式。</span><span class="sxs-lookup"><span data-stu-id="acb17-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acb17-106">如果您有超過 300 個工作流程的單一的集區中的回應群組部署中，最好是使用 Lync Server 管理命令介面指令程式來建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="acb17-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="acb17-107">如果您使用「回應群組設定工具」，為內含 300 多個工作流程的集區建立更多工作流程，該網頁需要一段時間載入。</span><span class="sxs-lookup"><span data-stu-id="acb17-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="acb17-108">代理程式相關聯間接透過佇列的工作流程數目也有調和間距影響載入頁面。</span><span class="sxs-lookup"><span data-stu-id="acb17-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="acb17-109">本節中的主題提供逐步程序的工作，您可以執行來自訂和維護您的部署中的回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="acb17-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="acb17-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="acb17-110">In This Section</span></span>

  - [<span data-ttu-id="acb17-111">Lync Server 2013 中管理回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="acb17-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="acb17-112">Lync Server 2013 中管理回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="acb17-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="acb17-113">Lync Server 2013 中管理回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="acb17-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="acb17-114">管理 Lync Server 2013 中的應用程式層級回應群組設定</span><span class="sxs-lookup"><span data-stu-id="acb17-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="acb17-115">將回應群組移至 Lync Server 2013 中的新集區</span><span class="sxs-lookup"><span data-stu-id="acb17-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="acb17-116">在災害期間管理 Lync Server 2013 中的回應群組</span><span class="sxs-lookup"><span data-stu-id="acb17-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

