---
title: Lync Server 2013： 容量和可用性管理
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
ms.openlocfilehash: 315b8a70451e762c6eafd82a221b3266696034eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="1b013-102">Lync Server 2013 中的容量和可用性管理</span><span class="sxs-lookup"><span data-stu-id="1b013-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b013-103">_**上次修改主題：** 2014年-08-18_</span><span class="sxs-lookup"><span data-stu-id="1b013-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="1b013-104">容量管理及可用性管理的目的是要測量和控制系統的效能。</span><span class="sxs-lookup"><span data-stu-id="1b013-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="1b013-105">我們建議您實作容量管理及可用性管理程序，以便您可以測量和控制系統的效能。</span><span class="sxs-lookup"><span data-stu-id="1b013-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="1b013-106">您必須知道系統是否可用，且如果它可以藉由設定基準線和監視趨勢尋找系統處理目前與預計的要求。</span><span class="sxs-lookup"><span data-stu-id="1b013-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="1b013-107">容量管理</span><span class="sxs-lookup"><span data-stu-id="1b013-107">Capacity management</span></span>

<span data-ttu-id="1b013-108">容量管理有關規劃、 調整大小，以及控制服務容量，以協助確保超出您 SLA 中所指定的最小的效能層級。</span><span class="sxs-lookup"><span data-stu-id="1b013-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="1b013-109">良好的容量管理可協助確定您可以提供 IT 服務合理的費用，同時仍符合您符合 Sla 中定義與用戶端的效能層級。</span><span class="sxs-lookup"><span data-stu-id="1b013-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="1b013-110">這些條件可以包含下列：</span><span class="sxs-lookup"><span data-stu-id="1b013-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="1b013-111">**系統回應時間**   這是測量的系統所需執行一般動作的時間。</span><span class="sxs-lookup"><span data-stu-id="1b013-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="1b013-112">範例包括來處理音訊/視訊流量，是要建立並加入會議，讓用戶端所需的時間的音訊/視訊伺服器角色所需的時間或若要在監看員的所有用戶端更新的目前狀態的時間。</span><span class="sxs-lookup"><span data-stu-id="1b013-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="1b013-113">**儲存體容量**   這是系統的容量儲存空間，不論是內容資料庫、 備份裝置或本機磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1b013-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="1b013-114">範例包括的每個網站提供的儲存空間量上限，他們會覆寫應該之前儲存備份的時間。</span><span class="sxs-lookup"><span data-stu-id="1b013-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="1b013-115">調整容量通常是確保有足夠的實體資源可供使用，例如磁碟空間和網路頻寬大小寫。</span><span class="sxs-lookup"><span data-stu-id="1b013-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="1b013-116">下表列出容量相關問題的一般解決方法。</span><span class="sxs-lookup"><span data-stu-id="1b013-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="1b013-117">容量相關問題的一般解決方案</span><span class="sxs-lookup"><span data-stu-id="1b013-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b013-118">問題</span><span class="sxs-lookup"><span data-stu-id="1b013-118">Issue</span></span></th>
<th><span data-ttu-id="1b013-119">可行的解決方法</span><span class="sxs-lookup"><span data-stu-id="1b013-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b013-120">遠端使用者擁有音訊/視訊效能不佳</span><span class="sxs-lookup"><span data-stu-id="1b013-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="1b013-121">請檢查是否有可用的 WAN 連結上適當的頻寬和 QoS 如果已啟用，並適當地設定。</span><span class="sxs-lookup"><span data-stu-id="1b013-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="1b013-122">檢查 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="1b013-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b013-123">整體 Lync 環境的回應緩慢。</span><span class="sxs-lookup"><span data-stu-id="1b013-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="1b013-124">執行測試，以檢查現有的前端伺服器可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="1b013-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="1b013-125">如果需要請引進新的前端伺服器。檢查 SQL 資料庫的回應時間，並修正的延遲原因 （例如，改善的磁碟 I/O）。</span><span class="sxs-lookup"><span data-stu-id="1b013-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1b013-126">疑難排解更詳細討論 Lync Server 網路快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="1b013-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="1b013-127">容量受到系統組態和取決於實體資源，例如網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="1b013-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="1b013-128">例如，如果執行一次完整備份夜間設定 Lync 環境，則必須小心以協助確保互動式使用者所遇到的效能影響最小化。</span><span class="sxs-lookup"><span data-stu-id="1b013-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="1b013-129">容量管理是保持在可接受的層級和地址下列問題系統的容量的程序：</span><span class="sxs-lookup"><span data-stu-id="1b013-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="1b013-130">**反應需求中的變更**   調整，以變更帳戶系統或組織中有容量需求。</span><span class="sxs-lookup"><span data-stu-id="1b013-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="1b013-131">例如，如果您的環境會決定要實作 Enterprise Voice，數目與中繼伺服器與公用交換的電話網路 (PSTN) 閘道的位置會非常重要。</span><span class="sxs-lookup"><span data-stu-id="1b013-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="1b013-132">如果您將執行的工作階段初始通訊協定 (SIP) 主幹或直接 SIP，整體設計會大幅變更以提供最佳的 Enterprise Voice 效能。</span><span class="sxs-lookup"><span data-stu-id="1b013-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="1b013-133">**預測未來需求，**   某些容量需求作文隨著時間而改變。</span><span class="sxs-lookup"><span data-stu-id="1b013-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="1b013-134">追蹤趨勢您可以在事先規劃升級。</span><span class="sxs-lookup"><span data-stu-id="1b013-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="1b013-135">例如，必須監視各種 Lync 站台之間的可用頻寬，以建立基準。</span><span class="sxs-lookup"><span data-stu-id="1b013-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="1b013-136">此比較基準可讓您預測有時間與這些遠端站台增加中使用者計數這些連結加入更多的頻寬時。</span><span class="sxs-lookup"><span data-stu-id="1b013-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="1b013-137">可用性管理</span><span class="sxs-lookup"><span data-stu-id="1b013-137">Availability management</span></span>

<span data-ttu-id="1b013-138">可用性管理是服務的確定任何 IT 服務持續和成本效益的程序提供一致且可靠，由客戶所需的層級。</span><span class="sxs-lookup"><span data-stu-id="1b013-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="1b013-139">可用性管理處理最小化服務遺失與對確保服務遺失時不會採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="1b013-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="1b013-140">在 Lync 環境中，您可能會擔心企業語音服務是否為可用、 是否使用者可以加入排定的會議等等。</span><span class="sxs-lookup"><span data-stu-id="1b013-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="1b013-141">SLA 定義可接受的頻率及中斷的長度，並可讓系統時無法進行規劃的維護特定期間。</span><span class="sxs-lookup"><span data-stu-id="1b013-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="1b013-142">如果您必須提供您管理系統的可用性相關的報告，或必須與遺失的可用性目標相關聯的財務或其他負面影響，您必須記錄中的可用性資料。</span><span class="sxs-lookup"><span data-stu-id="1b013-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="1b013-143">即使您沒有這類正式的需求，它是不錯的選項，至少瞭解的系統在一段特定時間中失敗的頻率。</span><span class="sxs-lookup"><span data-stu-id="1b013-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="1b013-144">例如，系統的可用性在過去 12 個月及每項失敗復原所花費的時間長度。</span><span class="sxs-lookup"><span data-stu-id="1b013-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="1b013-145">此資訊可協助您測量及改善您的小組回應系統失敗的有效性。</span><span class="sxs-lookup"><span data-stu-id="1b013-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="1b013-146">它也讓您很有用的資訊是否有爭議。</span><span class="sxs-lookup"><span data-stu-id="1b013-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="1b013-147">可用性相關的量值如下所示：</span><span class="sxs-lookup"><span data-stu-id="1b013-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="1b013-148">**可用性**   這通常以時間為表示系統或服務，可存取相較於它是向下的時間。</span><span class="sxs-lookup"><span data-stu-id="1b013-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="1b013-149">它通常是以百分比表示。</span><span class="sxs-lookup"><span data-stu-id="1b013-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="1b013-150">（您可能會看到 「 三個 9 」 或 「 五個 9 」 的參照。</span><span class="sxs-lookup"><span data-stu-id="1b013-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="1b013-151">這些參照高達 99.9%或 99.999%的可用性。）</span><span class="sxs-lookup"><span data-stu-id="1b013-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="1b013-152">**可靠性**   這是系統的失敗之間的時間量值，而且有時候以表示 mean （或平均） 失敗 (MTBF) 之間的時間。</span><span class="sxs-lookup"><span data-stu-id="1b013-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="1b013-153">**修復階段**   這是之後失敗發生，通常表示為標準 （亦即平均） 時間以修復復原服務所花費的時間 (MTTR)。</span><span class="sxs-lookup"><span data-stu-id="1b013-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="1b013-154">可用性、 可靠性和修復的時間與相關，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1b013-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="1b013-155">**可用性 = (MTBF – MTTR) / MTBF**   比方說，如果伺服器失敗的六個月期間內進行兩次，且無法使用的平均 20 分鐘，MTBF 是三個月或 90 天和 MTTR 是 20 分鐘。</span><span class="sxs-lookup"><span data-stu-id="1b013-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="1b013-156">因此，可用性 = （90 天 – 20 分鐘為單位） / 90 天 = 99.985%。</span><span class="sxs-lookup"><span data-stu-id="1b013-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="1b013-157">可用性管理是確定可用性是最大化，並保留在符合 Sla 中定義的參數範圍內的程序。</span><span class="sxs-lookup"><span data-stu-id="1b013-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="1b013-158">可用性管理包含下列程序：</span><span class="sxs-lookup"><span data-stu-id="1b013-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="1b013-159">**監視**   檢查何時及多久的服務便無法使用。</span><span class="sxs-lookup"><span data-stu-id="1b013-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="1b013-160">**報告**   可用性數字應該定期提供給管理、 使用者和作業小組。</span><span class="sxs-lookup"><span data-stu-id="1b013-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="1b013-161">這些報告應反白顯示趨勢，並識別以及執行動作的區域和需要注意的區域。</span><span class="sxs-lookup"><span data-stu-id="1b013-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="1b013-162">報表應彙總的合規性目標 Sla 中設定。</span><span class="sxs-lookup"><span data-stu-id="1b013-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="1b013-163">**改進**   如果可用性不符合的目標 Sla 中所定義，或其中趨勢是向降低可用性，可用性管理程序應該規劃補救步驟。</span><span class="sxs-lookup"><span data-stu-id="1b013-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="1b013-164">這應該包括與以反白顯示中斷的原因，並規劃補救措施來避免中斷的循環其他負責小組的工作。</span><span class="sxs-lookup"><span data-stu-id="1b013-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="1b013-165">容量和可用性度量是重複適用： 適用的自動化的工具及指令碼，例如 Microsoft System Center Operations Manager (前名為 Microsoft Operations Manager)，本文件稍後討論的工作。</span><span class="sxs-lookup"><span data-stu-id="1b013-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b013-166">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1b013-166">See Also</span></span>


[<span data-ttu-id="1b013-167">監視與 System Center Operations Manager 的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b013-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

