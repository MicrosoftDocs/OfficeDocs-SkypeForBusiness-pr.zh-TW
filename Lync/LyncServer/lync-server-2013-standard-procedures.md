---
title: Lync Server 2013：標準程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Standard procedures
ms:assetid: 1b45d610-9840-4568-89e5-004ba31a15cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720323(v=OCS.15)
ms:contentKeyID: 63969581
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac1d42075f48b780a96f9ca7ad8b831379b5187
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-procedures-in-lync-server-2013"></a><span data-ttu-id="66e11-102">Lync Server 2013 中的標準程式</span><span class="sxs-lookup"><span data-stu-id="66e11-102">Standard procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66e11-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="66e11-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="66e11-104">有數個資源可協助您定義組織中需要哪些標準程式，以及如何執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="66e11-104">Several resources can help you define what standard procedures are required in the organization, and how to perform them.</span></span> <span data-ttu-id="66e11-105">因為每個組織都是唯一的，所以您可能必須另行自訂並調整這些資源，以符合日常需求。標準的操作程式變更，而且偶爾必須修改檔。</span><span class="sxs-lookup"><span data-stu-id="66e11-105">Because each organization is unique, you may have to additionally customize and adapt these resources to suit everyday requirements.Standard operational procedures change, and documentation occasionally has to be revised.</span></span> <span data-ttu-id="66e11-106">隨著所做的變更，變更管理程式（如 Microsoft 操作架構的服務管理函式所定義），應該會識別出每個變更可能會如何影響執行管理工作的方式和時機。</span><span class="sxs-lookup"><span data-stu-id="66e11-106">As changes are made, the change management process, as defined in the Service Management Functions of the Microsoft Operational Framework, should identify how each change is likely to affect how and when administrative tasks are performed.</span></span> <span data-ttu-id="66e11-107">使用變更管理函式來更新及控制程式化檔。我們建議您將工作工作劃分成可管理的工作負載，其中的工作是在每日、每週、每月，以及根據需要執行任務。</span><span class="sxs-lookup"><span data-stu-id="66e11-107">Use the change management function to update and control the procedural documentation.We recommend that operational tasks be separated into manageable workloads, where tasks are performed on a daily, weekly, monthly, and as-needed basis.</span></span> <span data-ttu-id="66e11-108">每日工作都將重點放在對系統運作非常重要的方面，且每月任務都將側重于確保系統長期健康情況。</span><span class="sxs-lookup"><span data-stu-id="66e11-108">Daily tasks would focus efforts on aspects that are very important to the functioning of a system and monthly tasks would focus more on ensuring the long-term health of a system.</span></span> <span data-ttu-id="66e11-109">必須執行的工作可以分成下列類別：</span><span class="sxs-lookup"><span data-stu-id="66e11-109">The tasks that must be performed can be separated into the following categories:</span></span>

  - [<span data-ttu-id="66e11-110">Lync Server 2013 中的每日工作</span><span class="sxs-lookup"><span data-stu-id="66e11-110">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="66e11-111">Lync Server 2013 中的每週工作</span><span class="sxs-lookup"><span data-stu-id="66e11-111">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="66e11-112">Lync Server 2013 中的每月工作</span><span class="sxs-lookup"><span data-stu-id="66e11-112">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="66e11-113">Lync Server 2013 中的必要工作</span><span class="sxs-lookup"><span data-stu-id="66e11-113">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

<span data-ttu-id="66e11-114">準備作業管理的檔時，請使用檢查清單來協助確保所需的工作在適當的時間執行。</span><span class="sxs-lookup"><span data-stu-id="66e11-114">When preparing documentation for operations management, use checklists to help ensure that the required tasks are performed at the appropriate time.</span></span> <span data-ttu-id="66e11-115">如需如何準備作業檢查清單的詳細資訊，請參閱位於作業檢查清單中的範例檢查清單。</span><span class="sxs-lookup"><span data-stu-id="66e11-115">For detailed information about how to prepare operations checklists, see the sample checklists located in Operations Checklists.</span></span>

<span data-ttu-id="66e11-116">通常，變更管理會接管系統管理完成的位置。</span><span class="sxs-lookup"><span data-stu-id="66e11-116">Frequently, change management takes over where system administration finishes.</span></span> <span data-ttu-id="66e11-117">如果工作是由標準程式所涵蓋，則是系統管理功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="66e11-117">If a task is covered by a standard procedure, it is part of the system administration function.</span></span> <span data-ttu-id="66e11-118">如果沒有任務的標準程式，則應該使用變更管理函式處理該工作。</span><span class="sxs-lookup"><span data-stu-id="66e11-118">If there is no standard procedure for a task, it should be handled by using the change management function.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="66e11-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="66e11-119">See Also</span></span>


[<span data-ttu-id="66e11-120">每日工作檢查清單</span><span class="sxs-lookup"><span data-stu-id="66e11-120">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
[<span data-ttu-id="66e11-121">每週任務檢查清單</span><span class="sxs-lookup"><span data-stu-id="66e11-121">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
[<span data-ttu-id="66e11-122">每月任務檢查清單</span><span class="sxs-lookup"><span data-stu-id="66e11-122">Monthly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

