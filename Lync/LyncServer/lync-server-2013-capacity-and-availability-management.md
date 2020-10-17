---
title: Lync Server 2013：容量和可用性管理
description: Lync Server 2013：容量和可用性管理。
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
ms.openlocfilehash: d498649651f8cfbccc65f5b1b5f010025ac418e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565149"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="0cb4e-103">Lync Server 2013 的容量和可用性管理</span><span class="sxs-lookup"><span data-stu-id="0cb4e-103">Capacity and availability management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cb4e-104">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="0cb4e-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="0cb4e-105">容量管理與可用性管理的目的是測量和控制系統效能。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-105">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="0cb4e-106">建議您執行容量管理和可用性管理程式，讓您能夠測量和控制系統效能。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-106">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="0cb4e-107">您必須瞭解系統是否可供使用，以及是否可以透過設定基線及監控系統以尋找趨勢，來處理目前和預計的需求。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-107">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="0cb4e-108">容量管理</span><span class="sxs-lookup"><span data-stu-id="0cb4e-108">Capacity management</span></span>

<span data-ttu-id="0cb4e-109">容量管理包括規劃、調整大小及控制服務容量，以協助保證已超過 SLA 中所指定的最低效能等級。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-109">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="0cb4e-110">良好的容量管理可協助確保您能夠以合理的成本提供 IT 服務，而且仍然符合您在用戶端的 Sla 中所定義的效能等級。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-110">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="0cb4e-111">這些準則可包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="0cb4e-111">These criteria can include the following:</span></span>

  - <span data-ttu-id="0cb4e-112">**系統回應時間**    這是系統執行一般動作所需的測量時間。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-112">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="0cb4e-113">範例包括音訊/視訊伺服器角色處理音訊/視頻流量所需的時間、用戶端建立及加入會議所需的時間，或要在所有的觀察者用戶端中更新目前狀態所需的時間。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-113">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="0cb4e-114">**儲存容量**    不論是內容資料庫、備份裝置或本機磁片磁碟機，都是指儲存系統的容量。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-114">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="0cb4e-115">範例包含每個網站所提供的儲存空間量上限，以及備份在覆寫之前應儲存的時間。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-115">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="0cb4e-116">調整容量的情況通常是確定有足夠的實體資源可供使用，例如磁碟空間和網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-116">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="0cb4e-117">下表列出容量相關問題的一般解決方法。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-117">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="0cb4e-118">容量相關問題的一般解決方案</span><span class="sxs-lookup"><span data-stu-id="0cb4e-118">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cb4e-119">問題</span><span class="sxs-lookup"><span data-stu-id="0cb4e-119">Issue</span></span></th>
<th><span data-ttu-id="0cb4e-120">可能的解決方法</span><span class="sxs-lookup"><span data-stu-id="0cb4e-120">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cb4e-121">具有不良音訊/視頻效能的遠端使用者</span><span class="sxs-lookup"><span data-stu-id="0cb4e-121">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="0cb4e-122">查看 WAN 連結上是否有適當的頻寬可用，以及是否 QoS 已啟用且設定正確。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-122">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="0cb4e-123">檢查 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-123">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb4e-124">Lync 環境整體回應的速度很慢。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-124">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="0cb4e-125">執行測試，檢查現有的前端伺服器是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-125">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="0cb4e-126">如有需要，請引進新的前端伺服器。請檢查 SQL 資料庫回應時間，並修正延遲的原因 (例如，改善磁片 I/O) 。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-126">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0cb4e-127">有關疑難排解的詳細資訊，請參考 Lync Server 網路指南。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-127">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="0cb4e-128">容量會受到系統設定的影響，取決於實體資源，例如網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-128">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="0cb4e-129">例如，如果 Lync 環境已設定為每夜執行完整備份，則必須小心謹慎，以協助保證使用者對互動式效能的影響降至最低。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-129">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="0cb4e-130">容量管理是將系統容量保持在可接受的層級，並解決下列問題的程式：</span><span class="sxs-lookup"><span data-stu-id="0cb4e-130">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="0cb4e-131">**對需求**     變更的反應必須調整容量需求，以考慮系統或組織中的變更。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-131">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="0cb4e-132">例如，如果您的環境決定實現 Enterprise Voice，轉送伺服器和公用交換電話網路 (PSTN) 閘道的數目和位置將非常重要。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-132">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="0cb4e-133">如果您會執行會話初始通訊協定 (SIP) 中繼或直接 SIP，整體設計將會大幅變更，以提供最佳的企業語音效能。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-133">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="0cb4e-134">**預測未來需求**    有些容量需求會隨著時間而變更。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-134">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="0cb4e-135">透過追蹤趨勢，您可以事先規劃升級。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-135">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="0cb4e-136">例如，必須監視不同 Lync 網站間的可用頻寬，以建立基準。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-136">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="0cb4e-137">此基準可讓您預測當您必須將更多頻寬新增至這些連結時，這些遠端網站中的使用者計數會隨著時間而增加。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-137">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="0cb4e-138">可用性管理</span><span class="sxs-lookup"><span data-stu-id="0cb4e-138">Availability management</span></span>

<span data-ttu-id="0cb4e-139">可用性管理是一種程式，可確保任何 IT 服務始終如一且成本有效地傳遞客戶所需的一致、可靠的服務層級。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-139">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="0cb4e-140">可用性管理會使服務遺失降至最低，並確保在服務遺失時採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-140">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="0cb4e-141">在 Lync 環境中，您可能會擔心 Enterprise Voice 服務是否可供使用、使用者是否可以加入排程的會議等等。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-141">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="0cb4e-142">SLA 定義可接受的頻率及中斷長度，當系統無法用於計畫的維護時，可在特定期間內使用。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-142">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="0cb4e-143">如果您必須提供報告給您的系統可用性，或您有財務或其他與缺失可用性目標相關的處罰，您必須記錄可用性資料。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-143">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="0cb4e-144">即使您沒有這類正式的需求，最好還是至少知道系統在特定時段內失敗的頻率。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-144">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="0cb4e-145">例如，最近12個月的系統可用性，以及從每個失敗中復原所需的時間。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-145">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="0cb4e-146">此資訊可協助您測量和提高小組回應系統失敗的效能。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-146">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="0cb4e-147">如果有爭議，也可提供您有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-147">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="0cb4e-148">可用性的相關度量如下：</span><span class="sxs-lookup"><span data-stu-id="0cb4e-148">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="0cb4e-149">**可用性**    這通常會以系統或服務可存取的時間來表示，與系統或服務的使用時間相較。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-149">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="0cb4e-150">它通常會以百分比表示。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-150">It is typically expressed as a percentage.</span></span> <span data-ttu-id="0cb4e-151"> (您可能會看到「三個9」或「五個9」的參照。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-151">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="0cb4e-152">這兩個參考是99.9% 或99.999% 的可用性。 ) </span><span class="sxs-lookup"><span data-stu-id="0cb4e-152">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="0cb4e-153">**可靠性**    這是測量系統失敗之間的時間，有時會以平均 (或平均) 時間之間的平均 (MTBF) 來表示。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-153">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="0cb4e-154">**修復時間**    這是發生失敗後復原服務所花費的時間，而且通常表示為平均) 修復 (MTTR) 的平均時間 (。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-154">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="0cb4e-155">可用性、可靠性及修復時間與下列相關：</span><span class="sxs-lookup"><span data-stu-id="0cb4e-155">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="0cb4e-156">**可用性 = (MTBF-MTTR) /MTBF**    例如，如果伺服器在六個月的期間內失敗兩次，且平均的20分鐘無法使用，則 MTBF 為三個月或90天，而 MTTR 是20分鐘。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-156">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="0cb4e-157">因此，可用性 = (90 天–20分鐘) /90 天 = 99.985%。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-157">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="0cb4e-158">可用性管理是確定可用性是否已最大化並保留在 Sla 中所定義的參數中的處理常式。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-158">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="0cb4e-159">可用性管理包含下列程式：</span><span class="sxs-lookup"><span data-stu-id="0cb4e-159">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="0cb4e-160">**監控**    檢查服務無法使用的時間和時間。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-160">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="0cb4e-161">**報表**    可用性圖表應該定期提供給管理、使用者和作業團隊。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-161">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="0cb4e-162">這些報告應該會反白顯示趨勢，並找出順利進行的區域，以及需要注意的區域。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-162">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="0cb4e-163">報告應該摘要規定與 Sla 中所設定的目標。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-163">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="0cb4e-164">**改進**    如果可用性不符合 Sla 中所定義的目標，或趨勢在降低可用性的位置，則可用性管理程式應規劃補救步驟。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-164">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="0cb4e-165">這應包括與其他責任小組合作，以強調中斷的原因，並規劃補救的動作，以防止中斷週期的重複。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-165">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="0cb4e-166">容量和可用性測量值是重複性的工作，特別適合自動工具和腳本，例如 Microsoft System Center Operations Manager (先前的 Microsoft Operations Manager) ，本檔稍後將討論。</span><span class="sxs-lookup"><span data-stu-id="0cb4e-166">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0cb4e-167">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0cb4e-167">See Also</span></span>


[<span data-ttu-id="0cb4e-168">使用 System Center Operations Manager 監視 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cb4e-168">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

