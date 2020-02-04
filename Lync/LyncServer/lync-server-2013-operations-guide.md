---
title: Lync Server 2013：操作指南
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
ms.openlocfilehash: 21b4f3e0a9beaae9419b11bf7353319b3b3ad2b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="fd614-102">Operations Guide for Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd614-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd614-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="fd614-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="fd614-104">本檔說明維護 Microsoft Lync Server 2013 通訊軟體環境所需的操作流程、工作和工具。</span><span class="sxs-lookup"><span data-stu-id="fd614-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="fd614-105">說明如何根據 Microsoft 操作架構（MOF）模型管理 Lync Server 2013，它將協助您設計高效的操作管理環境，包括實施排程、程式及程式來維護有效的工作環境。</span><span class="sxs-lookup"><span data-stu-id="fd614-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd614-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="fd614-106">In This Section</span></span>

<span data-ttu-id="fd614-107">包括下列各節：</span><span class="sxs-lookup"><span data-stu-id="fd614-107">The following sections are included:</span></span>

  - [<span data-ttu-id="fd614-108">Lync Server 2013 環境的最佳做法</span><span class="sxs-lookup"><span data-stu-id="fd614-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="fd614-109">Lync Server 2013 中的每日工作</span><span class="sxs-lookup"><span data-stu-id="fd614-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="fd614-110">Lync Server 2013 中的每週工作</span><span class="sxs-lookup"><span data-stu-id="fd614-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="fd614-111">Lync Server 2013 中的每月工作</span><span class="sxs-lookup"><span data-stu-id="fd614-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="fd614-112">Lync Server 2013 中的必要工作</span><span class="sxs-lookup"><span data-stu-id="fd614-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="fd614-113">Lync Server 2013 的作業檢查清單</span><span class="sxs-lookup"><span data-stu-id="fd614-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="fd614-114">使用 System Center Operations Manager 監視 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd614-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="fd614-115">Lync Server 2013 的操作相依性</span><span class="sxs-lookup"><span data-stu-id="fd614-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="fd614-116">Lync Server 2013 中的疑難排解與重要的健康情況指示</span><span class="sxs-lookup"><span data-stu-id="fd614-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="fd614-117">假設您的 Microsoft Lync Server 2013 部署已完成。</span><span class="sxs-lookup"><span data-stu-id="fd614-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="fd614-118">如果不是這種情況，請參閱 Microsoft Lync Server 2013 的規劃與部署內容，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="fd614-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd614-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="fd614-119">See Also</span></span>


[<span data-ttu-id="fd614-120">Lync Server 2013 快速入門</span><span class="sxs-lookup"><span data-stu-id="fd614-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="fd614-121">規劃 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd614-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="fd614-122">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd614-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="fd614-123">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="fd614-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

