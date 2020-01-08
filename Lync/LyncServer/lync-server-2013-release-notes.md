---
title: Lync Server 2013 版本資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a93fabf10355dcc4ba7873921c0aaf35475927c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="005fa-102">Lync Server 2013 的版本資訊</span><span class="sxs-lookup"><span data-stu-id="005fa-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="005fa-103">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="005fa-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="005fa-104">歡迎使用 Lync Server 2013 版本資訊。</span><span class="sxs-lookup"><span data-stu-id="005fa-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="005fa-105">請參閱此檔案，以取得有關 Lync Server 2013 已知問題的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="005fa-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="005fa-106">關於這份檔</span><span class="sxs-lookup"><span data-stu-id="005fa-106">About this document</span></span>

<span data-ttu-id="005fa-107">此檔包含您在部署和使用 Lync Server 2013 之前應該知道的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="005fa-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="005fa-108">如需 Lync Server 2013 的詳細資訊，請參閱[Microsoft Lync server 2013](microsoft-lync-server-2013.md)檔。</span><span class="sxs-lookup"><span data-stu-id="005fa-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="005fa-109">本檔包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="005fa-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="005fa-110">Lync 2013 用戶端</span><span class="sxs-lookup"><span data-stu-id="005fa-110">Lync 2013 client</span></span>

  - <span data-ttu-id="005fa-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="005fa-111">Lync Server</span></span>

  - <span data-ttu-id="005fa-112">安裝</span><span class="sxs-lookup"><span data-stu-id="005fa-112">Installation</span></span>

  - <span data-ttu-id="005fa-113">行動性</span><span class="sxs-lookup"><span data-stu-id="005fa-113">Mobility</span></span>

  - <span data-ttu-id="005fa-114">會議</span><span class="sxs-lookup"><span data-stu-id="005fa-114">Conferencing</span></span>

  - <span data-ttu-id="005fa-115">企業語音</span><span class="sxs-lookup"><span data-stu-id="005fa-115">Enterprise Voice</span></span>

  - <span data-ttu-id="005fa-116">目前狀態</span><span class="sxs-lookup"><span data-stu-id="005fa-116">Presence</span></span>

  - <span data-ttu-id="005fa-117">回應群組應用程式與通話駐留應用程式</span><span class="sxs-lookup"><span data-stu-id="005fa-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="005fa-118">Lync Server 控制台、拓撲產生器及規劃工具</span><span class="sxs-lookup"><span data-stu-id="005fa-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="005fa-119">翻譯</span><span class="sxs-lookup"><span data-stu-id="005fa-119">Localization</span></span>

  - <span data-ttu-id="005fa-120">著作權</span><span class="sxs-lookup"><span data-stu-id="005fa-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="005fa-121">Lync 2013 用戶端</span><span class="sxs-lookup"><span data-stu-id="005fa-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="005fa-122">如果檔案已在另一個應用程式中開啟，則在立即訊息中轉移檔案失敗</span><span class="sxs-lookup"><span data-stu-id="005fa-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="005fa-123">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-123">**Issue:**</span></span>

<span data-ttu-id="005fa-124">如果您嘗試傳送檔案（例如 Word 檔），並將它納入至另一個 Lync 使用者的立即訊息中，則傳輸會顯示為成功，但實際上無法傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="005fa-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="005fa-125">該檔案類型的圖示會顯示在 Lync 用戶端中，但預期的接收器無法開啟該檔案。</span><span class="sxs-lookup"><span data-stu-id="005fa-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="005fa-126">不會顯示任何錯誤訊息，通知您傳輸未成功。</span><span class="sxs-lookup"><span data-stu-id="005fa-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="005fa-127">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-127">**Workaround:**</span></span>

<span data-ttu-id="005fa-128">若要解決此問題，請先關閉開啟的檔案或應用程式，然後再嘗試在立即訊息中傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="005fa-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="005fa-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="005fa-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="005fa-130">如果 Lync Server Storage Services 資料複製失敗，系統管理員將需要檢查陳舊儲存服務佇列專案的效能計數器</span><span class="sxs-lookup"><span data-stu-id="005fa-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="005fa-131">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-131">**Issue:**</span></span>

<span data-ttu-id="005fa-132">Lync Server Storage Service 使用 Windows Fabric 進行複製。</span><span class="sxs-lookup"><span data-stu-id="005fa-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="005fa-133">如果資料是在主前端伺服器上刪除，但在副前端伺服器上的刪除失敗（例如，如果前端伺服器出現意外的關閉或錯誤），則資料可以留下並「孤立」。</span><span class="sxs-lookup"><span data-stu-id="005fa-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="005fa-134">孤立的資料可能會造成效能下降，並浪費磁片磁碟機空間。</span><span class="sxs-lookup"><span data-stu-id="005fa-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="005fa-135">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-135">**Workaround:**</span></span>

<span data-ttu-id="005fa-136">\_若要解決此問題，如果使用\_\_\_中的事件 LYSS DB 空間錯誤（id = 32058），\_且\_已\_使用\_的 LYSS DB 空間（Id = 32059）是在事件記錄檔中產生，系統管理員應該檢查前端伺服器上的效能計數器，其中的**LS： LYSS-storage service API**的名稱為**LYSS-目前數量的 storage services 過時佇列專案**。</span><span class="sxs-lookup"><span data-stu-id="005fa-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="005fa-137">如果這個效能計數器具有高值（例如，大於50000），系統管理員應該在 Lync Server 2013 資源套件中執行 CleanuUpStorageServiceData 工具，這會從池中刪除所有孤立的資料。</span><span class="sxs-lookup"><span data-stu-id="005fa-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="005fa-138">如需有關工具的詳細資訊，請參閱 Lync Server 2013 資源套件檔。</span><span class="sxs-lookup"><span data-stu-id="005fa-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="005fa-139">每當伺服器或池中的 IP 位址設定變更時，必須重新開機 Lync Server 服務</span><span class="sxs-lookup"><span data-stu-id="005fa-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="005fa-140">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-140">**Issue:**</span></span>

<span data-ttu-id="005fa-141">當 Lync Server 2013 部署的 IP 位址設定變更時（例如從 IPv4 改為雙堆疊，或從雙堆疊變更到 Ipv6 時），並不是所有伺服器元件都會在重新開機服務之前，選取設定的變更。</span><span class="sxs-lookup"><span data-stu-id="005fa-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="005fa-142">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-142">**Workaround:**</span></span>

<span data-ttu-id="005fa-143">若要解決此問題，請在變更部署的 IP 位址設定後重新開機 Lync Server services。</span><span class="sxs-lookup"><span data-stu-id="005fa-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="005fa-144">若要這樣做，請在 Lync Server 管理命令介面中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="005fa-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```
    Stop-CsWindowsService -graceful
   ```

   ```
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="005fa-145">Lync Server 2013 管理套件中不再提供電話撥入式會議綜合交易 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="005fa-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="005fa-146">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-146">**Issue:**</span></span>

<span data-ttu-id="005fa-147">Lync Server 2013 管理套件中的電話撥入式會議綜合交易 Cmdlet Cmdlet **CsDialInConferencing**已不再提供。</span><span class="sxs-lookup"><span data-stu-id="005fa-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="005fa-148">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-148">**Workaround:**</span></span>

<span data-ttu-id="005fa-149">使用電話撥入式會議綜合交易 Cmdlet**的 CsDialInConferencing**僅限在企業內部支援。</span><span class="sxs-lookup"><span data-stu-id="005fa-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="005fa-150">系統管理員可能會繼續使用 Lync Server Management Shell 中的 Cmdlet 來進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="005fa-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="005fa-151">如有需要，企業也可以開發私人管理套件來在內部執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="005fa-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="005fa-152">如果在將記錄檔案複製到網路共用時，網路流量會中斷，集中式記錄服務就會停止</span><span class="sxs-lookup"><span data-stu-id="005fa-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="005fa-153">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-153">**Issue:**</span></span>

<span data-ttu-id="005fa-154">當集中式記錄服務設定為使用網路路徑時（CsClsConfiguration Cmdlet 的 CacheFileNetworkFolder 參數值是有效的 UNC 路徑），系統會將**快取的**記錄檔複製到網路共用。</span><span class="sxs-lookup"><span data-stu-id="005fa-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="005fa-155">如果在複製檔案時網路流量中斷，就會發生例外狀況，導致集中式記錄服務停止。</span><span class="sxs-lookup"><span data-stu-id="005fa-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="005fa-156">此服務會設定為自動重新開機多達三次，因此服務將會從前三個例外狀況中復原。</span><span class="sxs-lookup"><span data-stu-id="005fa-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="005fa-157">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-157">**Workaround:**</span></span>

<span data-ttu-id="005fa-158">這個問題目前沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-158">There is no workaround for this issue.</span></span> <span data-ttu-id="005fa-159">若要找出問題，請從 [服務控制管理員] 監視記錄「Lync Server 中央記錄服務代理程式」意外終止的事件 ID 7031 事件記錄。</span><span class="sxs-lookup"><span data-stu-id="005fa-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="005fa-160">如果發生這種情況超過三次，請使用**CsWindowService** Cmdlet 手動重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="005fa-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="005fa-161">必須手動匯入儲存服務佇列專案</span><span class="sxs-lookup"><span data-stu-id="005fa-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="005fa-162">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-162">**Issue:**</span></span>

<span data-ttu-id="005fa-163">Lync Server 2013 儲存關於會議與立即訊息的資料，例如封存的郵件，以及呼叫詳細資料錄製（CDR），在每個前端伺服器上的資料庫上。</span><span class="sxs-lookup"><span data-stu-id="005fa-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="005fa-164">資料會在處理期間儲存在資料庫中，然後才能傳送到預定的目的地。</span><span class="sxs-lookup"><span data-stu-id="005fa-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="005fa-165">若要改善效能，Lync Server 2013 會定期從本機資料庫匯出不是經過長時間處理的佇列專案，並將它們儲存在檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="005fa-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="005fa-166">如果檔案存放區無法使用，這些專案會儲存在每個前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="005fa-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="005fa-167">在池容錯移轉期間，發生相同的操作，以避免資料遺失。</span><span class="sxs-lookup"><span data-stu-id="005fa-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="005fa-168">在匯出作業期間，Lync Server Storage Service 會在事件日誌中記錄每個階段，且事件 Id 為32075（完整刷新作業已開始）、32076（完全清除已完成）、32082（維護層級 flush 開始）、32083（維護層級 flush）已完成），32089（因填滿資料庫而發生清洗）。</span><span class="sxs-lookup"><span data-stu-id="005fa-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="005fa-169">此資料將不會自動匯入到系統，即可處理並傳送到其最終目的地（SQL Server 或 Exchange 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="005fa-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="005fa-170">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-170">**Workaround:**</span></span>

<span data-ttu-id="005fa-171">若要匯入資料至系統，系統管理員必須在 Lync Server 資源套件中使用 ImportStorageServiceData 工具，這會將資料重新加入系統，以進行處理並傳送到最終目的地。</span><span class="sxs-lookup"><span data-stu-id="005fa-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="005fa-172">如果 UseNormalizationRules 的預設值變更為 False，通訊錄網頁查詢搜尋就會失敗</span><span class="sxs-lookup"><span data-stu-id="005fa-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="005fa-173">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-173">**Issue:**</span></span>

<span data-ttu-id="005fa-174">如果 UseNormalizationRules 的預設值變更為 False，通訊錄網頁查詢搜尋將會失敗。</span><span class="sxs-lookup"><span data-stu-id="005fa-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="005fa-175">預設值變更之後，Lync 用戶端使用者將無法使用 Lync 通訊錄網頁查詢來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="005fa-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="005fa-176">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-176">**Workaround:**</span></span>

<span data-ttu-id="005fa-177">如果 UseNormalizationRules 的預設值設為 False，所以使用者可以使用在 Active Directory 網域服務中定義的電話號碼（不含 Lync Server 2013）應用正常化規則，請執行下列動作來解決此問題：</span><span class="sxs-lookup"><span data-stu-id="005fa-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="005fa-178">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="005fa-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="005fa-179">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="005fa-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="005fa-180">如果您的部署只包含 Lync Server 2013 伺服器，請在全域層級執行下列 Cmdlet，將 UseNormalizationRules 和 IgnoreGenericRules 的值變更為 True：</span><span class="sxs-lookup"><span data-stu-id="005fa-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="005fa-181">如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的組合，請執行下列 Cmdlet，並將它指派給拓撲中的每個 Lync Server 2013 池：</span><span class="sxs-lookup"><span data-stu-id="005fa-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="005fa-182">等待 CMS 複製在所有的池中進行。</span><span class="sxs-lookup"><span data-stu-id="005fa-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="005fa-183">針對您的部署修改電話正常化規則檔案，以清除內容。</span><span class="sxs-lookup"><span data-stu-id="005fa-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="005fa-184">檔案位於每個 Lync Server 2013 池的檔案共用位置。</span><span class="sxs-lookup"><span data-stu-id="005fa-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="005fa-185">如果檔案不存在，請建立名為「\_公司電話\_號碼\_正常化\_Rules .txt」的空檔案。</span><span class="sxs-lookup"><span data-stu-id="005fa-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="005fa-186">針對所有前端池，請等候幾分鐘，以讀取新檔案。</span><span class="sxs-lookup"><span data-stu-id="005fa-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="005fa-187">在您部署中的每個 Lync Server 2013 池中，執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="005fa-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="005fa-188">每個 Lync 2013 池每天都會產生通訊錄服務器錯誤事件21054</span><span class="sxs-lookup"><span data-stu-id="005fa-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="005fa-189">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-189">**Issue:**</span></span>

<span data-ttu-id="005fa-190">Lync Server 2013 通訊錄服務器會在執行日常維護時每天產生錯誤事件21054。</span><span class="sxs-lookup"><span data-stu-id="005fa-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="005fa-191">每當系統管理員執行**更新 csAddressBook** Cmdlet 時，也會產生錯誤，即使更新成功也一樣。</span><span class="sxs-lookup"><span data-stu-id="005fa-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="005fa-192">不過，更新成功時，可以安全地忽略此錯誤事件。</span><span class="sxs-lookup"><span data-stu-id="005fa-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="005fa-193">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-193">**Workaround:**</span></span>

<span data-ttu-id="005fa-194">當您遇到此錯誤事件時，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="005fa-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="005fa-195">如果 Cmdlet 報告沒有任何未編制或已放棄的物件，就可以放心地忽略錯誤事件21054。</span><span class="sxs-lookup"><span data-stu-id="005fa-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="005fa-196">此外，系統中心操作管理員應該已關閉 [正確編制索引的主要狀況指示（KHI）] 的 [通訊錄使用者]。</span><span class="sxs-lookup"><span data-stu-id="005fa-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="005fa-197">在 Edge 池中設定 IPv6 時，可能會發生要求失敗</span><span class="sxs-lookup"><span data-stu-id="005fa-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="005fa-198">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-198">**Issue:**</span></span>

<span data-ttu-id="005fa-199">當您在 Edge 池中設定 IPv6 時，對邊緣池的一些要求可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="005fa-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="005fa-200">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-200">**Workaround:**</span></span>

<span data-ttu-id="005fa-201">若要解決此問題，請不要使用 IPv6 設定 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="005fa-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="005fa-202">CsPoolFailback Cmdlet 在 pool 切回期間可能失敗</span><span class="sxs-lookup"><span data-stu-id="005fa-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="005fa-203">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-203">**Issue:**</span></span>

<span data-ttu-id="005fa-204">當您嘗試將池進行容錯回復時， **csPoolFailback** Cmdlet 可能會失敗，並出現錯誤 "無法在重複嘗試之後完成 hydration 程式。」</span><span class="sxs-lookup"><span data-stu-id="005fa-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="005fa-205">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-205">**Workaround:**</span></span>

<span data-ttu-id="005fa-206">若要解決此問題，請再次執行 Cmdlet，然後等到 Cmdlet 成功為止。</span><span class="sxs-lookup"><span data-stu-id="005fa-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="005fa-207">請注意，容錯回復程式可能需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="005fa-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="005fa-208">有20000個使用者的池可能需要長達60分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="005fa-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="005fa-209">當您將前端伺服器新增到已建立的 pool （混合式、商務用 Skype Online）時，可能會發生資料遺失問題</span><span class="sxs-lookup"><span data-stu-id="005fa-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="005fa-210">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-210">**Issue:**</span></span>

<span data-ttu-id="005fa-211">您可能會在擁有多個前端伺服器的環境中遇到這個問題，而且您可以重新開機其中一個前端伺服器，或新增先前不屬於該池的新前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="005fa-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="005fa-212">已封存資料的使用者可能會在資料封存建立到該池之前，遇到資料遺失的問題。</span><span class="sxs-lookup"><span data-stu-id="005fa-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="005fa-213">此期間的潛在資料遺失時間限制為15分鐘，讓人員對人員交談，以及30分鐘的會議。</span><span class="sxs-lookup"><span data-stu-id="005fa-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="005fa-214">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-214">**Workaround:**</span></span>

<span data-ttu-id="005fa-215">如果您執行的是維護，而不是將前端伺服器逐一啟動，您應該將該池容錯移轉到另一個池，然後在伺服器上執行維護任務。</span><span class="sxs-lookup"><span data-stu-id="005fa-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="005fa-216">您也可以在執行維護工作前，讓服務無法使用，然後在維護完成時還原可用性。</span><span class="sxs-lookup"><span data-stu-id="005fa-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="005fa-217">系統管理員無法使用 CsClientAccessLicense Cmdlet 取得受許可人人數</span><span class="sxs-lookup"><span data-stu-id="005fa-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="005fa-218">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-218">**Issue:**</span></span>

<span data-ttu-id="005fa-219">系統管理員無法使用**CsClientAccessLicense** Cmdlet 取得精確的客戶授權使用。</span><span class="sxs-lookup"><span data-stu-id="005fa-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="005fa-220">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-220">**Workaround:**</span></span>

<span data-ttu-id="005fa-221">若要檢查伺服器授權類型，您可以執行**CsService** Cmdlet，以取得所有資料庫的完整功能變數名稱（FDQNs）。</span><span class="sxs-lookup"><span data-stu-id="005fa-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="005fa-222">如果前端伺服器的 FQDN 與後端資料庫的 FQDN 相同，則該授權是標準版授權。</span><span class="sxs-lookup"><span data-stu-id="005fa-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="005fa-223">否則，授權就是企業版授權。</span><span class="sxs-lookup"><span data-stu-id="005fa-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="005fa-224">未準確報告用戶端獲許可人數量</span><span class="sxs-lookup"><span data-stu-id="005fa-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="005fa-225">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-225">**Issue:**</span></span>

<span data-ttu-id="005fa-226">在判斷用戶端授權計數時，您可能會遇到下列情況：</span><span class="sxs-lookup"><span data-stu-id="005fa-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="005fa-227">**行動使用者不准確的授權計數**</span><span class="sxs-lookup"><span data-stu-id="005fa-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="005fa-228">授權計數是以針對裝置的使用者的唯一 IP 位址數量為基礎。</span><span class="sxs-lookup"><span data-stu-id="005fa-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="005fa-229">授權計數會受到下列幾種限制：</span><span class="sxs-lookup"><span data-stu-id="005fa-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="005fa-230">如果使用者的 IP 位址在 Lync 會話期間發生變更，就會 overcounted 授權。</span><span class="sxs-lookup"><span data-stu-id="005fa-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="005fa-231">當使用者從多個位置使用桌面用戶端連線到 Lync Server 時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="005fa-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="005fa-232">如果使用者與行動用戶端連線，則會 undercounted 授權，因為無法判斷裝置的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="005fa-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="005fa-233">**授權的計算數量是將公用交換電話網絡（PSTN）呼叫傳送到 Lync 用戶端、Lync 用戶端呼叫 PSTN 線路，以及將 Lync 來電轉接至 PSTN 線路**</span><span class="sxs-lookup"><span data-stu-id="005fa-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="005fa-234">在下列案例中，將會計算兩個額外的授權，而不是一份，因為電話號碼和 Lync 使用者都會計算在內，以決定所使用的授權數量。</span><span class="sxs-lookup"><span data-stu-id="005fa-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="005fa-235">若要取得精確的授權資料，請手動移除電話號碼所產生的授權。</span><span class="sxs-lookup"><span data-stu-id="005fa-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="005fa-236">Lync 的 PSTN 電話通話</span><span class="sxs-lookup"><span data-stu-id="005fa-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="005fa-237">對 PSTN 線路進行 Lync 通話</span><span class="sxs-lookup"><span data-stu-id="005fa-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="005fa-238">Lync 的 PSTN 呼叫，然後 Lync 會將呼叫轉寄到 PSTN 線路。</span><span class="sxs-lookup"><span data-stu-id="005fa-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="005fa-239">其中一個 PSTN 線路會計算在內。</span><span class="sxs-lookup"><span data-stu-id="005fa-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="005fa-240">**授權不會對已登入的 Lync 手機計數**</span><span class="sxs-lookup"><span data-stu-id="005fa-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="005fa-241">當使用者使用 Lync 認證的手機時，如果電話登入並保持連線，這會保留其登入狀態，但如果在登入電話之後，就會將該電話算作授權。</span><span class="sxs-lookup"><span data-stu-id="005fa-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="005fa-242">**為 PSTN 手機加入會議所計算的授權**</span><span class="sxs-lookup"><span data-stu-id="005fa-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="005fa-243">當使用者使用 PSTN 手機加入會議時，系統會不准確地計算授權加入會議。</span><span class="sxs-lookup"><span data-stu-id="005fa-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="005fa-244">不過，不需要授權，就能使用 PSTN 手機加入會議。</span><span class="sxs-lookup"><span data-stu-id="005fa-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="005fa-245">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-245">**Workaround:**</span></span>

1.  <span data-ttu-id="005fa-246">**行動使用者不准確的授權計數**</span><span class="sxs-lookup"><span data-stu-id="005fa-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="005fa-247">您可以手動識別屬於同一個裝置的 IP 位址，然後在 [授權計數] 中移除其中一個。</span><span class="sxs-lookup"><span data-stu-id="005fa-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="005fa-248">使用 Lync 用戶端連線的行動裝置無法解決此問題。</span><span class="sxs-lookup"><span data-stu-id="005fa-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="005fa-249">**授權是針對 Lync 用戶端、Lync 用戶端呼叫 PSTN 線路，以及轉寄到 PSTN 線路的 PSTN 呼叫進行兩次計數**</span><span class="sxs-lookup"><span data-stu-id="005fa-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="005fa-250">您必須手動識別 PSTN 電話號碼，並移除為其所產生的授權計數。</span><span class="sxs-lookup"><span data-stu-id="005fa-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="005fa-251">**授權不會對已登入的 Lync 手機計數**</span><span class="sxs-lookup"><span data-stu-id="005fa-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="005fa-252">您可以將 Lync phone 設定為 [登出]，然後以定期間隔（例如每3個月）重新登入。</span><span class="sxs-lookup"><span data-stu-id="005fa-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="005fa-253">**為 PSTN 手機加入會議所計算的授權**</span><span class="sxs-lookup"><span data-stu-id="005fa-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="005fa-254">您可以手動識別用來加入會議並移除電話號碼所產生之授權的 PSTN 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="005fa-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="005fa-255">升級至 Silverlight 5 之後，Lync Server 控制台在 VMware 環境中停止運作</span><span class="sxs-lookup"><span data-stu-id="005fa-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="005fa-256">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-256">**Issue:**</span></span>

<span data-ttu-id="005fa-257">如果您在 VMware 環境中使用 Lync Server 控制台，在您將 Microsoft Silverlight 升級到版本5之後，Lync Server 控制台可能會停止運作。</span><span class="sxs-lookup"><span data-stu-id="005fa-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="005fa-258">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-258">**Workaround:**</span></span>

<span data-ttu-id="005fa-259">若要解決此問題，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="005fa-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="005fa-260">卸載 Silverlight 5，然後從[https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)安裝 silverlight 4。</span><span class="sxs-lookup"><span data-stu-id="005fa-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="005fa-261">從非 VMware 虛擬電腦的電腦存取 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="005fa-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="005fa-262">若要這樣做，您可以從伺服器上的 Windows [**開始**] 功能表中啟動 lync Server [控制台] （如果電腦上已安裝 Lync server 管理工具）。</span><span class="sxs-lookup"><span data-stu-id="005fa-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="005fa-263">您也可以使用網頁瀏覽器存取 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="005fa-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="005fa-264">URL 會類似\<HTTPs://前端\_池\_fqdn/cscp.\></span><span class="sxs-lookup"><span data-stu-id="005fa-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="005fa-265">在 Active Directory 中修改使用者的辨識名稱之後，通訊錄服務中的使用者資訊並未更新</span><span class="sxs-lookup"><span data-stu-id="005fa-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="005fa-266">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-266">**Issue:**</span></span>

<span data-ttu-id="005fa-267">如果在 Active Directory 網域服務中，使用者的判別名（也稱為 DN）已變更，任何其他變更將不會在通訊錄服務（ABS）中更新。</span><span class="sxs-lookup"><span data-stu-id="005fa-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="005fa-268">這不會影響使用者的登入或目前狀態，但如果 SIP 位址也有所變更，就會防止使用者進行通訊，因為搜尋會傳回過時的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="005fa-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="005fa-269">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-269">**Workaround:**</span></span>

<span data-ttu-id="005fa-270">若要解決此問題，請不要變更使用者的 DN。</span><span class="sxs-lookup"><span data-stu-id="005fa-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="005fa-271">如果您將使用者的 DN 還原為前一個值，更新將會反映在通訊錄服務中。</span><span class="sxs-lookup"><span data-stu-id="005fa-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="005fa-272">安裝</span><span class="sxs-lookup"><span data-stu-id="005fa-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="005fa-273">在 Lync server 無法啟動的情況中，使用非 ASCII 字元可能會導致</span><span class="sxs-lookup"><span data-stu-id="005fa-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="005fa-274">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-274">**Issue:**</span></span>

<span data-ttu-id="005fa-275">如果目的地資料夾名稱包含非 ASCII 字元（包括 UNICODE、雙位元組字元集（DBCS）、UTF-8 和 UTF-16），安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="005fa-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="005fa-276">此外，安裝程式可能會成功，但如果下列任何一項中包含非 ASCII 字元，則伺服器無法啟動：</span><span class="sxs-lookup"><span data-stu-id="005fa-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="005fa-277">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="005fa-277">Computer name</span></span>

  - <span data-ttu-id="005fa-278">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="005fa-278">Domain name</span></span>

  - <span data-ttu-id="005fa-279">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="005fa-279">User name</span></span>

  - <span data-ttu-id="005fa-280">使用者 SIP URI</span><span class="sxs-lookup"><span data-stu-id="005fa-280">User SIP URI</span></span>

  - <span data-ttu-id="005fa-281">服務帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="005fa-281">Service account name</span></span>

<span data-ttu-id="005fa-282">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-282">**Workaround:**</span></span>

<span data-ttu-id="005fa-283">在目的地資料夾名稱、[電腦名稱稱]、[功能變數名稱]、[使用者名稱]、[使用者 SIP URI] 及服務帳戶名稱中，只能使用 ASCII 字元。</span><span class="sxs-lookup"><span data-stu-id="005fa-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="005fa-284">在安裝 Lync Server 2013 之前，必須先安裝模組呼叫 IIS 7.5 中的 InsertEntityBody 方法時，會發生「堆損毀」的修復程式</span><span class="sxs-lookup"><span data-stu-id="005fa-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="005fa-285">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-285">**Issue:**</span></span>

<span data-ttu-id="005fa-286">在安裝 Lync Server 2013 之前，必須先安裝 Microsoft 知識庫文章264886（[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)）中所述的「堆損7.5 毀」的修復程式，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="005fa-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="005fa-287">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-287">**Workaround:**</span></span>

<span data-ttu-id="005fa-288">從 Microsoft 下載中心下載並安裝修複程式[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)。</span><span class="sxs-lookup"><span data-stu-id="005fa-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="005fa-289">Lync Server 2013 無法在 ITA Windows Server 2012 作業系統 RTM 版本上安裝</span><span class="sxs-lookup"><span data-stu-id="005fa-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="005fa-290">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-290">**Issue:**</span></span>

<span data-ttu-id="005fa-291">由於 Windows Fabric 安裝失敗，所以在 ITA Windows Server 2012 上安裝 Lync Server 2013 失敗。</span><span class="sxs-lookup"><span data-stu-id="005fa-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="005fa-292">Windows Fabric 安裝失敗，因為使用 HH： MM： SS 的時間格式建立結構追蹤。</span><span class="sxs-lookup"><span data-stu-id="005fa-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="005fa-293">不過，在 ITA Windows Server 中，時間格式為 HH。MM.SS。</span><span class="sxs-lookup"><span data-stu-id="005fa-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="005fa-294">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-294">**Workaround:**</span></span>

<span data-ttu-id="005fa-295">若要解決此問題，請在安裝 Lync Server 2013 之前更新系統登錄。</span><span class="sxs-lookup"><span data-stu-id="005fa-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="005fa-296">需要更新的登錄機碼為： HKEY\_使用者。\\預設\\控制台 [\\國際\\sTimeFormat]。</span><span class="sxs-lookup"><span data-stu-id="005fa-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="005fa-297">若要將 sTimeFormat 的值變更為 HH： mm： ss，請使用 Windows PowerShell 命令列介面，如下所示：</span><span class="sxs-lookup"><span data-stu-id="005fa-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="005fa-298">啟動 Windows PowerShell 並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="005fa-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="005fa-299">若要查看目前的值，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="005fa-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="005fa-300">記下 sTimeFormat 的目前值，以便在安裝完成後進行還原。</span><span class="sxs-lookup"><span data-stu-id="005fa-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="005fa-301">若要設定為新值，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="005fa-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="005fa-302">成功安裝 Lync Server 2013 之後，請執行下列 Cmdlet 來還原 sTimeFormat 的原始值：</span><span class="sxs-lookup"><span data-stu-id="005fa-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="005fa-303">在步驟3中，設定 ItemProperty $a 名稱 sTimeFormat-值 "<值。</span><span class="sxs-lookup"><span data-stu-id="005fa-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="005fa-304">上方> "</span><span class="sxs-lookup"><span data-stu-id="005fa-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="005fa-305">行動性</span><span class="sxs-lookup"><span data-stu-id="005fa-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="005fa-306">在伺服器容錯移轉程式期間，行動用戶端的問題</span><span class="sxs-lookup"><span data-stu-id="005fa-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="005fa-307">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-307">**Issue:**</span></span>

<span data-ttu-id="005fa-308">當 Lync 伺服器失敗且容錯移轉進程開始時，下列問題可能會影響行動用戶端使用者：</span><span class="sxs-lookup"><span data-stu-id="005fa-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="005fa-309">在容錯移轉開始之後，沒有最多10分鐘的撥入 Lync 通話或信號。</span><span class="sxs-lookup"><span data-stu-id="005fa-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="005fa-310">無法接受傳入的聊天要求</span><span class="sxs-lookup"><span data-stu-id="005fa-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="005fa-311">如果發生故障的伺服器是使用者的主伺服器，則無法加入會議</span><span class="sxs-lookup"><span data-stu-id="005fa-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="005fa-312">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-312">**Workaround:**</span></span>

<span data-ttu-id="005fa-313">這個問題目前沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-313">There is no workaround for this issue.</span></span> <span data-ttu-id="005fa-314">當容錯移轉程式完成後，就會還原正常的功能。</span><span class="sxs-lookup"><span data-stu-id="005fa-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="005fa-315">如果行動使用者拒絕來自另一個 Lync 端點的來電，該通話會在 Lync 行動用戶端上顯示為未接的轉換</span><span class="sxs-lookup"><span data-stu-id="005fa-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="005fa-316">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-316">**Issue:**</span></span>

<span data-ttu-id="005fa-317">如果行動使用者拒絕來電，而呼叫是從另一個 Lync 端點發出，則該通話會在 Lync 行動用戶端中顯示為未接的交談，而不是在裝置通話清單中的通話。</span><span class="sxs-lookup"><span data-stu-id="005fa-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="005fa-318">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-318">**Workaround:**</span></span>

<span data-ttu-id="005fa-319">這個問題目前沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="005fa-320">在搜尋連絡人時，行動用戶端可能不會顯示同盟連絡人的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="005fa-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="005fa-321">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-321">**Issue:**</span></span>

<span data-ttu-id="005fa-322">在某些情況下（例如在連絡人清單中搜尋同盟連絡人時），同盟連絡人的顯示名稱可能不會顯示。</span><span class="sxs-lookup"><span data-stu-id="005fa-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="005fa-323">在 Lync 行動用戶端沒有連絡人的有效目前狀態訂閱時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="005fa-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="005fa-324">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-324">**Workaround:**</span></span>

<span data-ttu-id="005fa-325">這個問題目前沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="005fa-326">在行動用戶端中，來自會議邀請的未接來電缺少被邀請者和 timestamp 資訊</span><span class="sxs-lookup"><span data-stu-id="005fa-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="005fa-327">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-327">**Issue:**</span></span>

<span data-ttu-id="005fa-328">在行動用戶端中，當未接的交談是會議邀請時，未接的交談訊息中的被邀請者和時間戳記資訊就會消失。</span><span class="sxs-lookup"><span data-stu-id="005fa-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="005fa-329">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-329">**Workaround:**</span></span>

<span data-ttu-id="005fa-330">這個問題目前沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="005fa-331">使用 VoIP 進行呼叫的行動用戶端使用者無法讓語音信箱針對 Exchange 2010 或較舊版本中設定的使用者留下語音信箱</span><span class="sxs-lookup"><span data-stu-id="005fa-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="005fa-332">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-332">**Issue:**</span></span>

<span data-ttu-id="005fa-333">如果行動用戶端使用者使用 VoIP 來進行通話，使用者將無法為已設定為在 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中使用語音信箱的使用者留下語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="005fa-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="005fa-334">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-334">**Workaround:**</span></span>

<span data-ttu-id="005fa-335">若要解決此問題，請將 Exchange 2010 與 SP1 或更新版本的 Microsoft Exchange Server 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="005fa-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="005fa-336">在行動用戶端上使用 Block 與用戶端版本設定的 URL 時，可能會顯示不正確的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="005fa-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="005fa-337">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-337">**Issue:**</span></span>

<span data-ttu-id="005fa-338">在行動用戶端上使用**Block 與**用戶端版本設定的 URL 時，可能會在用戶端版本不受支援時顯示不正確的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="005fa-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="005fa-339">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-339">**Workaround:**</span></span>

<span data-ttu-id="005fa-340">若要解決此問題，請將用戶端版本配置設定為使用**區塊**，而不是使用**URL 區塊**。</span><span class="sxs-lookup"><span data-stu-id="005fa-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="005fa-341">會議</span><span class="sxs-lookup"><span data-stu-id="005fa-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="005fa-342">在 Lync Server 2013 前端伺服器上執行的防毒軟體可能會造成應用程式網域回收，這會暫時中斷 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 用戶端的服務</span><span class="sxs-lookup"><span data-stu-id="005fa-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="005fa-343">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-343">**Issue:**</span></span>

<span data-ttu-id="005fa-344">防毒軟體可以觸發應用程式網域重新開機，這可能會導致 Lync 行動裝置服務2013和整合通訊（UC） Web API 用戶端應用程式（Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013）損失其狀態。</span><span class="sxs-lookup"><span data-stu-id="005fa-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="005fa-345">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-345">**Workaround:**</span></span>

<span data-ttu-id="005fa-346">若要解決此問題，請從防病毒掃描中排除包含網頁元件和 .NET framework 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="005fa-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="005fa-347">如需詳細資訊，請參閱 Microsoft 知識庫文章312592、"PRB： ASP.NET 中的應用程式重新開機時發生隨機應用程式重新開機[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)] 錯誤（位於）。</span><span class="sxs-lookup"><span data-stu-id="005fa-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="005fa-348">下列資料夾應被排除：</span><span class="sxs-lookup"><span data-stu-id="005fa-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="005fa-349">% ProgramFiles%\\Microsoft Lync Server 2013\\網頁元件\\Mcx\\Ext</span><span class="sxs-lookup"><span data-stu-id="005fa-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="005fa-350">% ProgramFiles%\\Microsoft Lync Server 2013\\網頁元件\\Mcx\\Int</span><span class="sxs-lookup"><span data-stu-id="005fa-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="005fa-351">% ProgramFiles%\\Microsoft Lync Server 2013\\網頁元件\\Ucwa\\Int</span><span class="sxs-lookup"><span data-stu-id="005fa-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="005fa-352">% ProgramFiles%\\Microsoft Lync Server 2013\\網頁元件\\Ucwa\\Ext</span><span class="sxs-lookup"><span data-stu-id="005fa-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="005fa-353">% Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\Config</span><span class="sxs-lookup"><span data-stu-id="005fa-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="005fa-354">必須啟用 Windows Internet Explorer 中的 ActiveX 控制項或原生 XMLHTTP 支援，才能成功加入會議</span><span class="sxs-lookup"><span data-stu-id="005fa-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="005fa-355">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-355">**Issue:**</span></span>

<span data-ttu-id="005fa-356">如果使用者已停用 Windows Internet Explorer Internet 瀏覽器設定中的 ActiveX 控制項和原生 XMLHTTP 支援，且選取 [Internet Explorer] 做為預設瀏覽器，使用者將無法加入會議。</span><span class="sxs-lookup"><span data-stu-id="005fa-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="005fa-357">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-357">**Workaround:**</span></span>

<span data-ttu-id="005fa-358">啟用 Internet Explorer 中的 ActiveX 控制項或「原生 XMLHTTP 支援」。</span><span class="sxs-lookup"><span data-stu-id="005fa-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="005fa-359">Lync Server Web 會議服務無法從緊急模式復原</span><span class="sxs-lookup"><span data-stu-id="005fa-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="005fa-360">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-360">**Issue:**</span></span>

<span data-ttu-id="005fa-361">如果已開啟 [關鍵模式] 進行封存，則在系統失敗時，系統會啟動重要模式，且會議將不再適用于參與者。</span><span class="sxs-lookup"><span data-stu-id="005fa-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="005fa-362">在管理員修正系統失敗（例如修正資料庫問題）之後，資料會議服務不會自動復原，而且管理員必須手動重新開機會議服務才能繼續進行會議。</span><span class="sxs-lookup"><span data-stu-id="005fa-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="005fa-363">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-363">**Workaround:**</span></span>

<span data-ttu-id="005fa-364">系統管理員必須在系統失敗修正之後，手動重新開機會議服務。</span><span class="sxs-lookup"><span data-stu-id="005fa-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="005fa-365">網路會議服務會忽略外部 Office Web App 伺服器的 HTTP proxy</span><span class="sxs-lookup"><span data-stu-id="005fa-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="005fa-366">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-366">**Issue:**</span></span>

<span data-ttu-id="005fa-367">如果您已在網際網路、周邊網路和網路會議服務中部署網路會議服務外部的 Office Web Apps 伺服器（也就是不在內部公司網路中的伺服器），請使用 HTTP proxy 連線至這項，Office Web Apps Server 探索將會失敗。</span><span class="sxs-lookup"><span data-stu-id="005fa-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="005fa-368">網路會議服務會忽略 HTTP proxy 設定，如在 [Office Web Apps 伺服器設定] 的 [拓撲建立器] 中定義。</span><span class="sxs-lookup"><span data-stu-id="005fa-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="005fa-369">因此，Lync 用戶端將無法與會議中的其他參與者共用 Microsoft PowerPoint 2010。</span><span class="sxs-lookup"><span data-stu-id="005fa-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="005fa-370">如果您是在內部部署安裝 Lync Server，而且也在內部網路中設定 Office Web Apps Server 內部部署，則不需要使用 proxy 配置。</span><span class="sxs-lookup"><span data-stu-id="005fa-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="005fa-371">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-371">**Workaround:**</span></span>

<span data-ttu-id="005fa-372">唯一的因應措施是不需要使用 HTTP proxy 來與外部 Office Web Apps 伺服器通訊的部署設定。</span><span class="sxs-lookup"><span data-stu-id="005fa-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="005fa-373">不支援在音訊會議提供者會議中新增影片</span><span class="sxs-lookup"><span data-stu-id="005fa-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="005fa-374">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-374">**Issue:**</span></span>

<span data-ttu-id="005fa-375">如果使用者已加入音訊會議提供者會議，則不支援新增影片。</span><span class="sxs-lookup"><span data-stu-id="005fa-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="005fa-376">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-376">**Workaround:**</span></span>

<span data-ttu-id="005fa-377">這個問題目前沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="005fa-378">啟用 IPv6 的拓撲會強制 Lync Web App Silverlight 外掛程式自動更新，以確保螢幕共用功能可從 Lync Web App 運作</span><span class="sxs-lookup"><span data-stu-id="005fa-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="005fa-379">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-379">**Issue:**</span></span>

<span data-ttu-id="005fa-380">當拓撲已設定為啟用 IPv6 時，如果已安裝舊版的螢幕共用外掛程式，使用者就無法從 Lync Web App 用戶端共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="005fa-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="005fa-381">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-381">**Workaround:**</span></span>

<span data-ttu-id="005fa-382">若要在透過 Lync Web App 加入會議時，強制更新最新版本的螢幕共用外掛程式，請在下列兩個檔案中，將**MinSupportedBuildVersion**的值從 "4.0.7457.0" 修改為 "4.0.7577.380"：</span><span class="sxs-lookup"><span data-stu-id="005fa-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="005fa-383">% ProgramFiles%\\Microsoft Lync Server 15\\網頁元件\\是\\Int\\個\\客戶\\端外掛程式 ReachAppShPluginProperties .xml</span><span class="sxs-lookup"><span data-stu-id="005fa-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="005fa-384">% ProgramFiles%\\Microsoft Lync Server 15\\網頁元件\\無法\\延伸\\至\\Ext\\用戶端外掛程式 ReachAppShPluginProperties .xml</span><span class="sxs-lookup"><span data-stu-id="005fa-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="005fa-385">企業語音</span><span class="sxs-lookup"><span data-stu-id="005fa-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="005fa-386">在某些情況下，在設定為使用 IPv4 和 IPv6 雙堆疊的電腦上執行的 Lync 用戶端，可能不支援依賴電腦的 IP 子網（例如 E911、媒體旁路、通話許可控制和位置式路由）的功能。</span><span class="sxs-lookup"><span data-stu-id="005fa-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="005fa-387">本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。</span><span class="sxs-lookup"><span data-stu-id="005fa-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="005fa-388">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-388">**Issue:**</span></span>

<span data-ttu-id="005fa-389">當 Lync 用戶端在啟用 IPv4 與 IPv6 雙堆疊的電腦上執行時，且根據 proxy 伺服器的 DNS 解析，用戶端可以使用電腦的 IPv6 位址登入。</span><span class="sxs-lookup"><span data-stu-id="005fa-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="005fa-390">如此一來，Lync 用戶端將只支援 IPv6 支援的功能，不包括 E911、媒體旁路、通話許可控制和位置路由。</span><span class="sxs-lookup"><span data-stu-id="005fa-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="005fa-391">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-391">**Workaround:**</span></span>

<span data-ttu-id="005fa-392">若要解決此問題，請在用戶端電腦上停用 IPv6 支援。</span><span class="sxs-lookup"><span data-stu-id="005fa-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="005fa-393">如果沒有為使用者設定企業語音，使用者將需要使用 E164 格式從會議撥出</span><span class="sxs-lookup"><span data-stu-id="005fa-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="005fa-394">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-394">**Issue:**</span></span>

<span data-ttu-id="005fa-395">如果沒有為使用者設定企業語音，該使用者將需要使用 E164 格式，才能從會議成功撥號。</span><span class="sxs-lookup"><span data-stu-id="005fa-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="005fa-396">如果未使用 E164 格式，則使用者將無法從會議撥出。</span><span class="sxs-lookup"><span data-stu-id="005fa-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="005fa-397">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-397">**Workaround:**</span></span>

<span data-ttu-id="005fa-398">若要解決這個問題，沒有啟用企業語音的使用者應該使用 E164 格式的號碼來撥打電話給會議。</span><span class="sxs-lookup"><span data-stu-id="005fa-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="005fa-399">目前狀態</span><span class="sxs-lookup"><span data-stu-id="005fa-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="005fa-400">如果使用者已選取 [封鎖所有邀請與通訊]，而整合連絡人存放區已開啟給使用者，目前狀態不會遭到拒絕</span><span class="sxs-lookup"><span data-stu-id="005fa-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="005fa-401">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-401">**Issue:**</span></span>

<span data-ttu-id="005fa-402">如果使用者已選取 [封鎖所有邀請與通訊]，而整合連絡人存放區已開啟給使用者，目前狀態不會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="005fa-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="005fa-403">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-403">**Workaround:**</span></span>

<span data-ttu-id="005fa-404">若要解決此問題，您可以關閉使用者的整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="005fa-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="005fa-405">若要這樣做，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="005fa-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="005fa-406">例如：</span><span class="sxs-lookup"><span data-stu-id="005fa-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="005fa-407">Office 通訊伺服器 2007 R2 使用者駐留內部部署無法在混合式部署中查看商務用 Skype Online 使用者的目前狀態（混合式部署）</span><span class="sxs-lookup"><span data-stu-id="005fa-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="005fa-408">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-408">**Issue:**</span></span>

<span data-ttu-id="005fa-409">當您使用 Lync Server 2013 控制器時，混合式部署中可能會發生這個問題。</span><span class="sxs-lookup"><span data-stu-id="005fa-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="005fa-410">[託管至商務用 Skype Online] 使用者的目前狀態顯示為內部部署使用者的目前狀態為未知。</span><span class="sxs-lookup"><span data-stu-id="005fa-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="005fa-411">此外，駐留在商務用 Skype Online 的使用者無法查看 Office 通訊伺服器 R2 內部部署使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="005fa-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="005fa-412">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-412">**Workaround:**</span></span>

<span data-ttu-id="005fa-413">若要解決此問題，請將商務用 Skype Online 使用者的主伺服器（msrtcsip-presencehomeserver）變更為指向 Lync Server 2013 內部部署池，而不是 Lync Server 2013 控制器。</span><span class="sxs-lookup"><span data-stu-id="005fa-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="005fa-414">您可以在內部部署前端伺服器上修改此設定。</span><span class="sxs-lookup"><span data-stu-id="005fa-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="005fa-415">此因應措施會將駐留到 Office 通訊伺服器 2007 R2 的使用者目前狀態正確顯示在商務用 Skype Online 使用者。</span><span class="sxs-lookup"><span data-stu-id="005fa-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="005fa-416">回應群組應用程式、通話駐留應用程式，以及群組通話提貨</span><span class="sxs-lookup"><span data-stu-id="005fa-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="005fa-417">在使用檢索方建立通話期間，來電者可能會聽到一秒的音樂暫停狀態</span><span class="sxs-lookup"><span data-stu-id="005fa-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="005fa-418">本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。</span><span class="sxs-lookup"><span data-stu-id="005fa-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="005fa-419">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-419">**Issue:**</span></span>

<span data-ttu-id="005fa-420">透過群組呼叫分揀來檢索通話時，呼叫者在與交叉檢索方進行通話期間，可能會聽到一秒的音樂暫停狀態。</span><span class="sxs-lookup"><span data-stu-id="005fa-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="005fa-421">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-421">**Workaround:**</span></span>

<span data-ttu-id="005fa-422">這個問題目前沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="005fa-423">回應群組代理程式可以透過 Lync Server 2010 代理程式主控台登入並登出至 Lync Server 2010 正式代理群組</span><span class="sxs-lookup"><span data-stu-id="005fa-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="005fa-424">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-424">**Issue:**</span></span>

<span data-ttu-id="005fa-425">Lync Server 2013 回應群組代理程式可以透過 Lync server 2010 代理程式主控台登入，並將其登出至 Lync Server 2010 正式代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="005fa-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="005fa-426">在 Lync Server 2010 代理程式主控台中，使用者只能看到其所屬的 Lync Server 2010 回應群組。</span><span class="sxs-lookup"><span data-stu-id="005fa-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="005fa-427">他們看不到他們所屬的任何 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="005fa-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="005fa-428">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-428">**Workaround:**</span></span>

<span data-ttu-id="005fa-429">如果回應群組代理是 Lync Server 2013 的使用者，而且是 Lync Server 2013 正式代理群組的一部分，使用者必須透過瀏覽器中的網頁連結直接存取 Lync Server 2013 代理程式主控台，才能從 Lync Server 2013 代理程式群組登入和登出。</span><span class="sxs-lookup"><span data-stu-id="005fa-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="005fa-430">Lync server 2010 回應群組代理程式無法代表 Lync Server 2013 回應群組撥打來電</span><span class="sxs-lookup"><span data-stu-id="005fa-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="005fa-431">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-431">**Issue:**</span></span>

<span data-ttu-id="005fa-432">Lync server 2013 回應群組代理的 Lync Server 2010 使用者無法代表回應群組撥打電話給您。</span><span class="sxs-lookup"><span data-stu-id="005fa-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="005fa-433">Lync Server 2013 回應群組將無法在 Lync 用戶端中使用，以進行通話。</span><span class="sxs-lookup"><span data-stu-id="005fa-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="005fa-434">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-434">**Workaround:**</span></span>

<span data-ttu-id="005fa-435">若要解決此問題，您必須將 Lync Server 2010 使用者移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="005fa-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="005fa-436">在將回應群組遷移至 Lync Server 2013 之後，將其從 Lync Server 2010 移除之後，將會導致回應群組無法接受任何來電</span><span class="sxs-lookup"><span data-stu-id="005fa-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="005fa-437">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-437">**Issue:**</span></span>

<span data-ttu-id="005fa-438">如果從 lync server 2010 遷移到 Lync server 2013 的回應群組已從 lync server 2010 透過 Lync server [控制台] 或 [Lync Server 管理命令介面] 移除，則 Lync Server 2013 中的 [回應] 群組將停止接收任何來電。</span><span class="sxs-lookup"><span data-stu-id="005fa-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="005fa-439">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-439">**Workaround:**</span></span>

<span data-ttu-id="005fa-440">若要解決此問題，請不要從 lync server 2010 （已從 Lync Server 2010 遷移到 Lync Server 2013）移除任何回應群組。</span><span class="sxs-lookup"><span data-stu-id="005fa-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="005fa-441">如果回應群組已移除，您應該在 Lync Server 2013 中重新部署。</span><span class="sxs-lookup"><span data-stu-id="005fa-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="005fa-442">當新的受管理工作流程在建立時設定為非使用中時，工作流程部署將會失敗</span><span class="sxs-lookup"><span data-stu-id="005fa-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="005fa-443">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-443">**Issue:**</span></span>

<span data-ttu-id="005fa-444">當新的受管理工作流程在建立時設定為非使用中時，工作流程部署將會失敗。</span><span class="sxs-lookup"><span data-stu-id="005fa-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="005fa-445">此問題是在建立工作流程時將它設為 [非使用中] 時，但不會影響已編輯為在部署後將其設為非使用中的工作流程。</span><span class="sxs-lookup"><span data-stu-id="005fa-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="005fa-446">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-446">**Workaround:**</span></span>

<span data-ttu-id="005fa-447">建立及部署工作流程時，請將工作流程設定為 [作用中]，然後進行部署。</span><span class="sxs-lookup"><span data-stu-id="005fa-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="005fa-448">成功部署工作流程之後，即可編輯工作流程並將其設為非使用中。</span><span class="sxs-lookup"><span data-stu-id="005fa-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="005fa-449">從擁有者池中移除回應群組，將會在回應群組已匯入到備份池中時，防止在容錯移轉期間，備份池的回應群組接受任何來電。</span><span class="sxs-lookup"><span data-stu-id="005fa-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="005fa-450">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-450">**Issue:**</span></span>

<span data-ttu-id="005fa-451">如果主要池所擁有的回應群組已匯入到備份池中，且未覆蓋擁有者，且已從擁有者池中移除回應群組，則在容錯移轉期間，備份池中的回應群組將不會接受任何來電。</span><span class="sxs-lookup"><span data-stu-id="005fa-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="005fa-452">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-452">**Workaround:**</span></span>

<span data-ttu-id="005fa-453">您將需要在主要池中重新部署回應群組。</span><span class="sxs-lookup"><span data-stu-id="005fa-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="005fa-454">接著，您必須從主要的池中匯出回應群組設定，然後再次將它匯入到備份池中。</span><span class="sxs-lookup"><span data-stu-id="005fa-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="005fa-455">您也可以在備份池中重新建立回應群組。</span><span class="sxs-lookup"><span data-stu-id="005fa-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="005fa-456">在這種情況下，備份池會是回應群組的擁有者池。</span><span class="sxs-lookup"><span data-stu-id="005fa-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="005fa-457">如果是代表回應群組完成檢索要求，則無法從通話駐留應用程式中檢索寄存通話</span><span class="sxs-lookup"><span data-stu-id="005fa-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="005fa-458">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-458">**Issue:**</span></span>

<span data-ttu-id="005fa-459">當下列條件成立時，寄存式呼叫的檢索要求將會失敗：</span><span class="sxs-lookup"><span data-stu-id="005fa-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="005fa-460">代理程式是匿名回應群組的一部分</span><span class="sxs-lookup"><span data-stu-id="005fa-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="005fa-461">代理程式嘗試透過匿名回應群組從通話駐留應用程式中檢索暫停的呼叫</span><span class="sxs-lookup"><span data-stu-id="005fa-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="005fa-462">工程師會嘗試透過 [代表撥號] 選項或在 Lync 助理用戶端中的相同選項撥打軌道編號來取回通話。</span><span class="sxs-lookup"><span data-stu-id="005fa-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="005fa-463">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-463">**Workaround:**</span></span>

<span data-ttu-id="005fa-464">這個問題沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="005fa-465">停用通話應該在未代表回應群組的情況下進行檢索。</span><span class="sxs-lookup"><span data-stu-id="005fa-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="005fa-466">Lync Server 控制台、拓撲產生器及規劃工具</span><span class="sxs-lookup"><span data-stu-id="005fa-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="005fa-467">規劃工具限制</span><span class="sxs-lookup"><span data-stu-id="005fa-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="005fa-468">本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。</span><span class="sxs-lookup"><span data-stu-id="005fa-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="005fa-469">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-469">**Issue:**</span></span>

<span data-ttu-id="005fa-470">規劃工具在規劃部署時有下列限制：</span><span class="sxs-lookup"><span data-stu-id="005fa-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="005fa-471">最多可支援10個中央網站</span><span class="sxs-lookup"><span data-stu-id="005fa-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="005fa-472">每個中央網站最多可以有14個分支網站</span><span class="sxs-lookup"><span data-stu-id="005fa-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="005fa-473">每個中央網站最多可有240000個使用者</span><span class="sxs-lookup"><span data-stu-id="005fa-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="005fa-474">此外，在計算建議的拓朴時，規劃工具不會包含下列值：</span><span class="sxs-lookup"><span data-stu-id="005fa-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="005fa-475">線上駐留的使用者數目</span><span class="sxs-lookup"><span data-stu-id="005fa-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="005fa-476">已啟用 XMPP 同盟的使用者百分比</span><span class="sxs-lookup"><span data-stu-id="005fa-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="005fa-477">使用 Lync Web App 之使用者的百分比</span><span class="sxs-lookup"><span data-stu-id="005fa-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="005fa-478">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-478">**Workaround:**</span></span>

<span data-ttu-id="005fa-479">這些問題目前沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-479">There is no workaround for these issues.</span></span> <span data-ttu-id="005fa-480">如需規劃工具的詳細資訊，請參閱[使用規劃工具設計 Lync Server 2013 的拓撲](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="005fa-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="005fa-481">在更新選項時，規劃工具可能不會針對 Edge 網路使用先前定義的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="005fa-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="005fa-482">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-482">**Issue:**</span></span>

<span data-ttu-id="005fa-483">使用規劃工具完成設計後，如果您變更 Edge 網路選項，可能會新增額外的 IP 位址，而不是更新現有的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="005fa-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="005fa-484">這可能會在您查看 Edge 網狀圖表的詳細資料時，請選取 [**按一下這裡以更新您的選項**]，然後在 [設定選項] 對話方塊中選取 [邊緣網路] 選取**我想要使用相同的 fqdn 和 IP 位址，但在我的 edge 伺服器上則邊緣服務的埠不同**。</span><span class="sxs-lookup"><span data-stu-id="005fa-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="005fa-485">如果套用任何變更，可能會導致新的 IP 位址與邊緣伺服器新增到設計中。</span><span class="sxs-lookup"><span data-stu-id="005fa-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="005fa-486">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-486">**Workaround:**</span></span>

<span data-ttu-id="005fa-487">目前沒有此問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="005fa-488">在 Lync Server 控制台中，"將所有使用者移至資源庫" 可能無法如期運作</span><span class="sxs-lookup"><span data-stu-id="005fa-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="005fa-489">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-489">**Issue:**</span></span>

<span data-ttu-id="005fa-490">當您使用 Lync Server [控制台] 將所有使用者從一個池移至複雜的 Active Directory 環境中的另一個池（例如有多個網網域控制站和父/子網域），可能會傳回錯誤訊息，指出「指定的使用者不是舊版使用者，請改用 Move-csuser Cmdlet」。</span><span class="sxs-lookup"><span data-stu-id="005fa-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="005fa-491">這是在複雜的 Active Directory 環境中複製時間較長的結果。</span><span class="sxs-lookup"><span data-stu-id="005fa-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="005fa-492">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-492">**Workaround:**</span></span>

<span data-ttu-id="005fa-493">若要解決此問題，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="005fa-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="005fa-494">在 Lync Server [控制台] 中使用篩選來搜尋舊版使用者，選取這些使用者，然後使用 [**將選取的使用者移至池中] 命令**，而不是 [**將所有使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="005fa-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="005fa-495">使用 Lync server 管理命令介面，透過 Lync Server Cmdlet，以批次方式移動舊版使用者。</span><span class="sxs-lookup"><span data-stu-id="005fa-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="005fa-496">在將 Microsoft Silverlight 瀏覽器外掛程式更新為版本5之後，Lync Server 控制台在 VMware 環境中停止運作</span><span class="sxs-lookup"><span data-stu-id="005fa-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="005fa-497">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-497">**Issue:**</span></span>

<span data-ttu-id="005fa-498">如果您在 VMware 環境中使用 Lync Server 控制台，在您將 Silverlight 升級到版本5之後，Lync Server 的 [控制台] 可能會停止運作。</span><span class="sxs-lookup"><span data-stu-id="005fa-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="005fa-499">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-499">**Workaround:**</span></span>

<span data-ttu-id="005fa-500">若要解決此問題，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="005fa-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="005fa-501">卸載 Silverlight 5，然後從[https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)安裝 silverlight 4。</span><span class="sxs-lookup"><span data-stu-id="005fa-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="005fa-502">從不是 VMware 虛擬電腦的電腦開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="005fa-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="005fa-503">若要從遠端電腦開啟 Lync Server 控制台，請在電腦上安裝 Lync Server 管理工具，然後從 Windows [**開始**] 功能表啟動 [Lync server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="005fa-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="005fa-504">您也可以透過在網頁瀏覽器中輸入 URL 來開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="005fa-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="005fa-505">URL 會類似\<HTTPs://前端\_池\_fqdn/cscp.\></span><span class="sxs-lookup"><span data-stu-id="005fa-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="005fa-506">在拓撲建立器中移除鏡像資料庫之後，系統管理員無法執行 csMirrorDB Cmdlet</span><span class="sxs-lookup"><span data-stu-id="005fa-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="005fa-507">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-507">**Issue:**</span></span>

<span data-ttu-id="005fa-508">當管理員在拓撲結構建立器中停用鏡像資料庫，然後在 [拓撲建立器] 中刪除鏡像資料庫時，系統會在 [待辦事項] 清單中顯示一則訊息，以執行**csMirrorDatabase** Cmdlet，以從 SQL Server 中移除鏡像。</span><span class="sxs-lookup"><span data-stu-id="005fa-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="005fa-509">當系統管理員嘗試執行 Cmdlet 時失敗。</span><span class="sxs-lookup"><span data-stu-id="005fa-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="005fa-510">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-510">**Workaround:**</span></span>

<span data-ttu-id="005fa-511">若要在拓撲建立器中移除某個池的 SQL 鏡像，您必須先使用 Cmdlet，才能在 SQL Server 中移除該鏡像。</span><span class="sxs-lookup"><span data-stu-id="005fa-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="005fa-512">然後，您就可以使用 [拓撲建立器] 從拓撲中移除鏡像。</span><span class="sxs-lookup"><span data-stu-id="005fa-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="005fa-513">若要在 SQL Server 中移除鏡像，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="005fa-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="005fa-514">例如，若要移除鏡像並刪除使用者資料庫的資料庫，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="005fa-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="005fa-515">*DropExistingDatabasesOnMirror*參數會使受影響的資料庫從鏡像中刪除。</span><span class="sxs-lookup"><span data-stu-id="005fa-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="005fa-516">接著，若要從拓撲中移除鏡像，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="005fa-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="005fa-517">在拓撲建立器中，以滑鼠右鍵按一下該池，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="005fa-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="005fa-518">清除 [**啟用 SQL Store 鏡像**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="005fa-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="005fa-519">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="005fa-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="005fa-520">每當您對後端資料庫鏡像關聯進行變更時，您必須重新開機池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="005fa-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="005fa-521">當系統管理員嘗試移除具有關聯見證存放區之前端池的部署時，會在拓撲產生器中傳回驗證錯誤</span><span class="sxs-lookup"><span data-stu-id="005fa-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="005fa-522">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-522">**Issue:**</span></span>

<span data-ttu-id="005fa-523">如果系統管理員嘗試使用拓撲建立器中的 [**移除部署**] 命令來移除包含含關聯見證存儲區之 [前端] 池的部署，拓撲建立器中會顯示驗證錯誤，且不會繼續執行此動作。</span><span class="sxs-lookup"><span data-stu-id="005fa-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="005fa-524">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-524">**Workaround:**</span></span>

<span data-ttu-id="005fa-525">若要解決此問題，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="005fa-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="005fa-526">在嘗試移除部署之前，請先移除見證儲存區。</span><span class="sxs-lookup"><span data-stu-id="005fa-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="005fa-527">為前端池新增見證存儲區，然後將它移除。</span><span class="sxs-lookup"><span data-stu-id="005fa-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="005fa-528">在規劃工具與拓撲建立器之間，持久聊天伺服器部署資訊不一致</span><span class="sxs-lookup"><span data-stu-id="005fa-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="005fa-529">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-529">**Issue:**</span></span>

<span data-ttu-id="005fa-530">當 Lync Server 2013、計畫工具在啟用災害復原的情況下，輸出持續聊天伺服器部署的網站拓撲圖時，網站拓撲圖會包含多個（物理）網站，每個網站都有均勻指派的永久聊天伺服器網站地圖.</span><span class="sxs-lookup"><span data-stu-id="005fa-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="005fa-531">在 [拓撲結構建立器] 中，所有持久的聊天伺服器都是由屬於單一（邏輯）網站，且列在相同的永久聊天伺服器池節點底下。</span><span class="sxs-lookup"><span data-stu-id="005fa-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="005fa-532">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-532">**Workaround:**</span></span>

<span data-ttu-id="005fa-533">我們目前沒有此問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="005fa-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="005fa-534">使用者應該分析持續聊天伺服器部署的規劃工具輸出，並修改方案以滿足其特定需求。</span><span class="sxs-lookup"><span data-stu-id="005fa-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="005fa-535">翻譯</span><span class="sxs-lookup"><span data-stu-id="005fa-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="005fa-536">監視</span><span class="sxs-lookup"><span data-stu-id="005fa-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="005fa-537">使用東亞版 Lync Server 時，[部署監視報告] 嚮導會在某些情況下顯示不正確的字元</span><span class="sxs-lookup"><span data-stu-id="005fa-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="005fa-538">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-538">**Issue:**</span></span>

<span data-ttu-id="005fa-539">使用東亞版的 Lync Server 2013 （例如，中文（簡體）、中文（繁體）、日文或韓語），在系統區域設定未設為東亞語言的作業系統上，[部署監視報告] 嚮導將會顯示問號或其他字元，而不是當地語系化的郵件。</span><span class="sxs-lookup"><span data-stu-id="005fa-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="005fa-540">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-540">**Workaround:**</span></span>

<span data-ttu-id="005fa-541">若要修正此問題，請將作業系統和 Lync Server 2013 的地區設定設為相同的語言，這樣就會正確顯示所有訊息。</span><span class="sxs-lookup"><span data-stu-id="005fa-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="005fa-542">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="005fa-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="005fa-543">在某些情況下，當您按一下上方導覽列中的最後一個專案時，Lync Server [控制台] 頁面頂端流覽列中的第一個專案就會消失</span><span class="sxs-lookup"><span data-stu-id="005fa-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="005fa-544">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-544">**Issue:**</span></span>

<span data-ttu-id="005fa-545">在下列情況中，有三個已知案例，按一下 Lync Server [控制台] 頁面上方流覽列中的最後一個專案，就會使上方流覽列中的第一個專案消失：</span><span class="sxs-lookup"><span data-stu-id="005fa-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="005fa-546">在法文版中，在頁面「Féderation et accès externe 中，「專案」 Stratégie d'accès externe」會在按一下 [Partenaires fédérés XMPP] 時消失。</span><span class="sxs-lookup"><span data-stu-id="005fa-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="005fa-547">在德文版本的 [用戶端] 頁面上，按一下 [Pushbenachrichtigungskonfiguration] 時，專案 "Clientversionskonfiguration" 會消失。</span><span class="sxs-lookup"><span data-stu-id="005fa-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="005fa-548">在俄語版本的 [Конфигурациясети] 頁面上，按一下 [Маршрутрегиона] 時，專案「Глобально」就會消失。</span><span class="sxs-lookup"><span data-stu-id="005fa-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="005fa-549">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-549">**Workaround:**</span></span>

<span data-ttu-id="005fa-550">若要解決此問題，請重新整理瀏覽器中 Lync Server [控制台] 的頁面。</span><span class="sxs-lookup"><span data-stu-id="005fa-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="005fa-551">隨即會在瀏覽器中載入頁面，並顯示上方導覽列中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="005fa-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="005fa-552">通訊錄</span><span class="sxs-lookup"><span data-stu-id="005fa-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="005fa-553">在通訊錄中編制索引時，在某些語言中無法如期運作</span><span class="sxs-lookup"><span data-stu-id="005fa-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="005fa-554">本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。</span><span class="sxs-lookup"><span data-stu-id="005fa-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="005fa-555">如果使用者的屬性包含索引欄位，而該欄位只包含無法編制索引的字元，則使用者不會出現在通訊錄中執行的搜尋中。</span><span class="sxs-lookup"><span data-stu-id="005fa-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="005fa-556">下列字元和地區設定無法編制索引：</span><span class="sxs-lookup"><span data-stu-id="005fa-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="005fa-557">小寫字母、希臘文及亞美尼亞文字元</span><span class="sxs-lookup"><span data-stu-id="005fa-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="005fa-558">大小寫符號的大寫字元</span><span class="sxs-lookup"><span data-stu-id="005fa-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="005fa-559">泰語</span><span class="sxs-lookup"><span data-stu-id="005fa-559">Thai</span></span>

  - <span data-ttu-id="005fa-560">寮國</span><span class="sxs-lookup"><span data-stu-id="005fa-560">Lao</span></span>

  - <span data-ttu-id="005fa-561">緬甸</span><span class="sxs-lookup"><span data-stu-id="005fa-561">Myanmar</span></span>

  - <span data-ttu-id="005fa-562">字母</span><span class="sxs-lookup"><span data-stu-id="005fa-562">Devanagari</span></span>

  - <span data-ttu-id="005fa-563">分</span><span class="sxs-lookup"><span data-stu-id="005fa-563">Ethiopic</span></span>

  - <span data-ttu-id="005fa-564">藏文</span><span class="sxs-lookup"><span data-stu-id="005fa-564">Tibetan</span></span>

  - <span data-ttu-id="005fa-565">孟加拉文</span><span class="sxs-lookup"><span data-stu-id="005fa-565">Bengali</span></span>

  - <span data-ttu-id="005fa-566">古吉拉特文</span><span class="sxs-lookup"><span data-stu-id="005fa-566">Gujarati</span></span>

  - <span data-ttu-id="005fa-567">特拉古文</span><span class="sxs-lookup"><span data-stu-id="005fa-567">Telugu</span></span>

  - <span data-ttu-id="005fa-568">所有其他印度文腳本</span><span class="sxs-lookup"><span data-stu-id="005fa-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="005fa-569">Lync Web App、網頁排程程式及網頁元件</span><span class="sxs-lookup"><span data-stu-id="005fa-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="005fa-570">Lync Web 排程器中特定語言的語言回退、撥入、加入啟動器、持續聊天室管理，以及 OCTab 可能無法如期運作</span><span class="sxs-lookup"><span data-stu-id="005fa-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="005fa-571">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-571">**Issue:**</span></span>

<span data-ttu-id="005fa-572">在網頁瀏覽器中選取非特定地區設定（在 Internet Explorer 中）時，例如，沒有進一步規範的語言名稱（ \[例如\]「挪威 no」），而不是指定語言、腳本和區域設定（例如「挪威文、 \[博克瑪律文\]（挪威） nb-no」）的特定語言，可能會在 Lync Web 排程器、撥入、加入啟動器、持續聊天室管理以及 OCTab 中導致意外的顯示行為。</span><span class="sxs-lookup"><span data-stu-id="005fa-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="005fa-573">例如，當選取下列其中一種語言時，使用者可能會看到英文頁面：</span><span class="sxs-lookup"><span data-stu-id="005fa-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="005fa-574">挪威語</span><span class="sxs-lookup"><span data-stu-id="005fa-574">Norwegian</span></span>

  - <span data-ttu-id="005fa-575">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="005fa-575">Portuguese</span></span>

  - <span data-ttu-id="005fa-576">塞爾維亞文</span><span class="sxs-lookup"><span data-stu-id="005fa-576">Serbian</span></span>

<span data-ttu-id="005fa-577">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-577">**Workaround:**</span></span>

<span data-ttu-id="005fa-578">如果您想要選取具有中立區域設定的語言，請務必務必在瀏覽器的語言喜好設定清單中，使用特定地區設定（使用腳本和/或國家/地區代碼）來新增語言。</span><span class="sxs-lookup"><span data-stu-id="005fa-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="005fa-579">使用 Lync Web 排程器、撥入、加入啟動器、持續聊天室管理，以及在某些網頁瀏覽器中 OCTab 時，對阿澤裡語和烏茲別克地區設定有限的支援</span><span class="sxs-lookup"><span data-stu-id="005fa-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="005fa-580">本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。</span><span class="sxs-lookup"><span data-stu-id="005fa-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="005fa-581">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-581">**Issue:**</span></span>

<span data-ttu-id="005fa-582">當您使用 Internet Explorer 8 或 Internet Explorer 9，並將瀏覽器語言設定為阿澤裡語（拉丁）或烏茲別克（拉丁）時，系統會以英文或瀏覽器中設定的喜好語言來顯示撥入與加入連接啟動器頁面。</span><span class="sxs-lookup"><span data-stu-id="005fa-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="005fa-583">當您使用 Firefox 或 Chrome 瀏覽器，並將瀏覽器語言設定為阿澤裡語（拉丁）或烏茲別克（拉丁），Lync Web App、Lync Web 排程程式和 RGS OCTab 將會以英文顯示，或針對瀏覽器設定的喜好語言。</span><span class="sxs-lookup"><span data-stu-id="005fa-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="005fa-584">在 Safari 瀏覽器中不支援烏茲別克（拉丁）區域設定。</span><span class="sxs-lookup"><span data-stu-id="005fa-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="005fa-585">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-585">**Workaround:**</span></span>

<span data-ttu-id="005fa-586">這些問題不提供因應措施。</span><span class="sxs-lookup"><span data-stu-id="005fa-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="005fa-587">在羅馬尼亞文版本的 Lync Web App 中，[從下列來源加入會議] 清單中缺少下拉式箭號</span><span class="sxs-lookup"><span data-stu-id="005fa-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="005fa-588">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-588">**Issue:**</span></span>

<span data-ttu-id="005fa-589">當使用羅馬尼亞文版本的 Lync Web App 的使用者執行下列步驟時，下拉式清單中不會顯示 [**加入會議**] 下拉式箭號：</span><span class="sxs-lookup"><span data-stu-id="005fa-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="005fa-590">在 [**一般**] 索引標籤上選取 [**在這台電腦上記住我**]。</span><span class="sxs-lookup"><span data-stu-id="005fa-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="005fa-591">選取 [**電話**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="005fa-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="005fa-592">按一下下拉式清單中的 [**加入會議**]。</span><span class="sxs-lookup"><span data-stu-id="005fa-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="005fa-593">使用者將不會看到指出有超過預設**Lync Web App**的選項，包括：**不加入音訊**（在羅馬尼亞文中，"Nu se asociaža la componenta 音訊"）和**新數位**"（在羅馬尼亞文中，" Număr nou "）。</span><span class="sxs-lookup"><span data-stu-id="005fa-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="005fa-594">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-594">**Workaround:**</span></span>

<span data-ttu-id="005fa-595">雖然不會顯示此下拉式清單的箭號，但使用者仍然可以按一下預設值，在清單中選取其他設定。</span><span class="sxs-lookup"><span data-stu-id="005fa-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="005fa-596">使用土耳其文版本的 Lync Web 排程器時，使用「誰是簡報者」下的「我選擇的人員」選項無法儲存會議</span><span class="sxs-lookup"><span data-stu-id="005fa-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="005fa-597">**出現**</span><span class="sxs-lookup"><span data-stu-id="005fa-597">**Issue:**</span></span>

<span data-ttu-id="005fa-598">在土耳其文版本的 Lync Web 排程器中建立或編輯會議時，不支援 [誰是簡報者] 下的選項 [我選擇的人員]。</span><span class="sxs-lookup"><span data-stu-id="005fa-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="005fa-599">選取此選項時，會議無法儲存。</span><span class="sxs-lookup"><span data-stu-id="005fa-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="005fa-600">相反地，會出現錯誤訊息，指出無法將一或多位人員設為簡報者。</span><span class="sxs-lookup"><span data-stu-id="005fa-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="005fa-601">**避免**</span><span class="sxs-lookup"><span data-stu-id="005fa-601">**Workaround:**</span></span>

<span data-ttu-id="005fa-602">若要解決此問題，使用者可以使用預設選項 [來自公司的人員] 或任何其他選項，例如「只有召集人」或「所有人在內，包括公司以外的人員」。</span><span class="sxs-lookup"><span data-stu-id="005fa-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="005fa-603">召集人在加入會議之後，可以將人員降級或宣傳給他們的正確角色。</span><span class="sxs-lookup"><span data-stu-id="005fa-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="005fa-604">或者，瞭解其他語言的使用者也可以將其瀏覽器中的語言選取變更為其他其中一個43支援的語言，然後嘗試使用「我選擇的人員」選項。</span><span class="sxs-lookup"><span data-stu-id="005fa-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="005fa-605">著作權</span><span class="sxs-lookup"><span data-stu-id="005fa-605">Copyright</span></span>

<span data-ttu-id="005fa-606">本檔支援軟體產品的預發行版本本，在最終的商業發行之前可能會有很大的變更，且是 Microsoft Corporation 的機密及專有資訊。</span><span class="sxs-lookup"><span data-stu-id="005fa-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="005fa-607">在收件者與 Microsoft 之間的保密協定中，會依據此條款披露。</span><span class="sxs-lookup"><span data-stu-id="005fa-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="005fa-608">本檔僅提供提供資訊的目的，Microsoft 在本檔中不做任何明示或暗示的保證。</span><span class="sxs-lookup"><span data-stu-id="005fa-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="005fa-609">本檔中的資訊（包括 URL 及其他網際網路網站參考）可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="005fa-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="005fa-610">使用本檔所帶來的全部風險或後果由使用者自行承擔。</span><span class="sxs-lookup"><span data-stu-id="005fa-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="005fa-611">除非另有說明，否則在本文範例中描述的公司、組織、產品、功能變數名稱、電子郵件地址、標誌、人員、位置及事件都是虛構的。</span><span class="sxs-lookup"><span data-stu-id="005fa-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="005fa-612">與任何真實的公司、組織、產品、功能變數名稱、電子郵件地址、標誌、人員、地點或事件不相關。</span><span class="sxs-lookup"><span data-stu-id="005fa-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="005fa-613">遵守所有適用的著作權法是使用者的責任。</span><span class="sxs-lookup"><span data-stu-id="005fa-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="005fa-614">在不限制版權所依據的權利的情況下，本檔的任何部分都不會複製、儲存或引進檢索系統，或是以任何形式或任何方式（電子、機械、複製、錄製或其他）進行傳播。沒有 Microsoft Corporation 的明確書面許可權。</span><span class="sxs-lookup"><span data-stu-id="005fa-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="005fa-615">Microsoft 可能具有專利、專利申請、商標、版權或其他智慧財產權，涵蓋本檔中的相關主題。</span><span class="sxs-lookup"><span data-stu-id="005fa-615">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="005fa-616">除了 Microsoft 的任何書面授權合約中明確提供之外，提供這份檔並不代表擁有這些專利、商標、版權或其他智慧財產權的授權。</span><span class="sxs-lookup"><span data-stu-id="005fa-616">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="005fa-617">© 2012 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="005fa-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="005fa-618">保留擁有權利。</span><span class="sxs-lookup"><span data-stu-id="005fa-618">All rights reserved.</span></span>

<span data-ttu-id="005fa-619">Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 及 SQL Server 都是 Microsoft Corporation 在美國和/或其他國家/地區的注冊商標或商標。</span><span class="sxs-lookup"><span data-stu-id="005fa-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="005fa-620">所有其他商標都是其各自擁有者的財產。</span><span class="sxs-lookup"><span data-stu-id="005fa-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

