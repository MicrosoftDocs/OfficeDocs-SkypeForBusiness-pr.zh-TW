---
title: Lync Server 2013：容量及可用性管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 169c2e383a1799f5f3ab7ca810de32f86350e51b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="23356-102">Lync Server 2013 的容量及可用性管理</span><span class="sxs-lookup"><span data-stu-id="23356-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23356-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="23356-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="23356-104">容量管理和可用性管理的目的是測量及控制系統效能。</span><span class="sxs-lookup"><span data-stu-id="23356-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="23356-105">我們建議您實施容量管理和可用性管理程式，讓您能夠測量及控制系統效能。</span><span class="sxs-lookup"><span data-stu-id="23356-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="23356-106">您必須先設定 [比較基準] 並監視系統，以尋找趨勢，以瞭解系統是否可供使用。</span><span class="sxs-lookup"><span data-stu-id="23356-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="23356-107">容量管理</span><span class="sxs-lookup"><span data-stu-id="23356-107">Capacity management</span></span>

<span data-ttu-id="23356-108">容量管理涉及規劃、調整大小及控制服務容量，以協助保證已超過您 SLA 中指定的最低效能等級。</span><span class="sxs-lookup"><span data-stu-id="23356-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="23356-109">良好的容量管理可協助確保您能夠以合理的成本提供 IT 服務，而且仍能符合您在 Sla 中定義的效能等級與用戶端。</span><span class="sxs-lookup"><span data-stu-id="23356-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="23356-110">這些準則可包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="23356-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="23356-111">**系統回應時間**   ：這是系統執行一般動作所需的測量時間。</span><span class="sxs-lookup"><span data-stu-id="23356-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="23356-112">範例包括音訊/視訊伺服器角色處理音訊/視頻流量所需的時間、建立及加入會議所需的時間，或在所有觀察者用戶端中要更新目前狀態所需的時間。</span><span class="sxs-lookup"><span data-stu-id="23356-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="23356-113">**儲存容量**   這是指儲存系統（無論是內容資料庫、備份裝置或本機磁片磁碟機）的容量。</span><span class="sxs-lookup"><span data-stu-id="23356-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="23356-114">範例包括每個網站所要提供的儲存空間量，以及備份在覆寫之前應該儲存的時間。</span><span class="sxs-lookup"><span data-stu-id="23356-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="23356-115">調整容量通常是確定有足夠的物理資源（例如磁碟空間和網路頻寬）可用的情況。</span><span class="sxs-lookup"><span data-stu-id="23356-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="23356-116">下表列出與容量相關問題的一般解析度。</span><span class="sxs-lookup"><span data-stu-id="23356-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="23356-117">針對容量相關問題的一般解決方案</span><span class="sxs-lookup"><span data-stu-id="23356-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23356-118">問題</span><span class="sxs-lookup"><span data-stu-id="23356-118">Issue</span></span></th>
<th><span data-ttu-id="23356-119">可能的解決方法</span><span class="sxs-lookup"><span data-stu-id="23356-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23356-120">無法進行音訊/視頻效能較差的遠端使用者</span><span class="sxs-lookup"><span data-stu-id="23356-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="23356-121">查看 WAN 連結上是否有適當的頻寬，以及是否已啟用 QoS 且已適當設定。</span><span class="sxs-lookup"><span data-stu-id="23356-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="23356-122">檢查 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="23356-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23356-123">Lync 環境的整體回應速度緩慢。</span><span class="sxs-lookup"><span data-stu-id="23356-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="23356-124">執行測試，檢查現有的前端伺服器是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="23356-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="23356-125">如有需要，請介紹新的前端伺服器。檢查 SQL 資料庫回應時間並修正延遲的原因（例如，改善磁片輸入/輸出）。</span><span class="sxs-lookup"><span data-stu-id="23356-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23356-126">如有更詳細的疑難排解，請參考 Lync Server 網路指南。</span><span class="sxs-lookup"><span data-stu-id="23356-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="23356-127">容量受系統設定影響，視物理資源（例如網路頻寬）而定。</span><span class="sxs-lookup"><span data-stu-id="23356-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="23356-128">例如，如果 Lync 環境設定為在夜間執行完整的備份，請務必小心，以協助保證使用者對互動式效能所產生的影響最小化。</span><span class="sxs-lookup"><span data-stu-id="23356-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="23356-129">容量管理是將系統容量保持在可接受的層級並解決下列問題的過程：</span><span class="sxs-lookup"><span data-stu-id="23356-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="23356-130">**回應需求**   產能需求的變更必須調整為考慮系統或組織中的變更。</span><span class="sxs-lookup"><span data-stu-id="23356-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="23356-131">例如，如果您的環境決定要實現企業語音，則中繼伺服器與公用交換電話網絡（PSTN）閘道的數目和位置將會非常重要。</span><span class="sxs-lookup"><span data-stu-id="23356-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="23356-132">如果您要進行會話初始通訊協定（SIP）中繼或直接 SIP，整體設計將會有很大的變更，以提供最佳的企業語音效能。</span><span class="sxs-lookup"><span data-stu-id="23356-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="23356-133">**預測未來需求**   某些容量需求會隨著時間推移而變化。</span><span class="sxs-lookup"><span data-stu-id="23356-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="23356-134">透過追蹤趨勢，您可以預先規劃升級。</span><span class="sxs-lookup"><span data-stu-id="23356-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="23356-135">例如，必須監視各個 Lync 網站之間的可用頻寬，才能建立比較基準。</span><span class="sxs-lookup"><span data-stu-id="23356-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="23356-136">此基線可讓您預測當您必須在這些連結中加入更多頻寬時，這些連結會隨著時間增加。</span><span class="sxs-lookup"><span data-stu-id="23356-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="23356-137">可用性管理</span><span class="sxs-lookup"><span data-stu-id="23356-137">Availability management</span></span>

<span data-ttu-id="23356-138">可用性管理是確保任何 IT 服務始終如一且經濟高效地提供客戶所需一致且可靠服務層級的程式。</span><span class="sxs-lookup"><span data-stu-id="23356-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="23356-139">可用性管理可將服務損失降至最低，並確保服務遺失時採取適當的行動。</span><span class="sxs-lookup"><span data-stu-id="23356-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="23356-140">在 Lync 環境中，您可能會擔心企業語音服務是否可用、使用者是否可以加入排程的會議等。</span><span class="sxs-lookup"><span data-stu-id="23356-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="23356-141">SLA 定義了可接受的頻率及停機時間長度，且在系統無法進行規劃中的維護時允許特定期間。</span><span class="sxs-lookup"><span data-stu-id="23356-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="23356-142">如果您必須提供報表給您的系統可用性，或者您有財務或與遺失的可用性目標相關的其他處罰，您必須記錄可用性資料。</span><span class="sxs-lookup"><span data-stu-id="23356-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="23356-143">即使您沒有這種正式需求，最好還是至少知道系統在特定的時段內失敗的頻率。</span><span class="sxs-lookup"><span data-stu-id="23356-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="23356-144">例如，過去12個月的系統可用性，以及從每個失敗中復原所需的時間。</span><span class="sxs-lookup"><span data-stu-id="23356-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="23356-145">此資訊可協助您測量並改善您的小組對系統失敗的回應效果。</span><span class="sxs-lookup"><span data-stu-id="23356-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="23356-146">如果有爭議，它也可以提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="23356-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="23356-147">與可用性相關的量值如下所示：</span><span class="sxs-lookup"><span data-stu-id="23356-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="23356-148">**可用性**   通常會以系統或服務的存取時間來表示，與系統或服務的存取時間進行比較。</span><span class="sxs-lookup"><span data-stu-id="23356-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="23356-149">它通常以百分比表示。</span><span class="sxs-lookup"><span data-stu-id="23356-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="23356-150">（您可能會看到 [三個 9] 或 "五個九" 的參照。</span><span class="sxs-lookup"><span data-stu-id="23356-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="23356-151">這些是指99.9% 或99.999% 的可用性。）</span><span class="sxs-lookup"><span data-stu-id="23356-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="23356-152">**可靠性**   這是一個測量系統失敗之間時間的量度，有時候會在失敗之間（MTBF）之間以平均時間（或平均值）表示。</span><span class="sxs-lookup"><span data-stu-id="23356-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="23356-153">**修復時間這**   是在發生失敗之後復原服務所需的時間，通常表示為要修復的平均時間（例如，average）（MTTR）。</span><span class="sxs-lookup"><span data-stu-id="23356-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="23356-154">與修復相關的可用性、可靠性和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="23356-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="23356-155">**可用性 = （MTBF – MTTR）/MTBF**   例如，如果伺服器在六個月期間內失敗兩次，且平均超過20分鐘，則 MTBF 為三個月或90天，而 MTTR 為20分鐘。</span><span class="sxs-lookup"><span data-stu-id="23356-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="23356-156">因此，可用性 = （90天到20分鐘）/90 天 = 99.985%。</span><span class="sxs-lookup"><span data-stu-id="23356-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="23356-157">可用性管理是確定可用性是否已最大化並保留在 Sla 中定義的參數中的程式。</span><span class="sxs-lookup"><span data-stu-id="23356-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="23356-158">可用性管理包括下列處理常式：</span><span class="sxs-lookup"><span data-stu-id="23356-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="23356-159">**監視**   檢查服務無法使用的時間和時間。</span><span class="sxs-lookup"><span data-stu-id="23356-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="23356-160">**報告**   可用性資料必須定期提供給管理、使用者和操作小組。</span><span class="sxs-lookup"><span data-stu-id="23356-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="23356-161">這些報表應該會醒目提示趨勢，並找出良好的區域及需要注意的區域。</span><span class="sxs-lookup"><span data-stu-id="23356-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="23356-162">報告應該摘要符合 Sla 中設定的目標。</span><span class="sxs-lookup"><span data-stu-id="23356-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="23356-163">**改善**   如果可用性不符合在 sla 中定義的目標，或趨勢降低可用性的位置，則可用性管理程式應該規劃補救步驟。</span><span class="sxs-lookup"><span data-stu-id="23356-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="23356-164">這應包括與其他責任團隊共同作業，以醒目提示中斷的原因，並規劃補救動作以避免發生中斷的週期。</span><span class="sxs-lookup"><span data-stu-id="23356-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="23356-165">容量和可用性測量是特別適合自動工具和腳本（例如 Microsoft System Center Operations Manager （舊稱 Microsoft Operations Manager））的重複性工作，本檔稍後會討論。</span><span class="sxs-lookup"><span data-stu-id="23356-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23356-166">請參閱</span><span class="sxs-lookup"><span data-stu-id="23356-166">See Also</span></span>


[<span data-ttu-id="23356-167">使用 System Center Operations Manager 監視 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23356-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

