---
title: Lync Server 2013 版本資訊
description: Lync Server 2013 發行附注。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fabb0912d7ea3defd91014df732368eced909e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555869"
---
# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="50595-103">Lync Server 2013 的版本資訊</span><span class="sxs-lookup"><span data-stu-id="50595-103">Release notes for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50595-104">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="50595-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="50595-105">歡迎使用 Lync Server 2013 版本資訊。</span><span class="sxs-lookup"><span data-stu-id="50595-105">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="50595-106">如需有關 Lync Server 2013 之已知問題的相關資訊，請參閱此檔案。</span><span class="sxs-lookup"><span data-stu-id="50595-106">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="50595-107">關於此檔</span><span class="sxs-lookup"><span data-stu-id="50595-107">About this document</span></span>

<span data-ttu-id="50595-108">此檔包含您在部署和使用 Lync Server 2013 之前應該知道的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="50595-108">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="50595-109">如需 Lync Server 2013 的詳細資訊，請參閱 [Microsoft Lync server 2013](microsoft-lync-server-2013.md) 檔。</span><span class="sxs-lookup"><span data-stu-id="50595-109">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="50595-110">此文件包含下列章節：</span><span class="sxs-lookup"><span data-stu-id="50595-110">This document contains the following sections:</span></span>

  - <span data-ttu-id="50595-111">Lync 2013 用戶端</span><span class="sxs-lookup"><span data-stu-id="50595-111">Lync 2013 client</span></span>

  - <span data-ttu-id="50595-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="50595-112">Lync Server</span></span>

  - <span data-ttu-id="50595-113">安裝</span><span class="sxs-lookup"><span data-stu-id="50595-113">Installation</span></span>

  - <span data-ttu-id="50595-114">行動性</span><span class="sxs-lookup"><span data-stu-id="50595-114">Mobility</span></span>

  - <span data-ttu-id="50595-115">會議</span><span class="sxs-lookup"><span data-stu-id="50595-115">Conferencing</span></span>

  - <span data-ttu-id="50595-116">設定使用者</span><span class="sxs-lookup"><span data-stu-id="50595-116">Enterprise Voice</span></span>

  - <span data-ttu-id="50595-117">目前狀態</span><span class="sxs-lookup"><span data-stu-id="50595-117">Presence</span></span>

  - <span data-ttu-id="50595-118">回應組應用程式和通話駐留應用程式</span><span class="sxs-lookup"><span data-stu-id="50595-118">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="50595-119">Lync Server 控制台、拓撲產生器和規劃工具</span><span class="sxs-lookup"><span data-stu-id="50595-119">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="50595-120">當地語系化</span><span class="sxs-lookup"><span data-stu-id="50595-120">Localization</span></span>

  - <span data-ttu-id="50595-121">著作權</span><span class="sxs-lookup"><span data-stu-id="50595-121">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="50595-122">Lync 2013 用戶端</span><span class="sxs-lookup"><span data-stu-id="50595-122">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="50595-123">如果檔案已在另一個應用程式中開啟，則在立即訊息中傳輸檔案會失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-123">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="50595-124">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-124">**Issue:**</span></span>

<span data-ttu-id="50595-125">如果您嘗試將檔案（例如 Word 檔）以立即訊息傳送到另一個 Lync 使用者，則該轉移似乎會成功，但實際上無法傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="50595-125">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="50595-126">該檔案類型的圖示會顯示在 Lync 用戶端中，但目標接收器無法開啟該檔案。</span><span class="sxs-lookup"><span data-stu-id="50595-126">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="50595-127">不會顯示錯誤訊息，通知您傳輸未成功。</span><span class="sxs-lookup"><span data-stu-id="50595-127">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="50595-128">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-128">**Workaround:**</span></span>

<span data-ttu-id="50595-129">若要解決此問題，請先關閉開啟的檔案或已開啟的應用程式，再嘗試在立即訊息中傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="50595-129">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="50595-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="50595-130">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="50595-131">如果 Lync Server Storage Service 資料複寫失敗，系統管理員將需要檢查陳舊儲存體服務佇列專案的效能計數器</span><span class="sxs-lookup"><span data-stu-id="50595-131">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="50595-132">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-132">**Issue:**</span></span>

<span data-ttu-id="50595-133">Lync Server Storage Service 使用 Windows Fabric 進行複寫。</span><span class="sxs-lookup"><span data-stu-id="50595-133">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="50595-134">如果在主要前端伺服器上刪除資料，但在次要前端伺服器上刪除失敗（例如，如果前端伺服器上有未預期的關機或錯誤），則資料可以留下，而且「孤立」。</span><span class="sxs-lookup"><span data-stu-id="50595-134">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="50595-135">孤立資料可能會導致效能降低，並浪費磁片磁碟機空間。</span><span class="sxs-lookup"><span data-stu-id="50595-135">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="50595-136">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-136">**Workaround:**</span></span>

<span data-ttu-id="50595-137">若要解決此問題，如果使用中的事件 LYSS 的 \_ db \_ 空間 \_ \_ 錯誤 (識別碼 = 32058) 和 LYSS \_ DB \_ 空間 \_ \_ 已使用關鍵型 (識別碼 = 32059) 會在事件記錄檔中產生，管理員應該在 **LS： LYSS-storage service API** 中檢查前端伺服器的效能計數器，其名稱為 **LYSS-目前的 storage service 陳舊佇列專案數目**。</span><span class="sxs-lookup"><span data-stu-id="50595-137">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="50595-138">如果此效能計數器具有高值（例如大於50000），則系統管理員應該在 Lync Server 2013 資源套件中執行 CleanuUpStorageServiceData.exe 工具，該工具會刪除集區中的所有孤立資料。</span><span class="sxs-lookup"><span data-stu-id="50595-138">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="50595-139">如需有關此工具的詳細資訊，請參閱 Lync Server 2013 資源套件檔。</span><span class="sxs-lookup"><span data-stu-id="50595-139">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="50595-140">每當伺服器或集區的 IP 位址設定變更時，必須重新開機 Lync Server 服務</span><span class="sxs-lookup"><span data-stu-id="50595-140">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="50595-141">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-141">**Issue:**</span></span>

<span data-ttu-id="50595-142">當 Lync Server 2013 部署的 IP 位址設定變更時（例如，從 IPv4 變更為雙重堆疊，或從雙堆疊變更為 Ipv6），直到重新開機服務之後，所有的伺服器元件才會選取設定變更。</span><span class="sxs-lookup"><span data-stu-id="50595-142">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="50595-143">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-143">**Workaround:**</span></span>

<span data-ttu-id="50595-144">若要解決此問題，請在變更部署的 IP 位址設定後，重新開機 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="50595-144">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="50595-145">若要這麼做，請在 Lync Server 管理命令介面中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50595-145">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="50595-146">Lync Server 2013 管理元件已無法再使用電話撥入式會議綜合交易 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="50595-146">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="50595-147">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-147">**Issue:**</span></span>

<span data-ttu-id="50595-148">Lync Server 2013 管理元件已不再提供撥入式會議綜合交易 Cmdlet Cmdlet **Test-CsDialInConferencing** 。</span><span class="sxs-lookup"><span data-stu-id="50595-148">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="50595-149">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-149">**Workaround:**</span></span>

<span data-ttu-id="50595-150">只有在企業內部才支援使用 Dial-In 會議綜合交易 Cmdlet **Test-CsDialInConferencing** 。</span><span class="sxs-lookup"><span data-stu-id="50595-150">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="50595-151">管理員可以繼續使用 Lync Server 管理命令介面中的 Cmdlet 進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="50595-151">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="50595-152">如有需要，企業也可以開發私人管理套件，以在內部執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50595-152">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="50595-153">當將記錄檔複製到網路共用時，如果網路流量中斷，集中式記錄服務便會停止。</span><span class="sxs-lookup"><span data-stu-id="50595-153">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="50595-154">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-154">**Issue:**</span></span>

<span data-ttu-id="50595-155">當集中式記錄服務設定成使用網路路徑時 (**Get-CsClsConfiguration** Cmdlet 的 CacheFileNetworkFolder 參數值是有效的 UNC 路徑) 時，會將快取的記錄檔複製到網路共用。</span><span class="sxs-lookup"><span data-stu-id="50595-155">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="50595-156">若複製檔案時網路流量中斷，將會發生例外狀況，以導致集中式記錄服務停止。</span><span class="sxs-lookup"><span data-stu-id="50595-156">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="50595-157">服務設定為自動重新開機三次，所以服務會從前三個例外狀況復原。</span><span class="sxs-lookup"><span data-stu-id="50595-157">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="50595-158">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-158">**Workaround:**</span></span>

<span data-ttu-id="50595-159">此問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-159">There is no workaround for this issue.</span></span> <span data-ttu-id="50595-160">若要找出問題，請從「服務控制管理員」監視事件識別碼7031的事件記錄檔，以記錄「Lync Server 集中式記錄服務代理程式」服務意外終止的情況。</span><span class="sxs-lookup"><span data-stu-id="50595-160">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="50595-161">如果發生三次以上，請使用 **CsWindowService** Cmdlet 手動重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="50595-161">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="50595-162">需要手動匯入 Storage Service 佇列專案</span><span class="sxs-lookup"><span data-stu-id="50595-162">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="50595-163">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-163">**Issue:**</span></span>

<span data-ttu-id="50595-164">Lync Server 2013 儲存有關會議和立即訊息的資料，例如封存的郵件，以及在每一部前端伺服器上的資料庫中 (CDR) 的詳細資料記錄。</span><span class="sxs-lookup"><span data-stu-id="50595-164">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="50595-165">在處理資料庫時，會將資料儲存在資料庫中，然後再傳遞至預定的目的地。</span><span class="sxs-lookup"><span data-stu-id="50595-165">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="50595-166">為了改善效能，Lync Server 2013 會定期從本機資料庫匯出佇列專案，而這些專案不會在一段時間內處理，並將它們儲存在檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="50595-166">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="50595-167">如果檔案存放區無法使用，這些專案會儲存在每一部前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="50595-167">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="50595-168">執行相同的作業，以防止集區容錯移轉時發生資料遺失。</span><span class="sxs-lookup"><span data-stu-id="50595-168">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="50595-169">在匯出作業期間，Lync Server Storage Service 會記錄事件記錄中的每個階段，事件 IDs 32075 (完整清除作業已啟動) ，32076 (完全清除已完成) ，32082 (維護層級清理已完成) ，32083 (維護層級清理已完成) ，由於填滿資料庫 (，因此會進行 32089) 的清洗。</span><span class="sxs-lookup"><span data-stu-id="50595-169">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="50595-170">此資料將不會自動匯入回系統，以進行處理，並傳遞至其最終目的地 (SQL Server 或 Exchange Server) 。</span><span class="sxs-lookup"><span data-stu-id="50595-170">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="50595-171">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-171">**Workaround:**</span></span>

<span data-ttu-id="50595-172">若要將資料匯入系統，系統管理員必須使用 Lync Server 資源套件中的 ImportStorageServiceData 工具，該工具會將資料送回系統，以進行處理並傳遞至其最終目的地。</span><span class="sxs-lookup"><span data-stu-id="50595-172">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="50595-173">如果 UseNormalizationRules 的預設值變更為 False，則通訊錄 Web 查詢搜尋會失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-173">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="50595-174">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-174">**Issue:**</span></span>

<span data-ttu-id="50595-175">如果 UseNormalizationRules 的預設值變更為 False，通訊錄 Web 查詢搜尋會失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-175">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="50595-176">預設值變更後，Lync 用戶端使用者將無法使用 Lync 通訊錄 web 查詢來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="50595-176">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="50595-177">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-177">**Workaround:**</span></span>

<span data-ttu-id="50595-178">如果 UseNormalizationRules 的預設值設為 False，讓使用者可以使用 Active Directory 網域服務中定義的電話號碼，但不包括 Lync Server 2013。在使用正規化規則時，請執行下列動作來解決此問題：</span><span class="sxs-lookup"><span data-stu-id="50595-178">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="50595-179">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="50595-179">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="50595-180">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="50595-180">Do one of the following:</span></span>
    
      - <span data-ttu-id="50595-181">如果您的部署只包含 Lync Server 2013 server，請在全域層級執行下列 Cmdlet，將 UseNormalizationRules 和 IgnoreGenericRules 的值變更為 True：</span><span class="sxs-lookup"><span data-stu-id="50595-181">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="50595-182">如果您的部署包含 Lync Server 2013 和 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的組合，請執行下列 Cmdlet，並將其指派給拓撲中的每個 Lync Server 2013 集區：</span><span class="sxs-lookup"><span data-stu-id="50595-182">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="50595-183">等待在所有集區上進行 CMS 複寫。</span><span class="sxs-lookup"><span data-stu-id="50595-183">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="50595-184">修改您部署的電話正規化規則檔案，以清除內容。</span><span class="sxs-lookup"><span data-stu-id="50595-184">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="50595-185">檔位於每個 Lync Server 2013 集區的檔案共用上。</span><span class="sxs-lookup"><span data-stu-id="50595-185">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="50595-186">如果檔案不存在，請建立名為 "Company Phone Number 正規化Rules.txt 的空檔案 \_ \_ \_ \_ 。</span><span class="sxs-lookup"><span data-stu-id="50595-186">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="50595-187">請等候幾分鐘，讓所有前端集區讀取新的檔案。</span><span class="sxs-lookup"><span data-stu-id="50595-187">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="50595-188">在您部署中的每個 Lync Server 2013 集區上執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50595-188">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="50595-189">針對每個 Lync 2013 集區每天產生一次 Address Book Server 錯誤事件21054</span><span class="sxs-lookup"><span data-stu-id="50595-189">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="50595-190">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-190">**Issue:**</span></span>

<span data-ttu-id="50595-191">Lync Server 2013 Address Book Server 會在每日執行每日維護時產生錯誤事件21054一次。</span><span class="sxs-lookup"><span data-stu-id="50595-191">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="50595-192">每當管理員執行 **update-csaddressbook** Cmdlet 時，即使更新成功，也會產生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="50595-192">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="50595-193">不過，當更新成功時，可以安全地忽略此錯誤事件。</span><span class="sxs-lookup"><span data-stu-id="50595-193">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="50595-194">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-194">**Workaround:**</span></span>

<span data-ttu-id="50595-195">當您遇到此錯誤事件時，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50595-195">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="50595-196">如果此 Cmdlet 報告沒有任何未編制索引或已放棄的物件，則可以放心忽略錯誤事件21054。</span><span class="sxs-lookup"><span data-stu-id="50595-196">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="50595-197">此外，在 System Center Operations Manager 中應關閉 KHI) 「通訊錄使用者已正確編制索引」的主要健康情況 (指示器。</span><span class="sxs-lookup"><span data-stu-id="50595-197">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="50595-198">在 Edge 集區上設定 IPv6 時，可能會失敗要求</span><span class="sxs-lookup"><span data-stu-id="50595-198">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="50595-199">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-199">**Issue:**</span></span>

<span data-ttu-id="50595-200">在 Edge 集區上設定 IPv6 時，某些對 Edge 集區的要求可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-200">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="50595-201">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-201">**Workaround:**</span></span>

<span data-ttu-id="50595-202">若要解決此問題，請不要使用 IPv6 設定 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="50595-202">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="50595-203">集區回復時，invoke-csPoolFailback Cmdlet 可能會失敗</span><span class="sxs-lookup"><span data-stu-id="50595-203">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="50595-204">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-204">**Issue:**</span></span>

<span data-ttu-id="50595-205">嘗試容錯回復集區時， **invoke-csPoolFailback** Cmdlet 可能會失敗，錯誤為「重複嘗試後，無法完成分解處理常式」。」</span><span class="sxs-lookup"><span data-stu-id="50595-205">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="50595-206">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-206">**Workaround:**</span></span>

<span data-ttu-id="50595-207">若要解決此問題，請再次執行 Cmdlet，然後等到 Cmdlet 成功為止。</span><span class="sxs-lookup"><span data-stu-id="50595-207">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="50595-208">請注意，容錯移轉程式可能需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="50595-208">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="50595-209">在有20000使用者的集區中，可能需要長達60分鐘。</span><span class="sxs-lookup"><span data-stu-id="50595-209">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="50595-210">當您將前端伺服器新增至已建立的集區時，可能會發生資料遺失-混合式、商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="50595-210">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="50595-211">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-211">**Issue:**</span></span>

<span data-ttu-id="50595-212">在集區有多部前端伺服器的環境中，您可能會遇到此問題，您必須重新開機其中一部前端伺服器，或是新增先前沒有集區的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="50595-212">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="50595-213">資料封存的使用者可能會發生資料遺失，直到為集區建立資料封存的穩定散佈。</span><span class="sxs-lookup"><span data-stu-id="50595-213">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="50595-214">此週期的潛在資料遺失限制為15分鐘供人員對人員交談，而30分鐘用於會議。</span><span class="sxs-lookup"><span data-stu-id="50595-214">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="50595-215">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-215">**Workaround:**</span></span>

<span data-ttu-id="50595-216">當您執行維護時，您應該將集區容錯移轉至另一個集區，然後在伺服器上執行維護工作，而不是將集區容錯移轉到另一個集區。</span><span class="sxs-lookup"><span data-stu-id="50595-216">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="50595-217">您也可以在執行維護工作之前將服務變為不可用，然後在維護完成時還原可用性。</span><span class="sxs-lookup"><span data-stu-id="50595-217">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="50595-218">管理員無法使用 Get-CsClientAccessLicense Cmdlet 取得獲許可人計數</span><span class="sxs-lookup"><span data-stu-id="50595-218">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="50595-219">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-219">**Issue:**</span></span>

<span data-ttu-id="50595-220">管理員無法使用 **Get-CsClientAccessLicense** Cmdlet 取得正確的用戶端授權用法。</span><span class="sxs-lookup"><span data-stu-id="50595-220">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="50595-221">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-221">**Workaround:**</span></span>

<span data-ttu-id="50595-222">若要檢查伺服器授權類型，您可以執行 **Get-CsService** Cmdlet，以 (所有資料庫的 FDQNs) 中取得完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="50595-222">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="50595-223">如果前端伺服器的 FQDN 與後端資料庫的 FQDN 相同，則授權為 Standard edition 授權。</span><span class="sxs-lookup"><span data-stu-id="50595-223">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="50595-224">否則，授權是 Enterprise edition 授權。</span><span class="sxs-lookup"><span data-stu-id="50595-224">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="50595-225">未正確報告用戶端獲許可人計數</span><span class="sxs-lookup"><span data-stu-id="50595-225">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="50595-226">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-226">**Issue:**</span></span>

<span data-ttu-id="50595-227">決定用戶端授權計數時，您可能會遇到下列情況：</span><span class="sxs-lookup"><span data-stu-id="50595-227">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="50595-228">**行動使用者的不正確授權計數**</span><span class="sxs-lookup"><span data-stu-id="50595-228">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="50595-229">授權計數是以裝置型使用者的唯一 IP 位址數目為基礎。</span><span class="sxs-lookup"><span data-stu-id="50595-229">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="50595-230">授權數目會以下列方式限制：</span><span class="sxs-lookup"><span data-stu-id="50595-230">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="50595-231">如果使用者的 IP 位址在 Lync 會話期間變更，將會 overcounted 授權。</span><span class="sxs-lookup"><span data-stu-id="50595-231">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="50595-232">當使用者使用桌面用戶端從多個位置連接至 Lync Server 時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="50595-232">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="50595-233">若使用者與行動用戶端進行連線，將會低估授權，因為無法判斷裝置的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="50595-233">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="50595-234">**針對公用交換電話網路 (PSTN) 呼叫 Lync 用戶端、Lync 用戶端通話至 PSTN 線路，以及轉接至 PSTN 線路的 Lync 來電，計算兩次的授權**</span><span class="sxs-lookup"><span data-stu-id="50595-234">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="50595-235">在下列案例中，會同時計算兩個額外的授權，而不是一個授權，因為電話號碼和 Lync 使用者都會進行計算，以決定所使用的授權數目。</span><span class="sxs-lookup"><span data-stu-id="50595-235">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="50595-236">若要取得正確的授權資料，請手動移除電話號碼所產生的授權。</span><span class="sxs-lookup"><span data-stu-id="50595-236">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="50595-237">對 Lync 的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="50595-237">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="50595-238">對 PSTN 線路的 Lync 通話</span><span class="sxs-lookup"><span data-stu-id="50595-238">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="50595-239">對 Lync 的 PSTN 通話，然後 Lync 會將通話轉寄至 PSTN 線路。</span><span class="sxs-lookup"><span data-stu-id="50595-239">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="50595-240">其中一條 PSTN 線會計算在內。</span><span class="sxs-lookup"><span data-stu-id="50595-240">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="50595-241">**不會計算已登入之 Lync phone 的授權**</span><span class="sxs-lookup"><span data-stu-id="50595-241">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="50595-242">當使用者使用 Lync 認證的電話時，如果電話登入並保持連線，這會保留其登入狀態，如果在電話登入後發生授權的查詢，則不會將電話計為使用授權。</span><span class="sxs-lookup"><span data-stu-id="50595-242">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="50595-243">**針對加入會議的 PSTN 電話所計算的授權**</span><span class="sxs-lookup"><span data-stu-id="50595-243">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="50595-244">當使用者加入使用 PSTN 電話的會議時，會不准確地計算授權加入會議。</span><span class="sxs-lookup"><span data-stu-id="50595-244">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="50595-245">不過，使用 PSTN 電話加入會議時，不需要授權。</span><span class="sxs-lookup"><span data-stu-id="50595-245">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="50595-246">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-246">**Workaround:**</span></span>

1.  <span data-ttu-id="50595-247">**行動使用者的不正確授權計數**</span><span class="sxs-lookup"><span data-stu-id="50595-247">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="50595-248">您可以手動識別屬於相同裝置的 IP 位址，然後在許可證計數中移除其中一個。</span><span class="sxs-lookup"><span data-stu-id="50595-248">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="50595-249">使用 Lync 用戶端連線的行動裝置，無法解決此問題。</span><span class="sxs-lookup"><span data-stu-id="50595-249">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="50595-250">**對 Lync 用戶端、Lync 用戶端撥打到 PSTN 線路的 PSTN 呼叫進行兩次的授權，以及轉接至 PSTN 線路的 Lync 來電。**</span><span class="sxs-lookup"><span data-stu-id="50595-250">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="50595-251">您將需要手動識別 PSTN 電話號碼，並移除其所產生的授權計數。</span><span class="sxs-lookup"><span data-stu-id="50595-251">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="50595-252">**登入的 Lync phone 不會計算授權**</span><span class="sxs-lookup"><span data-stu-id="50595-252">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="50595-253">您可以設定 Lync phone 登出，然後定期登入（如每三個月）。</span><span class="sxs-lookup"><span data-stu-id="50595-253">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="50595-254">**針對加入會議的 PSTN 電話所計算的授權**</span><span class="sxs-lookup"><span data-stu-id="50595-254">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="50595-255">您可以手動識別用來加入會議的 PSTN 電話號碼，並移除電話號碼所產生的授權。</span><span class="sxs-lookup"><span data-stu-id="50595-255">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="50595-256">在升級至 Silverlight 5 後，Lync Server 控制台在 VMware 環境中停止運作</span><span class="sxs-lookup"><span data-stu-id="50595-256">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="50595-257">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-257">**Issue:**</span></span>

<span data-ttu-id="50595-258">如果您使用 VMware 環境中的 Lync Server 控制台，當您將 Microsoft Silverlight 升級為第5版之後，Lync Server 控制台可能會停止運作。</span><span class="sxs-lookup"><span data-stu-id="50595-258">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="50595-259">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-259">**Workaround:**</span></span>

<span data-ttu-id="50595-260">若要解決此問題，請執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="50595-260">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="50595-261">卸載 Silverlight 5，然後從安裝 Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) 。</span><span class="sxs-lookup"><span data-stu-id="50595-261">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="50595-262">從非 VMware 虛擬電腦的電腦存取 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="50595-262">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="50595-263">若要這麼做，您可以從伺服器上的 Windows [ **開始** ] 功能表啟動 Lync server 控制台（如果電腦上已安裝 lync Server 系統管理工具）。</span><span class="sxs-lookup"><span data-stu-id="50595-263">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="50595-264">您也可以使用網頁瀏覽器來存取 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="50595-264">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="50595-265">URL 會類似 HTTPs:// \<frontend\_pool\_fqdn\> /cscp。</span><span class="sxs-lookup"><span data-stu-id="50595-265">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="50595-266">在 Active Directory 中修改使用者的辨識名稱後，通訊錄服務中的使用者資訊未更新</span><span class="sxs-lookup"><span data-stu-id="50595-266">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="50595-267">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-267">**Issue:**</span></span>

<span data-ttu-id="50595-268">如果使用者的辨識名稱 (也稱為 DN) 在 Active Directory 網域服務中已變更，則任何額外的變更將不會更新于通訊錄服務 (ABS) 。</span><span class="sxs-lookup"><span data-stu-id="50595-268">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="50595-269">這不會影響使用者的登入或顯示狀態，但是如果 SIP 位址也會變更，則會防止使用者進行通訊，因為搜尋會傳回過期的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="50595-269">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="50595-270">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-270">**Workaround:**</span></span>

<span data-ttu-id="50595-271">若要解決此問題，請不要變更使用者的 DN。</span><span class="sxs-lookup"><span data-stu-id="50595-271">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="50595-272">如果您將使用者的 DN 還原為上一個值，更新將會反映在通訊錄服務中。</span><span class="sxs-lookup"><span data-stu-id="50595-272">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="50595-273">安裝</span><span class="sxs-lookup"><span data-stu-id="50595-273">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="50595-274">使用非 ASCII 字元可能會導致 Lync server 啟動失敗</span><span class="sxs-lookup"><span data-stu-id="50595-274">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="50595-275">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-275">**Issue:**</span></span>

<span data-ttu-id="50595-276">若目的地資料夾名稱包含非 ASCII 字元 (包括 UNICODE、雙位元組字元集 (DBCS) 、UTF-8 及 UTF-16) ，安裝程式將會失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-276">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="50595-277">此外，安裝程式可能會成功，但是如果有下列任何一種非 ASCII 字元，則伺服器不會啟動：</span><span class="sxs-lookup"><span data-stu-id="50595-277">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="50595-278">電腦名稱</span><span class="sxs-lookup"><span data-stu-id="50595-278">Computer name</span></span>

  - <span data-ttu-id="50595-279">網域名稱</span><span class="sxs-lookup"><span data-stu-id="50595-279">Domain name</span></span>

  - <span data-ttu-id="50595-280">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="50595-280">User name</span></span>

  - <span data-ttu-id="50595-281">使用者 SIP URI</span><span class="sxs-lookup"><span data-stu-id="50595-281">User SIP URI</span></span>

  - <span data-ttu-id="50595-282">服務帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="50595-282">Service account name</span></span>

<span data-ttu-id="50595-283">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-283">**Workaround:**</span></span>

<span data-ttu-id="50595-284">使用目的資料夾名稱、電腦名稱稱、功能變數名稱、使用者名稱、使用者 SIP URI 及服務帳戶名稱中的 ASCII 字元。</span><span class="sxs-lookup"><span data-stu-id="50595-284">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="50595-285">在安裝 Lync Server 2013 之前必須安裝模組呼叫 IIS 7.5 中的 InsertEntityBody 方法時，就會發生「堆損毀」的修復程式。</span><span class="sxs-lookup"><span data-stu-id="50595-285">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="50595-286">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-286">**Issue:**</span></span>

<span data-ttu-id="50595-287">當 module 7.5 InsertEntityBody 呼叫在 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) 安裝 Lync Server 2013 之前，必須先安裝 Microsoft 知識庫文章 264886 () 中所述的「 () 的「堆損毀」的修復程式，才會發生堆損毀。</span><span class="sxs-lookup"><span data-stu-id="50595-287">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="50595-288">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-288">**Workaround:**</span></span>

<span data-ttu-id="50595-289">從 Microsoft 下載中心下載並安裝修複程式 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) 。</span><span class="sxs-lookup"><span data-stu-id="50595-289">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="50595-290">Lync Server 2013 無法在 ITA Windows Server 2012 作業系統 RTM 版本上安裝</span><span class="sxs-lookup"><span data-stu-id="50595-290">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="50595-291">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-291">**Issue:**</span></span>

<span data-ttu-id="50595-292">由於 Windows Fabric 安裝失敗，所以 Lync Server 2013 在 ITA Windows Server 2012 上安裝失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-292">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="50595-293">Windows Fabric 安裝失敗，因為會以 HH： MM： SS 的時間格式建立 Fabric 追蹤。</span><span class="sxs-lookup"><span data-stu-id="50595-293">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="50595-294">不過，在 ITA Windows Server 中，時間格式為 HH。MM.SS。</span><span class="sxs-lookup"><span data-stu-id="50595-294">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="50595-295">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-295">**Workaround:**</span></span>

<span data-ttu-id="50595-296">若要解決此問題，請在安裝 Lync Server 2013 之前，先更新系統登錄。</span><span class="sxs-lookup"><span data-stu-id="50595-296">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="50595-297">需要更新的登錄機碼是： HKEY \_ 使用者 \\ 。預設 \\ 控制台 \\ 國際化 \\ sTimeFormat。</span><span class="sxs-lookup"><span data-stu-id="50595-297">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="50595-298">使用 Windows PowerShell 命令列介面，將 sTimeFormat 的值變更為 HH： mm： ss，如下所示：</span><span class="sxs-lookup"><span data-stu-id="50595-298">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="50595-299">啟動 Windows PowerShell，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50595-299">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="50595-300">若要查看目前的值，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50595-300">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="50595-301">記下 sTimeFormat 的目前值，以便在安裝完成後能夠進行還原。</span><span class="sxs-lookup"><span data-stu-id="50595-301">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="50595-302">若要設定為新值，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50595-302">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="50595-303">成功安裝 Lync Server 2013 之後，請執行下列 Cmdlet 來還原 sTimeFormat 的原始值：</span><span class="sxs-lookup"><span data-stu-id="50595-303">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="50595-304">Set-ItemProperty $a 名稱 sTimeFormat-值「步驟3中所述 <的值。</span><span class="sxs-lookup"><span data-stu-id="50595-304">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="50595-305">以上> "</span><span class="sxs-lookup"><span data-stu-id="50595-305">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="50595-306">行動性</span><span class="sxs-lookup"><span data-stu-id="50595-306">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="50595-307">在伺服器容錯移轉過程中行動用戶端的問題</span><span class="sxs-lookup"><span data-stu-id="50595-307">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="50595-308">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-308">**Issue:**</span></span>

<span data-ttu-id="50595-309">當 Lync 伺服器失敗，且容錯移轉程式開始時，下列問題可能會影響行動用戶端使用者：</span><span class="sxs-lookup"><span data-stu-id="50595-309">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="50595-310">容錯移轉開始之後，不會有最多10分鐘的傳入 Lync 通話或信號。</span><span class="sxs-lookup"><span data-stu-id="50595-310">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="50595-311">無法接受傳入的交談要求</span><span class="sxs-lookup"><span data-stu-id="50595-311">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="50595-312">如果失敗的伺服器是使用者的主伺服器，就無法加入會議</span><span class="sxs-lookup"><span data-stu-id="50595-312">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="50595-313">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-313">**Workaround:**</span></span>

<span data-ttu-id="50595-314">此問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-314">There is no workaround for this issue.</span></span> <span data-ttu-id="50595-315">容錯移轉程式完成後，就會還原正常功能。</span><span class="sxs-lookup"><span data-stu-id="50595-315">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="50595-316">如果行動使用者拒絕來自其他 Lync 端點的來電，則此呼叫會在 Lync Mobile 用戶端上顯示為未接轉換</span><span class="sxs-lookup"><span data-stu-id="50595-316">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="50595-317">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-317">**Issue:**</span></span>

<span data-ttu-id="50595-318">如果行動使用者拒絕來電，且呼叫來自其他 Lync 端點，則此呼叫會顯示為 Lync Mobile 用戶端中未接的交談，而不是在 [裝置呼叫] 清單中通話。</span><span class="sxs-lookup"><span data-stu-id="50595-318">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="50595-319">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-319">**Workaround:**</span></span>

<span data-ttu-id="50595-320">此問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-320">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="50595-321">行動用戶端在搜尋連絡人時，可能不會顯示同盟連絡人的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="50595-321">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="50595-322">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-322">**Issue:**</span></span>

<span data-ttu-id="50595-323">同盟連絡人的顯示名稱可能不會顯示在某些案例中，例如在連絡人清單中搜尋同盟連絡人時。</span><span class="sxs-lookup"><span data-stu-id="50595-323">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="50595-324">當 Lync mobile 用戶端的連絡人沒有任何作用中的目前狀態訂閱時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="50595-324">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="50595-325">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-325">**Workaround:**</span></span>

<span data-ttu-id="50595-326">此問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-326">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="50595-327">在行動用戶端中，未接來電（即會議邀請）的被邀請者和時間戳記資訊缺失</span><span class="sxs-lookup"><span data-stu-id="50595-327">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="50595-328">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-328">**Issue:**</span></span>

<span data-ttu-id="50595-329">在行動用戶端中，當錯過交談是邀請參加會議時，未接的交談郵件中遺漏了被邀請者和時間戳記資訊。</span><span class="sxs-lookup"><span data-stu-id="50595-329">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="50595-330">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-330">**Workaround:**</span></span>

<span data-ttu-id="50595-331">此問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-331">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="50595-332">使用 VoIP 進行通話的行動用戶端使用者無法留下語音信箱給其語音信箱已設定在 Exchange 2010 或更早版本中的使用者</span><span class="sxs-lookup"><span data-stu-id="50595-332">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="50595-333">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-333">**Issue:**</span></span>

<span data-ttu-id="50595-334">若行動用戶端使用者正在使用 VoIP 進行通話，則使用者將無法為設定為使用 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中的語音信箱的使用者留下語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="50595-334">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="50595-335">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-335">**Workaround:**</span></span>

<span data-ttu-id="50595-336">若要解決此問題，請將 Exchange 2010 與 SP1 或更新版本的 Microsoft Exchange Server 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="50595-336">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="50595-337">在行動用戶端上使用 Block 搭配用戶端版本設定的 URL 時，可能會顯示不正確的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="50595-337">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="50595-338">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-338">**Issue:**</span></span>

<span data-ttu-id="50595-339">在行動用戶端上使用 Block 搭配用戶端版本設定的 **URL** 時，當用戶端版本不受支援時，可能會顯示不正確的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="50595-339">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="50595-340">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-340">**Workaround:**</span></span>

<span data-ttu-id="50595-341">若要解決此問題，請將 Client Version Configuration 設定**Block**為使用區塊 **，** 而不是使用 URL 的 block。</span><span class="sxs-lookup"><span data-stu-id="50595-341">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="50595-342">會議</span><span class="sxs-lookup"><span data-stu-id="50595-342">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="50595-343">在 Lync Server 2013 前端伺服器上執行的防毒軟體可能會造成應用程式網域回收，這會暫時中斷 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 用戶端的服務</span><span class="sxs-lookup"><span data-stu-id="50595-343">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="50595-344">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-344">**Issue:**</span></span>

<span data-ttu-id="50595-345">防毒軟體可能會觸發應用程式網域重新開機，這可能會導致 Lync Mobile Service 2013 和整合通訊 (UC) 網頁 API 用戶端應用程式 (Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013) 以失去其狀態。</span><span class="sxs-lookup"><span data-stu-id="50595-345">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="50595-346">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-346">**Workaround:**</span></span>

<span data-ttu-id="50595-347">若要解決此問題，請從防病毒掃描中排除包含網頁元件及 .NET framework 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="50595-347">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="50595-348">如需詳細資訊，請參閱 Microsoft 知識庫文章312592：「PRB：在 ASP.NET 中重新開機應用程式的隨機應用程式」錯誤，「at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) 。</span><span class="sxs-lookup"><span data-stu-id="50595-348">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="50595-349">應該排除下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="50595-349">The following folders should be excluded:</span></span>

  - <span data-ttu-id="50595-350">%ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 元件 \\ Mcx \\ Ext</span><span class="sxs-lookup"><span data-stu-id="50595-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="50595-351">%ProgramFiles% \\ Microsoft Lync Server 2013 \\ 網頁元件 \\ Mcx \\ Int</span><span class="sxs-lookup"><span data-stu-id="50595-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="50595-352">%ProgramFiles% \\ Microsoft Lync Server 2013 \\ 網頁元件 \\ Ucwa \\ Int</span><span class="sxs-lookup"><span data-stu-id="50595-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="50595-353">%ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 元件 \\ Ucwa \\ Ext</span><span class="sxs-lookup"><span data-stu-id="50595-353">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="50595-354">% Windir% \\ Microsoft.NET \\ Framework64 \\ v 4.0.30319 \\ Config</span><span class="sxs-lookup"><span data-stu-id="50595-354">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="50595-355">必須在 Windows Internet Explorer 中啟用 ActiveX 控制項或原生 XMLHTTP 支援，才能成功加入會議</span><span class="sxs-lookup"><span data-stu-id="50595-355">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="50595-356">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-356">**Issue:**</span></span>

<span data-ttu-id="50595-357">如果使用者在 Windows Internet Explorer Internet browser 設定中同時停用 ActiveX 控制項和原生 XMLHTTP 支援，當已選取 [Internet Explorer] 做為預設瀏覽器時，使用者將無法加入會議。</span><span class="sxs-lookup"><span data-stu-id="50595-357">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="50595-358">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-358">**Workaround:**</span></span>

<span data-ttu-id="50595-359">在 Internet Explorer 中啟用 ActiveX 控制項或「原生 XMLHTTP 支援」。</span><span class="sxs-lookup"><span data-stu-id="50595-359">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="50595-360">Lync Server Web 會議服務無法從重要模式復原</span><span class="sxs-lookup"><span data-stu-id="50595-360">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="50595-361">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-361">**Issue:**</span></span>

<span data-ttu-id="50595-362">如果已開啟關鍵模式進行封存，則在發生系統失敗時，將會啟動重要模式，並且會議將不再為參與者運作。</span><span class="sxs-lookup"><span data-stu-id="50595-362">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="50595-363">在管理員修正系統失敗 (例如修復資料庫問題時) ，[資料會議服務] 不會自動復原，而且系統管理員必須手動重新開機會議服務才能繼續會議。</span><span class="sxs-lookup"><span data-stu-id="50595-363">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="50595-364">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-364">**Workaround:**</span></span>

<span data-ttu-id="50595-365">系統管理員需要在修復系統失敗後，手動重新開機會議服務。</span><span class="sxs-lookup"><span data-stu-id="50595-365">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="50595-366">Web 會議服務會忽略外部 Office Web App 伺服器的 HTTP proxy</span><span class="sxs-lookup"><span data-stu-id="50595-366">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="50595-367">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-367">**Issue:**</span></span>

<span data-ttu-id="50595-368">如果您已將 Office Web Apps Server 部署在 Web 會議服務外 (也就是說，Internet、周邊網路和 Web 會議服務中不是內部公司網路) 中的伺服器，則 Office Web Apps Server 探索將會失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-368">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="50595-369">Web 會議服務會忽略 HTTP proxy 設定，如 Office Web Apps Server 安裝程式的拓撲產生器所定義。</span><span class="sxs-lookup"><span data-stu-id="50595-369">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="50595-370">因此，Lync 用戶端將無法與會議中的其他參與者共用 Microsoft PowerPoint 2010。</span><span class="sxs-lookup"><span data-stu-id="50595-370">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="50595-371">如果您要在內部網路安裝 Lync Server，並在內部網路中設定 Office Web Apps Server 內部部署，則不需要 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="50595-371">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="50595-372">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-372">**Workaround:**</span></span>

<span data-ttu-id="50595-373">唯一的解決方法是不需要使用 HTTP proxy 來與外部 Office Web Apps Server 通訊的部署設定。</span><span class="sxs-lookup"><span data-stu-id="50595-373">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="50595-374">不支援將影片加入音訊會議提供者會議</span><span class="sxs-lookup"><span data-stu-id="50595-374">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="50595-375">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-375">**Issue:**</span></span>

<span data-ttu-id="50595-376">如果使用者加入音訊的音訊會議提供者會議，則不支援新增影片。</span><span class="sxs-lookup"><span data-stu-id="50595-376">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="50595-377">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-377">**Workaround:**</span></span>

<span data-ttu-id="50595-378">此問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-378">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="50595-379">啟用 IPv6 的拓撲會強制 Lync Web App Silverlight 外掛程式自動更新，以確保螢幕共用功能可從 Lync Web App 運作</span><span class="sxs-lookup"><span data-stu-id="50595-379">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="50595-380">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-380">**Issue:**</span></span>

<span data-ttu-id="50595-381">當拓撲設定為啟用 IPv6 時，如果已安裝舊版的螢幕共用外掛程式，使用者就無法從 Lync Web App 用戶端共用其畫面。</span><span class="sxs-lookup"><span data-stu-id="50595-381">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="50595-382">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-382">**Workaround:**</span></span>

<span data-ttu-id="50595-383">若要在透過 Lync Web App 加入會議時，強制更新至最新版本的螢幕共用外掛程式，請在下列兩個檔案中，將 **MinSupportedBuildVersion** 的值從 "4.0.7457.0" 修改為 "4.0.7577.380"：</span><span class="sxs-lookup"><span data-stu-id="50595-383">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="50595-384">%ProgramFiles% \\ Microsoft Lync Server 15 \\ 網頁元件是以 \\ \\ Int \\ 用戶端 \\ 外掛程式送達 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="50595-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="50595-385">%ProgramFiles% \\ Microsoft Lync Server 15 網頁元件都無法連線至 \\ \\ 外部的 \\ \\ 用戶端 \\ 外掛程式 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="50595-385">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="50595-386">設定使用者</span><span class="sxs-lookup"><span data-stu-id="50595-386">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="50595-387">在某些情況下，在設定成使用 IPv4 和 IPv6 雙堆疊的電腦上執行的 Lync 用戶端，可能不支援依賴電腦的 IP 子網（如 E911、媒體旁路、通話許可控制和位置基礎路由）的功能。</span><span class="sxs-lookup"><span data-stu-id="50595-387">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="50595-388">本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="50595-388">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="50595-389">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-389">**Issue:**</span></span>

<span data-ttu-id="50595-390">當 Lync 用戶端在已啟用 IPv4 和 IPv6 雙堆疊的電腦上執行，且以 proxy 伺服器的 DNS 解析為基礎時，用戶端可能會使用該電腦的 IPv6 位址登入。</span><span class="sxs-lookup"><span data-stu-id="50595-390">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="50595-391">這樣做之後，Lync 用戶端只會支援 IPv6 所支援的功能，但不包括 E911、媒體旁路、通話許可控制和位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="50595-391">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="50595-392">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-392">**Workaround:**</span></span>

<span data-ttu-id="50595-393">若要解決此問題，請在用戶端電腦上停用 IPv6 支援。</span><span class="sxs-lookup"><span data-stu-id="50595-393">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="50595-394">如果沒有為使用者設定 Enterprise Voice，使用者將需要使用 E164 格式從會議撥出</span><span class="sxs-lookup"><span data-stu-id="50595-394">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="50595-395">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-395">**Issue:**</span></span>

<span data-ttu-id="50595-396">如果使用者未設定 Enterprise Voice，該使用者將需要使用 E164 格式才能從會議中成功撥出。</span><span class="sxs-lookup"><span data-stu-id="50595-396">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="50595-397">若未使用 E164 格式，則使用者將無法從會議撥出。</span><span class="sxs-lookup"><span data-stu-id="50595-397">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="50595-398">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-398">**Workaround:**</span></span>

<span data-ttu-id="50595-399">若要解決此問題，未啟用 Enterprise Voice 的使用者，應使用 E164 格式的數位來撥出會議。</span><span class="sxs-lookup"><span data-stu-id="50595-399">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="50595-400">目前狀態</span><span class="sxs-lookup"><span data-stu-id="50595-400">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="50595-401">如果使用者在開啟統一連絡人存放區時已選取「封鎖所有邀請和通訊」，則不會拒絕目前狀態，應為</span><span class="sxs-lookup"><span data-stu-id="50595-401">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="50595-402">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-402">**Issue:**</span></span>

<span data-ttu-id="50595-403">如果使用者已選取「封鎖所有邀請與通訊」，當統一連絡人存放區開啟時，就不會拒絕其狀態。</span><span class="sxs-lookup"><span data-stu-id="50595-403">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="50595-404">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-404">**Workaround:**</span></span>

<span data-ttu-id="50595-405">若要解決此問題，您可以關閉使用者的整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="50595-405">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="50595-406">若要這麼做，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50595-406">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="50595-407">例如：</span><span class="sxs-lookup"><span data-stu-id="50595-407">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="50595-408">Office 通訊伺服器 2007 R2 使用者在內部部署中無法看到混合式部署中商務用 Skype Online 使用者的目前狀態-混合式</span><span class="sxs-lookup"><span data-stu-id="50595-408">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="50595-409">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-409">**Issue:**</span></span>

<span data-ttu-id="50595-410">當您使用 Lync Server 2013 Director 時，可能會在混合部署中發生此問題。</span><span class="sxs-lookup"><span data-stu-id="50595-410">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="50595-411">屬於內部部署使用者的目前狀態為「商務用 Skype Online」之使用者的狀態為「未知」。</span><span class="sxs-lookup"><span data-stu-id="50595-411">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="50595-412">此外，位於商務用 Skype Online 的使用者無法查看 Office 通訊伺服器 R2 內部部署使用者的狀態。</span><span class="sxs-lookup"><span data-stu-id="50595-412">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="50595-413">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-413">**Workaround:**</span></span>

<span data-ttu-id="50595-414">若要解決此問題，請將商務用 Skype Online 使用者的「家用伺服器」 (系-presencehomeserver) 變更為指向 Lync Server 2013 內部部署集區，而不是 Lync Server 2013 Director。</span><span class="sxs-lookup"><span data-stu-id="50595-414">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="50595-415">您可以在內部部署前端伺服器上修改此設定。</span><span class="sxs-lookup"><span data-stu-id="50595-415">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="50595-416">此解決方法會正確顯示位於 Office 通訊伺服器 2007 R2 的使用者目前狀態，以供商務用 Skype Online 使用者。</span><span class="sxs-lookup"><span data-stu-id="50595-416">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="50595-417">回應群組應用程式、通話駐留應用程式和群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="50595-417">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="50595-418">來電者使用「檢索方」建立通話期間，來電者可能會聽到一秒的等待音樂。</span><span class="sxs-lookup"><span data-stu-id="50595-418">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="50595-419">本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="50595-419">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="50595-420">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-420">**Issue:**</span></span>

<span data-ttu-id="50595-421">透過群組呼叫收取通話時，來電者可能會在使用檢索程式建立通話時，聽到一秒的等待音樂。</span><span class="sxs-lookup"><span data-stu-id="50595-421">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="50595-422">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-422">**Workaround:**</span></span>

<span data-ttu-id="50595-423">此問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-423">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="50595-424">回應群組代理程式只能透過 Lync Server 2010 Agent 主控台登入並登出，以僅限 Lync Server 2010 正式代理群組</span><span class="sxs-lookup"><span data-stu-id="50595-424">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="50595-425">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-425">**Issue:**</span></span>

<span data-ttu-id="50595-426">Lync Server 2013 回應群組代理程式只能透過 Lync Server 2010 代理程式主控台登入並登出，以供 Lync Server 2010 正式代理群組。</span><span class="sxs-lookup"><span data-stu-id="50595-426">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="50595-427">在 Lync Server 2010 Agent 主控台中，使用者只能看到他們所屬的 Lync Server 2010 回應群組。</span><span class="sxs-lookup"><span data-stu-id="50595-427">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="50595-428">他們無法看到任何屬於的 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="50595-428">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="50595-429">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-429">**Workaround:**</span></span>

<span data-ttu-id="50595-430">若回應群組代理程式是 Lync Server 2013 使用者，以及 Lync Server 2013 正式代理群組的一部分，使用者必須透過瀏覽器中的網路連結直接存取 Lync Server 2013 代理程式主控台，以登入並登出 Lync Server 2013 Agent 群組。</span><span class="sxs-lookup"><span data-stu-id="50595-430">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="50595-431">Lync Server 2010 回應群組代理程式無法代表 Lync Server 2013 回應群組進行呼叫</span><span class="sxs-lookup"><span data-stu-id="50595-431">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="50595-432">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-432">**Issue:**</span></span>

<span data-ttu-id="50595-433">Lync server 2010 使用者是 Lync Server 2013 回應群組的代理人，無法代表回應群組撥打電話。</span><span class="sxs-lookup"><span data-stu-id="50595-433">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="50595-434">Lync Server 2013 回應群組將無法在 Lync 用戶端中使用，以進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="50595-434">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="50595-435">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-435">**Workaround:**</span></span>

<span data-ttu-id="50595-436">若要解決此問題，您必須將 Lync Server 2010 使用者移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="50595-436">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="50595-437">從 Lync Server 2010 遷移至 Lync Server 2013 之後移除回應群組，將會使回應群組無法接受任何來電</span><span class="sxs-lookup"><span data-stu-id="50595-437">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="50595-438">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-438">**Issue:**</span></span>

<span data-ttu-id="50595-439">如果已從 Lync server 2010 遷移至 Lync Server 2013 的回應群組是透過 Lync Server 控制台或 Lync Server 管理命令介面從 Lync server 2010 中移除，則 Lync Server 2013 中的回應群組會停止接收任何來電。</span><span class="sxs-lookup"><span data-stu-id="50595-439">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="50595-440">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-440">**Workaround:**</span></span>

<span data-ttu-id="50595-441">若要解決此問題，請勿移除從 Lync server 2010 遷移至 Lync Server 2013 之 Lync Server 2010 的任何回應群組。</span><span class="sxs-lookup"><span data-stu-id="50595-441">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="50595-442">若回應群組已移除，您應該在 Lync Server 2013 中重新部署它。</span><span class="sxs-lookup"><span data-stu-id="50595-442">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="50595-443">當新的受管理工作流程在建立時設定為非使用中時，工作流程的部署會失敗</span><span class="sxs-lookup"><span data-stu-id="50595-443">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="50595-444">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-444">**Issue:**</span></span>

<span data-ttu-id="50595-445">當新的受管理工作流程在建立時設定為非使用中時，工作流程的部署會失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-445">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="50595-446">當工作流程在建立時設定為非使用中時，就會發生此問題，但不會影響已編輯的工作流程，以在部署後將其設定為非使用中。</span><span class="sxs-lookup"><span data-stu-id="50595-446">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="50595-447">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-447">**Workaround:**</span></span>

<span data-ttu-id="50595-448">建立及部署工作流程時，請將工作流程設定為使用中，然後加以部署。</span><span class="sxs-lookup"><span data-stu-id="50595-448">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="50595-449">成功部署工作流程之後，即可編輯工作流程，並將其設為非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="50595-449">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="50595-450">若回應群組已匯入到備份組區，則從擁有者集區移除回應群組將會防止備份組區的回應群組接受任何來電時接受所有來電。</span><span class="sxs-lookup"><span data-stu-id="50595-450">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="50595-451">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-451">**Issue:**</span></span>

<span data-ttu-id="50595-452">如果主要集區所擁有的回應群組已匯入到備份組區，但未覆寫擁有者，且回應群組已從擁有者集區中移除，則備份組區中的回應群組將不會接受容錯移轉期間的任何來電。</span><span class="sxs-lookup"><span data-stu-id="50595-452">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="50595-453">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-453">**Workaround:**</span></span>

<span data-ttu-id="50595-454">您將需要在主要集區中重新部署回應群組。</span><span class="sxs-lookup"><span data-stu-id="50595-454">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="50595-455">然後，您必須從主要集區中匯出回應群組設定，並重新將它匯入至備份組區。</span><span class="sxs-lookup"><span data-stu-id="50595-455">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="50595-456">您也可以在備份組區中重新建立回應群組。</span><span class="sxs-lookup"><span data-stu-id="50595-456">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="50595-457">在此情況下，備份組區將是回應群組的擁有者集區。</span><span class="sxs-lookup"><span data-stu-id="50595-457">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="50595-458">如果代表回應群組執行取回要求，則無法從通話駐留應用程式中檢索寄存通話</span><span class="sxs-lookup"><span data-stu-id="50595-458">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="50595-459">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-459">**Issue:**</span></span>

<span data-ttu-id="50595-460">當下列條件為 true 時，對寄存通話的檢索要求會失敗：</span><span class="sxs-lookup"><span data-stu-id="50595-460">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="50595-461">代理程式屬於匿名回應群組</span><span class="sxs-lookup"><span data-stu-id="50595-461">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="50595-462">代理程式會嘗試透過匿名回應群組來從通話駐留應用程式取得寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="50595-462">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="50595-463">工程師會嘗試透過 [代表來電] 選項或透過 Lync 語音應答用戶端中的相同選項，撥打軌道號碼，以取回通話。</span><span class="sxs-lookup"><span data-stu-id="50595-463">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="50595-464">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-464">**Workaround:**</span></span>

<span data-ttu-id="50595-465">此問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-465">There are no workarounds for this issue.</span></span> <span data-ttu-id="50595-466">停用呼叫應以無回應群組的方式，加以取回。</span><span class="sxs-lookup"><span data-stu-id="50595-466">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="50595-467">Lync Server 控制台、拓撲產生器和規劃工具</span><span class="sxs-lookup"><span data-stu-id="50595-467">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="50595-468">規劃工具限制</span><span class="sxs-lookup"><span data-stu-id="50595-468">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="50595-469">本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="50595-469">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="50595-470">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-470">**Issue:**</span></span>

<span data-ttu-id="50595-471">規劃部署時，規劃工具具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="50595-471">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="50595-472">最多可支援10個中央網站</span><span class="sxs-lookup"><span data-stu-id="50595-472">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="50595-473">每個中央網站最多可以有14個分支網站</span><span class="sxs-lookup"><span data-stu-id="50595-473">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="50595-474">每個中央網站最多可以有240000位使用者</span><span class="sxs-lookup"><span data-stu-id="50595-474">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="50595-475">此外，在計算建議的拓撲時，規劃工具並未包含下列值：</span><span class="sxs-lookup"><span data-stu-id="50595-475">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="50595-476">線上中的使用者人數</span><span class="sxs-lookup"><span data-stu-id="50595-476">The number of users that are homed online</span></span>

  - <span data-ttu-id="50595-477">啟用 XMPP 同盟的使用者百分比</span><span class="sxs-lookup"><span data-stu-id="50595-477">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="50595-478">使用 Lync Web App 的使用者百分比</span><span class="sxs-lookup"><span data-stu-id="50595-478">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="50595-479">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-479">**Workaround:**</span></span>

<span data-ttu-id="50595-480">這些問題沒有任何解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-480">There is no workaround for these issues.</span></span> <span data-ttu-id="50595-481">如需規劃工具的相關資訊，請參閱 [使用規劃工具設計 Lync Server 2013 的拓撲](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="50595-481">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="50595-482">在更新選項時，規劃工具可能不會對 Edge 網路使用先前定義的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="50595-482">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="50595-483">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-483">**Issue:**</span></span>

<span data-ttu-id="50595-484">使用規劃工具完成設計後，如果您對 Edge 網路選項進行變更，則其他的 IP 位址可能會新增至設計，而不是更新現有的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="50595-484">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="50595-485">當您查看 Edge Network 圖表的詳細資料時，可能會發生這種情況，請選取 [ **按一下這裡以更新您的選項**]，然後在 [設定選項] 對話方塊中選取 [edge 網路]。 **我想要使用相同的 fqdn 和 IP 位址，但在 edge Server 上使用 edge service 的不同埠**。</span><span class="sxs-lookup"><span data-stu-id="50595-485">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="50595-486">套用任何變更可能會導致新的 IP 位址和 Edge server 新增到設計中。</span><span class="sxs-lookup"><span data-stu-id="50595-486">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="50595-487">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-487">**Workaround:**</span></span>

<span data-ttu-id="50595-488">目前尚無此問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-488">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="50595-489">在 [Lync Server 控制台] 中，[將所有使用者移至集區] 可能無法如預期般運作</span><span class="sxs-lookup"><span data-stu-id="50595-489">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="50595-490">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-490">**Issue:**</span></span>

<span data-ttu-id="50595-491">使用 Lync Server 控制台將所有使用者從一個集區移至複雜的 Active Directory 環境中的另一個集區時（例如有多個網域控制站和父/子系網域的一個集區），可能會傳回錯誤訊息：「指定的使用者不是舊版使用者，請改用 Move-CsUser Cmdlet」。</span><span class="sxs-lookup"><span data-stu-id="50595-491">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="50595-492">這是在複雜的 Active Directory 環境中較長時間複寫的結果。</span><span class="sxs-lookup"><span data-stu-id="50595-492">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="50595-493">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-493">**Workaround:**</span></span>

<span data-ttu-id="50595-494">若要解決此問題，請執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="50595-494">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="50595-495">使用 Lync Server 控制台中的篩選器來搜尋舊版使用者，請選取這些使用者，然後使用 [ **將選取的使用者移至集** 區] 命令，而不是 **將所有使用者移至集**區。</span><span class="sxs-lookup"><span data-stu-id="50595-495">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="50595-496">使用 Lync Server 管理命令介面，透過 Lync Server Cmdlet 以批次移動舊版使用者。</span><span class="sxs-lookup"><span data-stu-id="50595-496">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="50595-497">在 Microsoft Silverlight 瀏覽器外掛程式更新為第5版之後，Lync Server 控制台會在 VMware 環境中停止運作</span><span class="sxs-lookup"><span data-stu-id="50595-497">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="50595-498">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-498">**Issue:**</span></span>

<span data-ttu-id="50595-499">如果您使用 VMware 環境中的 Lync Server 控制台，當您將 Silverlight 升級為第5版之後，Lync Server 控制台可能會停止運作。</span><span class="sxs-lookup"><span data-stu-id="50595-499">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="50595-500">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-500">**Workaround:**</span></span>

<span data-ttu-id="50595-501">若要解決此問題，請執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="50595-501">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="50595-502">卸載 Silverlight 5，然後從安裝 Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) 。</span><span class="sxs-lookup"><span data-stu-id="50595-502">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="50595-503">從非 VMware 虛擬電腦的電腦上，開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="50595-503">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="50595-504">若要從遠端電腦開啟 Lync Server 控制台，請在電腦上安裝 Lync Server 系統管理工具，然後從 Windows [ **開始** ] 功能表啟動 lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="50595-504">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="50595-505">您也可以在網頁瀏覽器中輸入 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="50595-505">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="50595-506">URL 會類似 HTTPs:// \<frontend\_pool\_fqdn\> /cscp。</span><span class="sxs-lookup"><span data-stu-id="50595-506">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="50595-507">在拓撲產生器中移除鏡像資料庫之後，管理員無法執行 Uninstall-csMirrorDB Cmdlet</span><span class="sxs-lookup"><span data-stu-id="50595-507">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="50595-508">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-508">**Issue:**</span></span>

<span data-ttu-id="50595-509">當系統管理員在拓撲產生器中停用鏡像資料庫，然後刪除拓撲產生器中的鏡像資料庫時，系統會在 [待辦事項] 清單中顯示一則訊息，以執行 **uninstall-csmirrordatabase 指令程式** ，以從 SQL Server 中移除鏡像。</span><span class="sxs-lookup"><span data-stu-id="50595-509">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="50595-510">當系統管理員嘗試執行 Cmdlet 時，它會失敗。</span><span class="sxs-lookup"><span data-stu-id="50595-510">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="50595-511">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-511">**Workaround:**</span></span>

<span data-ttu-id="50595-512">若要在拓撲產生器中移除集區的 SQL 鏡像，您必須先使用 Cmdlet 來移除 SQL Server 中的鏡像。</span><span class="sxs-lookup"><span data-stu-id="50595-512">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="50595-513">然後您就可以使用拓撲產生器，從拓撲中移除鏡像。</span><span class="sxs-lookup"><span data-stu-id="50595-513">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="50595-514">若要在 SQL Server 中移除鏡像，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50595-514">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="50595-515">例如，若要移除使用者資料庫的鏡像並放下資料庫，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="50595-515">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="50595-516">*DropExistingDatabasesOnMirror*參數會從鏡像中刪除受影響的資料庫。</span><span class="sxs-lookup"><span data-stu-id="50595-516">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="50595-517">此外，若要從拓撲移除鏡像伺服器，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="50595-517">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="50595-518">在拓撲產生器中，以滑鼠右鍵按一下集區，再按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="50595-518">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="50595-519">清除 [ **啟用 SQL 存放區鏡像** ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="50595-519">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="50595-520">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="50595-520">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="50595-521">當您變更後端資料庫鏡像關係時，必須重新開機集區中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="50595-521">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="50595-522">當系統管理員嘗試移除具有相關見證存放區之前端集區的部署時，拓撲產生器會傳回驗證錯誤。</span><span class="sxs-lookup"><span data-stu-id="50595-522">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="50595-523">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-523">**Issue:**</span></span>

<span data-ttu-id="50595-524">如果系統管理員嘗試使用拓撲產生器中的 [ **移除部署** ] 命令，以移除包含具有相關見證存放區之前端集區的部署，則會在拓撲產生器中顯示驗證錯誤，且不會繼續執行該動作。</span><span class="sxs-lookup"><span data-stu-id="50595-524">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="50595-525">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-525">**Workaround:**</span></span>

<span data-ttu-id="50595-526">若要解決此問題，請執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="50595-526">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="50595-527">在嘗試移除部署之前，請先移除見證存放區。</span><span class="sxs-lookup"><span data-stu-id="50595-527">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="50595-528">新增前端集區的見證存放區，然後將其移除。</span><span class="sxs-lookup"><span data-stu-id="50595-528">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="50595-529">在規劃工具和拓撲產生器之間，Persistent Chat Server 部署資訊不一致</span><span class="sxs-lookup"><span data-stu-id="50595-529">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="50595-530">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-530">**Issue:**</span></span>

<span data-ttu-id="50595-531">當 Lync Server 2013 （計畫工具）在啟用嚴重損壞修復的情況下，針對 Persistent Chat Server 部署輸出網站拓撲圖表時，網站拓撲圖表會包含多個 (實體) 網站，且每個網站上都有均勻指派的持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="50595-531">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="50595-532">在 [拓撲產生器] 中，所有的持久聊天伺服器都代表屬於單一 (邏輯) 網站，而且會列在相同 Persistent Chat Server 集區節點底下。</span><span class="sxs-lookup"><span data-stu-id="50595-532">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="50595-533">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-533">**Workaround:**</span></span>

<span data-ttu-id="50595-534">目前，我們沒有此問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-534">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="50595-535">使用者應分析 Persistent Chat Server 部署規劃工具的輸出，並修改計畫以滿足其特定需求。</span><span class="sxs-lookup"><span data-stu-id="50595-535">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="50595-536">當地語系化</span><span class="sxs-lookup"><span data-stu-id="50595-536">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="50595-537">監視</span><span class="sxs-lookup"><span data-stu-id="50595-537">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="50595-538">使用東亞版的 Lync Server 時，「部署監控報告嚮導會在某些情況下顯示不正確的字元</span><span class="sxs-lookup"><span data-stu-id="50595-538">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="50595-539">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-539">**Issue:**</span></span>

<span data-ttu-id="50595-540">使用東亞版的 Lync Server 2013 （例如，中文 (簡體) 、中文 (傳統) 、日文或韓文）在系統地區設定未設定為東亞語言的作業系統上，「部署監控報告」嚮導會顯示試題符號或其他字元，而非當地語系化的郵件。</span><span class="sxs-lookup"><span data-stu-id="50595-540">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="50595-541">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-541">**Workaround:**</span></span>

<span data-ttu-id="50595-542">若要修正此問題，請將作業系統和 Lync Server 2013 的地區設定設定為相同的語言，這樣會正確顯示所有郵件。</span><span class="sxs-lookup"><span data-stu-id="50595-542">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="50595-543">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="50595-543">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="50595-544">在某些情況下，當按一下上方導覽列中的最後一個專案時，[Lync Server 控制台] 頁面上方導覽列中的第一個專案便會消失。</span><span class="sxs-lookup"><span data-stu-id="50595-544">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="50595-545">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-545">**Issue:**</span></span>

<span data-ttu-id="50595-546">在下列三個已知案例中，按一下 [Lync Server 控制台] 頁面上方導覽列中的最後一個專案會導致上方導覽列中的第一個專案消失：</span><span class="sxs-lookup"><span data-stu-id="50595-546">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="50595-547">在法文版的頁面「Féderation et accès externe 上，當按一下「D'accès externe PARTENAIRES」時，會消失專案 "Stratégie fédérés XMPP"。</span><span class="sxs-lookup"><span data-stu-id="50595-547">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="50595-548">在德文版本的「用戶端」頁面上，按一下 "Pushbenachrichtigungskonfiguration" 時，專案 "Clientversionskonfiguration" 會消失。</span><span class="sxs-lookup"><span data-stu-id="50595-548">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="50595-549">在 [Конфигурациясети] 頁面上的俄語版本中，當按一下 "на" 時，專案 "Глобально" 便會消失。</span><span class="sxs-lookup"><span data-stu-id="50595-549">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="50595-550">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-550">**Workaround:**</span></span>

<span data-ttu-id="50595-551">若要解決此問題，請在瀏覽器中重新整理 Lync Server 控制台的頁面。</span><span class="sxs-lookup"><span data-stu-id="50595-551">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="50595-552">頁面將會在瀏覽器中載入，並顯示上方導覽列中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="50595-552">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="50595-553">通訊錄</span><span class="sxs-lookup"><span data-stu-id="50595-553">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="50595-554">在 [通訊錄] 中的索引在某些語言中未如預期的方式運作</span><span class="sxs-lookup"><span data-stu-id="50595-554">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="50595-555">本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="50595-555">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="50595-556">如果使用者的屬性包含索引欄位，而該欄位只包含無法索引的字元，則使用者不會出現在通訊錄中的搜尋中。</span><span class="sxs-lookup"><span data-stu-id="50595-556">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="50595-557">下列字元及地區設定無法進行索引：</span><span class="sxs-lookup"><span data-stu-id="50595-557">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="50595-558">小寫的西瑞爾文、希臘字母和亞美尼亞文字元</span><span class="sxs-lookup"><span data-stu-id="50595-558">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="50595-559">大寫字母的重音符號</span><span class="sxs-lookup"><span data-stu-id="50595-559">Upper-case accented characters</span></span>

  - <span data-ttu-id="50595-560">泰文</span><span class="sxs-lookup"><span data-stu-id="50595-560">Thai</span></span>

  - <span data-ttu-id="50595-561">寮文</span><span class="sxs-lookup"><span data-stu-id="50595-561">Lao</span></span>

  - <span data-ttu-id="50595-562">緬甸</span><span class="sxs-lookup"><span data-stu-id="50595-562">Myanmar</span></span>

  - <span data-ttu-id="50595-563">梵文</span><span class="sxs-lookup"><span data-stu-id="50595-563">Devanagari</span></span>

  - <span data-ttu-id="50595-564">衣索比亞文</span><span class="sxs-lookup"><span data-stu-id="50595-564">Ethiopic</span></span>

  - <span data-ttu-id="50595-565">西藏文</span><span class="sxs-lookup"><span data-stu-id="50595-565">Tibetan</span></span>

  - <span data-ttu-id="50595-566">孟加拉文</span><span class="sxs-lookup"><span data-stu-id="50595-566">Bengali</span></span>

  - <span data-ttu-id="50595-567">古吉拉特文</span><span class="sxs-lookup"><span data-stu-id="50595-567">Gujarati</span></span>

  - <span data-ttu-id="50595-568">特拉古文</span><span class="sxs-lookup"><span data-stu-id="50595-568">Telugu</span></span>

  - <span data-ttu-id="50595-569">所有其他印度文腳本</span><span class="sxs-lookup"><span data-stu-id="50595-569">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="50595-570">Lync Web App、Web 排程程式和 Web 元件</span><span class="sxs-lookup"><span data-stu-id="50595-570">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="50595-571">Lync Web 排程器中某些語言的語言回退、Dial-In、加入啟動器、持續聊天室管理，以及 OCTab 可能無法如預期般運作</span><span class="sxs-lookup"><span data-stu-id="50595-571">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="50595-572">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-572">**Issue:**</span></span>

<span data-ttu-id="50595-573">在 Internet Explorer 中的網頁瀏覽器中選取中立地區設定時，請 (例如，沒有進一步規範的語言名稱，例如 "挪威 \[ no \] " ) ，而不是指定語言、腳本及地區設定 (（例如 "挪威，博克瑪律文 (挪威) \[ nb-NO \] "） ) 可能會導致 Lync web 排程器、Dial-In、加入啟動器、持續聊天室管理及 OCTab 的特定語言的非預期顯示行為。</span><span class="sxs-lookup"><span data-stu-id="50595-573">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="50595-574">例如，當選取下列其中一種語言時，使用者可能會看到英文頁面：</span><span class="sxs-lookup"><span data-stu-id="50595-574">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="50595-575">挪威文</span><span class="sxs-lookup"><span data-stu-id="50595-575">Norwegian</span></span>

  - <span data-ttu-id="50595-576">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="50595-576">Portuguese</span></span>

  - <span data-ttu-id="50595-577">塞爾維亞文</span><span class="sxs-lookup"><span data-stu-id="50595-577">Serbian</span></span>

<span data-ttu-id="50595-578">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-578">**Workaround:**</span></span>

<span data-ttu-id="50595-579">如果您想要選取具有中立地區設定的語言，請務必確定您也可以使用特定地區設定來新增語言， (搭配 script 和/或國家/地區代碼) 做為瀏覽器的語言喜好設定清單中的其他語言。</span><span class="sxs-lookup"><span data-stu-id="50595-579">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="50595-580">在某些網頁瀏覽器中使用 Lync Web 排程器、Dial-In、加入啟動器、持續聊天室管理和 OCTab 時，對亞塞拜然和烏茲別克地區設定的支援有限</span><span class="sxs-lookup"><span data-stu-id="50595-580">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="50595-581">本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="50595-581">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="50595-582">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-582">**Issue:**</span></span>

<span data-ttu-id="50595-583">當您使用 Internet Explorer 8 或 Internet Explorer 9，並將瀏覽器語言設定為阿塞 (拉丁) 或烏茲別克 (拉丁) 時，撥號對應程式頁面會以英文或瀏覽器中設定的慣用語言顯示。</span><span class="sxs-lookup"><span data-stu-id="50595-583">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="50595-584">當您使用 Firefox 或 Chrome 瀏覽器，並將瀏覽器語言設定為阿塞 (拉丁) 或烏茲別克 (拉丁) 時，Lync Web App、Lync Web 排程程式和 RGS OCTab 將會以英文或瀏覽器的慣用語言集顯示。</span><span class="sxs-lookup"><span data-stu-id="50595-584">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="50595-585">在 Safari 瀏覽器中，不支援烏茲別克 (拉丁) 地區設定。</span><span class="sxs-lookup"><span data-stu-id="50595-585">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="50595-586">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-586">**Workaround:**</span></span>

<span data-ttu-id="50595-587">這些問題沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="50595-587">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="50595-588">在 Lync Web App 的羅馬尼亞語版本中，「加入會議」清單的下拉式箭頭遺失</span><span class="sxs-lookup"><span data-stu-id="50595-588">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="50595-589">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-589">**Issue:**</span></span>

<span data-ttu-id="50595-590">當使用 Lync Web App 的羅馬尼亞版本的使用者執行下列步驟時，下拉式清單中不會顯示 [ **加入會議** ] 下拉式箭頭：</span><span class="sxs-lookup"><span data-stu-id="50595-590">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="50595-591">在 [**一般**] 索引標籤上，選取 [**在這部電腦**上記錄]。</span><span class="sxs-lookup"><span data-stu-id="50595-591">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="50595-592">選取 [ **電話** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="50595-592">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="50595-593">按一下 [ **加入會議**] 的下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="50595-593">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="50595-594">使用者看不到指出其選項超過預設 **Lync Web App**的箭號，其包括：請勿在羅馬尼亞文中 **加入音訊** (，"Nu se asociaža la componenta 音訊" ) and **New number**" (文中的" Număr nou ") 。</span><span class="sxs-lookup"><span data-stu-id="50595-594">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="50595-595">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-595">**Workaround:**</span></span>

<span data-ttu-id="50595-596">即使此下拉式清單的箭號並未顯示出來，使用者仍可按一下預設值，在清單中選取其他設定。</span><span class="sxs-lookup"><span data-stu-id="50595-596">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="50595-597">使用土耳其文版本的 Lync Web 排程器時，當使用「誰是簡報者」下的「我選擇」選項時，無法儲存會議。</span><span class="sxs-lookup"><span data-stu-id="50595-597">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="50595-598">**問題：**</span><span class="sxs-lookup"><span data-stu-id="50595-598">**Issue:**</span></span>

<span data-ttu-id="50595-599">在土耳其文版本的 Lync Web 排程程式中建立或編輯會議時，不支援 [誰是簡報者] 底下的 [人員我選擇] 選項。</span><span class="sxs-lookup"><span data-stu-id="50595-599">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="50595-600">選取此選項時，無法儲存會議。</span><span class="sxs-lookup"><span data-stu-id="50595-600">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="50595-601">相反地，會出現錯誤訊息，指出無法將一個或多個人員設為簡報者。</span><span class="sxs-lookup"><span data-stu-id="50595-601">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="50595-602">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="50595-602">**Workaround:**</span></span>

<span data-ttu-id="50595-603">若要解決此問題，使用者可以使用「我的公司人員」的預設選項，或任何其他選項，例如「只有召集人」或「所有人（包括公司以外的人員）」）。</span><span class="sxs-lookup"><span data-stu-id="50595-603">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="50595-604">召集人可以在使用者加入會議之後，將其降級或將其提升為正確的角色。</span><span class="sxs-lookup"><span data-stu-id="50595-604">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="50595-605">或者，瞭解其他語言的使用者可以將其瀏覽器中的語言選擇變更為其他43支援的語言，並嘗試使用「人員選擇」選項。</span><span class="sxs-lookup"><span data-stu-id="50595-605">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="50595-606">著作權</span><span class="sxs-lookup"><span data-stu-id="50595-606">Copyright</span></span>

<span data-ttu-id="50595-607">這份檔支援軟體產品的初步發行，該產品可能會在最終發行版本本之前變更，而且是 Microsoft Corporation 的機密和專有資訊。</span><span class="sxs-lookup"><span data-stu-id="50595-607">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="50595-608">它會依照收件者和 Microsoft 之間的保密合約條款披露。</span><span class="sxs-lookup"><span data-stu-id="50595-608">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="50595-609">本檔僅供提供資訊之用，但 Microsoft 對本檔中的任何明示或默示的保證都沒有任何擔保。</span><span class="sxs-lookup"><span data-stu-id="50595-609">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="50595-610">本檔中的資訊（包括 URL 及其他網際網路網站參考）如有變更恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="50595-610">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="50595-611">使用此檔帶來的全部風險，或因使用此檔所產生的結果，都由使用者自行保留。</span><span class="sxs-lookup"><span data-stu-id="50595-611">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="50595-612">除非另有說明，否則本文範例中所描述的公司、組織、產品、功能變數名稱、電子郵件地址、徽標、人員、地點和事件皆為虛構。</span><span class="sxs-lookup"><span data-stu-id="50595-612">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="50595-613">與任何真實的公司、組織、產品、功能變數名稱、電子郵件地址、標誌、人員、地點或事件都沒有任何關聯或應加以推斷。</span><span class="sxs-lookup"><span data-stu-id="50595-613">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="50595-614">遵守所有適用著作權法律為使用者的責任。</span><span class="sxs-lookup"><span data-stu-id="50595-614">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="50595-615">除著作權之下的權利外，未獲 Microsoft Corporation 明確的書面許可，本文件任何部分均不得複製、儲存或引入擷取系統、或以任何形式或藉任何方式 (電子、機械、影印、錄音、或其他) 傳輸，或做為任何用途。</span><span class="sxs-lookup"><span data-stu-id="50595-615">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="50595-p162">Microsoft 對本文件中主題事務可能擁有專利、專利應用程式、商標、著作權或其他智慧財產權。除非在 Microsoft 的任何書面授權合約中已明確載明，否則提供本文件並未賦予貴用戶對這些專利、商標、著作權或其他智慧財產權的任何授權。</span><span class="sxs-lookup"><span data-stu-id="50595-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="50595-618">© 2012 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="50595-618">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="50595-619">著作權所有，並保留一切權利。</span><span class="sxs-lookup"><span data-stu-id="50595-619">All rights reserved.</span></span>

<span data-ttu-id="50595-620">Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 和 SQL Server 是 Microsoft Corporation 在美國及（或）其他國家/地區的注冊商標或商標。</span><span class="sxs-lookup"><span data-stu-id="50595-620">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="50595-621">所有其他商標為其各自擁有者的商標。</span><span class="sxs-lookup"><span data-stu-id="50595-621">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

