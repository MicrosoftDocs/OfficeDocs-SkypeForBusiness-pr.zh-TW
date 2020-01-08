---
title: Lync Server 2013： Lync Server 環境的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00dbbf95990875b8366ce5a03f1d2d70e6652828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="51926-102">Lync Server 2013 環境的最佳做法</span><span class="sxs-lookup"><span data-stu-id="51926-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51926-103">_**主題上次修改日期：** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="51926-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="51926-104">下列一般原則適用于您系統的日常作業：</span><span class="sxs-lookup"><span data-stu-id="51926-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="51926-105">**瞭解並利用 MOF**   mof 是最佳做法、原則和模型的集合，這些方案提供組織有關 IT 資產管理的技術指導方針，例如每日 Lync Server 2013 作業。</span><span class="sxs-lookup"><span data-stu-id="51926-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="51926-106">下列 MOF 指導方針可協助您達到 Microsoft 產品的任務關鍵型生產系統可靠性、可用性、支援及可管理性。</span><span class="sxs-lookup"><span data-stu-id="51926-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="51926-107">如需詳細資訊，請參閱[Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)。</span><span class="sxs-lookup"><span data-stu-id="51926-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="51926-108">**瞭解 Lync server 2013**   的最佳做法我們建議您執行實用且切實可行的程式來管理 Lync server 2013。</span><span class="sxs-lookup"><span data-stu-id="51926-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="51926-109">使用已嘗試、經過測試且已記錄的管理作業方法，可能會比開發自己的方法更有效率。</span><span class="sxs-lookup"><span data-stu-id="51926-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="51926-110">**將作業分為每日、每週及每月處理**   程式記錄您定期執行的工作所需的作業。</span><span class="sxs-lookup"><span data-stu-id="51926-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="51926-111">記錄您執行工作的方式，以協助確保當您的操作環境（例如部署新技術或員工變更）發生變更時，系統會保留您的資訊。</span><span class="sxs-lookup"><span data-stu-id="51926-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="51926-112">我們建議您將作業工作分成每天、每週及每月工作，以易於管理的工作負載進行。</span><span class="sxs-lookup"><span data-stu-id="51926-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="51926-113">每日工作都將重點放在系統的運作中，而且每月工作都將重點放在確保系統長期健康情況。</span><span class="sxs-lookup"><span data-stu-id="51926-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="51926-114">這份檔可在僅部署立即訊息/目前狀態（IM/P）元件或使用企業語音的 IM/P 的環境中使用。</span><span class="sxs-lookup"><span data-stu-id="51926-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="51926-115">如果工作或檢查清單專案是企業語音所特有的，則會提及此情況，如果您的環境不包含企業語音，可能會略過該部分。</span><span class="sxs-lookup"><span data-stu-id="51926-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="51926-116">**部署操作 Lync Server 2013**   所需的工具有許多工具可協助您排查問題、自動化工作，以及協助監視及維護 Lync Server 2013 環境。</span><span class="sxs-lookup"><span data-stu-id="51926-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="51926-117">為您的組織定義一組標準的工具，讓由操作小組所執行的工作以正確、高效且一致的方式執行，並以可控的方式進行。</span><span class="sxs-lookup"><span data-stu-id="51926-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="51926-118">您也應該執行處理常式來追蹤事件和主要設定變更。</span><span class="sxs-lookup"><span data-stu-id="51926-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="51926-119">參考</span><span class="sxs-lookup"><span data-stu-id="51926-119">Reference</span></span>

<span data-ttu-id="51926-120">如需閱讀者對伺服器管理基礎知識的好處，我們提供伺服器管理做法的概覽。</span><span class="sxs-lookup"><span data-stu-id="51926-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="51926-121">讀者已熟悉伺服器管理，可能會選擇略過本節。</span><span class="sxs-lookup"><span data-stu-id="51926-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="51926-122">最佳做法是根據 IT 專業人員在許多環境中取得的知識和經驗來提供的建議。</span><span class="sxs-lookup"><span data-stu-id="51926-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="51926-123">它們提供您的 Lync Server 管理員每天必須執行之一般工作的標準程式，並列出他們應該用來管理 Lync Server 環境的工具。</span><span class="sxs-lookup"><span data-stu-id="51926-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="51926-124">Lync 系統管理員的一般工作包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="51926-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="51926-125">**容量及可用性管理**   定義如何以及測量未來容量需求的方式，以及報告系統的容量、可靠性及可用性。</span><span class="sxs-lookup"><span data-stu-id="51926-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="51926-126">您必須確認執行 Lync Server 的伺服器已調整大小，以處理系統上的負載，而且未計畫的停機時間會保留在服務等級協定（SLA）中定義的等級底下。</span><span class="sxs-lookup"><span data-stu-id="51926-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="51926-127">此外，您必須升級硬體，才能繼續滿足已定義的需求。</span><span class="sxs-lookup"><span data-stu-id="51926-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="51926-128">**變更管理和設定管理**   控制對 IT 系統所做的變更。</span><span class="sxs-lookup"><span data-stu-id="51926-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="51926-129">這應該包括測試、應用程式意見反應與應急規劃、記錄所有變更，以及在問題發生時的管理核准。</span><span class="sxs-lookup"><span data-stu-id="51926-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="51926-130">記錄您的軟體和硬體資產及其設定。</span><span class="sxs-lookup"><span data-stu-id="51926-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="51926-131">**系統管理**   概述執行管理工作（例如資料庫管理和網站管理）的標準方法。</span><span class="sxs-lookup"><span data-stu-id="51926-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="51926-132">**安全性管理**   有一個詳細的原則和規劃，可保護 IT 基礎結構的資料機密性、資料完整性，以及資料的可用性。</span><span class="sxs-lookup"><span data-stu-id="51926-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="51926-133">這包括與維護和調整 IT 安全基礎結構相關的日常活動和工作。</span><span class="sxs-lookup"><span data-stu-id="51926-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="51926-134">**系統疑難排解**   大綱方法，以處理意外問題，包括避免未來的類似問題的步驟。</span><span class="sxs-lookup"><span data-stu-id="51926-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="51926-135">**服務層級協定**   針對 IT 系統效能維護一組目標，並定期針對這些目標評估效能。</span><span class="sxs-lookup"><span data-stu-id="51926-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="51926-136">**檔**   檔標準程式，例如配置資訊和吸取的經驗，並讓他們能供需要他們的員工成員使用。</span><span class="sxs-lookup"><span data-stu-id="51926-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="51926-137">變更設定之後，請據此更新檔。</span><span class="sxs-lookup"><span data-stu-id="51926-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="51926-138">相關各節</span><span class="sxs-lookup"><span data-stu-id="51926-138">Related Sections</span></span>

<span data-ttu-id="51926-139">繼續進行之前，請先複習下列有關系統操作的主題：</span><span class="sxs-lookup"><span data-stu-id="51926-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="51926-140">Lync Server 2013 的容量及可用性管理</span><span class="sxs-lookup"><span data-stu-id="51926-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="51926-141">Lync Server 2013 中的變更管理</span><span class="sxs-lookup"><span data-stu-id="51926-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="51926-142">Lync Server 2013 中的建構管理</span><span class="sxs-lookup"><span data-stu-id="51926-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="51926-143">Lync Server 2013 中的系統管理</span><span class="sxs-lookup"><span data-stu-id="51926-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="51926-144">Lync Server 2013 中的服務等級協定</span><span class="sxs-lookup"><span data-stu-id="51926-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="51926-145">Lync Server 2013 中的檔</span><span class="sxs-lookup"><span data-stu-id="51926-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="51926-146">Lync Server 2013 中的標準程式</span><span class="sxs-lookup"><span data-stu-id="51926-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="51926-147">Lync Server 2013 中的急診程式</span><span class="sxs-lookup"><span data-stu-id="51926-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51926-148">請參閱</span><span class="sxs-lookup"><span data-stu-id="51926-148">See Also</span></span>


[<span data-ttu-id="51926-149">Microsoft Operations Framework 4。0</span><span class="sxs-lookup"><span data-stu-id="51926-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

