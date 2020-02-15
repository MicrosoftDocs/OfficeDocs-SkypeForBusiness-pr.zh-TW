---
title: Lync Server 2013： 變更管理
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
ms.openlocfilehash: abd6af0af5722d05d7439ac262ff36e62d2b12e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a><span data-ttu-id="89e65-102">Lync Server 2013 中的變更管理</span><span class="sxs-lookup"><span data-stu-id="89e65-102">Change management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89e65-103">_**上次修改主題：** 2014年-08-18_</span><span class="sxs-lookup"><span data-stu-id="89e65-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="89e65-104">變更至 IT 環境會無法避免。</span><span class="sxs-lookup"><span data-stu-id="89e65-104">Changes to the IT environment are unavoidable.</span></span> <span data-ttu-id="89e65-105">變更角色和責任，包括新的技術、 系統、 應用程式、 硬體、 工具、 程序，以及變更。</span><span class="sxs-lookup"><span data-stu-id="89e65-105">Changes include new technologies, systems, applications, hardware, tools, processes, and changes in roles and responsibilities.</span></span> <span data-ttu-id="89e65-106">有效的變更管理系統，可讓您變更引入 IT 環境，快速且具有最少服務中斷。</span><span class="sxs-lookup"><span data-stu-id="89e65-106">An effective change management system lets you introduce changes to the IT environment quickly and with minimal service disruption.</span></span> <span data-ttu-id="89e65-107">變更管理系統整合在一起的團隊參與變更系統。</span><span class="sxs-lookup"><span data-stu-id="89e65-107">A change management system brings together the teams involved in changing a system.</span></span> <span data-ttu-id="89e65-108">例如，若要利用 Office Web Apps 決定。</span><span class="sxs-lookup"><span data-stu-id="89e65-108">For example, deciding to take advantage of the Office Web Apps.</span></span> <span data-ttu-id="89e65-109">這是整合的 Lync 服務應用程式，可讓使用者讀取及編輯文件中的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="89e65-109">This is an integrated Lync Service application that enables users to read and edit documents in a browser.</span></span> <span data-ttu-id="89e65-110">實作這項服務，您已經投入正式之後, 需要有幾個小組的參與程度：</span><span class="sxs-lookup"><span data-stu-id="89e65-110">The implementation of this service, after you have gone into production, requires the involvement of several teams:</span></span>

  - <span data-ttu-id="89e65-111">**測試小組**   這小組負載測試 Office Web Apps 的測試伺服器上，提供預期的流量模式與預期的效能，實際執行伺服器的相關資訊的程序中。</span><span class="sxs-lookup"><span data-stu-id="89e65-111">**Test Team**   This team load-tests the Office Web Apps on a test server, in the process providing information about the expected usage patterns and expected performance of the production servers.</span></span>

  - <span data-ttu-id="89e65-112">**Lync 系統管理員**   此小組決定部署策略，並可能已安裝的指令碼。</span><span class="sxs-lookup"><span data-stu-id="89e65-112">**Lync Administrators**   This team determines the deployment strategy and scripts the installation where it was possible.</span></span> <span data-ttu-id="89e65-113">小組負責確保變更部署在生產環境，並負責管理之後。</span><span class="sxs-lookup"><span data-stu-id="89e65-113">The team is responsible for making sure that the change is deployed on the production environment, and it is responsible for administration afterward.</span></span> <span data-ttu-id="89e65-114">小組必須了解變更的效果，並將這些程序中所做的變更都放入實際執行環境之前</span><span class="sxs-lookup"><span data-stu-id="89e65-114">The team must understand the effect of the changes and incorporate them in procedures before the changes are put into production</span></span>

  - <span data-ttu-id="89e65-115">**網路團隊**   此小組負責變更允許從網際網路存取內部 Lync 集區伺服器的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="89e65-115">**Network Team**   This team is responsible for changes to firewall rules that allow access from the Internet to the internal Lync pool servers.</span></span> <span data-ttu-id="89e65-116">小組也負責中使用 Lync 系統管理員，確保可用頻寬可支援的額外負載。</span><span class="sxs-lookup"><span data-stu-id="89e65-116">The team is also responsible in working with the Lync administrators for making sure that the available bandwidth can support the additional load.</span></span>

  - <span data-ttu-id="89e65-117">**安全性小組**   此小組會評估安全性和風險降至最低。</span><span class="sxs-lookup"><span data-stu-id="89e65-117">**Security Team**   This team assesses security and minimizes risks.</span></span> <span data-ttu-id="89e65-118">安全性小組必須檢閱已知的弱點，並協助確保安全性風險會最小化。</span><span class="sxs-lookup"><span data-stu-id="89e65-118">The security team must review known vulnerabilities and help ensure that security risks are minimized.</span></span>

  - <span data-ttu-id="89e65-119">**使用者接受度小組**   此小組組成願意測試系統並提供意見反應的改良功能的使用者。</span><span class="sxs-lookup"><span data-stu-id="89e65-119">**User Acceptance Team**   This team is composed of users who are willing to test the system and offer feedback for improvements.</span></span>

<span data-ttu-id="89e65-120">變更管理程序定義的每個小組的責任，並排程工作，以執行，納入檢查與它們所需的測試。</span><span class="sxs-lookup"><span data-stu-id="89e65-120">The change management process defines the responsibilities of each team and schedules the work to be performed, incorporating checks and tests where they are required.</span></span> <span data-ttu-id="89e65-121">變更控制項而定的複雜度和變更的預期的影響。</span><span class="sxs-lookup"><span data-stu-id="89e65-121">Change controls will vary depending on the complexity and expected effect of a change.</span></span> <span data-ttu-id="89e65-122">他們從自動核准的次要變更，若要變更為完整專案層級評論的檢閱會議，而異。</span><span class="sxs-lookup"><span data-stu-id="89e65-122">They can vary from automatic approval of minor changes, to change review meetings, to full project-level reviews.</span></span> <span data-ttu-id="89e65-123">若要進一步說明這個，本節討論變更的群組。</span><span class="sxs-lookup"><span data-stu-id="89e65-123">To explain this better, the groups of changes are discussed in this section.</span></span>

  - <span data-ttu-id="89e65-124">**主要變更**   重大變更具有通用影響系統及可能需要從各種 microsoft teams 的輸入。</span><span class="sxs-lookup"><span data-stu-id="89e65-124">**Major Changes**   Major changes have a global effect on the system and may require input from various teams.</span></span> <span data-ttu-id="89e65-125">例如，這升級至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="89e65-125">An example of this is upgrading to Lync Server 2013.</span></span> <span data-ttu-id="89e65-126">主要的變更會影響許多 microsoft teams 和或許是不同的系統。</span><span class="sxs-lookup"><span data-stu-id="89e65-126">Major changes affect many teams and perhaps different systems.</span></span> <span data-ttu-id="89e65-127">變更管理程序可能會包含一或多個變更檢閱會議來通知的團隊都將會變更所涉及或變更所影響。</span><span class="sxs-lookup"><span data-stu-id="89e65-127">The change management process will probably include one or more change review meetings to inform the teams that will be involved in the change or be affected by the change.</span></span>

  - <span data-ttu-id="89e65-128">**重大變更**   重大變更，需要大量資源計劃、 建置及實作。</span><span class="sxs-lookup"><span data-stu-id="89e65-128">**Significant Changes**   Significant changes require significant resources to plan, build, and implement.</span></span> <span data-ttu-id="89e65-129">適當的變更控制項應採用以協助提升確定理解變更的影響、 測試部署程序，且 rollback 和緊急應變計劃已做好準備。</span><span class="sxs-lookup"><span data-stu-id="89e65-129">Appropriate change controls should be introduced to help make ensure that the effect of the change is understood, deployment procedures are tested, and the rollback and contingency plans are ready.</span></span> <span data-ttu-id="89e65-130">重大變更的範例部署新的累計更新。</span><span class="sxs-lookup"><span data-stu-id="89e65-130">An example of a significant change is deploying a new cumulative update.</span></span>

  - <span data-ttu-id="89e65-131">**次要變更**   次要變更不會大幅影響 IT 環境中，例如，變更透過 Microsoft Lync Server 2013 控制台特定 Lync 原則。</span><span class="sxs-lookup"><span data-stu-id="89e65-131">**Minor Changes**   Minor changes do not significantly affect the IT environment, for example, changing certain Lync policies via the Microsoft Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="89e65-132">**標準變更**   標準的變更會定期執行和容易理解且記錄。</span><span class="sxs-lookup"><span data-stu-id="89e65-132">**Standard Changes**   Standard changes are performed regularly and are well understood and documented.</span></span> <span data-ttu-id="89e65-133">變更管理程序應該檢閱程序的所有變更。</span><span class="sxs-lookup"><span data-stu-id="89e65-133">The change management process should review all changes to the procedures.</span></span> <span data-ttu-id="89e65-134">它應該不需要建立內容資料庫，或將使用者新增例行變更。</span><span class="sxs-lookup"><span data-stu-id="89e65-134">It should not be needed for routine changes like creating a content database or adding a user.</span></span>

<span data-ttu-id="89e65-135">變更管理下列範例會檢查方式不同團隊互動，並部署新的 service pack 時，會執行的動作。</span><span class="sxs-lookup"><span data-stu-id="89e65-135">The following example of change management examines how different teams interact and the actions that are performed when a new service pack is deployed.</span></span> <span data-ttu-id="89e65-136">這些動作組織及管理的變更管理程序。</span><span class="sxs-lookup"><span data-stu-id="89e65-136">These actions are organized and managed by the change management process.</span></span>

  - <span data-ttu-id="89e65-137">**引發變更要求**   安全性小組已評估最新的 service pack，並確認它在實際執行系統中可以解決可能弱點。</span><span class="sxs-lookup"><span data-stu-id="89e65-137">**Raise a change request**   The security team has assessed the latest service pack and confirmed that it resolves a possible vulnerability in the production system.</span></span> <span data-ttu-id="89e65-138">小組會引發變更要求給已套用到所有伺服器執行 Lync Server 的新累計更新。</span><span class="sxs-lookup"><span data-stu-id="89e65-138">The team raises a change request to have the new cumulative update applied to all servers that are running Lync Server.</span></span>

  - <span data-ttu-id="89e65-139">**Service pack 發行 notes 檢閱**   Lync 管理員小組檢閱 service pack 版本資訊來識別系統上的效果。</span><span class="sxs-lookup"><span data-stu-id="89e65-139">**Service pack release notes review**   The Lync administrator team reviews the service pack release notes to identify the effect on the system.</span></span>

  - <span data-ttu-id="89e65-140">**執行一系列的測試實驗室**   Lync 管理員小組必須決定是否 service pack 可以順利套用而不影響任何已安裝的應用程式與伺服器系統的測試環境中的伺服器上執行測試更新。</span><span class="sxs-lookup"><span data-stu-id="89e65-140">**A series of lab tests is performed**   The Lync administrator team must perform test updates on a server in a test environment to decide whether the service pack can be applied successfully without affecting any of the installed applications and server systems.</span></span> <span data-ttu-id="89e65-141">如果有協力廠商或內部建立介面的應用程式與 Lync Server，在實際執行環境中，這些應該也未經過測試。</span><span class="sxs-lookup"><span data-stu-id="89e65-141">If there are third-party or internally created applications that interface with Lync Server in a production environment, these should be also tested.</span></span> <span data-ttu-id="89e65-142">這些測試也可以用來評估，才能執行升級的時間。</span><span class="sxs-lookup"><span data-stu-id="89e65-142">These tests can also be used to estimate the time that is required to perform the upgrades.</span></span>

  - <span data-ttu-id="89e65-143">**使用者會通知的中斷**   Lync 管理員小組、 通訊小組或使用者支援工程師通知所有受影響的使用者的計劃的維護週期和多久服務將無法使用。</span><span class="sxs-lookup"><span data-stu-id="89e65-143">**Users are informed of the outage**   The Lync administrator team, communications team, or user help desk informs all affected users about the planned maintenance cycle and how long the service will be unavailable.</span></span>

  - <span data-ttu-id="89e65-144">**Lync 的完整備份執行升級前**   Lync 管理員小組必須確認是有效的備份，可以用來安裝 service pack 失敗時還原成原來的系統狀態。</span><span class="sxs-lookup"><span data-stu-id="89e65-144">**A full backup of Lync is performed before the upgrade**   The Lync administrator team must verify that there is a valid backup that can be used to revert to the original system state if the service pack installation fails.</span></span> <span data-ttu-id="89e65-145">我們建議您備份，還原至待命伺服器至已備妥此系統，如果有問題。</span><span class="sxs-lookup"><span data-stu-id="89e65-145">We recommend that the backup be restored to a standby server to have this system readily available if there are issues.</span></span>

  - <span data-ttu-id="89e65-146">**部署累計更新**   Lync 管理員小組並未計劃的維護週期期間安裝。</span><span class="sxs-lookup"><span data-stu-id="89e65-146">**The cumulative update is deployed**   The Lync administrator team does the installation during the planned maintenance cycle.</span></span>

<div>

## <a name="managing-the-timing-of-changes"></a><span data-ttu-id="89e65-147">管理變更的時機</span><span class="sxs-lookup"><span data-stu-id="89e65-147">Managing the timing of changes</span></span>

<span data-ttu-id="89e65-148">我們建議您實作排程變更] 以避免干擾中重疊的工作的各節的程序。</span><span class="sxs-lookup"><span data-stu-id="89e65-148">We recommend that you implement a procedure for scheduling changes to avoid disruptions in overlapping sections of your work.</span></span> <span data-ttu-id="89e65-149">例如，兩個小組可能同時規劃系統的次要變更。</span><span class="sxs-lookup"><span data-stu-id="89e65-149">For example, two teams may both be planning a minor change to a system.</span></span> <span data-ttu-id="89e65-150">一小組可能要套用累計更新或集區時另一個小組會將舊版使用者移轉至該集區。</span><span class="sxs-lookup"><span data-stu-id="89e65-150">One team may be applying a cumulative update on a pool while another team is migrating legacy users into that pool.</span></span> <span data-ttu-id="89e65-151">未小組會受到其他小組規劃，變更和每個小組可能不一定是了解規劃其他小組的變更。</span><span class="sxs-lookup"><span data-stu-id="89e65-151">Neither team is affected by the changes that the other team is planning, and each team may not necessarily know about changes that the other team is planning.</span></span> <span data-ttu-id="89e65-152">如果同時發生這兩種變更，可能會有問題實作所做的變更。</span><span class="sxs-lookup"><span data-stu-id="89e65-152">If both changes occurred at the same time, there might be issues implementing the changes.</span></span> <span data-ttu-id="89e65-153">此外，如果之後所做的變更已套用有問題，例如，如果使用者移轉失敗，它可能難以決定哪些變更應該復原。</span><span class="sxs-lookup"><span data-stu-id="89e65-153">Also, if there are issues after the changes were applied, for example, if the user migration fails, it may be difficult to decide which change should be rolled back.</span></span> <span data-ttu-id="89e65-154">應該定期維護期間設定之間 IT 和測試所做的變更，並接受加以管理。</span><span class="sxs-lookup"><span data-stu-id="89e65-154">There should be regular maintenance periods set up between IT and management to test the changes and accept them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

