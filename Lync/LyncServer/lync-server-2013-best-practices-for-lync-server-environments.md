---
title: Lync Server 2013： Lync Server 環境的最佳作法
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
ms.openlocfilehash: f65e7d210c069a5b629e0fbf093e3abea291ce6a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513020"
---
# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="93d00-102">Lync Server 2013 環境的最佳作法</span><span class="sxs-lookup"><span data-stu-id="93d00-102">Best practices for Lync Server 2013 environments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93d00-103">_**主題上次修改日期：** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="93d00-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="93d00-104">下列一般原則適用于系統的日常作業：</span><span class="sxs-lookup"><span data-stu-id="93d00-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="93d00-105">**瞭解和使用 MOF**    MOF 是一組最佳作法、原則及模型，提供組織的 IT 資產管理相關技術指導方針，例如每日 Lync Server 2013 作業。</span><span class="sxs-lookup"><span data-stu-id="93d00-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="93d00-106">下列 MOF 指導方針可協助您達到 Microsoft 產品的任務關鍵型實際執行系統可靠性、可用性、支援性及可管理性。</span><span class="sxs-lookup"><span data-stu-id="93d00-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="93d00-107">如需詳細資訊，請參閱 [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939)。</span><span class="sxs-lookup"><span data-stu-id="93d00-107">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="93d00-108">**深入瞭解 Lync Server 2013**     的最佳作法建議您執行實用且經驗證的程式來管理 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="93d00-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="93d00-109">使用嘗試的、經過測試及記錄的方法來管理作業，可能會比開發您自己的方法更有效率。</span><span class="sxs-lookup"><span data-stu-id="93d00-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="93d00-110">**個別作業分為每日、每週及每月處理**     程式記錄您定期執行的必要作業工作。</span><span class="sxs-lookup"><span data-stu-id="93d00-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="93d00-111">記錄您如何執行工作，可協助確保當您的作業環境發生變更時（例如，部署新技術或發生人員變更時），保留您的資訊。</span><span class="sxs-lookup"><span data-stu-id="93d00-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="93d00-112">我們建議將作業工作分割成可管理的工作負載，以每天、每週及每月執行工作。</span><span class="sxs-lookup"><span data-stu-id="93d00-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="93d00-113">每一項工作會著重致力於系統的運作，而每月的工作將著重致力於確保系統的長期健康情況。</span><span class="sxs-lookup"><span data-stu-id="93d00-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="93d00-114">這份檔可用於僅部署立即訊息/顯示狀態 (IM/P) 元件或 IM/P 搭配 Enterprise Voice 的環境。</span><span class="sxs-lookup"><span data-stu-id="93d00-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="93d00-115">當工作或檢查清單專案專屬於 Enterprise Voice 時，會提及這一點，如果您的環境不包含 Enterprise Voice，則可以略過此部分。</span><span class="sxs-lookup"><span data-stu-id="93d00-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="93d00-116">**部署運作 Lync Server 2013**     所需的工具有許多工具可協助疑難排解問題、自動化工作，以及協助監控和維護 Lync Server 2013 環境。</span><span class="sxs-lookup"><span data-stu-id="93d00-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="93d00-117">為您的組織定義一組標準的工具，讓操作小組所執行的工作以正確、有效且一致的方式執行，並以可控的方式執行。</span><span class="sxs-lookup"><span data-stu-id="93d00-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="93d00-118">您也應該執行處理常式來追蹤事件及主要設定變更。</span><span class="sxs-lookup"><span data-stu-id="93d00-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="93d00-119">參考</span><span class="sxs-lookup"><span data-stu-id="93d00-119">Reference</span></span>

<span data-ttu-id="93d00-120">針對讀者尚未熟悉伺服器管理基礎知識的優點，我們提供了伺服器管理作法的概述。</span><span class="sxs-lookup"><span data-stu-id="93d00-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="93d00-121">讀者已熟悉伺服器管理，可以選擇略過本節。</span><span class="sxs-lookup"><span data-stu-id="93d00-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="93d00-122">最佳作法是以 IT 專業人員在許多環境中取得的知識和經驗為依據的建議。</span><span class="sxs-lookup"><span data-stu-id="93d00-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="93d00-123">它們為您的 Lync Server 系統管理員每天必須執行的一般工作提供標準程式，並列出他們應該用來管理 Lync Server 環境的工具。</span><span class="sxs-lookup"><span data-stu-id="93d00-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="93d00-124">Lync 系統管理員的一般工作包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="93d00-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="93d00-125">**容量和可用性管理**    定義評估未來容量需求的方法和方式，以及報告系統的容量、可靠性和可用性。</span><span class="sxs-lookup"><span data-stu-id="93d00-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="93d00-126">您必須確認執行 Lync Server 的伺服器大小，以處理系統上的負載，而且未計畫的停機時間會保留在服務等級協定 (SLA) 中所定義的層級。</span><span class="sxs-lookup"><span data-stu-id="93d00-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="93d00-127">此外，您必須升級硬體，以繼續滿足定義的需求。</span><span class="sxs-lookup"><span data-stu-id="93d00-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="93d00-128">**變更管理和設定管理**    控制對 IT 系統進行變更的方式。</span><span class="sxs-lookup"><span data-stu-id="93d00-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="93d00-129">這應該包括測試、應用程式意見反應與應變計劃、檔的所有變更，以及在發生問題時進行管理的核准。</span><span class="sxs-lookup"><span data-stu-id="93d00-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="93d00-130">保留軟體和硬體資產及其設定的記錄。</span><span class="sxs-lookup"><span data-stu-id="93d00-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="93d00-131">**系統管理**    分級顯示執行系統管理工作（例如資料庫管理及網站管理）的標準方法。</span><span class="sxs-lookup"><span data-stu-id="93d00-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="93d00-132">**安全性管理**    具備詳細的原則與計畫，以保護 IT 基礎結構的資料機密性、資料完整性及資料可用性。</span><span class="sxs-lookup"><span data-stu-id="93d00-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="93d00-133">這包括與維護和調整 IT 安全性基礎結構相關的日常活動和工作。</span><span class="sxs-lookup"><span data-stu-id="93d00-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="93d00-134">**系統疑難排解**    用於處理意外問題的大綱方法，包括防止未來的類似問題的步驟。</span><span class="sxs-lookup"><span data-stu-id="93d00-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="93d00-135">**服務等級協定**    針對 IT 系統的效能維護一組目標，並根據這些目標定期衡量效能。</span><span class="sxs-lookup"><span data-stu-id="93d00-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="93d00-136">**檔**    記錄標準程式，例如設定資訊和經驗教訓，並使其可供需要他們的人員成員使用。</span><span class="sxs-lookup"><span data-stu-id="93d00-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="93d00-137">對設定進行變更之後，請據此更新檔。</span><span class="sxs-lookup"><span data-stu-id="93d00-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="93d00-138">相關各節</span><span class="sxs-lookup"><span data-stu-id="93d00-138">Related Sections</span></span>

<span data-ttu-id="93d00-139">繼續之前，請先複習下列有關系統作業的主題：</span><span class="sxs-lookup"><span data-stu-id="93d00-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="93d00-140">Lync Server 2013 的容量和可用性管理</span><span class="sxs-lookup"><span data-stu-id="93d00-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="93d00-141">Lync Server 2013 中的變更管理</span><span class="sxs-lookup"><span data-stu-id="93d00-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="93d00-142">Lync Server 2013 中的設定管理</span><span class="sxs-lookup"><span data-stu-id="93d00-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="93d00-143">Lync Server 2013 中的系統管理</span><span class="sxs-lookup"><span data-stu-id="93d00-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="93d00-144">Lync Server 2013 中的服務等級協定</span><span class="sxs-lookup"><span data-stu-id="93d00-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="93d00-145">Lync Server 2013 中的檔</span><span class="sxs-lookup"><span data-stu-id="93d00-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="93d00-146">Lync Server 2013 中的標準程式</span><span class="sxs-lookup"><span data-stu-id="93d00-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="93d00-147">Lync Server 2013 中的緊急程式</span><span class="sxs-lookup"><span data-stu-id="93d00-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93d00-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="93d00-148">See Also</span></span>


[<span data-ttu-id="93d00-149">Microsoft Operations Framework 4。0</span><span class="sxs-lookup"><span data-stu-id="93d00-149">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

