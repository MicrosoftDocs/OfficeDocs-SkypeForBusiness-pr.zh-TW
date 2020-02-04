---
title: Lync Server 2013：建立備份和還原方案
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
ms.openlocfilehash: cee1c4571dafa4e513f42613de13205ecec9de42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="b0dd6-102">建立 Lync Server 2013 的備份與還原方案</span><span class="sxs-lookup"><span data-stu-id="b0dd6-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0dd6-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="b0dd6-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="b0dd6-104">建立備份和還原方案涉及下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b0dd6-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="b0dd6-105">開發規劃。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-105">Developing the plan.</span></span>

  - <span data-ttu-id="b0dd6-106">實施方案。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-106">Implementing the plan.</span></span>

  - <span data-ttu-id="b0dd6-107">維護方案。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="b0dd6-108">開發備份與還原方案</span><span class="sxs-lookup"><span data-stu-id="b0dd6-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="b0dd6-109">在您開發 Lync Server 的備份和還原策略之後，請使用它來記錄詳細的備份和還原方案。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="b0dd6-110">您的計畫應該清楚地傳達備份資料和設定的優先順序與需求。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="b0dd6-111">您可以使用此資訊來[建立 Lync server 2013 的備份與還原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md)，以及[Lync server 2013 備份與還原工作](lync-server-2013-backup-and-restoration-worksheets.md)表中的工作表，以協助您的戰略檔。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="b0dd6-112">您的規劃也應該包含決定何時及如何還原服務的準則。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="b0dd6-113">當您開發方案時，您必須考慮下列事項，並考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="b0dd6-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="b0dd6-114">您將在新硬體上復原伺服器的方式。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="b0dd6-115">您將如何復原需要在多個商務區域或部門中進行動作的服務。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="b0dd6-116">您可以如何快速取得待命伺服器。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="b0dd6-117">使用您的策略來復原所需的時間。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="b0dd6-118">考慮貴組織對恢復時間目標（RTO）的需求。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="b0dd6-119">修改本主題中的備份和還原程式，視需要新增及刪除程式，以反映部署中的伺服器和元件。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="b0dd6-120">您也可以在適當的程式中新增適當的詳細資料（例如備份排程），以確保資訊不會被忽略。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0dd6-121">最好的做法是建立盡可能多步驟的腳本，以協助確保程式的品質與 reproducibility。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="b0dd6-122">在您的計畫中，指定負責仲裁者案的人員，負責測試和驗證任何新程式或工具的人員，以及必須核准方案和相關程式的任何變更。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="b0dd6-123">若要確保您的備份和還原方案完全符合所有已建立的目標與優先順序，請在實施方案之前，先核准貴組織中適當的商業決策者和技術決策者。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="b0dd6-124">實施備份和還原方案</span><span class="sxs-lookup"><span data-stu-id="b0dd6-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="b0dd6-125">執行備份和還原方案需要執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b0dd6-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="b0dd6-126">測試和驗證方案。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="b0dd6-127">溝通方案。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-127">Communicating the plan.</span></span>

  - <span data-ttu-id="b0dd6-128">驗證備份和還原作業。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="b0dd6-129">測試和驗證方案</span><span class="sxs-lookup"><span data-stu-id="b0dd6-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="b0dd6-130">這裡所述的程式已在實驗室環境中測試和驗證。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="b0dd6-131">若要確保這些或任何其他程式可在您的環境中運作，您應該測試並驗證您想要實現的每個程式。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="b0dd6-132">在提交您的最終核准方案之前，請先完成測試和驗證。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="b0dd6-133">溝通方案</span><span class="sxs-lookup"><span data-stu-id="b0dd6-133">Communicating the Plan</span></span>

<span data-ttu-id="b0dd6-134">您的備份和還原方案應該清楚描述執行程式的人員，以及執行程式的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="b0dd6-135">您應該確定任何負責備份和還原之層面的人都瞭解規劃、其實施方式，以及角色的作用。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="b0dd6-136">這包括下列各項的實現需求：</span><span class="sxs-lookup"><span data-stu-id="b0dd6-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="b0dd6-137">[池] 和 [伺服器備份]。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-137">Pool and server backup.</span></span>

  - <span data-ttu-id="b0dd6-138">還原服務。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-138">Restoration of service.</span></span>

<span data-ttu-id="b0dd6-139">**池和伺服器備份**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-139">**Pool and server backup**</span></span>

<span data-ttu-id="b0dd6-140">備份與還原方案應包含完成備份程式所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-140">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="b0dd6-141">將主要資訊傳達給負責的小組成員，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="b0dd6-141">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="b0dd6-142">負責備份每個伺服器的小組或人員（指定為個人或角色）。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="b0dd6-143">備份每個伺服器的特定排程。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="b0dd6-144">每個資料類型（設定、資料庫及檔案共用）的備份位置。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="b0dd6-145">要使用的備份程式，包括完成每個程式所需的工具。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="b0dd6-146">完成備份所需的資訊，如[Lync Server 2013 的備份和還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="b0dd6-147">驗證方法可用來協助確保資料和設定已適當備份且可供還原，這可能包括週期性審核及測試還原。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="b0dd6-148">**還原服務**</span><span class="sxs-lookup"><span data-stu-id="b0dd6-148">**Restoration of service**</span></span>

<span data-ttu-id="b0dd6-149">備份與還原方案應包含還原服務所需的所有資訊，以防一或多個伺服器遇到使服務無法使用的損失。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="b0dd6-150">將主要資訊傳達給負責的小組成員，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="b0dd6-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="b0dd6-151">小組或人員（指定為個人或角色）負責決定何時需要還原服務，以及用來還原服務的程式小組或人員，以及負責執行每個程式的程式。還原案例。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="b0dd6-152">決定哪一種還原程式最適合特定情況的準則。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="b0dd6-153">在每個還原案例中，還原服務與復原時間目標（RTO）的時間估計。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="b0dd6-154">要使用的還原程式，包括完成每個程式所需的工具。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="b0dd6-155">還原資料和設定所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-155">Information required to restore data and settings.</span></span> <span data-ttu-id="b0dd6-156">在[Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供工作表。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="b0dd6-157">驗證備份和還原作業</span><span class="sxs-lookup"><span data-stu-id="b0dd6-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="b0dd6-158">在您的生產環境中，以指定的間隔（如備份與還原方案中所述）完成初始備份工作之後，您應該確認下列事項：</span><span class="sxs-lookup"><span data-stu-id="b0dd6-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="b0dd6-159">根據需要進行備份。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="b0dd6-160">已備份的資料和設定可供存取。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="b0dd6-161">您可以在備份和還原方案中指定的恢復時間目標（RTO）時間內執行還原程式，結果就能滿足所有業務需求。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="b0dd6-162">備份工作表已完成並驗證，且儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="b0dd6-163">這些工作表是在[Lync Server 2013 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="b0dd6-164">還原程式已經過測試和驗證，如您在備份和還原方案中所指定的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="b0dd6-165">維護備份和還原方案</span><span class="sxs-lookup"><span data-stu-id="b0dd6-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="b0dd6-166">Lync Server 拓撲是與您的組織變更的動態環境。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="b0dd6-167">重新評估您的組織變更的備份和還原方案，並定期進行審查，以確保它繼續符合您的企業需求。</span><span class="sxs-lookup"><span data-stu-id="b0dd6-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

