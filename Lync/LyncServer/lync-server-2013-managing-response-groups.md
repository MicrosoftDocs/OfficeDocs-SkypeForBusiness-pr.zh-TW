---
title: Lync Server 2013：管理回應群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c0d8ac0fbfa8464fd0cd078fc90784eb9fdd3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="fcc6a-102">在 Lync Server 2013 中管理回應群組</span><span class="sxs-lookup"><span data-stu-id="fcc6a-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcc6a-103">_**主題上次修改日期：** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="fcc6a-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="fcc6a-104">[回應群組] 是通話管理功能，可讓您將對特定區域所做的通話排隊（例如問訊台），然後將呼叫傳送給指定的人員群組（稱為 [*代理*]）。</span><span class="sxs-lookup"><span data-stu-id="fcc6a-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="fcc6a-105">若要管理回應群組，您需要設定代理群組、佇列和工作流程，以定義從所設定的時間開始，直到工程師回答它。</span><span class="sxs-lookup"><span data-stu-id="fcc6a-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fcc6a-106">如果您在回應群組部署的單一池中有超過300個工作流程，最好是使用 Lync Server 管理命令介面 Cmdlet 來建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="fcc6a-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="fcc6a-107">如果您使用 [回應群組設定] 工具來為擁有超過300個工作流程的池子建立工作流程，則會花費很長的時間來載入網頁。</span><span class="sxs-lookup"><span data-stu-id="fcc6a-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="fcc6a-108">透過佇列間接與工作流程相關聯的代理程式數量在頁面載入上也會有成比例的效果。</span><span class="sxs-lookup"><span data-stu-id="fcc6a-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="fcc6a-109">本節中的主題提供可執行檔工作逐步程式，以在您的部署中自訂及維護回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="fcc6a-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fcc6a-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="fcc6a-110">In This Section</span></span>

  - [<span data-ttu-id="fcc6a-111">在 Lync Server 2013 中管理回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="fcc6a-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="fcc6a-112">在 Lync Server 2013 中管理回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="fcc6a-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="fcc6a-113">在 Lync Server 2013 中管理回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="fcc6a-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="fcc6a-114">管理 Lync Server 2013 中的應用層級回應群組設定</span><span class="sxs-lookup"><span data-stu-id="fcc6a-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="fcc6a-115">在 Lync Server 2013 中將回應群組移至新的文件庫</span><span class="sxs-lookup"><span data-stu-id="fcc6a-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="fcc6a-116">在災害期間使用 Lync Server 2013 管理回應群組</span><span class="sxs-lookup"><span data-stu-id="fcc6a-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

