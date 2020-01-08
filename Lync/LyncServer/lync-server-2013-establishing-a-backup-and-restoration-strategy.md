---
title: Lync Server 2013：建立備份及還原策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d378c66ae820ef0be7b7b3b0492b023863e977ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="02739-102">建立 Lync Server 2013 的備份與還原策略</span><span class="sxs-lookup"><span data-stu-id="02739-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02739-103">_**主題上次修改日期：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="02739-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="02739-104">在您可以為 Lync Server 開發備份和還原方案之前，您必須開發符合貴組織目標的戰略。</span><span class="sxs-lookup"><span data-stu-id="02739-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="02739-105">若要開發有效的備份和還原策略，您必須：</span><span class="sxs-lookup"><span data-stu-id="02739-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="02739-106">建立業務優先順序。</span><span class="sxs-lookup"><span data-stu-id="02739-106">Establish business priorities.</span></span>

  - <span data-ttu-id="02739-107">找出備份和還原需求。</span><span class="sxs-lookup"><span data-stu-id="02739-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="02739-108">建立業務優先順序</span><span class="sxs-lookup"><span data-stu-id="02739-108">Establishing Business Priorities</span></span>

<span data-ttu-id="02739-109">評估貴組織的業務優先順序。</span><span class="sxs-lookup"><span data-stu-id="02739-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="02739-110">通常會影響您備份和還原策略的主要業務優先順序如下所示：</span><span class="sxs-lookup"><span data-stu-id="02739-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="02739-111">業務連續性需求</span><span class="sxs-lookup"><span data-stu-id="02739-111">Business continuity requirements</span></span>

  - <span data-ttu-id="02739-112">資料完整性</span><span class="sxs-lookup"><span data-stu-id="02739-112">Data completeness</span></span>

  - <span data-ttu-id="02739-113">資料重要程度</span><span class="sxs-lookup"><span data-stu-id="02739-113">Data criticality</span></span>

  - <span data-ttu-id="02739-114">便攜性需求</span><span class="sxs-lookup"><span data-stu-id="02739-114">Portability requirements</span></span>

  - <span data-ttu-id="02739-115">成本限制</span><span class="sxs-lookup"><span data-stu-id="02739-115">Cost constraints</span></span>

<span data-ttu-id="02739-116">如以下所述的商業需求，這些說明可判斷您與客戶一起開發的服務等級協定（Sla）。</span><span class="sxs-lookup"><span data-stu-id="02739-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="02739-117">服務層級協定會大大影響您的備份與復原策略。</span><span class="sxs-lookup"><span data-stu-id="02739-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="02739-118">識別備份和還原需求</span><span class="sxs-lookup"><span data-stu-id="02739-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="02739-119">您的業務優先順序與服務等級協定會在判斷貴組織對備份和還原 Lync Server 的需求時起作用。</span><span class="sxs-lookup"><span data-stu-id="02739-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="02739-120">針對下列專案，找出並記錄您的需求：</span><span class="sxs-lookup"><span data-stu-id="02739-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="02739-121">**備份頻率如**   需有關備份頻率之最佳做法的詳細資料，請參閱[Lync Server 2013 備份和還原的最佳做法](lync-server-2013-best-practices-for-backup-and-restoration.md)。</span><span class="sxs-lookup"><span data-stu-id="02739-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="02739-122">**備份和還原工具**   包括誰是要使用工具的人員，以及在哪些電腦上。</span><span class="sxs-lookup"><span data-stu-id="02739-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="02739-123">如需本主題中討論的工具及必要許可權的詳細資訊，請參閱[Lync Server 2013 中的備份與還原需求：工具和許可權](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="02739-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="02739-124">**[備份位置**   ] 找出備份是在本機或遠端保留，並考慮安全性及協助工具。</span><span class="sxs-lookup"><span data-stu-id="02739-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="02739-125">指定要用於備份的媒體。</span><span class="sxs-lookup"><span data-stu-id="02739-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="02739-126">**硬體和軟體需求**   可識別並記錄您的特定硬體和軟體需求，包括備份儲存空間的硬體及特定元件的還原，以及支援備份和還原所需的任何軟體和網路連線。</span><span class="sxs-lookup"><span data-stu-id="02739-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="02739-127">隨著您開發硬體和軟體需求，請記住下列各種不同的還原案例。</span><span class="sxs-lookup"><span data-stu-id="02739-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="02739-128">**還原案例**   以下是下列案例的還原程式：</span><span class="sxs-lookup"><span data-stu-id="02739-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="02739-129">Lync 伺服器池失敗。</span><span class="sxs-lookup"><span data-stu-id="02739-129">A Lync Server pool fails.</span></span> <span data-ttu-id="02739-130">這個案例需要重建池中的每個伺服器。</span><span class="sxs-lookup"><span data-stu-id="02739-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="02739-131">標準版伺服器無法使用。</span><span class="sxs-lookup"><span data-stu-id="02739-131">A Standard Edition server fails.</span></span> <span data-ttu-id="02739-132">這個案例需要在新的或乾淨的電腦上重建伺服器，並還原資料庫。</span><span class="sxs-lookup"><span data-stu-id="02739-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="02739-133">中央管理儲存區遺失。</span><span class="sxs-lookup"><span data-stu-id="02739-133">Loss of the Central Management store.</span></span> <span data-ttu-id="02739-134">這個案例至少需要還原併發布中央管理儲存體。</span><span class="sxs-lookup"><span data-stu-id="02739-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="02739-135">中央管理儲存仍正常運作時，後端伺服器遺失。</span><span class="sxs-lookup"><span data-stu-id="02739-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="02739-136">這個案例需要在新的或乾淨的電腦上重建伺服器，並還原資料庫。</span><span class="sxs-lookup"><span data-stu-id="02739-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="02739-137">成為 Lync 伺服器池成員的伺服器失敗。</span><span class="sxs-lookup"><span data-stu-id="02739-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="02739-138">這個案例需要在新的或乾淨的電腦上重建伺服器。</span><span class="sxs-lookup"><span data-stu-id="02739-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="02739-139">檔案儲存區失敗。</span><span class="sxs-lookup"><span data-stu-id="02739-139">A File Store fails.</span></span> <span data-ttu-id="02739-140">這個案例需要還原檔案伺服器或檔案群集。</span><span class="sxs-lookup"><span data-stu-id="02739-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="02739-141">[封存]、[監視] 或 [永久聊天] 資料庫失敗。</span><span class="sxs-lookup"><span data-stu-id="02739-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="02739-142">這個案例需要重新建立資料庫，如果資料對您的組織是重要的，請還原資料。</span><span class="sxs-lookup"><span data-stu-id="02739-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="02739-143">[封存]、[監視] 和 [持續聊天] 資料不需要讓 Lync Server 重新開機並執行。</span><span class="sxs-lookup"><span data-stu-id="02739-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

