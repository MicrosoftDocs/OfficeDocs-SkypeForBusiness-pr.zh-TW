---
title: Lync Server 2013： 作業指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1e6a07b881968f22b9ba36fc217002ea59032d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="a6eed-102">Lync Server 2013 的作業指南</span><span class="sxs-lookup"><span data-stu-id="a6eed-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6eed-103">_**上次修改主題：** 2014年-08-18_</span><span class="sxs-lookup"><span data-stu-id="a6eed-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="a6eed-104">本文件說明操作程序、 工作及工具所需的您維護的 Microsoft Lync Server 2013 通訊軟體環境。</span><span class="sxs-lookup"><span data-stu-id="a6eed-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="a6eed-105">本文說明如何根據 Microsoft Operations Framework (MOF) 模型管理 Lync Server 2013 和它可協助您有效率的操作管理環境，其中包括實作排程，處理的設計和程序來維護高效率運作的環境。</span><span class="sxs-lookup"><span data-stu-id="a6eed-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a6eed-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="a6eed-106">In This Section</span></span>

<span data-ttu-id="a6eed-107">會包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="a6eed-107">The following sections are included:</span></span>

  - [<span data-ttu-id="a6eed-108">Lync Server 2013 環境的最佳作法</span><span class="sxs-lookup"><span data-stu-id="a6eed-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="a6eed-109">Lync Server 2013 中的每日工作</span><span class="sxs-lookup"><span data-stu-id="a6eed-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="a6eed-110">Lync Server 2013 中的每週工作</span><span class="sxs-lookup"><span data-stu-id="a6eed-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="a6eed-111">Lync Server 2013 中的每月工作</span><span class="sxs-lookup"><span data-stu-id="a6eed-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="a6eed-112">視需要在 Lync Server 2013 中的工作</span><span class="sxs-lookup"><span data-stu-id="a6eed-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="a6eed-113">Lync Server 2013 的作業檢查清單</span><span class="sxs-lookup"><span data-stu-id="a6eed-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="a6eed-114">監視與 System Center Operations Manager 的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6eed-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="a6eed-115">在 Lync Server 2013 的操作相依性</span><span class="sxs-lookup"><span data-stu-id="a6eed-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="a6eed-116">Lync Server 2013 中疑難排解和重要的健康狀態指標</span><span class="sxs-lookup"><span data-stu-id="a6eed-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="a6eed-117">我們假設您的 Microsoft Lync Server 2013 部署已完成。</span><span class="sxs-lookup"><span data-stu-id="a6eed-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="a6eed-118">如果這不是這種情況，請參閱 Microsoft Lync Server 2013 的規劃和部署內容再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="a6eed-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6eed-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a6eed-119">See Also</span></span>


[<span data-ttu-id="a6eed-120">Lync Server 2013 快速入門</span><span class="sxs-lookup"><span data-stu-id="a6eed-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="a6eed-121">規劃 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6eed-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="a6eed-122">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6eed-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="a6eed-123">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="a6eed-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

