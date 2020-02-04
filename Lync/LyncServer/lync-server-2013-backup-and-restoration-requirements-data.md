---
title: Lync Server 2013：備份和還原需求：資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b9f077e0f9d7c4137844b2cba352b096fdb564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="9e2ea-102">Lync Server 2013 中的備份和還原需求：資料</span><span class="sxs-lookup"><span data-stu-id="9e2ea-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e2ea-103">_**主題上次修改日期：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="9e2ea-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="9e2ea-104">Lync Server 使用儲存在資料庫中的設定和配置資訊，以及儲存在資料庫和檔案存儲區中的資料。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="9e2ea-105">本主題說明當您的組織遇到失敗或中斷時，您必須備份才能還原服務的資料，也可以識別 Lync Server 所用的資料和元件，您需要分別進行備份。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="9e2ea-106">設定和配置需求</span><span class="sxs-lookup"><span data-stu-id="9e2ea-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="9e2ea-107">本主題包含備份和還原 Lync Server 服務復原所需的設定和設定資訊的程式。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="9e2ea-108">配置資訊位於中央管理儲存體或另一份後端資料庫或標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="9e2ea-109">下表列出備份及還原所需的設定和設定資訊。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="9e2ea-110">設定和配置資料</span><span class="sxs-lookup"><span data-stu-id="9e2ea-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e2ea-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="9e2ea-111">Type of data</span></span></th>
<th><span data-ttu-id="9e2ea-112">儲存位置</span><span class="sxs-lookup"><span data-stu-id="9e2ea-112">Where stored</span></span></th>
<th><span data-ttu-id="9e2ea-113">描述/備份時間</span><span class="sxs-lookup"><span data-stu-id="9e2ea-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e2ea-114">拓撲配置資訊</span><span class="sxs-lookup"><span data-stu-id="9e2ea-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-115">中央管理存放區（資料庫： Xds）</span><span class="sxs-lookup"><span data-stu-id="9e2ea-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-116">拓撲、原則和設定設定。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="9e2ea-117">使用 [Lync Server 控制台] 或 [Cmdlet] 來修改您的設定或原則，以備份您的一般備份。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e2ea-118">位置資訊</span><span class="sxs-lookup"><span data-stu-id="9e2ea-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-119">中央管理存放區（資料庫： .Lis. .mdf）</span><span class="sxs-lookup"><span data-stu-id="9e2ea-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-120">企業語音增強9-1-1 （E9-1-1）配置資訊。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="9e2ea-121">此資訊通常是靜態的。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="9e2ea-122">使用您的一般備份進行備份。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e2ea-123">回應群組設定資訊</span><span class="sxs-lookup"><span data-stu-id="9e2ea-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-124">後端伺服器或標準版伺服器（database： RgsConfig）</span><span class="sxs-lookup"><span data-stu-id="9e2ea-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-125">回應群組代理群組、佇列和工作流程。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="9e2ea-126">在您新增或變更代理群組、佇列或工作流程之後，再使用一般備份進行備份。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="9e2ea-127">資料需求</span><span class="sxs-lookup"><span data-stu-id="9e2ea-127">Data Requirements</span></span>

<span data-ttu-id="9e2ea-128">以下是您需要備份的 Lync 伺服器資料清單，讓您可以在發生失敗的情況下還原 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="9e2ea-129">請注意，恢復不需要某些類型的資料。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="9e2ea-130">本主題不包含備份這些類型資料的程式，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="9e2ea-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="9e2ea-131">暫時的使用者資料，例如端點與訂閱、活動會議服務器及暫時性的會議狀態（database： RtcDyn）</span><span class="sxs-lookup"><span data-stu-id="9e2ea-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="9e2ea-132">通訊錄資料（資料庫： Rtcab 和 Rtcab1）。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="9e2ea-133">通訊錄資料庫會自動從 Active Directory 網域服務重新產生。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="9e2ea-134">通話駐留應用程式（database： CpsDyn）的動態資訊</span><span class="sxs-lookup"><span data-stu-id="9e2ea-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="9e2ea-135">暫時回應群組資料，例如 agent 登入狀態及呼叫等待資訊（database： RgsDyn）</span><span class="sxs-lookup"><span data-stu-id="9e2ea-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="9e2ea-136">持續聊天（database： MgcComp）的相容性資料庫。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="9e2ea-137">如果您已啟用持續性聊天規範，只要您已將配接器設定為讀取資料庫中的資訊，並將其轉換為替代格式，就能讓持續聊天規範資料庫中的資訊成為暫時性的。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="9e2ea-138">因此，持久聊天的合規性資料庫會被視為暫時性的。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="9e2ea-139">Lync Server 2013 持續聊天伺服器隨附 XML 配接器。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="9e2ea-140">您也可以安裝接受此資料的自訂配接器，並將其移至其他來源，例如 Exchange 託管的檔案。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="9e2ea-141">下表列出您需要備份及還原的資料。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="9e2ea-142">儲存在資料庫中的資料</span><span class="sxs-lookup"><span data-stu-id="9e2ea-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e2ea-143">資料類型</span><span class="sxs-lookup"><span data-stu-id="9e2ea-143">Type of data</span></span></th>
<th><span data-ttu-id="9e2ea-144">儲存位置</span><span class="sxs-lookup"><span data-stu-id="9e2ea-144">Where stored</span></span></th>
<th><span data-ttu-id="9e2ea-145">描述/備份時間</span><span class="sxs-lookup"><span data-stu-id="9e2ea-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e2ea-146">持久性使用者資料</span><span class="sxs-lookup"><span data-stu-id="9e2ea-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-147">後端伺服器或標準版伺服器（database： RTCXDS）</span><span class="sxs-lookup"><span data-stu-id="9e2ea-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-148">使用者權利、使用者連絡人清單、伺服器或池資料、排定的會議等。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="9e2ea-149">此使用者資料不包含上傳到會議的內容。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="9e2ea-150">使用您的一般備份進行備份。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-150">Back up with your regular backups.</span></span> <span data-ttu-id="9e2ea-151">這項資訊是動態的，但如果您需要還原到上一個定期備份，則不會對 Lync 伺服器造成更新的災難性影響。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="9e2ea-152">如果連絡人清單對您的組織而言是重要的，您可以更頻繁地備份此資料。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e2ea-153">存檔資料</span><span class="sxs-lookup"><span data-stu-id="9e2ea-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-154">封存資料庫（資料庫： LcsLog）</span><span class="sxs-lookup"><span data-stu-id="9e2ea-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="9e2ea-155">如果您已啟用 Microsoft Exchange 整合選項，此資料可能會儲存在 Exchange 2013 上。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="9e2ea-156">否則，此資料會保留在 Lync Server 封存資料庫中，這可能會與另一個 Lync Server 資料庫 collocated，或獨立資料庫伺服器上獨立的方式。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-157">立即訊息（IM）及會議內容。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="9e2ea-158">這種資料對於 Lync Server 並不重要，但對您的組織而言，可能是您組織的重要用途。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="9e2ea-159">據此判斷您的備份排程。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e2ea-160">監控資料</span><span class="sxs-lookup"><span data-stu-id="9e2ea-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-161">監視資料庫（LcsCDR .mdf 與 QoeMetrics）</span><span class="sxs-lookup"><span data-stu-id="9e2ea-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="9e2ea-162">這些資料庫可能會與另一個 Lync Server 資料庫 collocated，或獨立資料庫伺服器上獨立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-163">通話詳細資料記錄（LcsCDR）和體驗品質（QoE）度量（QoeMetrics）。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="9e2ea-164">通話明細記錄是動態的，對您的企業可能是至關重要的。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="9e2ea-165">考慮是否需要這些記錄，以決定您的備份排程。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="9e2ea-166">經驗品質資訊是動態的。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="9e2ea-167">QoE 資料的遺失對於 Lync Server 的運作並不重要，但對您的公司可能是至關重要的。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="9e2ea-168">根據這些資訊對您組織的重要程度，決定您的備份排程。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e2ea-169">持續聊天資料</span><span class="sxs-lookup"><span data-stu-id="9e2ea-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-170">持續聊天資料庫（mgd）。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="9e2ea-171">這個資料庫可能是與另一個 Lync Server 資料庫 collocated，或獨立資料庫伺服器上獨立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-172">持續聊天資料是在聊天室中張貼的實際聊天內容。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="9e2ea-173">這個資料通常是業務關鍵型的。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="9e2ea-174">您可以選擇使用 SQL Server 備份，或使用 Lync Server 中提供的<strong>Export CsPersistentChatData</strong> Cmdlet 來匯出資料庫。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="9e2ea-175">若要還原資料，您可以將資料庫匯入並還原到最後一次完整備份的位置，這表示您無法將資料庫還原到失敗的位置。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="9e2ea-176">檔案儲存資料需求</span><span class="sxs-lookup"><span data-stu-id="9e2ea-176">File Store Data Requirements</span></span>

<span data-ttu-id="9e2ea-177">在企業版部署中，Lync Server 檔存放區通常位於檔案伺服器上。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="9e2ea-178">在標準版的部署中，Lync Server 檔案存放區預設位於標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="9e2ea-179">通常會有一個 Lync Server 檔案存放區共用給網站。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="9e2ea-180">永久聊天檔案存放區會使用與 Lync Server 檔案存放區相同的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="9e2ea-181">檔案存放位置會識別為\\ \\伺服器\\共用名稱。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="9e2ea-182">若要尋找檔案存放區的特定位置，請開啟 [拓撲建立器]，然後在 [檔案存放**區**] 節點中查看。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="9e2ea-183">下表列出您需要備份及還原的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="9e2ea-184">檔案存放區</span><span class="sxs-lookup"><span data-stu-id="9e2ea-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e2ea-185">資料類型</span><span class="sxs-lookup"><span data-stu-id="9e2ea-185">Type of data</span></span></th>
<th><span data-ttu-id="9e2ea-186">儲存位置</span><span class="sxs-lookup"><span data-stu-id="9e2ea-186">Where stored</span></span></th>
<th><span data-ttu-id="9e2ea-187">描述/備份時間</span><span class="sxs-lookup"><span data-stu-id="9e2ea-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e2ea-188">Lync Server 檔存放區</span><span class="sxs-lookup"><span data-stu-id="9e2ea-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-189">通常是在檔案伺服器、檔案群集或標準版伺服器上</span><span class="sxs-lookup"><span data-stu-id="9e2ea-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="9e2ea-190">會議內容、會議內容中繼資料、會議合規性記錄、應用程式資料檔案、裝置更新、音訊檔案（回應群組）、通話駐留及宣告應用程式，以及張貼到持續聊天室中的檔案。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="9e2ea-191">使用您的一般備份進行備份。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="9e2ea-192">其他備份需求</span><span class="sxs-lookup"><span data-stu-id="9e2ea-192">Additional Backup Requirements</span></span>

<span data-ttu-id="9e2ea-193">若要協助確保您在發生失敗時還原 Lync Server 服務的能力，您必須備份不屬於 Lync Server 本身的一些必要元件。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="9e2ea-194">下列元件不會在本檔所述的 Lync Server 備份和還原程式中進行備份或還原：</span><span class="sxs-lookup"><span data-stu-id="9e2ea-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="9e2ea-195">**Active directory 網域服務**   ：您需要在備份 Lync Server 時，同時使用 Active directory 工具備份 AD DS。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="9e2ea-196">請務必將 AD DS 與 Lync Server 保持同步，以避免當 Lync Server 預期與 AD DS 中的連絡人物件不相符時可能會發生的問題。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="9e2ea-197">AD DS 儲存 Lync Server 所使用的下列設定：</span><span class="sxs-lookup"><span data-stu-id="9e2ea-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="9e2ea-198">使用者 SIP URI 和其他使用者設定。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="9e2ea-199">針對回應群組和會議助理等應用程式的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="9e2ea-200">指向中央管理存放區的指標。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="9e2ea-201">Kerberos 驗證帳戶（選擇性電腦物件）和 Lync Server 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="9e2ea-202">如需在 Windows Server 2008 中備份及還原 AD DS 的詳細資料，請參閱「AD DS 備份與復原逐步指南」 [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="9e2ea-203">**憑證授權單位和憑證**   使用貴組織的原則來備份您的憑證授權單位（CA）及證書。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="9e2ea-204">如果您使用可匯出的私密金鑰，您可以備份憑證和私密金鑰，如果您使用本檔中的程式來還原 Lync Server，就可以將其匯出。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="9e2ea-205">如果您使用內部 CA，您可以在需要還原 Lync Server 時重新註冊。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="9e2ea-206">請務必將私人金鑰保留在能在電腦出現故障時使用的安全位置。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="9e2ea-207">**System Center operations manager**   如果您使用 Microsoft System center operations manager （舊稱 microsoft Operations manager）來監視 lync server 部署，您可以選擇性地備份在監視 lync server 時所建立的資料。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="9e2ea-208">使用您的標準 SQL Server 備份程式來備份 System Center Operations Manager 檔案。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="9e2ea-209">在恢復期間，不會還原這些檔案。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="9e2ea-210">**公用交換電話網絡（PSTN）閘道**   設定如果您使用企業語音或 Survivable 分支裝置，則需要備份 PSTN 閘道設定。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="9e2ea-211">如需備份及還原 PSTN 閘道設定的詳細資訊，請參閱您的廠商。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="9e2ea-212">**[共存版的 lync server] 或 [office 通訊伺服器**   ] 如果您的 lync server 2013 部署 coexists 使用 lync server 2010 或舊版 Office 通訊伺服器，則無法使用本檔中的程式來備份或還原較舊的版本。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="9e2ea-213">相反地，您必須使用專為舊版版本所記錄的備份和還原程式。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="9e2ea-214">如需備份及還原 Lync Server 2010 的詳細資訊， [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417)請參閱。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-214">For details about backing up and restoring Lync Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="9e2ea-215">如需備份及還原 Microsoft Office 通訊伺服器 2007 R2 的詳細資料， [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)請參閱。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="9e2ea-216">**基礎結構資訊**   您需要備份基礎結構的相關資訊，例如防火牆設定、負載平衡設定、網際網路資訊服務（IIS）設定、網域名稱系統（DNS）記錄和 IP 位址，以及動態主機設定通訊協定（DHCP）設定。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="9e2ea-217">如需有關備份這些元件的詳細資訊，請諮詢其各自的供應商。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="9e2ea-218">**Microsoft exchange 與 exchange 整合訊息（UM）**   備份及還原 microsoft exchange 與 exchange UM，如 microsoft exchange 檔中所述。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="9e2ea-219">如需備份及還原 Exchange Server 2013 的詳細資訊， [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)請參閱。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-219">For details about backing up and restoring Exchange Server 2013, see [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="9e2ea-220">如需備份及還原 Exchange Server 2010 的詳細資訊， [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)請參閱。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-220">For details about backing up and restoring Exchange Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="9e2ea-221">請注意，Lync Server 2013 引入了將使用者連絡人清單、高清晰度使用者相片和歸檔資料儲存在 Exchange 2013 中的功能。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="9e2ea-222">請參閱下列清單，以瞭解如何備份這些類型的資料：</span><span class="sxs-lookup"><span data-stu-id="9e2ea-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="9e2ea-223">**高清晰度相片**是作為 Exchange Server 備份的一部分進行備份。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="9e2ea-224">[Lync Server 2013] 中引入了 [**整合連絡人存放區**]。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="9e2ea-225">「整合連絡人存放區」可讓使用者在 Exchange 2013 中保留所有連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="9e2ea-226">您應該確定針對使用者的使用者連絡人是儲存在整合式連絡人存放區中，還是儲存在 Lync 後端伺服器上，才能讓備份保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="9e2ea-227">下列案例說明將使用者連絡人遷移至 [整合連絡人] 存放區的位置，可能會導致備份和還原程式發生問題。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="9e2ea-228">**案例1：** 使用者連絡人會遷移至 [整合] 連絡人存放區，然後從遷移使用者連絡人之前所進行的 Lync Server 備份執行還原。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="9e2ea-229">在這種情況下，使用者會將過時的連絡人狀態保持在一天，直到 Lync Server 遷移任務開始將使用者連絡人遷移到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="9e2ea-230">（請注意，因為使用者連絡人先前已遷移至 [整合連絡人] 存放區，則會使用 Exchange 連絡人資訊）。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="9e2ea-231">在這種情況下，不需要系統管理員干預。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="9e2ea-232">**案例2：** 使用者連絡人先前儲存在 [整合連絡人] 存放區中，但接著是 [回退]。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="9e2ea-233">當使用者連絡人儲存在「整合連絡人存放區」時，就會從 Lync Server 備份執行還原。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="9e2ea-234">在這種情況下，用戶端`Error: Incorrect Exchange Version`或 Lyss 伺服器記錄中的錯誤訊息可能會指出這是問題。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="9e2ea-235">使用者將能夠直接從 Exchange 存取 Lync 2013 中的連絡人清單，但用戶端的狀態不會與 Lync Server 狀態相符。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="9e2ea-236">若要修正此問題，管理員將需要針對受影響的使用者執行**CsUCSRollback** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="9e2ea-237">**存檔資料**可以儲存在 Exchange 2013 中。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="9e2ea-238">這種資料對於 Lync Server 並不重要，但對您的組織而言，可能是您組織的重要用途。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="9e2ea-239">如果封存資料是儲存在 Exchange 中，對您的組織而言是重要的，請依照 Exchange 備份和還原程式。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="9e2ea-240">請注意，儲存在 Exchange 中的歸檔資料不能移回 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="9e2ea-241">此外，也無法將已儲存在 Lync 封存資料庫中的資料移到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="9e2ea-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

