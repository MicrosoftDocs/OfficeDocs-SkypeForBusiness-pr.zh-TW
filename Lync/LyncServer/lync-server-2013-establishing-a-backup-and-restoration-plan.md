---
title: Lync Server 2013： 建立備份和還原規劃
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
ms.openlocfilehash: c0edc085ae57c8d261111726768b8ca3309c87dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="ccc3c-102">建立 Lync Server 2013 的備份和還原規劃</span><span class="sxs-lookup"><span data-stu-id="ccc3c-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc3c-103">_**上次修改主題：** 2013年-02-17_</span><span class="sxs-lookup"><span data-stu-id="ccc3c-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="ccc3c-104">建立備份和還原規劃包括下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ccc3c-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="ccc3c-105">研擬規劃。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-105">Developing the plan.</span></span>

  - <span data-ttu-id="ccc3c-106">實作計劃。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-106">Implementing the plan.</span></span>

  - <span data-ttu-id="ccc3c-107">維護計劃。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="ccc3c-108">研擬備份和還原規劃</span><span class="sxs-lookup"><span data-stu-id="ccc3c-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="ccc3c-109">Lync Server 的開發您的備份和還原策略之後，請用它來詳細的備份和還原規劃的文件。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="ccc3c-110">優先順序及備份資料和設定的需求，應該清楚地傳達您的計劃。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="ccc3c-111">您可以使用中[建立 Lync Server 2013 的備份和還原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md)的資訊和[Lync Server 2013 的備份及還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中的工作表，以利策略的說明文件。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="ccc3c-112">您的計劃應該也包含準則決定何時及如何還原服務。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="ccc3c-113">當您開發您的計劃，您必須考量，並考慮，下列：</span><span class="sxs-lookup"><span data-stu-id="ccc3c-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="ccc3c-114">如何還原在新硬體上的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="ccc3c-115">如何還原需涉及多個業務地區或部門的服務。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="ccc3c-116">您如何可以快速取得備用伺服器。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="ccc3c-117">復原使用您策略所需的時間。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="ccc3c-118">請考慮您的組織需求的復原時間目標 (RTO)。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="ccc3c-119">修改本主題中，新增和刪除視，以反映伺服器和元件在部署中的程序中的備份和還原程序。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="ccc3c-120">您也可以新增適當的詳細資訊，例如備份排程，以適當的程序，以確保資訊不會被忽略。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ccc3c-121">它是很好的作法盡可能，以協助確保品質和腳本程序建立多個步驟的指令碼。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="ccc3c-122">在您的計劃中，指定誰負責檢閱計劃，誰負責進行測試及驗證的任何新的程序或工具，以及使用者必須核准規劃和相關程序的任何變更。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="ccc3c-123">若要確認您的備份和還原規劃完全符合所有制定的目標和優先順序，實施規劃前，貴組織中取得適當的商務決策者和技術決策者的核准。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="ccc3c-124">實施備份和還原規劃</span><span class="sxs-lookup"><span data-stu-id="ccc3c-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="ccc3c-125">實作備份和還原規劃需要下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ccc3c-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="ccc3c-126">測試及驗證計劃。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="ccc3c-127">規劃的傳達。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-127">Communicating the plan.</span></span>

  - <span data-ttu-id="ccc3c-128">驗證備份與還原作業。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="ccc3c-129">測試及驗證計劃</span><span class="sxs-lookup"><span data-stu-id="ccc3c-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="ccc3c-130">此處所述的程序已經測試並在實驗室環境中進行驗證。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="ccc3c-131">若要確定在您的環境中這些或任何其他程序運作，您應測試及驗證您想要實作每項程序。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="ccc3c-132">完成測試和驗證才能提交您的計劃進行最終核准。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="ccc3c-133">規劃的傳達</span><span class="sxs-lookup"><span data-stu-id="ccc3c-133">Communicating the Plan</span></span>

<span data-ttu-id="ccc3c-134">您的備份和還原規劃應該清楚說明人員實作程序和 save 程序的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="ccc3c-135">您應該要確定所有人負責備份及還原的任何層面瞭解規劃、 它的方式實作，以及其角色是。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="ccc3c-136">這包括下列所有實作需求：</span><span class="sxs-lookup"><span data-stu-id="ccc3c-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="ccc3c-137">集區和伺服器備份。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-137">Pool and server backup.</span></span>

  - <span data-ttu-id="ccc3c-138">還原服務。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-138">Restoration of service.</span></span>

<span data-ttu-id="ccc3c-139">**集區和伺服器備份**</span><span class="sxs-lookup"><span data-stu-id="ccc3c-139">**Pool and server backup**</span></span>

<span data-ttu-id="ccc3c-140">備份和還原規劃應包含完成持續的備份程序所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-140">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="ccc3c-141">主要的資訊，以傳達給負責小組成員包含下列特性：</span><span class="sxs-lookup"><span data-stu-id="ccc3c-141">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="ccc3c-142">小組或人員 （指定為個人或職位） 負責備份各伺服器。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="ccc3c-143">備份每個伺服器的特定排程。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="ccc3c-144">每種類型的資料 （設定、 資料庫及檔案共用） 的備份位置。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="ccc3c-145">備份程序，以使用，包括完成每項程序所需的工具。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="ccc3c-146">完整備份，[備份及還原 Lync Server 2013 的工作表](lync-server-2013-backup-and-restoration-worksheets.md)所述所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="ccc3c-147">驗證方法是用來協助確保該資料和設定備份正確且可用來還原可以定期稽核或測試還原。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="ccc3c-148">**還原服務**</span><span class="sxs-lookup"><span data-stu-id="ccc3c-148">**Restoration of service**</span></span>

<span data-ttu-id="ccc3c-149">備份和還原規劃應包含所有的必要資訊還原服務，以防一或多部伺服器發生，讓服務無法使用。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="ccc3c-150">主要的資訊，以傳達給負責小組成員包含下列特性：</span><span class="sxs-lookup"><span data-stu-id="ccc3c-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="ccc3c-151">小組或人員 （指定為個人或職位） 是負責判斷還原服務時所需和要用來還原服務及也小組或人員負責實作每個程序的程序還原案例。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="ccc3c-152">決定哪些還原程序最適合用於特定情況下的準則。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="ccc3c-153">服務及復原時間目標 (RTO) 每個還原案例的還原估計時間。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="ccc3c-154">若要使用，包括完成每項程序所需的工具的還原程序。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="ccc3c-155">若要還原資料和設定所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-155">Information required to restore data and settings.</span></span> <span data-ttu-id="ccc3c-156">工作表會提供[Lync Server 2013 的備份及還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="ccc3c-157">驗證備份與還原作業</span><span class="sxs-lookup"><span data-stu-id="ccc3c-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="ccc3c-158">完成後您實際執行環境中，並在指定的時間間隔 （做為您的備份和還原規劃所述） 的初步備份工作，您應該確認下列項目：</span><span class="sxs-lookup"><span data-stu-id="ccc3c-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="ccc3c-159">視需要發生的備份。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="ccc3c-160">備份資料與設定均可存取。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="ccc3c-161">還原程序可備份和還原規劃，以及結果中所指定的時間內復原時間目標 (RTO) 符合所有業務需求。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="ccc3c-162">備份工作表已完成並驗證，以及它們會儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="ccc3c-163">這些工作表會提供[Lync Server 2013 的備份及還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="ccc3c-164">還原程序已經測試並確認運作如預期運作，您的備份和還原規劃中所指定。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="ccc3c-165">維護備份和還原規劃</span><span class="sxs-lookup"><span data-stu-id="ccc3c-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="ccc3c-166">Lync Server 拓撲是動態的環境，變更與您的組織。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="ccc3c-167">重新評估您的備份和還原規劃為您組織的變更，並檢閱定期以確定它會繼續以符合您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="ccc3c-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

