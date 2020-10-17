---
title: Lync Server 2013：部署監控
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fd56d0c06c9c81eda8cd1d7ef64b57da3219f3e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531170"
---
# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="11f5a-102">在 Lync Server 2013 中部署監控</span><span class="sxs-lookup"><span data-stu-id="11f5a-102">Deploying monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11f5a-103">_**主題上次修改日期：** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="11f5a-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="11f5a-104">從監控伺服器角色已被取代的事實開始，對 Microsoft Lync Server 2013 監控基礎結構所做的主要變更。</span><span class="sxs-lookup"><span data-stu-id="11f5a-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="11f5a-105">監視服務現在已組合在各前端伺服器上，不再是個別的監控伺服器角色 (通常需要組織設定專用電腦來作為監控伺服器)。</span><span class="sxs-lookup"><span data-stu-id="11f5a-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="11f5a-106">此變更的優點之一，就是有助於：</span><span class="sxs-lookup"><span data-stu-id="11f5a-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="11f5a-107">減少實施 Lync Server 2013 時所需的伺服器角色數目。</span><span class="sxs-lookup"><span data-stu-id="11f5a-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="11f5a-108">在此情況下，減少監控伺服器的伺服器角色也有助於減少成本，因為不需要維護用來監視的專用伺服器。</span><span class="sxs-lookup"><span data-stu-id="11f5a-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="11f5a-109">降低 Lync Server 安裝和管理的複雜度。</span><span class="sxs-lookup"><span data-stu-id="11f5a-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="11f5a-110">因為監視服務會自動組合在各前端伺服器上，所以您不再需要安裝、設定及管理監控伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="11f5a-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11f5a-111">在 Lync Server 2013 中，封存伺服器角色也已被取代。</span><span class="sxs-lookup"><span data-stu-id="11f5a-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="11f5a-112">就像監控服務，Lync Server 2013 封存服務現在會在每一部前端伺服器上組合。</span><span class="sxs-lookup"><span data-stu-id="11f5a-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="11f5a-113">這很值得注意，因為監視和封存經常共用相同的 SQL Server 資料庫執行個體。</span><span class="sxs-lookup"><span data-stu-id="11f5a-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="11f5a-114">如您所料，這些變更對如何安裝和管理監控服務有重大影響。</span><span class="sxs-lookup"><span data-stu-id="11f5a-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="11f5a-115">例如，因為監控伺服器角色不再存在，所以已從 Lync Server 拓撲產生器中移除監控伺服器節點。反過來，這表示您不再使用拓撲產生器的新監控伺服器嚮導，以將新的監控伺服器新增至您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="11f5a-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="11f5a-116"> (該嚮導已不存在。 ) 取而代之的是，您一般會透過完成下列兩個步驟來執行拓撲中的監控服務：</span><span class="sxs-lookup"><span data-stu-id="11f5a-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="11f5a-117">啟用同時監控您設定新的 Lync 伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="11f5a-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="11f5a-118">在 Lync Server 2013 中 (，監控功能會在集區依集區的基礎上啟用或停用。 ) 請注意，您可以啟用集區監控，但不實際收集監控資料，而是在此檔的 [設定詳細通話記錄與經驗品質設定] 區段中所述的程式。</span><span class="sxs-lookup"><span data-stu-id="11f5a-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="11f5a-p107">將監控存放區 (也就是監控資料庫) 與新集區建立關聯。請注意，單一監控存放區可與多個集區建立關聯。依據安置在登錄器集區的使用者數目，這表示您不需要為每個集區設定個別的監控資料庫。單一監控存放區即可供多集區使用。</span><span class="sxs-lookup"><span data-stu-id="11f5a-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="11f5a-p108">雖然在您建立新集區的同時啟用監視通常會比較容易，但也可能會建立停用監視的新集區。如果您這麼做，可以在稍後使用拓撲產生器來啟用服務：拓撲產生器有提供一種方法，可為集區啟用或停用監視，或是將集區與不同的監控存放區建立關聯。請記得，雖然已經沒有監控伺服器角色了，您還是需要建立一或多個監控存放區：用來儲存監視服務所收集之資料的後端資料庫。這些後端資料庫可以用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 來建立。</span><span class="sxs-lookup"><span data-stu-id="11f5a-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11f5a-127">如果已啟用集區監控，您可以停用收集監控資料的處理常式，而不需變更拓撲： Lync Server 管理命令介面提供一種方法，讓您能夠停用 (，然後再重新啟用) 通話詳細資料記錄 (CDR) 或經驗品質 (QoE) 資料收集。</span><span class="sxs-lookup"><span data-stu-id="11f5a-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="11f5a-128">如需詳細資訊，請參閱本文件中的＜設定詳細通話記錄和經驗品質設定＞一節。</span><span class="sxs-lookup"><span data-stu-id="11f5a-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="11f5a-129">Lync Server 2013 中監控的另一個重要增強功能是 Lync Server Monitoring Reports 現在支援 IPv6：使用 [IP 位址] 欄位的報告會顯示 IPv4 或 IPv6 的位址，取決於： 1) 所使用的 SQL 查詢;和，2) IPv6 位址會儲存在監控資料庫中。</span><span class="sxs-lookup"><span data-stu-id="11f5a-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11f5a-130">確定 SQL Server Agent Service 的啟動類型為 [自動]，且 SQL Server 代理程式服務正在執行中包含監控資料庫的 SQL 實例，因此，在 SQL Server 代理程式服務的控制下，可根據其排程執行預設監控 SQL Server 維護工作。</span><span class="sxs-lookup"><span data-stu-id="11f5a-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="11f5a-131">這份檔會引導您完成安裝及設定 Lync Server 2013 之監控和監控報告的程式。</span><span class="sxs-lookup"><span data-stu-id="11f5a-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="11f5a-132">文件中提供逐步指示，將可協助您：</span><span class="sxs-lookup"><span data-stu-id="11f5a-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="11f5a-133">在拓撲中啟用監視，以及將監控存放區與前端集區建立關聯。</span><span class="sxs-lookup"><span data-stu-id="11f5a-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="11f5a-134">安裝 SQL Server Reporting Services 和 Lync Server Monitoring Reports。</span><span class="sxs-lookup"><span data-stu-id="11f5a-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="11f5a-135">監視報告是預先設定的報告，針對儲存在監控資料庫中資訊提供不同的觀點。</span><span class="sxs-lookup"><span data-stu-id="11f5a-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="11f5a-136">設定詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料收集。</span><span class="sxs-lookup"><span data-stu-id="11f5a-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="11f5a-137">詳細通話記錄可讓您追蹤 Lync Server 功能的使用方式，例如 Voice over IP (VoIP) 電話;立即訊息 (IM) ;檔案傳輸;音訊/視頻 (A/V) 會議;和應用程式共用會話。</span><span class="sxs-lookup"><span data-stu-id="11f5a-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="11f5a-138">QoE 計量追蹤在組織中建立的音訊和視訊通話品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 量。</span><span class="sxs-lookup"><span data-stu-id="11f5a-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="11f5a-139">從監控資料庫手動清除 CDR 及/或 QoE 記錄。</span><span class="sxs-lookup"><span data-stu-id="11f5a-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

