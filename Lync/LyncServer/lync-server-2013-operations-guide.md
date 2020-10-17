---
title: Lync Server 2013：作業指南
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
ms.openlocfilehash: 212a640577d55e80225a597c9263b7a2573d257f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524530"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="ba4e1-102">Lync Server 2013 的作業指南</span><span class="sxs-lookup"><span data-stu-id="ba4e1-102">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba4e1-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="ba4e1-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="ba4e1-104">本檔說明維護 Microsoft Lync Server 2013 通訊軟體環境所需的作業程式、工作及工具。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="ba4e1-105">它會說明如何根據 Microsoft Operations Framework (MOF) 模型來管理 Lync Server 2013，並協助您設計有效的運作管理環境，其中包括實施排程、處理常式和程式，以維護有效的運作環境。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ba4e1-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="ba4e1-106">In This Section</span></span>

<span data-ttu-id="ba4e1-107">包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="ba4e1-107">The following sections are included:</span></span>

  - [<span data-ttu-id="ba4e1-108">Lync Server 2013 環境的最佳作法</span><span class="sxs-lookup"><span data-stu-id="ba4e1-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="ba4e1-109">Lync Server 2013 中的日常工作</span><span class="sxs-lookup"><span data-stu-id="ba4e1-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="ba4e1-110">Lync Server 2013 中的每週工作</span><span class="sxs-lookup"><span data-stu-id="ba4e1-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="ba4e1-111">Lync Server 2013 中的每月任務</span><span class="sxs-lookup"><span data-stu-id="ba4e1-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="ba4e1-112">Lync Server 2013 中的必要工作</span><span class="sxs-lookup"><span data-stu-id="ba4e1-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="ba4e1-113">Lync Server 2013 的作業檢查清單</span><span class="sxs-lookup"><span data-stu-id="ba4e1-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="ba4e1-114">使用 System Center Operations Manager 監視 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba4e1-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="ba4e1-115">Lync Server 2013 的運作相依性</span><span class="sxs-lookup"><span data-stu-id="ba4e1-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="ba4e1-116">Lync Server 2013 中的疑難排解與重要狀況指示器</span><span class="sxs-lookup"><span data-stu-id="ba4e1-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="ba4e1-117">假設您的 Microsoft Lync Server 2013 部署已完成。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="ba4e1-118">如果不是這種情況，請參閱 Microsoft Lync Server 2013 的規劃和部署內容，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="ba4e1-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba4e1-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ba4e1-119">See Also</span></span>


[<span data-ttu-id="ba4e1-120">Lync Server 2013 快速入門</span><span class="sxs-lookup"><span data-stu-id="ba4e1-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="ba4e1-121">規劃 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba4e1-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="ba4e1-122">Lync Server 2013 的部署</span><span class="sxs-lookup"><span data-stu-id="ba4e1-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="ba4e1-123">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="ba4e1-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

