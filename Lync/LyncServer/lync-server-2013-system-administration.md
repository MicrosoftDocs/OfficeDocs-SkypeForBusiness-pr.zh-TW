---
title: Lync Server 2013：系統管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="df479-102">Lync Server 2013 中的系統管理</span><span class="sxs-lookup"><span data-stu-id="df479-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df479-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="df479-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="df479-104">系統管理包括日常管理工作（規劃中與隨選），這些任務必須讓 IT 系統保持順暢運作。</span><span class="sxs-lookup"><span data-stu-id="df479-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="df479-105">一般來說，系統管理工作是由書面程式所涵蓋。</span><span class="sxs-lookup"><span data-stu-id="df479-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="df479-106">這些程式可協助確保所有支援人員都使用相同的標準工具和方法。</span><span class="sxs-lookup"><span data-stu-id="df479-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="df479-107">在 Lync 環境中，典型的系統管理工作包括備份及封存池、監視記錄、建立及管理使用者，以及更新防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="df479-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="df479-108">系統疑難排解</span><span class="sxs-lookup"><span data-stu-id="df479-108">System troubleshooting</span></span>

<span data-ttu-id="df479-109">組織必須準備好處理意外問題，而且應該有一個程式可以從報告的位置管理問題，直到其解析度。</span><span class="sxs-lookup"><span data-stu-id="df479-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="df479-110">關於如何診斷問題的相關資訊，應該在將來錄製並使用，以避免不必要的重複工作完成。</span><span class="sxs-lookup"><span data-stu-id="df479-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="df479-111">系統疑難排解程式</span><span class="sxs-lookup"><span data-stu-id="df479-111">System troubleshooting process</span></span>

<span data-ttu-id="df479-112">下圖顯示系統疑難排解程式，以及與其他操作角色的互動。</span><span class="sxs-lookup"><span data-stu-id="df479-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="df479-113">**系統疑難排解流程圖**</span><span class="sxs-lookup"><span data-stu-id="df479-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="df479-114">![系統疑難排解流程圖](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系統疑難排解流程圖")</span><span class="sxs-lookup"><span data-stu-id="df479-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="df479-115">**分類及優先順序**   ：此工作通常是由服務台所執行。</span><span class="sxs-lookup"><span data-stu-id="df479-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="df479-116">例如，問題可能會組成軟體問題或硬體問題。</span><span class="sxs-lookup"><span data-stu-id="df479-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="df479-117">接著該問題會傳送給適當的支援小組以進行調查。</span><span class="sxs-lookup"><span data-stu-id="df479-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="df479-118">判斷問題優先順序的規則，以及回應時間及解決時間，通常是在 SLA 中定義。</span><span class="sxs-lookup"><span data-stu-id="df479-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="df479-119">**調查與診斷**   適當的支援小組診斷問題，並建議變更以解決問題。</span><span class="sxs-lookup"><span data-stu-id="df479-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="df479-120">如果解決方案很簡單且不需要變更控制，就可以立即套用此方案。</span><span class="sxs-lookup"><span data-stu-id="df479-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="df479-121">如果方案不是很簡單，就應該引發變更要求，而建議的工作應該由變更管理程式來管理，通常是在「快速追蹤」程式底下。</span><span class="sxs-lookup"><span data-stu-id="df479-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="df479-122">所做的任何變更，都應該使用建構管理程式來記錄。</span><span class="sxs-lookup"><span data-stu-id="df479-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="df479-123">\*\*\*\*    測試解析度之後，請關閉並錄製問題，請關閉該問題。</span><span class="sxs-lookup"><span data-stu-id="df479-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="df479-124">如果有要從問題中學到的課程，請在知識庫中建立一個專案。</span><span class="sxs-lookup"><span data-stu-id="df479-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="df479-125">**審查及趨勢分析**   定期檢查最近的問題，以找出問題趨勢。</span><span class="sxs-lookup"><span data-stu-id="df479-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="df479-126">例如，如果使用者經常遇到無法登錄至 Lync 網站的問題，可能是網路頻寬問題造成的。</span><span class="sxs-lookup"><span data-stu-id="df479-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="df479-127">問題的解決時間，應對系統可用性造成任何停機的影響，都應該經過審查並與 SLA 進行比較。</span><span class="sxs-lookup"><span data-stu-id="df479-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="df479-128">Liaises 服務問題的人員（例如客戶管理員），應該會收到任何重要問題。</span><span class="sxs-lookup"><span data-stu-id="df479-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="df479-129">問題管理工具</span><span class="sxs-lookup"><span data-stu-id="df479-129">Issue management tools</span></span>

<span data-ttu-id="df479-130">服務台工具可讓員工記錄、分類，以及排定新問題的優先順序。</span><span class="sxs-lookup"><span data-stu-id="df479-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="df479-131">然後，工具會提供工作流程處理常式來透過調查與診斷來管理問題服務要求，通常是由一個以上的支援小組。</span><span class="sxs-lookup"><span data-stu-id="df479-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="df479-132">工具（通常會提供有關解析度時間與記錄趨勢的報告）也可能包含知識庫資料庫，可用於搜尋過去的問題。</span><span class="sxs-lookup"><span data-stu-id="df479-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="df479-133">Microsoft 知識庫是 Microsoft 所遇到之支援問題的實用記錄。</span><span class="sxs-lookup"><span data-stu-id="df479-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="df479-134">如需詳細資訊，請參閱 Microsoft 支援網站<http://go.microsoft.com/fwlink/?linkid=14898>（）。</span><span class="sxs-lookup"><span data-stu-id="df479-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="df479-135">協力廠商軟體通常需要自訂，以符合組織的需求，例如團隊的組織、報告需求，以及 SLA 所需的量值。</span><span class="sxs-lookup"><span data-stu-id="df479-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="df479-136">集中化與分散式管理</span><span class="sxs-lookup"><span data-stu-id="df479-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="df479-137">執行系統管理工作的角色和職責，取決於組織是採用集中式模型、分散式模型，還是兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="df479-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="df479-138">**集中式模型**   在集中式模型中，有一個或多個系統管理群組維持對整個 Lync Server 環境的完整控制。</span><span class="sxs-lookup"><span data-stu-id="df479-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="df479-139">此管理模型與資料中心類似，其中所有的管理工作都是由單一資訊技術群組來執行。</span><span class="sxs-lookup"><span data-stu-id="df479-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="df479-140">小組中的角色和職責應該根據經驗與專業知識來定義。</span><span class="sxs-lookup"><span data-stu-id="df479-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="df479-141">**分散模型**   分散組織位於多個地理位置，而且在不同的位置都能運作 Lync 伺服器伺服器和系統管理員團隊。</span><span class="sxs-lookup"><span data-stu-id="df479-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="df479-142">例如，您可能會有本機管理人員，以及一或多個針對每個國家/地區執行 Lync Server 2013 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="df479-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="df479-143">或者，您可能會有一個伺服器池正在執行 Lync Server 2013，以及一個適用于北美的系統管理小組，一個用於歐洲。</span><span class="sxs-lookup"><span data-stu-id="df479-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="df479-144">有時候，您可能會希望系統管理員只負責自己的地理區域，並限制管理其他區域中資源的許可權。</span><span class="sxs-lookup"><span data-stu-id="df479-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="df479-145">Lync Server 也可讓您使用角色式存取控制（RBAC），將特定的管理工作委派給特定人員或群組。</span><span class="sxs-lookup"><span data-stu-id="df479-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="df479-146">RBAC 可讓管理員將特定的使用者權利和許可權委派給其他管理員，以執行可能的管理工作子集。</span><span class="sxs-lookup"><span data-stu-id="df479-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="df479-147">使用 RBAC，使用者執行特定系統管理工作的能力取決於指派給使用者的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="df479-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="df479-148">RBAC 會根據使用者所屬的 RBAC 角色，提供使用者可以執行的 Cmdlet 清單。</span><span class="sxs-lookup"><span data-stu-id="df479-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

