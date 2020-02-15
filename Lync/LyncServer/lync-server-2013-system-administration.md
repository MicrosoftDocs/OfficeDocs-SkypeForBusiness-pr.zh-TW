---
title: Lync Server 2013： 系統管理
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
ms.openlocfilehash: 61285a73ba7fd3689842f15967286c4393b8e927
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="8fda3-102">Lync Server 2013 中的系統管理</span><span class="sxs-lookup"><span data-stu-id="8fda3-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fda3-103">_**上次修改主題：** 2014年-08-18_</span><span class="sxs-lookup"><span data-stu-id="8fda3-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8fda3-104">系統管理包含的日常系統管理工作、 兩者計劃及依需求所需讓 IT 系統操作順暢。</span><span class="sxs-lookup"><span data-stu-id="8fda3-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="8fda3-105">一般而言，撰寫程序所涵蓋的系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="8fda3-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="8fda3-106">這些程序可協助確保所有的支援人員，所使用的相同的標準工具和方法。</span><span class="sxs-lookup"><span data-stu-id="8fda3-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="8fda3-107">在 Lync 環境中，一般系統管理工作包括備份及封存集區、 監視記錄檔、 建立與管理使用者，以及更新防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="8fda3-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="8fda3-108">系統疑難排解</span><span class="sxs-lookup"><span data-stu-id="8fda3-108">System troubleshooting</span></span>

<span data-ttu-id="8fda3-109">組織必須準備好處理未預期的問題，且應該具有從這些報告直到其解決方案在其中點管理問題的程序。</span><span class="sxs-lookup"><span data-stu-id="8fda3-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="8fda3-110">如何支援人員來診斷問題的相關資訊應記錄，且在未來用來避免不必要地重複已完成的工時。</span><span class="sxs-lookup"><span data-stu-id="8fda3-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="8fda3-111">系統疑難排解程序</span><span class="sxs-lookup"><span data-stu-id="8fda3-111">System troubleshooting process</span></span>

<span data-ttu-id="8fda3-112">下圖顯示系統疑難排解程序和其他作業角色互動。</span><span class="sxs-lookup"><span data-stu-id="8fda3-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="8fda3-113">**系統疑難排解流程圖**</span><span class="sxs-lookup"><span data-stu-id="8fda3-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="8fda3-114">![系統疑難排解流程圖](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系統疑難排解流程圖")</span><span class="sxs-lookup"><span data-stu-id="8fda3-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="8fda3-115">**分類及排列優先順序**   通常由服務台執行這項工作。</span><span class="sxs-lookup"><span data-stu-id="8fda3-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="8fda3-116">例如，問題可能會分組為軟體問題或硬體問題。</span><span class="sxs-lookup"><span data-stu-id="8fda3-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="8fda3-117">問題是然後路由傳送到適當的支援小組的調查。</span><span class="sxs-lookup"><span data-stu-id="8fda3-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="8fda3-118">判斷問題，以及回應及解決問題，有時間的時間的優先順序的規則通常是在 SLA 中定義。</span><span class="sxs-lookup"><span data-stu-id="8fda3-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="8fda3-119">**調查並診斷**   適當支援小組診斷問題，並建議以解決問題的變更。</span><span class="sxs-lookup"><span data-stu-id="8fda3-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="8fda3-120">如果解決方案十分簡單，而且不需要變更控制，可立即套用解決方案。</span><span class="sxs-lookup"><span data-stu-id="8fda3-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="8fda3-121">如果解決方案並不容易，應該引發變更要求，並建議的工時應該由經常底下的 「 快速入門 」 程序的變更管理程序。</span><span class="sxs-lookup"><span data-stu-id="8fda3-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="8fda3-122">應該使用的組態管理程序記錄所做的任何變更。</span><span class="sxs-lookup"><span data-stu-id="8fda3-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="8fda3-123">**關閉並且將密碼記錄**   後測試解決方案時，應該關閉問題。</span><span class="sxs-lookup"><span data-stu-id="8fda3-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="8fda3-124">如果沒有此問題： 從學習課程，應該建立一個項目在知識庫中。</span><span class="sxs-lookup"><span data-stu-id="8fda3-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="8fda3-125">**檢閱及分析趨勢**   應該執行定期檢閱最近的問題，以識別問題的趨勢。</span><span class="sxs-lookup"><span data-stu-id="8fda3-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="8fda3-126">例如，如果使用者遇到緩慢的登入其 Lync 網站的常見問題，網路頻寬問題可能的原因。</span><span class="sxs-lookup"><span data-stu-id="8fda3-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="8fda3-127">應該檢閱，相較於 SLA 問題的解決時間，對於系統的可用性任何中斷的影響。</span><span class="sxs-lookup"><span data-stu-id="8fda3-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="8fda3-128">任何重大問題，應通知 liaises 與服務問題，例如帳戶管理員] 中，在客戶的人員。</span><span class="sxs-lookup"><span data-stu-id="8fda3-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="8fda3-129">此問題： 管理工具</span><span class="sxs-lookup"><span data-stu-id="8fda3-129">Issue management tools</span></span>

<span data-ttu-id="8fda3-130">Service desk 工具可讓人員來記錄、 分類，並排定優先順序新的問題。</span><span class="sxs-lookup"><span data-stu-id="8fda3-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="8fda3-131">接著工具會提供工作流程處理程序來管理此問題： 服務要求透過調查與診斷，通常由一個以上的支援小組。</span><span class="sxs-lookup"><span data-stu-id="8fda3-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="8fda3-132">工具，將會經常提供有關的解決時間與歷史趨勢報告，也可能包含知識庫資料庫中，可以用來搜尋整個過去的問題。</span><span class="sxs-lookup"><span data-stu-id="8fda3-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="8fda3-133">Microsoft 知識庫是很有用記錄遭遇到 microsoft 的支援問題。</span><span class="sxs-lookup"><span data-stu-id="8fda3-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="8fda3-134">如需詳細資訊，請參閱 Microsoft 支援網站 (<http://go.microsoft.com/fwlink/?linkid=14898>)。</span><span class="sxs-lookup"><span data-stu-id="8fda3-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="8fda3-135">協力廠商軟體通常需要自訂以符合組織的需求，例如 teams，報表需求，以及所需的 SLA 的量值的組織。</span><span class="sxs-lookup"><span data-stu-id="8fda3-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="8fda3-136">集中式與管理對分散管理</span><span class="sxs-lookup"><span data-stu-id="8fda3-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="8fda3-137">角色與職責執行系統管理工作取決於組織遵循集中的模型、 分散式的模型中或兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="8fda3-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="8fda3-138">**集中式模型**   在集中式模型中，一或多個系統管理群組會維護整個 Lync Server 環境的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="8fda3-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="8fda3-139">此系統管理模型類似於由單一資訊技術群組執行所有的管理工作的資料中心。</span><span class="sxs-lookup"><span data-stu-id="8fda3-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="8fda3-140">您應該根據經驗及專業知識定義角色和責任小組內。</span><span class="sxs-lookup"><span data-stu-id="8fda3-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="8fda3-141">**分散模型**   分散式組織都位於多個地理位置且有可正常運作的 Lync Server 伺服器和小組的系統管理員的不同位置。</span><span class="sxs-lookup"><span data-stu-id="8fda3-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="8fda3-142">例如，有可能是本機系統管理人員和執行 Lync Server 2013 每個國家/地區的一個或多個伺服器。</span><span class="sxs-lookup"><span data-stu-id="8fda3-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="8fda3-143">或者，可能會有執行 Lync Server 2013 和北美地區的系統管理小組，一個用於歐洲的伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="8fda3-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="8fda3-144">有時候，您可能想只負責自己的地理區域，並限制管理其他區域中的資源的權限的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="8fda3-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="8fda3-145">Lync Server 也可讓您藉由使用角色型存取控制 (RBAC) 將特定的管理工作委派給特定人員或群組。</span><span class="sxs-lookup"><span data-stu-id="8fda3-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="8fda3-146">RBAC 允許委派特定的使用者權限和其他系統管理員執行的部分可能的管理工作的權限的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="8fda3-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="8fda3-147">藉由使用 RBAC，使用者能夠執行特定的管理工作取決於指派給使用者的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="8fda3-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="8fda3-148">RBAC 會提供使用者又能執行的 cmdlet 根據使用者是成員的 RBAC 角色的清單。</span><span class="sxs-lookup"><span data-stu-id="8fda3-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

