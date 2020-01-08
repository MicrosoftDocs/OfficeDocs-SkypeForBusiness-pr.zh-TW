---
title: Lync Server 2013：變更管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13eb521ea6b4be5f8d701885df65a3e1672b2eaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a><span data-ttu-id="a4123-102">Lync Server 2013 中的變更管理</span><span class="sxs-lookup"><span data-stu-id="a4123-102">Change management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4123-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="a4123-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="a4123-104">無法避免對 IT 環境所做的變更。</span><span class="sxs-lookup"><span data-stu-id="a4123-104">Changes to the IT environment are unavoidable.</span></span> <span data-ttu-id="a4123-105">變更包括新技術、系統、應用程式、硬體、工具、流程，以及角色和職責中的變更。</span><span class="sxs-lookup"><span data-stu-id="a4123-105">Changes include new technologies, systems, applications, hardware, tools, processes, and changes in roles and responsibilities.</span></span> <span data-ttu-id="a4123-106">有效的變更管理系統可讓您快速地在 IT 環境中引入變更，並將服務中斷降至最低。</span><span class="sxs-lookup"><span data-stu-id="a4123-106">An effective change management system lets you introduce changes to the IT environment quickly and with minimal service disruption.</span></span> <span data-ttu-id="a4123-107">變更管理系統會將涉及變更系統的小組彙集在一起。</span><span class="sxs-lookup"><span data-stu-id="a4123-107">A change management system brings together the teams involved in changing a system.</span></span> <span data-ttu-id="a4123-108">例如，決定要利用 Office Web Apps。</span><span class="sxs-lookup"><span data-stu-id="a4123-108">For example, deciding to take advantage of the Office Web Apps.</span></span> <span data-ttu-id="a4123-109">這是一個整合的 Lync 服務應用程式，可讓使用者在瀏覽器中讀取及編輯檔。</span><span class="sxs-lookup"><span data-stu-id="a4123-109">This is an integrated Lync Service application that enables users to read and edit documents in a browser.</span></span> <span data-ttu-id="a4123-110">此服務的實現在您投入生產之後，需要幾個團隊的參與：</span><span class="sxs-lookup"><span data-stu-id="a4123-110">The implementation of this service, after you have gone into production, requires the involvement of several teams:</span></span>

  - <span data-ttu-id="a4123-111">**測試小組**   此小組載入-在測試伺服器上測試 Office Web Apps，此程式提供生產伺服器預期使用模式與預期效能的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a4123-111">**Test Team**   This team load-tests the Office Web Apps on a test server, in the process providing information about the expected usage patterns and expected performance of the production servers.</span></span>

  - <span data-ttu-id="a4123-112">**Lync 管理員**   ：這個小組會決定部署策略，並在可能的情況下，將安裝腳本腳本。</span><span class="sxs-lookup"><span data-stu-id="a4123-112">**Lync Administrators**   This team determines the deployment strategy and scripts the installation where it was possible.</span></span> <span data-ttu-id="a4123-113">小組負責確保變更已部署在生產環境中，且負責管理該變更。</span><span class="sxs-lookup"><span data-stu-id="a4123-113">The team is responsible for making sure that the change is deployed on the production environment, and it is responsible for administration afterward.</span></span> <span data-ttu-id="a4123-114">小組必須瞭解變更的效果，並將變更納入程式中，然後再將變更放入生產中</span><span class="sxs-lookup"><span data-stu-id="a4123-114">The team must understand the effect of the changes and incorporate them in procedures before the changes are put into production</span></span>

  - <span data-ttu-id="a4123-115">**網路小組**   ：此小組負責對防火牆規則所做的變更，允許從網際網路存取內部 Lync pool 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4123-115">**Network Team**   This team is responsible for changes to firewall rules that allow access from the Internet to the internal Lync pool servers.</span></span> <span data-ttu-id="a4123-116">小組也要與 Lync 系統管理員合作，以確保可用頻寬能夠支援額外的負載。</span><span class="sxs-lookup"><span data-stu-id="a4123-116">The team is also responsible in working with the Lync administrators for making sure that the available bandwidth can support the additional load.</span></span>

  - <span data-ttu-id="a4123-117">**安全小組**   這個小組會評估安全性並將風險降至最低。</span><span class="sxs-lookup"><span data-stu-id="a4123-117">**Security Team**   This team assesses security and minimizes risks.</span></span> <span data-ttu-id="a4123-118">安全小組必須審查已知的漏洞，並協助確保安全性風險降至最低。</span><span class="sxs-lookup"><span data-stu-id="a4123-118">The security team must review known vulnerabilities and help ensure that security risks are minimized.</span></span>

  - <span data-ttu-id="a4123-119">**使用者驗收小組**   這個小組是由願意測試系統並提供改良意見反應的使用者所組成。</span><span class="sxs-lookup"><span data-stu-id="a4123-119">**User Acceptance Team**   This team is composed of users who are willing to test the system and offer feedback for improvements.</span></span>

<span data-ttu-id="a4123-120">變更管理程式會定義每個團隊的職責，並排程所要執行的工作，並在必要時納入檢查和測試。</span><span class="sxs-lookup"><span data-stu-id="a4123-120">The change management process defines the responsibilities of each team and schedules the work to be performed, incorporating checks and tests where they are required.</span></span> <span data-ttu-id="a4123-121">變更控制項會根據複雜性及變更的預期效果而有所不同。</span><span class="sxs-lookup"><span data-stu-id="a4123-121">Change controls will vary depending on the complexity and expected effect of a change.</span></span> <span data-ttu-id="a4123-122">它們可能會因小變更的自動核准、變更評審會議，以及完全專案層級評論而有所不同。</span><span class="sxs-lookup"><span data-stu-id="a4123-122">They can vary from automatic approval of minor changes, to change review meetings, to full project-level reviews.</span></span> <span data-ttu-id="a4123-123">若要更清楚地說明這項功能，本節將討論變更群組。</span><span class="sxs-lookup"><span data-stu-id="a4123-123">To explain this better, the groups of changes are discussed in this section.</span></span>

  - <span data-ttu-id="a4123-124">**主要變更**   主要變更在系統上會有全域效果，而且可能需要來自不同小組的輸入。</span><span class="sxs-lookup"><span data-stu-id="a4123-124">**Major Changes**   Major changes have a global effect on the system and may require input from various teams.</span></span> <span data-ttu-id="a4123-125">升級至 Lync Server 2013 的範例。</span><span class="sxs-lookup"><span data-stu-id="a4123-125">An example of this is upgrading to Lync Server 2013.</span></span> <span data-ttu-id="a4123-126">主要變更會影響許多團隊，可能會有不同的系統。</span><span class="sxs-lookup"><span data-stu-id="a4123-126">Major changes affect many teams and perhaps different systems.</span></span> <span data-ttu-id="a4123-127">變更管理程式可能會包含一或多個變更評審會議，通知小組將參與變更或受變更影響。</span><span class="sxs-lookup"><span data-stu-id="a4123-127">The change management process will probably include one or more change review meetings to inform the teams that will be involved in the change or be affected by the change.</span></span>

  - <span data-ttu-id="a4123-128">**重要變更**   重要變更需要大量的資源來規劃、組建及實現。</span><span class="sxs-lookup"><span data-stu-id="a4123-128">**Significant Changes**   Significant changes require significant resources to plan, build, and implement.</span></span> <span data-ttu-id="a4123-129">應該引入適當的變更控制項，以協助確保已瞭解變更的效果、測試部署程式，以及回滾與應急方案已就緒。</span><span class="sxs-lookup"><span data-stu-id="a4123-129">Appropriate change controls should be introduced to help make ensure that the effect of the change is understood, deployment procedures are tested, and the rollback and contingency plans are ready.</span></span> <span data-ttu-id="a4123-130">部署新的累加更新是一個重要變更的範例。</span><span class="sxs-lookup"><span data-stu-id="a4123-130">An example of a significant change is deploying a new cumulative update.</span></span>

  - <span data-ttu-id="a4123-131">**次要變更**   微小變更不會顯著影響 IT 環境，例如，透過 Microsoft Lync Server 2013 [控制台] 變更某些 Lync 原則。</span><span class="sxs-lookup"><span data-stu-id="a4123-131">**Minor Changes**   Minor changes do not significantly affect the IT environment, for example, changing certain Lync policies via the Microsoft Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="a4123-132">**標準變更**   標準變更是定期執行，且充分瞭解並加以記錄。</span><span class="sxs-lookup"><span data-stu-id="a4123-132">**Standard Changes**   Standard changes are performed regularly and are well understood and documented.</span></span> <span data-ttu-id="a4123-133">變更管理程式應審查程式的所有變更。</span><span class="sxs-lookup"><span data-stu-id="a4123-133">The change management process should review all changes to the procedures.</span></span> <span data-ttu-id="a4123-134">在建立內容資料庫或新增使用者等例行變更時，不需要使用它。</span><span class="sxs-lookup"><span data-stu-id="a4123-134">It should not be needed for routine changes like creating a content database or adding a user.</span></span>

<span data-ttu-id="a4123-135">下列變更管理範例會檢查不同小組的互動方式，以及部署新 service pack 時所執行的動作。</span><span class="sxs-lookup"><span data-stu-id="a4123-135">The following example of change management examines how different teams interact and the actions that are performed when a new service pack is deployed.</span></span> <span data-ttu-id="a4123-136">這些動作由變更管理程式來組織和管理。</span><span class="sxs-lookup"><span data-stu-id="a4123-136">These actions are organized and managed by the change management process.</span></span>

  - <span data-ttu-id="a4123-137">**提出變更要求**   安全小組已評估最新的 service pack，並確認它能解決生產系統中可能的漏洞。</span><span class="sxs-lookup"><span data-stu-id="a4123-137">**Raise a change request**   The security team has assessed the latest service pack and confirmed that it resolves a possible vulnerability in the production system.</span></span> <span data-ttu-id="a4123-138">團隊會引發變更要求，以將新的累加更新套用至所有執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4123-138">The team raises a change request to have the new cumulative update applied to all servers that are running Lync Server.</span></span>

  - <span data-ttu-id="a4123-139">**Service pack 版本資訊檢查**   Lync 管理員小組審查 service pack 版本資訊，以找出系統上的效果。</span><span class="sxs-lookup"><span data-stu-id="a4123-139">**Service pack release notes review**   The Lync administrator team reviews the service pack release notes to identify the effect on the system.</span></span>

  - <span data-ttu-id="a4123-140">**一系列的實驗測試是由**   Lync 系統管理員小組必須在測試環境中的伺服器上執行測試更新，以決定是否能成功套用 service pack，而不會影響任何已安裝的應用程式和伺服器系統。</span><span class="sxs-lookup"><span data-stu-id="a4123-140">**A series of lab tests is performed**   The Lync administrator team must perform test updates on a server in a test environment to decide whether the service pack can be applied successfully without affecting any of the installed applications and server systems.</span></span> <span data-ttu-id="a4123-141">如果有在生產環境中與 Lync Server 進行介面的協力廠商或內部建立的應用程式，也應該加以測試。</span><span class="sxs-lookup"><span data-stu-id="a4123-141">If there are third-party or internally created applications that interface with Lync Server in a production environment, these should be also tested.</span></span> <span data-ttu-id="a4123-142">您也可以使用這些測試來估計執行升級所需的時間。</span><span class="sxs-lookup"><span data-stu-id="a4123-142">These tests can also be used to estimate the time that is required to perform the upgrades.</span></span>

  - <span data-ttu-id="a4123-143">\*\*\*\*    在 Lync 系統管理員小組、溝通小組或使用者技術人員的中斷中，系統會通知使用者，告訴所有受影響的使用者有關規劃中的維護週期，以及該服務將無法使用的時間。</span><span class="sxs-lookup"><span data-stu-id="a4123-143">**Users are informed of the outage**   The Lync administrator team, communications team, or user help desk informs all affected users about the planned maintenance cycle and how long the service will be unavailable.</span></span>

  - <span data-ttu-id="a4123-144">**在升級**   前執行 lync 的完整備份： lync 管理員小組必須確認有有效的備份可用於在 service pack 安裝失敗時還原為原始系統狀態。</span><span class="sxs-lookup"><span data-stu-id="a4123-144">**A full backup of Lync is performed before the upgrade**   The Lync administrator team must verify that there is a valid backup that can be used to revert to the original system state if the service pack installation fails.</span></span> <span data-ttu-id="a4123-145">我們建議將備份還原至待命伺服器，以讓此系統在發生問題時可供使用。</span><span class="sxs-lookup"><span data-stu-id="a4123-145">We recommend that the backup be restored to a standby server to have this system readily available if there are issues.</span></span>

  - <span data-ttu-id="a4123-146">**累積更新是由**   Lync 系統管理員小組在規劃的維護週期期間進行安裝。</span><span class="sxs-lookup"><span data-stu-id="a4123-146">**The cumulative update is deployed**   The Lync administrator team does the installation during the planned maintenance cycle.</span></span>

<div>

## <a name="managing-the-timing-of-changes"></a><span data-ttu-id="a4123-147">管理變更的時間</span><span class="sxs-lookup"><span data-stu-id="a4123-147">Managing the timing of changes</span></span>

<span data-ttu-id="a4123-148">我們建議您執行排程變更的程式，避免在工作的重疊區段中造成中斷。</span><span class="sxs-lookup"><span data-stu-id="a4123-148">We recommend that you implement a procedure for scheduling changes to avoid disruptions in overlapping sections of your work.</span></span> <span data-ttu-id="a4123-149">例如，兩個小組可能都會規劃對系統的微小變更。</span><span class="sxs-lookup"><span data-stu-id="a4123-149">For example, two teams may both be planning a minor change to a system.</span></span> <span data-ttu-id="a4123-150">一個小組可能會在另一個小組將舊版使用者遷移到該池中時，在池中套用累加更新。</span><span class="sxs-lookup"><span data-stu-id="a4123-150">One team may be applying a cumulative update on a pool while another team is migrating legacy users into that pool.</span></span> <span data-ttu-id="a4123-151">其他團隊正在規劃的變更不會影響任何小組，而且每個小組可能不一定知道其他小組正在規劃的變更。</span><span class="sxs-lookup"><span data-stu-id="a4123-151">Neither team is affected by the changes that the other team is planning, and each team may not necessarily know about changes that the other team is planning.</span></span> <span data-ttu-id="a4123-152">如果同時發生這兩種變更，可能會在實施變更時發生問題。</span><span class="sxs-lookup"><span data-stu-id="a4123-152">If both changes occurred at the same time, there might be issues implementing the changes.</span></span> <span data-ttu-id="a4123-153">此外，如果在應用變更之後發生問題，例如，如果使用者遷移失敗，可能很難決定要回滾哪些變更。</span><span class="sxs-lookup"><span data-stu-id="a4123-153">Also, if there are issues after the changes were applied, for example, if the user migration fails, it may be difficult to decide which change should be rolled back.</span></span> <span data-ttu-id="a4123-154">您應該在 IT 與管理之間設定定期維護期間，以測試變更並接受這些變更。</span><span class="sxs-lookup"><span data-stu-id="a4123-154">There should be regular maintenance periods set up between IT and management to test the changes and accept them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

