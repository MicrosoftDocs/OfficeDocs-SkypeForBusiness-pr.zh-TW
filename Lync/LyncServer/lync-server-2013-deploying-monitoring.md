---
title: Lync Server 2013：部署監視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="0e088-102">在 Lync Server 2013 中部署監視</span><span class="sxs-lookup"><span data-stu-id="0e088-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e088-103">_**主題上次修改日期：** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="0e088-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="0e088-104">Microsoft Lync Server 2013 監視基礎結構的主要變更，從已棄用監視伺服器角色的情況開始。</span><span class="sxs-lookup"><span data-stu-id="0e088-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="0e088-105">您現在可以在每個前端伺服器上 collocated 監視服務，而不是個別的監視伺服器角色（通常是必要的組織，將專用電腦設定為充當監視伺服器）。</span><span class="sxs-lookup"><span data-stu-id="0e088-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="0e088-106">在其他專案中，這項變更有助於：</span><span class="sxs-lookup"><span data-stu-id="0e088-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="0e088-107">減少實現 Lync Server 2013 時所需的伺服器角色數目。</span><span class="sxs-lookup"><span data-stu-id="0e088-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="0e088-108">在這種情況下，遞減監視伺服器的角色也能避免維護專用伺服器來進行監視，以減少成本。</span><span class="sxs-lookup"><span data-stu-id="0e088-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="0e088-109">減少 Lync Server 設定和管理的複雜性。</span><span class="sxs-lookup"><span data-stu-id="0e088-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="0e088-110">在每個前端伺服器上自動 collocating 監視服務，您就不需要再安裝、設定及管理監視伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="0e088-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e088-111">在 Lync Server 2013 中，存檔伺服器角色也已被棄用。</span><span class="sxs-lookup"><span data-stu-id="0e088-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="0e088-112">就像監視服務一樣，Lync Server 2013 封存服務現已在每個前端伺服器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="0e088-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="0e088-113">這只需要注意，因為監視和歸檔通常會共用相同的 SQL Server 資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="0e088-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="0e088-114">正如您預期的，這些變更對監視服務的安裝與管理方式有很大的影響。</span><span class="sxs-lookup"><span data-stu-id="0e088-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="0e088-115">例如，因為已不存在監視伺服器角色，所以已從 Lync Server 拓撲建立器中移除 [監視伺服器] 節點;也就是說，這表示您將不會再使用拓撲建立器的新監視伺服器嚮導，將新的監視伺服器新增到您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="0e088-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="0e088-116">（該嚮導已不存在）。相反地，您通常會透過完成下列兩個步驟來在拓撲內執行監視服務：</span><span class="sxs-lookup"><span data-stu-id="0e088-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="0e088-117">當您設定新的 Lync 伺服器池時，同時啟用監視。</span><span class="sxs-lookup"><span data-stu-id="0e088-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="0e088-118">（在 Lync Server 2013 中，會針對每個池逐一啟用或停用監視）。請注意，您可以在不實際收集監視資料的情況下啟用對某個池的監視，在本檔的 [設定呼叫詳細資料記錄] 和 [經驗品質設定] 區段中說明的程式。</span><span class="sxs-lookup"><span data-stu-id="0e088-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="0e088-119">將監視存放區（即監視資料庫）與新的池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="0e088-119">Associating a monitoring store (that is, a monitoring database) with the new pool.</span></span> <span data-ttu-id="0e088-120">請注意，單一監視存儲可以與多個池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="0e088-120">Note that a single monitoring store can be associated with multiple pools.</span></span> <span data-ttu-id="0e088-121">根據您的註冊機構池中駐留的使用者數目而定，這表示您不需要為每個池設定個別的監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="0e088-121">Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools.</span></span> <span data-ttu-id="0e088-122">相反地，單一監視存放區可以由多個池使用。</span><span class="sxs-lookup"><span data-stu-id="0e088-122">Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="0e088-123">雖然在您建立新的資料庫池的同時啟用監視通常是比較容易的，但是也可以建立一個已停用監視的新池。</span><span class="sxs-lookup"><span data-stu-id="0e088-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="0e088-124">如果您這樣做，您可以在稍後使用拓撲建立器來啟用服務： [拓撲建立器] 提供啟用或停用池監視的方式，或將池與不同的監視存放區建立關聯。</span><span class="sxs-lookup"><span data-stu-id="0e088-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="0e088-125">請記住，即使不再有監視伺服器角色，您仍需建立一或多個監視存儲：後端資料庫，用來儲存由監視服務收集的資料。</span><span class="sxs-lookup"><span data-stu-id="0e088-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="0e088-126">您可以使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 來建立這些後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="0e088-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e088-127">如果已針對某個池啟用監視，您可以停用收集監控資料的程式，而不需變更您的拓撲： Lync Server 管理命令介面提供一種方式，讓您可以停用（然後重新啟用）通話詳細資料錄製（CDR）或品質的體驗（QoE）資料收集。</span><span class="sxs-lookup"><span data-stu-id="0e088-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="0e088-128">如需詳細資訊，請參閱本檔的設定通話詳細資料錄製和體驗設定一節。</span><span class="sxs-lookup"><span data-stu-id="0e088-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="0e088-129">在 2013 Lync server 中進行監視的另一個重要增強功能，就是 Lync Server 監視報告現在支援 IPv6：使用 [IP 位址] 欄位的報表會顯示 IPv4 或 IPv6 位址（視：1）所使用的 SQL 查詢;與，2） IPv6 位址儲存在監視資料庫中的位置。</span><span class="sxs-lookup"><span data-stu-id="0e088-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e088-130">確定 SQL Server Agent 服務啟動類型為 [自動]，且 SQL Server Agent 服務正在針對擁有監視資料庫的 SQL 實例執行，因此預設的監視 SQL Server 維護作業可以依排程的方式執行[SQL Server 代理程式服務] 的控制權。</span><span class="sxs-lookup"><span data-stu-id="0e088-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="0e088-131">本檔會逐步引導您完成安裝和設定 Lync Server 2013 的監視及監視報告的程式。</span><span class="sxs-lookup"><span data-stu-id="0e088-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="0e088-132">本檔提供可協助您執行下列逐步指示：</span><span class="sxs-lookup"><span data-stu-id="0e088-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="0e088-133">在拓撲中啟用監視，並將監視存放區與前端池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="0e088-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="0e088-134">安裝 SQL Server Reporting Services 和 Lync Server Monitoring 報告。</span><span class="sxs-lookup"><span data-stu-id="0e088-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="0e088-135">監視報告是預先配置的報告，可為監視資料庫中儲存的資訊提供不同的視圖。</span><span class="sxs-lookup"><span data-stu-id="0e088-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="0e088-136">設定通話詳細資料錄製（CDR）和體驗品質（QoE）資料收集。</span><span class="sxs-lookup"><span data-stu-id="0e088-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="0e088-137">通話詳細資料錄製提供一種方式，讓您追蹤 Lync 伺服器功能（例如，語音 over IP 通話）的使用方式;立即訊息（IM）;檔案傳輸;音訊/視頻（A/V）會議;與應用程式共用會話。</span><span class="sxs-lookup"><span data-stu-id="0e088-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="0e088-138">QoE 度量單位會追蹤您組織中的音訊和視頻通話品質，包括網路資料包遺失、背景雜色及「抖動」（資料包延遲的差異）等專案。</span><span class="sxs-lookup"><span data-stu-id="0e088-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="0e088-139">從監視資料庫手動清除 CDR 和/或 QoE 記錄。</span><span class="sxs-lookup"><span data-stu-id="0e088-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

