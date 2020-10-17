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
ms.openlocfilehash: 7c830b689f0f55c2af191443583394e9f8c22eed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497500"
---
# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="feb28-102">Lync Server 2013 中的系統管理</span><span class="sxs-lookup"><span data-stu-id="feb28-102">System administration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feb28-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="feb28-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="feb28-104">系統管理包括一天的日常管理工作，也就是已計畫及隨需的管理工作，都是讓 IT 系統保持順利運作所需的作業。</span><span class="sxs-lookup"><span data-stu-id="feb28-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="feb28-105">通常，系統管理工作會在書面程式中涵蓋。</span><span class="sxs-lookup"><span data-stu-id="feb28-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="feb28-106">這些程式可協助確保所有支援人員都使用相同的標準工具和方法。</span><span class="sxs-lookup"><span data-stu-id="feb28-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="feb28-107">在 Lync 環境中，一般系統管理工作包括備份及封存集區、監控記錄檔、建立及管理使用者，以及更新防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="feb28-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="feb28-108">系統疑難排解</span><span class="sxs-lookup"><span data-stu-id="feb28-108">System troubleshooting</span></span>

<span data-ttu-id="feb28-109">組織必須準備好處理未預期的問題，而且應該有一個程式可從報告問題的位置開始，直到解決問題為止。</span><span class="sxs-lookup"><span data-stu-id="feb28-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="feb28-110">有關如何診斷問題之支援人員的資訊應該記錄下來，以備今後使用，以避免不必要的重複作業。</span><span class="sxs-lookup"><span data-stu-id="feb28-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="feb28-111">系統疑難排解程式</span><span class="sxs-lookup"><span data-stu-id="feb28-111">System troubleshooting process</span></span>

<span data-ttu-id="feb28-112">下圖顯示系統疑難排解程式以及與其他作業角色的互動。</span><span class="sxs-lookup"><span data-stu-id="feb28-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="feb28-113">**系統疑難排解流程圖**</span><span class="sxs-lookup"><span data-stu-id="feb28-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="feb28-114">![系統疑難排解流程圖](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系統疑難排解流程圖")</span><span class="sxs-lookup"><span data-stu-id="feb28-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="feb28-115">**分類及優先順序**    此工作通常是由服務台執行。</span><span class="sxs-lookup"><span data-stu-id="feb28-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="feb28-116">例如，問題可能會歸群組為軟體問題或硬體問題。</span><span class="sxs-lookup"><span data-stu-id="feb28-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="feb28-117">然後將問題路由傳送給適當的支援小組進行調查。</span><span class="sxs-lookup"><span data-stu-id="feb28-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="feb28-118">判斷問題優先順序的規則以及回應的時間及解決時間，通常是在 SLA 中定義的。</span><span class="sxs-lookup"><span data-stu-id="feb28-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="feb28-119">**調查和診斷**    適當的支援小組會診斷問題，並建議變更以解決問題。</span><span class="sxs-lookup"><span data-stu-id="feb28-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="feb28-120">如果解決方案很簡單且不需要變更控制，則可以立即套用解決方案。</span><span class="sxs-lookup"><span data-stu-id="feb28-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="feb28-121">如果解決方案不是很簡單，應會引發變更要求，而建議的工作應該由變更管理程式（通常是「快速追蹤」）來管理。</span><span class="sxs-lookup"><span data-stu-id="feb28-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="feb28-122">所做的任何變更都應該使用設定管理程式來記錄。</span><span class="sxs-lookup"><span data-stu-id="feb28-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="feb28-123">**Close 和 Record**    測試解決方法後，應關閉問題。</span><span class="sxs-lookup"><span data-stu-id="feb28-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="feb28-124">如果有從問題中學到的課程，應在知識庫中建立專案。</span><span class="sxs-lookup"><span data-stu-id="feb28-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="feb28-125">**回顧和趨勢分析**    應該定期複查最近的問題，以找出問題趨勢。</span><span class="sxs-lookup"><span data-stu-id="feb28-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="feb28-126">例如，如果使用者發生經常的登入至其 Lync 網站的問題，可能是網路頻寬問題。</span><span class="sxs-lookup"><span data-stu-id="feb28-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="feb28-127">問題的解決時間，應檢查任何中斷系統可用性的影響，並與 SLA 進行比較。</span><span class="sxs-lookup"><span data-stu-id="feb28-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="feb28-128">與客戶 liaises 服務問題（如帳戶管理員）的人員應該知道任何重大問題。</span><span class="sxs-lookup"><span data-stu-id="feb28-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="feb28-129">問題管理工具</span><span class="sxs-lookup"><span data-stu-id="feb28-129">Issue management tools</span></span>

<span data-ttu-id="feb28-130">服務台工具可讓員工記錄、分類及優先順序新的問題。</span><span class="sxs-lookup"><span data-stu-id="feb28-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="feb28-131">然後，工具會提供工作流程處理常式，透過調查和診斷來管理問題服務要求，這通常是由多個支援小組進行。</span><span class="sxs-lookup"><span data-stu-id="feb28-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="feb28-132">工具（通常會提供有關解析度時間及歷史趨勢的報告）可能也會包含知識庫資料庫，可用於搜尋過去的問題。</span><span class="sxs-lookup"><span data-stu-id="feb28-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="feb28-133">Microsoft 知識庫是 Microsoft 所遇到支援問題的有用記錄。</span><span class="sxs-lookup"><span data-stu-id="feb28-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="feb28-134">如需詳細資訊，請參閱 Microsoft 支援網站 (<https://go.microsoft.com/fwlink/?linkid=14898>) 。</span><span class="sxs-lookup"><span data-stu-id="feb28-134">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="feb28-135">協力廠商軟體通常需要自訂，以符合組織的需求，例如小組組織、報告需求，以及 SLA 所需的量值。</span><span class="sxs-lookup"><span data-stu-id="feb28-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="feb28-136">集中式管理與分散式管理</span><span class="sxs-lookup"><span data-stu-id="feb28-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="feb28-137">執行系統管理工作的角色和責任取決於組織遵循集中式模型、分散式模型或兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="feb28-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="feb28-138">**集中式模型**    在集中式模型中，一或多個系統管理群組維護完整的 Lync 伺服器環境控制。</span><span class="sxs-lookup"><span data-stu-id="feb28-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="feb28-139">這種系統管理模型類似于資料中心，所有的管理工作都是由單一資訊技術群組執行。</span><span class="sxs-lookup"><span data-stu-id="feb28-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="feb28-140">小組中的角色和責任應根據經驗和專業知識加以定義。</span><span class="sxs-lookup"><span data-stu-id="feb28-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="feb28-141">**分散模型**    分散組織位於數個地理位置，且在不同的位置運作 Lync Server 伺服器和管理員團隊。</span><span class="sxs-lookup"><span data-stu-id="feb28-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="feb28-142">例如，對於每個國家/地區，可能會有本機管理人員和一或多部執行 Lync Server 2013 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="feb28-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="feb28-143">或者，您可能會有執行 Lync Server 2013 的伺服器集區，以及一部適用于北美和第一版的系統管理團隊。</span><span class="sxs-lookup"><span data-stu-id="feb28-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="feb28-144">在某些情況下，您可能會想要讓系統管理員只負責其專屬地理區域，並限制管理其他區域中資源的許可權。</span><span class="sxs-lookup"><span data-stu-id="feb28-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="feb28-145">Lync Server 也可讓您使用以角色為基礎的存取控制 (RBAC) ，將特定的管理工作委派給特定人員或群組。</span><span class="sxs-lookup"><span data-stu-id="feb28-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="feb28-146">RBAC 可讓系統管理員將特定使用者權利和許可權委派給其他管理員，以執行可能的系統管理工作子集。</span><span class="sxs-lookup"><span data-stu-id="feb28-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="feb28-147">透過使用 RBAC，使用者執行特定系統管理工作的能力，會根據指派給使用者的 RBAC 角色而定。</span><span class="sxs-lookup"><span data-stu-id="feb28-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="feb28-148">RBAC 提供使用者可根據使用者隸屬之 RBAC 角色執行的 Cmdlet 清單。</span><span class="sxs-lookup"><span data-stu-id="feb28-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

