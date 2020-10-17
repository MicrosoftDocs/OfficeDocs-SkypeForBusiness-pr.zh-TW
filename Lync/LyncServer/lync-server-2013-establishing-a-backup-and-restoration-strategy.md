---
title: Lync Server 2013：建立備份與還原策略
description: Lync Server 2013：建立備份與還原策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555039"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="5f0e7-103">建立 Lync Server 2013 的備份與還原策略</span><span class="sxs-lookup"><span data-stu-id="5f0e7-103">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f0e7-104">_**主題上次修改日期：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="5f0e7-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="5f0e7-105">在您開發 Lync Server 的備份與還原計劃之前，您必須開發符合組織目標的策略。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-105">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="5f0e7-106">若要開發有效的備份與還原策略，您必須：</span><span class="sxs-lookup"><span data-stu-id="5f0e7-106">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="5f0e7-107">建立業務優先順序。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-107">Establish business priorities.</span></span>

  - <span data-ttu-id="5f0e7-108">識別備份與還原的需求。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-108">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="5f0e7-109">建立業務優先順序</span><span class="sxs-lookup"><span data-stu-id="5f0e7-109">Establishing Business Priorities</span></span>

<span data-ttu-id="5f0e7-110">評估貴組織的業務優先順序。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-110">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="5f0e7-111">一般來說，影響備份和還原策略的主要業務優先順序如下：</span><span class="sxs-lookup"><span data-stu-id="5f0e7-111">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="5f0e7-112">業務持續性需求</span><span class="sxs-lookup"><span data-stu-id="5f0e7-112">Business continuity requirements</span></span>

  - <span data-ttu-id="5f0e7-113">資料完整性</span><span class="sxs-lookup"><span data-stu-id="5f0e7-113">Data completeness</span></span>

  - <span data-ttu-id="5f0e7-114">資料重要程度</span><span class="sxs-lookup"><span data-stu-id="5f0e7-114">Data criticality</span></span>

  - <span data-ttu-id="5f0e7-115">可攜性需求</span><span class="sxs-lookup"><span data-stu-id="5f0e7-115">Portability requirements</span></span>

  - <span data-ttu-id="5f0e7-116">成本限制</span><span class="sxs-lookup"><span data-stu-id="5f0e7-116">Cost constraints</span></span>

<span data-ttu-id="5f0e7-117">這類業務需求，如這項協助，可判斷您為客戶開發 (Sla) 的服務等級協定。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-117">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="5f0e7-118">服務等級協定會大幅影響您的備份和復原策略。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-118">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="5f0e7-119">識別備份與還原需求</span><span class="sxs-lookup"><span data-stu-id="5f0e7-119">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="5f0e7-120">您的商務優先順序和服務等級協定會在決定組織備份及還原 Lync Server 的需求時起作用。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-120">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="5f0e7-121">為下列專案識別並記錄您的需求：</span><span class="sxs-lookup"><span data-stu-id="5f0e7-121">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="5f0e7-122">**備份頻率**    如需有關備份頻率之最佳作法的詳細資訊，請參閱[Lync Server 2013 備份與還原的最佳作法](lync-server-2013-best-practices-for-backup-and-restoration.md)。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-122">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="5f0e7-123">**備份及還原工具**    包含誰要使用工具，以及在哪些電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-123">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="5f0e7-124">如需本主題所討論之工具的詳細資訊，請參閱 [Lync Server 2013 中的備份和還原需求：工具和許可權](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-124">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="5f0e7-125">**備份位置**    識別備份是否要在本機或從遠端保存，以進行安全性及可存取性考慮。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-125">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="5f0e7-126">指定備份所使用的媒體。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-126">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="5f0e7-127">**硬體和軟體需求**    識別及記錄您特定的硬體和軟體需求，包括備份儲存空間的硬體，以及支援備份及還原所需的任何軟體和網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-127">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="5f0e7-128">當您開發硬體和軟體需求時，請牢記下列各種還原案例。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-128">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="5f0e7-129">**還原案例**    以下是下列案例的還原程式：</span><span class="sxs-lookup"><span data-stu-id="5f0e7-129">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="5f0e7-130">Lync Server 集區失敗。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-130">A Lync Server pool fails.</span></span> <span data-ttu-id="5f0e7-131">此案例需要重新構建集區中的每一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-131">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="5f0e7-132">Standard Edition server 失敗。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-132">A Standard Edition server fails.</span></span> <span data-ttu-id="5f0e7-133">此案例需要在新的或全新的電腦上重建伺服器，並還原資料庫。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-133">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="5f0e7-134">失去中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-134">Loss of the Central Management store.</span></span> <span data-ttu-id="5f0e7-135">此案例至少需要還原及發佈中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-135">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="5f0e7-136">當中央管理存放區正常運作時，失去後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-136">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="5f0e7-137">此案例需要在新的或全新的電腦上重建伺服器，並還原資料庫。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-137">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="5f0e7-138">屬於 Lync Server 集區成員的伺服器失敗。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-138">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="5f0e7-139">此案例需要在新電腦或全新電腦上重建伺服器。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-139">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="5f0e7-140">檔存放區失敗。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-140">A File Store fails.</span></span> <span data-ttu-id="5f0e7-141">此案例需要還原檔案伺服器或檔叢集。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-141">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="5f0e7-142">封存、監控或 Persistent 聊天資料庫失敗。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-142">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="5f0e7-143">此案例需要重新建立資料庫，如果資料對您的組織而言很重要，請還原資料。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-143">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="5f0e7-144">若要讓 Lync Server 重新備份及執行，則不需要封存、監控及持久聊天資料。</span><span class="sxs-lookup"><span data-stu-id="5f0e7-144">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

