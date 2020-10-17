---
title: Lync Server 2013：變更管理
description: Lync Server 2013：變更管理。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69ea019f6366528c40b60a39ca8b646b49b336b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564459"
---
# <a name="change-management-in-lync-server-2013"></a><span data-ttu-id="12886-103">Lync Server 2013 中的變更管理</span><span class="sxs-lookup"><span data-stu-id="12886-103">Change management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12886-104">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="12886-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="12886-105">無法避免對 IT 環境所做的變更。</span><span class="sxs-lookup"><span data-stu-id="12886-105">Changes to the IT environment are unavoidable.</span></span> <span data-ttu-id="12886-106">變更包括新的技術、系統、應用程式、硬體、工具、程式，以及角色和責任的變更。</span><span class="sxs-lookup"><span data-stu-id="12886-106">Changes include new technologies, systems, applications, hardware, tools, processes, and changes in roles and responsibilities.</span></span> <span data-ttu-id="12886-107">有效的變更管理系統可讓您快速地為 IT 環境引入變更，並以極小的服務中斷。</span><span class="sxs-lookup"><span data-stu-id="12886-107">An effective change management system lets you introduce changes to the IT environment quickly and with minimal service disruption.</span></span> <span data-ttu-id="12886-108">變更管理系統會將變更系統的小組彙集在一起。</span><span class="sxs-lookup"><span data-stu-id="12886-108">A change management system brings together the teams involved in changing a system.</span></span> <span data-ttu-id="12886-109">例如，決定要利用 Office Web Apps。</span><span class="sxs-lookup"><span data-stu-id="12886-109">For example, deciding to take advantage of the Office Web Apps.</span></span> <span data-ttu-id="12886-110">這是一個整合型 Lync 服務應用程式，可讓使用者在瀏覽器中讀取及編輯檔。</span><span class="sxs-lookup"><span data-stu-id="12886-110">This is an integrated Lync Service application that enables users to read and edit documents in a browser.</span></span> <span data-ttu-id="12886-111">在您進入生產環境之後，此服務的實施需要有數個團隊的參與：</span><span class="sxs-lookup"><span data-stu-id="12886-111">The implementation of this service, after you have gone into production, requires the involvement of several teams:</span></span>

  - <span data-ttu-id="12886-112">**測試小組**    此小組會在測試伺服器上測試 Office Web Apps，在此程式中提供實際使用模式的相關資訊，以及實際執行伺服器的效能。</span><span class="sxs-lookup"><span data-stu-id="12886-112">**Test Team**   This team load-tests the Office Web Apps on a test server, in the process providing information about the expected usage patterns and expected performance of the production servers.</span></span>

  - <span data-ttu-id="12886-113">**Lync 系統管理員**    此小組會決定部署策略，並在可能的情況下將安裝腳本。</span><span class="sxs-lookup"><span data-stu-id="12886-113">**Lync Administrators**   This team determines the deployment strategy and scripts the installation where it was possible.</span></span> <span data-ttu-id="12886-114">小組負責確定變更已部署在實際執行環境中，而且會在以後負責管理。</span><span class="sxs-lookup"><span data-stu-id="12886-114">The team is responsible for making sure that the change is deployed on the production environment, and it is responsible for administration afterward.</span></span> <span data-ttu-id="12886-115">團隊必須瞭解變更的影響，並將這些變更納入程式中，然後再將變更放入實際執行中。</span><span class="sxs-lookup"><span data-stu-id="12886-115">The team must understand the effect of the changes and incorporate them in procedures before the changes are put into production</span></span>

  - <span data-ttu-id="12886-116">**網路小組**    此小組負責允許從網際網路存取內部 Lync 集區伺服器的防火牆規則變更。</span><span class="sxs-lookup"><span data-stu-id="12886-116">**Network Team**   This team is responsible for changes to firewall rules that allow access from the Internet to the internal Lync pool servers.</span></span> <span data-ttu-id="12886-117">小組也負責與 Lync 系統管理員合作，以確保可用的頻寬可支援額外的負載。</span><span class="sxs-lookup"><span data-stu-id="12886-117">The team is also responsible in working with the Lync administrators for making sure that the available bandwidth can support the additional load.</span></span>

  - <span data-ttu-id="12886-118">**安全小組**    此小組會評估安全性並將風險降至最低。</span><span class="sxs-lookup"><span data-stu-id="12886-118">**Security Team**   This team assesses security and minimizes risks.</span></span> <span data-ttu-id="12886-119">安全小組必須查看已知的漏洞，並協助確保安全性風險降到最低。</span><span class="sxs-lookup"><span data-stu-id="12886-119">The security team must review known vulnerabilities and help ensure that security risks are minimized.</span></span>

  - <span data-ttu-id="12886-120">**使用者驗收小組**    此小組所組成的使用者願意測試系統，並提供改善的意見反應。</span><span class="sxs-lookup"><span data-stu-id="12886-120">**User Acceptance Team**   This team is composed of users who are willing to test the system and offer feedback for improvements.</span></span>

<span data-ttu-id="12886-121">變更管理程式會定義每個小組的責任，並排定要執行的工作，並在需要時納入檢查及測試。</span><span class="sxs-lookup"><span data-stu-id="12886-121">The change management process defines the responsibilities of each team and schedules the work to be performed, incorporating checks and tests where they are required.</span></span> <span data-ttu-id="12886-122">變更控制會因變更的複雜性和預期影響而異。</span><span class="sxs-lookup"><span data-stu-id="12886-122">Change controls will vary depending on the complexity and expected effect of a change.</span></span> <span data-ttu-id="12886-123">它們可能會因次要變更的自動核准、變更評審會議，以及對完整專案層級的評論而有所不同。</span><span class="sxs-lookup"><span data-stu-id="12886-123">They can vary from automatic approval of minor changes, to change review meetings, to full project-level reviews.</span></span> <span data-ttu-id="12886-124">為了更好地說明這種情況，本節將討論變更的群組。</span><span class="sxs-lookup"><span data-stu-id="12886-124">To explain this better, the groups of changes are discussed in this section.</span></span>

  - <span data-ttu-id="12886-125">**主要變更**    主要變更對系統有全域影響，而且可能需要不同小組的輸入。</span><span class="sxs-lookup"><span data-stu-id="12886-125">**Major Changes**   Major changes have a global effect on the system and may require input from various teams.</span></span> <span data-ttu-id="12886-126">升級至 Lync Server 2013 的範例。</span><span class="sxs-lookup"><span data-stu-id="12886-126">An example of this is upgrading to Lync Server 2013.</span></span> <span data-ttu-id="12886-127">主要變更會影響許多小組，也可能會影響不同的系統。</span><span class="sxs-lookup"><span data-stu-id="12886-127">Major changes affect many teams and perhaps different systems.</span></span> <span data-ttu-id="12886-128">變更管理程式可能會包含一或多個變更評審會議，告知小組會參與變更或受變更影響的小組。</span><span class="sxs-lookup"><span data-stu-id="12886-128">The change management process will probably include one or more change review meetings to inform the teams that will be involved in the change or be affected by the change.</span></span>

  - <span data-ttu-id="12886-129">**重大變更**    重大變更需要大量的資源來規劃、組建及實施。</span><span class="sxs-lookup"><span data-stu-id="12886-129">**Significant Changes**   Significant changes require significant resources to plan, build, and implement.</span></span> <span data-ttu-id="12886-130">應該引入適當的變更控制，以協助確保能夠瞭解變更的影響、測試部署程式，以及復原和應急計畫是否已就緒。</span><span class="sxs-lookup"><span data-stu-id="12886-130">Appropriate change controls should be introduced to help make ensure that the effect of the change is understood, deployment procedures are tested, and the rollback and contingency plans are ready.</span></span> <span data-ttu-id="12886-131">大量變更的範例是部署新的累計更新。</span><span class="sxs-lookup"><span data-stu-id="12886-131">An example of a significant change is deploying a new cumulative update.</span></span>

  - <span data-ttu-id="12886-132">**次要變更**    次要變更不會大幅影響 IT 環境，例如，透過 Microsoft Lync Server 2013 控制台變更某些 Lync 原則。</span><span class="sxs-lookup"><span data-stu-id="12886-132">**Minor Changes**   Minor changes do not significantly affect the IT environment, for example, changing certain Lync policies via the Microsoft Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="12886-133">**標準變更**    標準變更會定期執行，並且會受到充分瞭解和記錄。</span><span class="sxs-lookup"><span data-stu-id="12886-133">**Standard Changes**   Standard changes are performed regularly and are well understood and documented.</span></span> <span data-ttu-id="12886-134">變更管理程式應檢查對程式所做的所有變更。</span><span class="sxs-lookup"><span data-stu-id="12886-134">The change management process should review all changes to the procedures.</span></span> <span data-ttu-id="12886-135">例如，建立內容資料庫或新增使用者時，不需要進行例行變更。</span><span class="sxs-lookup"><span data-stu-id="12886-135">It should not be needed for routine changes like creating a content database or adding a user.</span></span>

<span data-ttu-id="12886-136">下列變更管理範例會檢查不同的小組如何互動，以及部署新 service pack 時所執行的動作。</span><span class="sxs-lookup"><span data-stu-id="12886-136">The following example of change management examines how different teams interact and the actions that are performed when a new service pack is deployed.</span></span> <span data-ttu-id="12886-137">這些動作會透過變更管理程式進行組織和管理。</span><span class="sxs-lookup"><span data-stu-id="12886-137">These actions are organized and managed by the change management process.</span></span>

  - <span data-ttu-id="12886-138">**引發變更要求**    安全小組已評估最新的 service pack，並已確認它可解決實際執行系統中的可能弱點。</span><span class="sxs-lookup"><span data-stu-id="12886-138">**Raise a change request**   The security team has assessed the latest service pack and confirmed that it resolves a possible vulnerability in the production system.</span></span> <span data-ttu-id="12886-139">團隊會引發變更要求，讓新的累計更新套用至所有執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="12886-139">The team raises a change request to have the new cumulative update applied to all servers that are running Lync Server.</span></span>

  - <span data-ttu-id="12886-140">**Service pack 版本資訊備忘回顧**    Lync 管理員小組會複查 service pack 發行附注，以識別對系統的影響。</span><span class="sxs-lookup"><span data-stu-id="12886-140">**Service pack release notes review**   The Lync administrator team reviews the service pack release notes to identify the effect on the system.</span></span>

  - <span data-ttu-id="12886-141">執行一系列**的實驗室測試**    Lync 管理員小組必須在測試環境中的伺服器上執行測試更新，以決定 service pack 是否可成功套用，而不會影響任何已安裝的應用程式和伺服器系統。</span><span class="sxs-lookup"><span data-stu-id="12886-141">**A series of lab tests is performed**   The Lync administrator team must perform test updates on a server in a test environment to decide whether the service pack can be applied successfully without affecting any of the installed applications and server systems.</span></span> <span data-ttu-id="12886-142">如果有協力廠商或內部建立的應用程式在實際執行環境中與 Lync Server 介面，也應測試這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="12886-142">If there are third-party or internally created applications that interface with Lync Server in a production environment, these should be also tested.</span></span> <span data-ttu-id="12886-143">這些測試也可以用來估計執行升級所需的時間。</span><span class="sxs-lookup"><span data-stu-id="12886-143">These tests can also be used to estimate the time that is required to perform the upgrades.</span></span>

  - <span data-ttu-id="12886-144">**通知使用者停機**    Lync 系統管理員小組、通訊小組或使用者問訊台會通知所有受影響的使用者有關計畫的維修週期，以及服務將無法使用的時間。</span><span class="sxs-lookup"><span data-stu-id="12886-144">**Users are informed of the outage**   The Lync administrator team, communications team, or user help desk informs all affected users about the planned maintenance cycle and how long the service will be unavailable.</span></span>

  - <span data-ttu-id="12886-145">在**升級**     前執行 Lync 的完整備份當 service pack 安裝失敗時，Lync 管理員小組必須確認是否有有效的備份可用於還原為原始系統狀態。</span><span class="sxs-lookup"><span data-stu-id="12886-145">**A full backup of Lync is performed before the upgrade**   The Lync administrator team must verify that there is a valid backup that can be used to revert to the original system state if the service pack installation fails.</span></span> <span data-ttu-id="12886-146">建議您將備份還原至待命伺服器，以便在發生問題時可輕鬆使用此系統。</span><span class="sxs-lookup"><span data-stu-id="12886-146">We recommend that the backup be restored to a standby server to have this system readily available if there are issues.</span></span>

  - <span data-ttu-id="12886-147">**部署**     累計更新Lync 管理員小組會在規劃的維護週期內執行安裝。</span><span class="sxs-lookup"><span data-stu-id="12886-147">**The cumulative update is deployed**   The Lync administrator team does the installation during the planned maintenance cycle.</span></span>

<div>

## <a name="managing-the-timing-of-changes"></a><span data-ttu-id="12886-148">管理變更的時機</span><span class="sxs-lookup"><span data-stu-id="12886-148">Managing the timing of changes</span></span>

<span data-ttu-id="12886-149">建議您執行排程變更的程式，以避免在工作的重疊區段中造成中斷。</span><span class="sxs-lookup"><span data-stu-id="12886-149">We recommend that you implement a procedure for scheduling changes to avoid disruptions in overlapping sections of your work.</span></span> <span data-ttu-id="12886-150">例如，兩個小組可能都在規劃系統的微小變更。</span><span class="sxs-lookup"><span data-stu-id="12886-150">For example, two teams may both be planning a minor change to a system.</span></span> <span data-ttu-id="12886-151">一個小組可能會在集區上套用累計更新，而另一個小組正在將舊版使用者遷移至該集區。</span><span class="sxs-lookup"><span data-stu-id="12886-151">One team may be applying a cumulative update on a pool while another team is migrating legacy users into that pool.</span></span> <span data-ttu-id="12886-152">這兩個小組所影響的是另一個小組所做的變更，而每個小組可能不一定知道另一個小組所規劃的變更。</span><span class="sxs-lookup"><span data-stu-id="12886-152">Neither team is affected by the changes that the other team is planning, and each team may not necessarily know about changes that the other team is planning.</span></span> <span data-ttu-id="12886-153">如果同時發生這兩項變更，則可能會有執行變更的問題。</span><span class="sxs-lookup"><span data-stu-id="12886-153">If both changes occurred at the same time, there might be issues implementing the changes.</span></span> <span data-ttu-id="12886-154">此外，如果在套用變更之後發生問題，例如，如果使用者遷移失敗，可能很難決定應復原的變更。</span><span class="sxs-lookup"><span data-stu-id="12886-154">Also, if there are issues after the changes were applied, for example, if the user migration fails, it may be difficult to decide which change should be rolled back.</span></span> <span data-ttu-id="12886-155">在 IT 與管理之間應該設定定期維護期間，以測試變更並接受這些變更。</span><span class="sxs-lookup"><span data-stu-id="12886-155">There should be regular maintenance periods set up between IT and management to test the changes and accept them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

