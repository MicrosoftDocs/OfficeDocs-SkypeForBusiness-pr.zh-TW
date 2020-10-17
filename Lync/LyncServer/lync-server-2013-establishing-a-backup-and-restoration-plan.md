---
title: Lync Server 2013：建立備份與還原計劃
description: Lync Server 2013：建立備份與還原計劃。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d93c713364bf6b5f230b255b68a2c1dfe1d04a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555049"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="46c99-103">建立 Lync Server 2013 的備份與還原方案</span><span class="sxs-lookup"><span data-stu-id="46c99-103">Establishing a backup and restoration plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c99-104">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="46c99-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="46c99-105">建立備份與還原計劃包含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="46c99-105">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="46c99-106">開發計畫。</span><span class="sxs-lookup"><span data-stu-id="46c99-106">Developing the plan.</span></span>

  - <span data-ttu-id="46c99-107">實施計畫。</span><span class="sxs-lookup"><span data-stu-id="46c99-107">Implementing the plan.</span></span>

  - <span data-ttu-id="46c99-108">維護計畫。</span><span class="sxs-lookup"><span data-stu-id="46c99-108">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="46c99-109">開發備份與還原計劃</span><span class="sxs-lookup"><span data-stu-id="46c99-109">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="46c99-110">在您開發 Lync Server 的備份與還原策略後，請使用它來記錄詳細的備份與還原計劃。</span><span class="sxs-lookup"><span data-stu-id="46c99-110">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="46c99-111">您的計畫應明確傳達備份資料和設定的優先順序和需求。</span><span class="sxs-lookup"><span data-stu-id="46c99-111">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="46c99-112">您可以使用此資訊來 [建立 lync server 2013 的備份與還原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) ，以及 [Lync server 2013 備份與還原工作](lync-server-2013-backup-and-restoration-worksheets.md) 表中的工作表，以協助您的策略的檔。</span><span class="sxs-lookup"><span data-stu-id="46c99-112">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="46c99-113">您的計畫還應該包含決定何時及如何還原服務的準則。</span><span class="sxs-lookup"><span data-stu-id="46c99-113">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="46c99-114">當您開發計畫時，您必須考慮下列各項，並加以考慮：</span><span class="sxs-lookup"><span data-stu-id="46c99-114">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="46c99-115">如何在新的硬體上復原伺服器。</span><span class="sxs-lookup"><span data-stu-id="46c99-115">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="46c99-116">在多個商務區域或部門中，您將如何復原需要動作的服務。</span><span class="sxs-lookup"><span data-stu-id="46c99-116">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="46c99-117">您可以如何快速取得待命伺服器。</span><span class="sxs-lookup"><span data-stu-id="46c99-117">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="46c99-118">使用您的策略復原所需的時間。</span><span class="sxs-lookup"><span data-stu-id="46c99-118">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="46c99-119">請考慮貴組織對於恢復時間目標 (RTO) 的需求。</span><span class="sxs-lookup"><span data-stu-id="46c99-119">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="46c99-120">修改本主題中的備份與還原程式，以適當的方式新增及刪除程式，以反映部署中的伺服器和元件。</span><span class="sxs-lookup"><span data-stu-id="46c99-120">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="46c99-121">您也可以將適當的詳細資料（例如備份排程）新增至適當的程式，以確保資訊不會被忽視。</span><span class="sxs-lookup"><span data-stu-id="46c99-121">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46c99-122">最佳作法是盡可能建立腳本，以協助確保程式的品質和 reproducibility。</span><span class="sxs-lookup"><span data-stu-id="46c99-122">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="46c99-123">在您的計畫中，指定負責檢查方案的人員、負責測試及驗證任何新程式或工具的人員，以及必須核准方案和相關程式的任何變更的人員。</span><span class="sxs-lookup"><span data-stu-id="46c99-123">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="46c99-124">若要確定您的備份和還原方案完全符合所有既定的目標和優先順序，請在實施計畫之前，先核准組織中適當的 business 決策者和技術決策者。</span><span class="sxs-lookup"><span data-stu-id="46c99-124">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="46c99-125">實施備份與還原計劃</span><span class="sxs-lookup"><span data-stu-id="46c99-125">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="46c99-126">執行備份與還原計劃需要下列步驟：</span><span class="sxs-lookup"><span data-stu-id="46c99-126">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="46c99-127">測試及驗證計畫。</span><span class="sxs-lookup"><span data-stu-id="46c99-127">Testing and validating the plan.</span></span>

  - <span data-ttu-id="46c99-128">交流計畫。</span><span class="sxs-lookup"><span data-stu-id="46c99-128">Communicating the plan.</span></span>

  - <span data-ttu-id="46c99-129">驗證備份及還原作業。</span><span class="sxs-lookup"><span data-stu-id="46c99-129">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="46c99-130">測試及驗證計畫</span><span class="sxs-lookup"><span data-stu-id="46c99-130">Testing and Validating the Plan</span></span>

<span data-ttu-id="46c99-131">這裡所述的程式已在實驗室環境中測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="46c99-131">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="46c99-132">若要確定這些或任何其他程式在您的環境中運作，您應該測試及驗證您要執行的每個程式。</span><span class="sxs-lookup"><span data-stu-id="46c99-132">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="46c99-133">在您提交最終核准的計畫之前，請先完成測試和驗證。</span><span class="sxs-lookup"><span data-stu-id="46c99-133">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="46c99-134">交流計畫</span><span class="sxs-lookup"><span data-stu-id="46c99-134">Communicating the Plan</span></span>

<span data-ttu-id="46c99-135">您的備份和還原計劃應該清楚地說明執行程式的執行者及執行程式的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="46c99-135">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="46c99-136">您應確定負責備份與還原之任何方面的人員瞭解計畫、其實施方式及其角色。</span><span class="sxs-lookup"><span data-stu-id="46c99-136">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="46c99-137">這包括下列各項的執行需求：</span><span class="sxs-lookup"><span data-stu-id="46c99-137">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="46c99-138">集區和伺服器備份。</span><span class="sxs-lookup"><span data-stu-id="46c99-138">Pool and server backup.</span></span>

  - <span data-ttu-id="46c99-139">還原服務。</span><span class="sxs-lookup"><span data-stu-id="46c99-139">Restoration of service.</span></span>

<span data-ttu-id="46c99-140">**集區和伺服器備份**</span><span class="sxs-lookup"><span data-stu-id="46c99-140">**Pool and server backup**</span></span>

<span data-ttu-id="46c99-141">備份與還原計劃應包含在日常執行備份程式時所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="46c99-141">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="46c99-142">要傳遞給負責的小組成員的主要資訊如下：</span><span class="sxs-lookup"><span data-stu-id="46c99-142">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="46c99-143">小組或個人 (會指定為個人或角色) 負責備份每台伺服器。</span><span class="sxs-lookup"><span data-stu-id="46c99-143">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="46c99-144">備份每一部伺服器的特定計劃。</span><span class="sxs-lookup"><span data-stu-id="46c99-144">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="46c99-145">每個資料類型的備份位置 (設定、資料庫及檔案共用) 。</span><span class="sxs-lookup"><span data-stu-id="46c99-145">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="46c99-146">要使用的備份程式，包含完成每個程式所需的工具。</span><span class="sxs-lookup"><span data-stu-id="46c99-146">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="46c99-147">完成備份所需的資訊，如 [Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="46c99-147">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="46c99-148">用來協助確保資料和設定進行適當備份及可供還原使用的驗證方法，其中包括週期性審計及測試還原。</span><span class="sxs-lookup"><span data-stu-id="46c99-148">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="46c99-149">**服務的還原**</span><span class="sxs-lookup"><span data-stu-id="46c99-149">**Restoration of service**</span></span>

<span data-ttu-id="46c99-150">備份與還原計劃應包含還原服務時所需的所有資訊，以防一或多部伺服器遇到使服務無法使用的遺失。</span><span class="sxs-lookup"><span data-stu-id="46c99-150">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="46c99-151">要傳遞給負責的小組成員的主要資訊如下：</span><span class="sxs-lookup"><span data-stu-id="46c99-151">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="46c99-152">小組或個人 (會指定為個人或角色) ，負責決定何時需要還原服務，以及用來還原服務的程式，也就是負責針對每個還原案例執行程式的小組或人員。</span><span class="sxs-lookup"><span data-stu-id="46c99-152">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="46c99-153">決定哪些還原程式最適合特定狀況的準則。</span><span class="sxs-lookup"><span data-stu-id="46c99-153">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="46c99-154">還原服務和恢復時間目標的時間估計 (每個還原案例中的 RTO) 。</span><span class="sxs-lookup"><span data-stu-id="46c99-154">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="46c99-155">要使用的還原程式，包含完成每個程式所需的工具。</span><span class="sxs-lookup"><span data-stu-id="46c99-155">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="46c99-156">還原資料及設定所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="46c99-156">Information required to restore data and settings.</span></span> <span data-ttu-id="46c99-157">工作表會在 [Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。</span><span class="sxs-lookup"><span data-stu-id="46c99-157">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="46c99-158">驗證備份及還原作業</span><span class="sxs-lookup"><span data-stu-id="46c99-158">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="46c99-159">在實際執行環境中和指定的間隔完成初始備份工作之後，您應該在 (備份與還原計劃) 中，確認下列各項：</span><span class="sxs-lookup"><span data-stu-id="46c99-159">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="46c99-160">備份會在必要時進行。</span><span class="sxs-lookup"><span data-stu-id="46c99-160">Backups are occurring as required.</span></span>

  - <span data-ttu-id="46c99-161">備份的資料和設定可供存取。</span><span class="sxs-lookup"><span data-stu-id="46c99-161">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="46c99-162">您可以在復原時間目標中執行還原程式， (備份與還原計劃中所指定的 RTO) 時間，以及結果是否符合所有業務需求。</span><span class="sxs-lookup"><span data-stu-id="46c99-162">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="46c99-163">備份工作表已完成並驗證，且儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="46c99-163">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="46c99-164">在 [Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供這些工作表。</span><span class="sxs-lookup"><span data-stu-id="46c99-164">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="46c99-165">還原程式已經過測試及驗證，可如您的備份和還原計劃中所指定的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="46c99-165">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="46c99-166">維護備份與還原計劃</span><span class="sxs-lookup"><span data-stu-id="46c99-166">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="46c99-167">Lync Server 拓撲是隨組織變更的動態環境。</span><span class="sxs-lookup"><span data-stu-id="46c99-167">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="46c99-168">在您的組織變更時重新評估備份與還原方案，並定期複查，以確保它繼續符合您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="46c99-168">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

