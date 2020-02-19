---
title: 'Lync Server 2013: Lync Server 環境的最佳作法'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c31d39ae7537fc53fc4e72c8b1c57863b2ba189
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="f08c3-102">Lync Server 2013 環境的最佳作法</span><span class="sxs-lookup"><span data-stu-id="f08c3-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f08c3-103">_**上次修改主題：** 2014年-08-04_</span><span class="sxs-lookup"><span data-stu-id="f08c3-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="f08c3-104">下列的一般原則應套用至系統的進行中作業：</span><span class="sxs-lookup"><span data-stu-id="f08c3-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="f08c3-105">**了解，並利用 MOF**   MOF 是一群最佳作法、 原則和模型，提供組織有關管理 IT 資產，例如每日的 Lync Server 2013 操作的技術指導。</span><span class="sxs-lookup"><span data-stu-id="f08c3-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="f08c3-106">遵循 MOF 指導方針，可協助您達成重要生產系統的可靠性、 可用性、 支援性和 Microsoft 產品的管理性。</span><span class="sxs-lookup"><span data-stu-id="f08c3-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="f08c3-107">如需詳細資訊，請參閱[Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939)。</span><span class="sxs-lookup"><span data-stu-id="f08c3-107">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="f08c3-108">**了解 Lync Server 2013 的最佳做法**   我們建議您實作實用及證實程序來管理 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f08c3-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="f08c3-109">藉由使用企圖，可能會比自行開發方法更有效率的管理作業的測試，並記錄方法。</span><span class="sxs-lookup"><span data-stu-id="f08c3-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="f08c3-110">**分隔作業分成每日、 每週及每月處理程序**   您定期執行的必要作業工作的文件。</span><span class="sxs-lookup"><span data-stu-id="f08c3-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="f08c3-111">記載如何執行工作，可協助確定作業環境，例如當部署新的技術變更時，會保留您資訊或人員變更就會發生。</span><span class="sxs-lookup"><span data-stu-id="f08c3-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="f08c3-112">我們建議每週及每月的操作工作可分成易於管理的工作會每日、 執行的工作負載。</span><span class="sxs-lookup"><span data-stu-id="f08c3-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="f08c3-113">每日工作而著重於系統的運作的努力，並每月工作而更著重於確保長期系統的狀況。</span><span class="sxs-lookup"><span data-stu-id="f08c3-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="f08c3-114">這份文件可用在環境中部署僅限立即訊息/目前狀態 (IM/P) 元件或 IM/P 與 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="f08c3-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="f08c3-115">Enterprise Voice 的特定工作或檢查清單項目時，這所述，如果您的環境不包括企業語音部分可能會略過。</span><span class="sxs-lookup"><span data-stu-id="f08c3-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="f08c3-116">**部署所需的操作 Lync Server 2013 的工具**   許多工具可協助疑難排解問題、 自動執行工作，以及協助監視及維護的 Lync Server 2013 環境。</span><span class="sxs-lookup"><span data-stu-id="f08c3-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="f08c3-117">定義一組標準工具為您的組織，因此精確、 有效、 一致地執行作業小組所執行的工作和受控制的方式。</span><span class="sxs-lookup"><span data-stu-id="f08c3-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="f08c3-118">您也應該實作用以追蹤事件及主要組態變更的程序。</span><span class="sxs-lookup"><span data-stu-id="f08c3-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="f08c3-119">參考</span><span class="sxs-lookup"><span data-stu-id="f08c3-119">Reference</span></span>

<span data-ttu-id="f08c3-120">造福讀者不熟悉伺服器管理的基本概念一般而言，我們提供伺服器管理作法的概觀。</span><span class="sxs-lookup"><span data-stu-id="f08c3-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="f08c3-121">已經熟悉伺服器管理的讀者可能會選擇略過本節。</span><span class="sxs-lookup"><span data-stu-id="f08c3-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="f08c3-122">最佳作法是根據知識，以及體驗的 IT 專業人員獲得了許多環境之間的建議。</span><span class="sxs-lookup"><span data-stu-id="f08c3-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="f08c3-123">它們提供標準程序的一般工作，您的 Lync Server 系統管理員必須執行每日、] 和 [清單工具他們應該用來管理 Lync Server 環境。</span><span class="sxs-lookup"><span data-stu-id="f08c3-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="f08c3-124">Lync 系統管理員的一般工作包括：</span><span class="sxs-lookup"><span data-stu-id="f08c3-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="f08c3-125">**容量和可用性管理**   定義如何該怎麼做以預測未來容量需求的量值和容量、 可靠性和您的系統的可用性相關的報告。</span><span class="sxs-lookup"><span data-stu-id="f08c3-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="f08c3-126">您必須驗證執行 Lync Server 的伺服器的大小，以處理系統上的負載，且該意外的停機時間會保留在服務層級協議 (SLA) 中所定義的層級下。</span><span class="sxs-lookup"><span data-stu-id="f08c3-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="f08c3-127">此外，您必須升級硬體，以繼續以符合已定義的需求。</span><span class="sxs-lookup"><span data-stu-id="f08c3-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="f08c3-128">**變更管理和組態管理**   控制如何與 IT 系統進行變更。</span><span class="sxs-lookup"><span data-stu-id="f08c3-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="f08c3-129">這應該包括測試、 應用程式的意見反應及緊急應變計劃、 文件的所有變更，並核准管理是否發生問題。</span><span class="sxs-lookup"><span data-stu-id="f08c3-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="f08c3-130">保留記錄的軟體和硬體資產和其組態。</span><span class="sxs-lookup"><span data-stu-id="f08c3-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="f08c3-131">**系統管理**   大綱標準方法來執行系統管理工作，例如資料庫管理與網站管理。</span><span class="sxs-lookup"><span data-stu-id="f08c3-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="f08c3-132">**安全性管理**   有詳細的原則及保護資料的機密性、 資料完整性和資料可用性的 IT 基礎結構的計劃。</span><span class="sxs-lookup"><span data-stu-id="f08c3-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="f08c3-133">這包括日常活動和與維護及調整 IT 安全性基礎結構相關的工作。</span><span class="sxs-lookup"><span data-stu-id="f08c3-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="f08c3-134">**系統疑難排解**   大綱方法來處理未預期的問題，包括可在未來防止類似的問題的步驟。</span><span class="sxs-lookup"><span data-stu-id="f08c3-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="f08c3-135">**服務等級協定**   維護一組的 IT 系統的效能目標並定期測量對這些目標的效能。</span><span class="sxs-lookup"><span data-stu-id="f08c3-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="f08c3-136">**文件**   記錄標準程序，例如設定資訊與經驗，並使其能需要這些人員成員。</span><span class="sxs-lookup"><span data-stu-id="f08c3-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="f08c3-137">進行組態變更時，請據此更新文件。</span><span class="sxs-lookup"><span data-stu-id="f08c3-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="f08c3-138">相關各節</span><span class="sxs-lookup"><span data-stu-id="f08c3-138">Related Sections</span></span>

<span data-ttu-id="f08c3-139">檢閱關於系統作業繼續進行之前的下列主題：</span><span class="sxs-lookup"><span data-stu-id="f08c3-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="f08c3-140">Lync Server 2013 中的容量和可用性管理</span><span class="sxs-lookup"><span data-stu-id="f08c3-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="f08c3-141">Lync Server 2013 中的變更管理</span><span class="sxs-lookup"><span data-stu-id="f08c3-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="f08c3-142">Lync Server 2013 中設定管理</span><span class="sxs-lookup"><span data-stu-id="f08c3-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="f08c3-143">Lync Server 2013 中的系統管理</span><span class="sxs-lookup"><span data-stu-id="f08c3-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="f08c3-144">Lync Server 2013 中的服務等級協定</span><span class="sxs-lookup"><span data-stu-id="f08c3-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="f08c3-145">Lync Server 2013 中的文件</span><span class="sxs-lookup"><span data-stu-id="f08c3-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="f08c3-146">Lync Server 2013 中的標準程序</span><span class="sxs-lookup"><span data-stu-id="f08c3-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="f08c3-147">Lync Server 2013 中的緊急程序</span><span class="sxs-lookup"><span data-stu-id="f08c3-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f08c3-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f08c3-148">See Also</span></span>


[<span data-ttu-id="f08c3-149">Microsoft Operations Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="f08c3-149">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

