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
ms.openlocfilehash: cf5b2b6e707820986b20f0592d2f2051e6f47bc5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="0971c-102">Lync Server 2013 中的備份和還原需求：資料</span><span class="sxs-lookup"><span data-stu-id="0971c-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0971c-103">_**主題上次修改日期：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="0971c-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="0971c-104">Lync Server 會使用儲存在資料庫中的設定和設定資訊，以及儲存在資料庫和檔案存放區中的資料。</span><span class="sxs-lookup"><span data-stu-id="0971c-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="0971c-105">本主題說明當您的組織遇到故障或中斷時，需要備份以還原服務的資料，也會識別您需要個別備份之 Lync Server 所使用的資料和元件。</span><span class="sxs-lookup"><span data-stu-id="0971c-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="0971c-106">設定和設定需求</span><span class="sxs-lookup"><span data-stu-id="0971c-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="0971c-107">本主題包含備份及還原 Lync Server 服務的修復所需設定和設定資訊的程式。</span><span class="sxs-lookup"><span data-stu-id="0971c-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="0971c-108">設定資訊位於中央管理存放區，或在其他後端資料庫或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="0971c-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="0971c-109">下表列出備份與還原所需的設定和設定資訊。</span><span class="sxs-lookup"><span data-stu-id="0971c-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="0971c-110">設定和設定資料</span><span class="sxs-lookup"><span data-stu-id="0971c-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0971c-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="0971c-111">Type of data</span></span></th>
<th><span data-ttu-id="0971c-112">儲存位置</span><span class="sxs-lookup"><span data-stu-id="0971c-112">Where stored</span></span></th>
<th><span data-ttu-id="0971c-113">Description/備份時間</span><span class="sxs-lookup"><span data-stu-id="0971c-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0971c-114">拓撲設定資訊</span><span class="sxs-lookup"><span data-stu-id="0971c-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="0971c-115">中央管理存放區 (資料庫： Xds) </span><span class="sxs-lookup"><span data-stu-id="0971c-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="0971c-116">拓撲、原則及設定設定。</span><span class="sxs-lookup"><span data-stu-id="0971c-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="0971c-117">使用 Lync Server 控制台或 Cmdlet 修改您的設定或原則，以備份一般備份。</span><span class="sxs-lookup"><span data-stu-id="0971c-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0971c-118">位置資訊</span><span class="sxs-lookup"><span data-stu-id="0971c-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="0971c-119">中央管理存放區 (資料庫： .Lis) </span><span class="sxs-lookup"><span data-stu-id="0971c-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="0971c-120">Enterprise Voice 增強型 9-1-1 (E9-1-1) 設定資訊。</span><span class="sxs-lookup"><span data-stu-id="0971c-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="0971c-121">這種資訊通常是靜態的。</span><span class="sxs-lookup"><span data-stu-id="0971c-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="0971c-122">以定期備份備份。</span><span class="sxs-lookup"><span data-stu-id="0971c-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0971c-123">回應群組設定資訊</span><span class="sxs-lookup"><span data-stu-id="0971c-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="0971c-124">後端伺服器或 Standard Edition Server (資料庫： RgsConfig.mdf) </span><span class="sxs-lookup"><span data-stu-id="0971c-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="0971c-125">回應群組代理程式群組、佇列和工作流程。</span><span class="sxs-lookup"><span data-stu-id="0971c-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="0971c-126">在您新增或變更代理人群組、佇列或工作流程之後，再備份一般備份。</span><span class="sxs-lookup"><span data-stu-id="0971c-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="0971c-127">資料需求</span><span class="sxs-lookup"><span data-stu-id="0971c-127">Data Requirements</span></span>

<span data-ttu-id="0971c-128">以下是您需要備份之 Lync Server 資料的清單，讓您在失敗的情況您可以還原 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="0971c-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="0971c-129">請注意，修復不需要某些類型的資料。</span><span class="sxs-lookup"><span data-stu-id="0971c-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="0971c-130">本主題不包含備份這些類型資料的程式，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="0971c-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="0971c-131">暫態使用者資料，例如端點和訂閱、使用中會議服務器及暫時性會議狀態 (資料庫： RtcDyn.mdf) </span><span class="sxs-lookup"><span data-stu-id="0971c-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="0971c-132">通訊錄資料 (資料庫： Rtcab 及 Rtcab1.mdf) 。</span><span class="sxs-lookup"><span data-stu-id="0971c-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="0971c-133">通訊錄資料庫會自動從 Active Directory 網域服務重新產生。</span><span class="sxs-lookup"><span data-stu-id="0971c-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="0971c-134">通話駐留應用程式 (資料庫的動態資訊： CpsDyn.mdf) </span><span class="sxs-lookup"><span data-stu-id="0971c-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="0971c-135">暫時性的回應群組資料，例如 agent 登入狀態及通話等候資訊 (資料庫： RgsDyn.mdf) </span><span class="sxs-lookup"><span data-stu-id="0971c-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="0971c-136">Persistent Chat (資料庫： MgcComp) 的規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="0971c-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="0971c-137">如果您已啟用持續性聊天規範，只要您已設定配接器來讀取資料庫中的資訊，並將其轉換成替代格式，則 Persistent Chat 規範資料庫中的資訊就是暫時性的。</span><span class="sxs-lookup"><span data-stu-id="0971c-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="0971c-138">因此，持久聊天的規範資料庫被視為暫時性。</span><span class="sxs-lookup"><span data-stu-id="0971c-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="0971c-139">Lync Server 2013 Persistent Chat Server 隨附有 XML 介面卡。</span><span class="sxs-lookup"><span data-stu-id="0971c-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="0971c-140">您也可以安裝採用此資料的自訂配接器，並將其移至其他來源（例如 Exchange 主控的封存）。</span><span class="sxs-lookup"><span data-stu-id="0971c-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="0971c-141">下表列出備份與還原所需的資料。</span><span class="sxs-lookup"><span data-stu-id="0971c-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="0971c-142">儲存在資料庫中的資料</span><span class="sxs-lookup"><span data-stu-id="0971c-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0971c-143">資料類型</span><span class="sxs-lookup"><span data-stu-id="0971c-143">Type of data</span></span></th>
<th><span data-ttu-id="0971c-144">儲存位置</span><span class="sxs-lookup"><span data-stu-id="0971c-144">Where stored</span></span></th>
<th><span data-ttu-id="0971c-145">Description/備份時間</span><span class="sxs-lookup"><span data-stu-id="0971c-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0971c-146">Persistent 使用者資料</span><span class="sxs-lookup"><span data-stu-id="0971c-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="0971c-147">後端伺服器或 Standard Edition Server (資料庫： RTCXDS) </span><span class="sxs-lookup"><span data-stu-id="0971c-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="0971c-148">使用者權限、使用者連絡人清單、伺服器或集區資料、排程的會議等等。</span><span class="sxs-lookup"><span data-stu-id="0971c-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="0971c-149">此使用者資料不包含上傳至會議的內容。</span><span class="sxs-lookup"><span data-stu-id="0971c-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="0971c-150">以定期備份備份。</span><span class="sxs-lookup"><span data-stu-id="0971c-150">Back up with your regular backups.</span></span> <span data-ttu-id="0971c-151">這項資訊是動態的，但是如果您需要還原至您的最後一次定期備份，則不會有更新失敗的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="0971c-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="0971c-152">如果連絡人清單對您的組織來說很重要，您可以更經常備份此資料。</span><span class="sxs-lookup"><span data-stu-id="0971c-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0971c-153">封存資料</span><span class="sxs-lookup"><span data-stu-id="0971c-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="0971c-154">封存資料庫 (資料庫： LcsLog.mdf) </span><span class="sxs-lookup"><span data-stu-id="0971c-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="0971c-155">如果您已啟用 Microsoft Exchange 整合選項，則此資料可能會儲存在 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="0971c-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="0971c-156">否則，此資料會保留在 Lync Server 封存資料庫中，該資料庫可能會組合其他 Lync Server 資料庫，或獨立資料庫伺服器上獨立。</span><span class="sxs-lookup"><span data-stu-id="0971c-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="0971c-157">立即訊息 (IM) 和會議內容。</span><span class="sxs-lookup"><span data-stu-id="0971c-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="0971c-158">這種資料對 Lync Server 並非很重要，但對於您的組織而言，它對您的組織來說可能是很重要的。</span><span class="sxs-lookup"><span data-stu-id="0971c-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="0971c-159">據以判斷備份排程。</span><span class="sxs-lookup"><span data-stu-id="0971c-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0971c-160">監控資料</span><span class="sxs-lookup"><span data-stu-id="0971c-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="0971c-161">監視資料庫 (LcsCDR.mdf 及 QoeMetrics.mdf) </span><span class="sxs-lookup"><span data-stu-id="0971c-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="0971c-162">這些資料庫可能會與其他 Lync Server 資料庫組合，或獨立于個別資料庫伺服器上獨立。</span><span class="sxs-lookup"><span data-stu-id="0971c-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="0971c-163">詳細通話記錄 (LcsCDR.mdf) 和經驗品質 (QoE) 度量 (QoeMetrics.mdf) 。</span><span class="sxs-lookup"><span data-stu-id="0971c-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="0971c-164">詳細通話記錄是動態的，可能對您的業務很重要。</span><span class="sxs-lookup"><span data-stu-id="0971c-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="0971c-165">考慮是否出於法規原因而需要這些記錄來決定備份排程。</span><span class="sxs-lookup"><span data-stu-id="0971c-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="0971c-166">經驗品質資訊是動態的。</span><span class="sxs-lookup"><span data-stu-id="0971c-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="0971c-167">QoE 資料遺失對 Lync Server 的運作而言並不重要，但對您的企業而言可能很重要。</span><span class="sxs-lookup"><span data-stu-id="0971c-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="0971c-168">根據組織的重要資訊，判斷備份排程。</span><span class="sxs-lookup"><span data-stu-id="0971c-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0971c-169">Persistent Chat 資料</span><span class="sxs-lookup"><span data-stu-id="0971c-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="0971c-170">Persistent Chat database (managed) 。</span><span class="sxs-lookup"><span data-stu-id="0971c-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="0971c-171">這個資料庫可能會組合其他 Lync Server 資料庫，或獨立于不同的資料庫伺服器上。</span><span class="sxs-lookup"><span data-stu-id="0971c-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="0971c-172">Persistent Chat Data 是在聊天室中張貼的實際聊天內容。</span><span class="sxs-lookup"><span data-stu-id="0971c-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="0971c-173">這種資料通常是商務重要的。</span><span class="sxs-lookup"><span data-stu-id="0971c-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="0971c-174">您可以選擇使用 SQL Server 備份，或是使用 Lync Server 中提供的 <strong>Export-CsPersistentChatData</strong> Cmdlet 來匯出資料庫。</span><span class="sxs-lookup"><span data-stu-id="0971c-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="0971c-175">若要復原資料，您可以匯入資料庫並將其還原至最後一次完整備份的點，這表示您無法將資料庫還原至失敗點。</span><span class="sxs-lookup"><span data-stu-id="0971c-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="0971c-176">檔案存放區資料需求</span><span class="sxs-lookup"><span data-stu-id="0971c-176">File Store Data Requirements</span></span>

<span data-ttu-id="0971c-177">在 Enterprise Edition 部署中，Lync Server 檔存放區通常位於檔案伺服器上。</span><span class="sxs-lookup"><span data-stu-id="0971c-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="0971c-178">在 Standard Edition 部署中，Lync Server 檔存放區在 Standard Edition Server 上是預設所在的。</span><span class="sxs-lookup"><span data-stu-id="0971c-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="0971c-179">一般來說，網站有一個共用的 Lync Server 檔存放區。</span><span class="sxs-lookup"><span data-stu-id="0971c-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="0971c-180">Persistent Chat file store 使用與 Lync Server 檔案存放區相同的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="0971c-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="0971c-181">檔案存放區位置識別為 \\ \\ 伺服器 \\ 共用名稱稱。</span><span class="sxs-lookup"><span data-stu-id="0971c-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="0971c-182">若要尋找檔案存放區的特定位置，請開啟拓撲產生器，然後在 [檔案存放 **區** ] 節點中查看。</span><span class="sxs-lookup"><span data-stu-id="0971c-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="0971c-183">下表列出備份與還原所需的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="0971c-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="0971c-184">檔案存放區</span><span class="sxs-lookup"><span data-stu-id="0971c-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0971c-185">資料類型</span><span class="sxs-lookup"><span data-stu-id="0971c-185">Type of data</span></span></th>
<th><span data-ttu-id="0971c-186">儲存位置</span><span class="sxs-lookup"><span data-stu-id="0971c-186">Where stored</span></span></th>
<th><span data-ttu-id="0971c-187">Description/備份時間</span><span class="sxs-lookup"><span data-stu-id="0971c-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0971c-188">Lync Server 檔存放區</span><span class="sxs-lookup"><span data-stu-id="0971c-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="0971c-189">通常是在檔案伺服器、檔叢集或 Standard Edition server 上</span><span class="sxs-lookup"><span data-stu-id="0971c-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="0971c-190">會議內容、會議內容中繼資料、會議相容性記錄檔、應用程式資料檔案、裝置更新的更新檔案、回應群組的音訊檔、通話駐留及宣告應用程式，以及張貼在 Persistent 聊天室中的檔案。</span><span class="sxs-lookup"><span data-stu-id="0971c-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="0971c-191">以定期備份備份。</span><span class="sxs-lookup"><span data-stu-id="0971c-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="0971c-192">其他備份需求</span><span class="sxs-lookup"><span data-stu-id="0971c-192">Additional Backup Requirements</span></span>

<span data-ttu-id="0971c-193">為了協助確保您還原 Lync Server 服務的能力，在發生失敗時，您必須備份並非 Lync Server 本身一部分的某些必要元件。</span><span class="sxs-lookup"><span data-stu-id="0971c-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="0971c-194">這份檔中所述的 Lync Server 備份與還原程式的一部分，不會備份或還原下列元件：</span><span class="sxs-lookup"><span data-stu-id="0971c-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="0971c-195">**Active Directory 網域服務**    當您備份 Lync Server 時，您需要使用 Active Directory 工具備份 AD DS。</span><span class="sxs-lookup"><span data-stu-id="0971c-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="0971c-196">請務必將 AD DS 與 Lync Server 保持同步，以避免當 Lync Server 預期的連絡人物件與 AD DS 中的連絡人物件不符時可能發生的問題。</span><span class="sxs-lookup"><span data-stu-id="0971c-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="0971c-197">AD DS 會儲存 Lync Server 所使用的下列設定：</span><span class="sxs-lookup"><span data-stu-id="0971c-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="0971c-198">使用者 SIP URI 及其他使用者設定。</span><span class="sxs-lookup"><span data-stu-id="0971c-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="0971c-199">回應群組和會議助理等應用程式的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="0971c-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="0971c-200">中央管理存放區的指標。</span><span class="sxs-lookup"><span data-stu-id="0971c-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="0971c-201">Kerberos 驗證帳戶 (選用的電腦物件) 和 Lync Server 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0971c-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="0971c-202">如需在 Windows Server 2008 中備份及還原 AD DS 的詳細資訊，請參閱《 AD DS 備份和復原逐步指南》 [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) 。</span><span class="sxs-lookup"><span data-stu-id="0971c-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="0971c-203">**憑證授權單位單位和憑證**    使用組織的原則 (CA) 和憑證備份憑證授權單位單位。</span><span class="sxs-lookup"><span data-stu-id="0971c-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="0971c-204">如果您使用可匯出的私密金鑰，您可以備份憑證和私密金鑰，然後在使用本檔中的程式來還原 Lync Server 時，將其匯出。</span><span class="sxs-lookup"><span data-stu-id="0971c-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="0971c-205">如果您使用內部 CA，當您需要還原 Lync Server 時，您可以重新註冊。</span><span class="sxs-lookup"><span data-stu-id="0971c-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="0971c-206">請務必將私密金鑰保留在安全的位置，以便在電腦失敗時使用。</span><span class="sxs-lookup"><span data-stu-id="0971c-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="0971c-207">**System Center Operations Manager**    如果您使用 Microsoft System Center Operations Manager (過去的 Microsoft Operations Manager) 若要監視 Lync Server 部署，您可以選擇性地備份它在監視 Lync Server 時所建立的資料。</span><span class="sxs-lookup"><span data-stu-id="0971c-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="0971c-208">使用您的標準 SQL Server 備份程式來備份 System Center Operations Manager 檔案。</span><span class="sxs-lookup"><span data-stu-id="0971c-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="0971c-209">復原期間不會還原這些檔案。</span><span class="sxs-lookup"><span data-stu-id="0971c-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="0971c-210">**公用交換電話網路 (PSTN) 閘道**     設定如果您使用 Enterprise Voice 或 Survivable 分支裝置，則必須備份 PSTN 閘道設定。</span><span class="sxs-lookup"><span data-stu-id="0971c-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="0971c-211">如需備份及還原 PSTN 閘道設定的詳細資訊，請參閱廠商。</span><span class="sxs-lookup"><span data-stu-id="0971c-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="0971c-212">**Lync server 或 Office 通訊伺服器**     的共存版本如果您的 Lync Server 2013 部署 coexists 使用 Lync Server 2010 或舊版的 Office 通訊伺服器，您就無法使用本檔中的程式來備份或還原舊版本。</span><span class="sxs-lookup"><span data-stu-id="0971c-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="0971c-213">相反地，您必須使用專為舊版所記錄的備份與還原程式。</span><span class="sxs-lookup"><span data-stu-id="0971c-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="0971c-214">如需備份及還原 Lync Server 2010 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) 。</span><span class="sxs-lookup"><span data-stu-id="0971c-214">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="0971c-215">如需備份及還原 Microsoft Office 通訊伺服器 2007 R2 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) 。</span><span class="sxs-lookup"><span data-stu-id="0971c-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="0971c-216">**基礎結構資訊**    您必須備份基礎結構的相關資訊，例如防火牆設定、負載平衡設定、Internet Information Services (IIS) 設定、網域名稱系統 (DNS) 記錄和 IP 位址，以及動態主機設定通訊協定 (DHCP) 設定。</span><span class="sxs-lookup"><span data-stu-id="0971c-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="0971c-217">如需備份這些元件的詳細資訊，請與其各自的廠商核實。</span><span class="sxs-lookup"><span data-stu-id="0971c-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="0971c-218">\*\*Microsoft exchange 和 Exchange 整合通訊 (UM) \*\*    如 Microsoft Exchange 檔中所述，備份及還原 Microsoft Exchange 和 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="0971c-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="0971c-219">如需備份及還原 Exchange Server 2013 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) 。</span><span class="sxs-lookup"><span data-stu-id="0971c-219">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="0971c-220">如需備份及還原 Exchange Server 2010 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) 。</span><span class="sxs-lookup"><span data-stu-id="0971c-220">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="0971c-221">請注意，Lync Server 2013 引進使用者連絡人清單、高清晰使用者相片，以及封存資料儲存在 Exchange 2013 中的功能。</span><span class="sxs-lookup"><span data-stu-id="0971c-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="0971c-222">請參閱下列清單，查看如何備份這些類型的資料：</span><span class="sxs-lookup"><span data-stu-id="0971c-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="0971c-223">**高清晰度相片** 會備份為 Exchange Server 備份的一部分。</span><span class="sxs-lookup"><span data-stu-id="0971c-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="0971c-224">在 Lync Server 2013 中引入**整合連絡人存放區**。</span><span class="sxs-lookup"><span data-stu-id="0971c-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="0971c-225">整合連絡人存放區可讓使用者在 Exchange 2013 中保留所有的連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="0971c-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="0971c-226">您應確定針對使用者的使用者連絡人是儲存在「整合連絡人存放區」或 Lync 後端伺服器上，來決定備份是否是最新的。</span><span class="sxs-lookup"><span data-stu-id="0971c-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="0971c-227">下列案例說明將使用者連絡人遷移至整合連絡人存放區的位置，可能會造成備份及還原程式的問題。</span><span class="sxs-lookup"><span data-stu-id="0971c-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="0971c-228">**案例1：** 使用者連絡人會遷移至整合連絡人存放區，而且會從遷移使用者連絡人之前所進行的 Lync Server 備份執行還原。</span><span class="sxs-lookup"><span data-stu-id="0971c-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="0971c-229">在此案例中，使用者會在一天內狀態為過期的連絡人，直到 Lync Server 遷移任務開始將使用者連絡人遷移至 Exchange。</span><span class="sxs-lookup"><span data-stu-id="0971c-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="0971c-230"> (請注意，因為使用者的連絡人先前已遷移至整合連絡人存放區，所以會) 使用 Exchange 連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="0971c-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="0971c-231">此案例不需要系統管理員介入。</span><span class="sxs-lookup"><span data-stu-id="0971c-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="0971c-232">**案例2：** 使用者連絡人先前已儲存在統一連絡人存放區中，但會進行還原。</span><span class="sxs-lookup"><span data-stu-id="0971c-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="0971c-233">當使用者連絡人儲存在統一連絡人存放區中時，會從 Lync Server 備份執行還原。</span><span class="sxs-lookup"><span data-stu-id="0971c-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="0971c-234">在此情況下， `Error: Incorrect Exchange Version` 用戶端或 Lyss server 記錄中的錯誤訊息可能表示這是問題。</span><span class="sxs-lookup"><span data-stu-id="0971c-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="0971c-235">使用者將可以直接從 Exchange 存取 Lync 2013 中的連絡人清單，但用戶端的狀態將不會符合 Lync Server 狀態。</span><span class="sxs-lookup"><span data-stu-id="0971c-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="0971c-236">若要修正此問題，系統管理員必須對受影響的使用者執行 **CsUCSRollback** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0971c-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="0971c-237">封存**資料**可以儲存在 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="0971c-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="0971c-238">這種資料對 Lync Server 並非很重要，但對於您的組織而言，它對您的組織來說可能是很重要的。</span><span class="sxs-lookup"><span data-stu-id="0971c-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="0971c-239">如果封存資料儲存在 Exchange 中，且對您的組織很重要，請遵循 Exchange 備份及還原程式。</span><span class="sxs-lookup"><span data-stu-id="0971c-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="0971c-240">請注意，儲存在 Exchange 中的封存資料無法移回 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="0971c-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="0971c-241">此外，無法將已儲存在 Lync 封存資料庫中的資料移至 Exchange。</span><span class="sxs-lookup"><span data-stu-id="0971c-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

