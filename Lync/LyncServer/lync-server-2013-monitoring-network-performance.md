---
title: Lync Server 2013：監控網路效能
description: Lync Server 2013：監控網路效能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ead7e3f9001b06c783c9b22327581e795a20322
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549449"
---
# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="fccab-103">在 Lync Server 2013 中監控網路效能</span><span class="sxs-lookup"><span data-stu-id="fccab-103">Monitoring network performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fccab-104">_**主題上次修改日期：** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="fccab-104">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="fccab-105">Lync Server 2013 是一種即時通訊技術，其主要是透過網路來啟用使用者之間的通訊，既可以透過立即訊息 (IM) 、語音通話或視頻通訊。</span><span class="sxs-lookup"><span data-stu-id="fccab-105">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="fccab-106">因此，請務必連續監視網路效能，以協助確保使用者選擇的通訊形式可提供最佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="fccab-106">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="fccab-107">網路效能的衡量可以是兩個層級：</span><span class="sxs-lookup"><span data-stu-id="fccab-107">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="fccab-108">**整體網路效能**    這種效能測量層級可讓組織建立其網路的「大圖片」視圖，通常是透過協力廠商網路監控系統來執行。</span><span class="sxs-lookup"><span data-stu-id="fccab-108">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="fccab-109">這些系統會接收來自遠端網路裝置（例如路由器）上的效能及容量資料，以供系統管理員在一天中的任何時間決定任何指定網路元件的健康情況。</span><span class="sxs-lookup"><span data-stu-id="fccab-109">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="fccab-110">**個別的伺服器效能**    這層級的效能測量會限制在特定伺服器上，並可協助系統管理員 gauging 特定伺服器的網路效能，以協助疑難排解特定效能問題，或在指定期間內評估各伺服器的效能，做為容量規劃程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="fccab-110">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="fccab-111">您可以使用下列各節所述的工具來監視網路。</span><span class="sxs-lookup"><span data-stu-id="fccab-111">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="fccab-112">整體網路效能監控工具</span><span class="sxs-lookup"><span data-stu-id="fccab-112">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="fccab-113">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="fccab-113">System Center Operations Manager 2012</span></span>

<span data-ttu-id="fccab-114">System Center Operations Manager 提供端對端的服務管理，便於自訂及擴充，以改善整個 IT 環境中的服務等級。</span><span class="sxs-lookup"><span data-stu-id="fccab-114">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="fccab-115">這可讓作業和 IT 管理小組識別及解決影響分散式 IT 服務健康情況的問題。</span><span class="sxs-lookup"><span data-stu-id="fccab-115">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="fccab-116">端對端服務管理不受限於以 Microsoft 為基礎的環境。</span><span class="sxs-lookup"><span data-stu-id="fccab-116">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="fccab-117">支援管理的 Web 服務 (WS-MANAGEMENT) 、簡易網路管理通訊協定 (SNMP) 及夥伴解決方案，都可以在 System Center Operations Manager 2012 內的服務監視中包含未執行 Microsoft 作業系統和硬體的系統。</span><span class="sxs-lookup"><span data-stu-id="fccab-117">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="fccab-118">System Center Operations Manager 2012 及 Third-Party 網路管理解決方案</span><span class="sxs-lookup"><span data-stu-id="fccab-118">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="fccab-119">**EMC Smarts**    EMC 的 Operations Manager 解決方案可協助您快速解決整個中影響服務層級的問題。</span><span class="sxs-lookup"><span data-stu-id="fccab-119">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="fccab-120">透過使用 EMC 的 Operations Manager 解決方案，您可以使用一個整合、自動化的解決方案，管理及監視整個 IT 服務鏈。</span><span class="sxs-lookup"><span data-stu-id="fccab-120">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="fccab-121">您可以輕鬆識別效能及可用性問題的根本原因，並更快地解決影響和成本。</span><span class="sxs-lookup"><span data-stu-id="fccab-121">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="fccab-122">主要優點包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="fccab-122">Key benefits include the following:</span></span>

  - <span data-ttu-id="fccab-123">高級、便於使用的管理著重于提供戰略性的商業價值，而不是手動排序和篩選混亂的警示。</span><span class="sxs-lookup"><span data-stu-id="fccab-123">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="fccab-124">**更快的解析度**    更快速地解決 IT 問題，並回應業務需求，以降低影響及成本。</span><span class="sxs-lookup"><span data-stu-id="fccab-124">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="fccab-125">**精簡作業**    結合多個管理工具、應用程式和終端，避免 IT 複雜性。</span><span class="sxs-lookup"><span data-stu-id="fccab-125">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="fccab-126">您可以在以下位置找到相關資訊：</span><span class="sxs-lookup"><span data-stu-id="fccab-126">More information can be found here:</span></span>

[<span data-ttu-id="fccab-127">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="fccab-127">Microsoft System Center Operations Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="fccab-128">Microsoft System Center Operations Manager 的解決方案</span><span class="sxs-lookup"><span data-stu-id="fccab-128">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="fccab-129">Third-Party 解決方案</span><span class="sxs-lookup"><span data-stu-id="fccab-129">Third-Party Solutions</span></span>

<span data-ttu-id="fccab-130">\*\*Hp 網路管理中心 (之前稱為 hp OpenView) \*\*    [hp 網路管理中心](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__)提供整合式的故障和效能管理，以提升網路可用性和效能。</span><span class="sxs-lookup"><span data-stu-id="fccab-130">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="fccab-131">網路管理中心是 HP 自動化網路管理解決方案的一部分，可統一執行錯誤、效能、設定及變更管理。</span><span class="sxs-lookup"><span data-stu-id="fccab-131">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="fccab-132">**Cisco 網路管理和自動化產品**    針對企業，Cisco 具有數個可供使用的管理產品，包括 CiscoWorks LAN 管理解決方案和 Cisco 網路分析模組，以協助改善操作效率並減少網路停機時間。</span><span class="sxs-lookup"><span data-stu-id="fccab-132">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="fccab-133">如需這些產品的其他資料，請參閱 Cisco 網站，網址為 [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html) 。</span><span class="sxs-lookup"><span data-stu-id="fccab-133">For additional data on these products, refer to the Cisco website at [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="fccab-134">簡易網路管理通訊協定 (SNMP) 簡易網路管理通訊協定 (SNMP) 是網路管理標準，用來定義管理 TCP/IP 網路的策略。</span><span class="sxs-lookup"><span data-stu-id="fccab-134">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="fccab-135">SNMP 可讓您捕獲網路的設定和狀態資訊，並將資訊傳送至指定的電腦，以進行事件監視。</span><span class="sxs-lookup"><span data-stu-id="fccab-135">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="fccab-136">這種以標準為基礎的網路管理通訊協定使用分散式架構，其中包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="fccab-136">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="fccab-137">多個受管理的節點，每個都有一個稱為「代理程式」的 SNMP 實體，可提供管理規範的遠端存取。</span><span class="sxs-lookup"><span data-stu-id="fccab-137">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="fccab-138">至少有一個 SNMP 實體稱為管理員，它會執行管理應用程式來監視和控制受管理的元素。</span><span class="sxs-lookup"><span data-stu-id="fccab-138">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="fccab-139">Managed 元素是主機、路由器等裝置。</span><span class="sxs-lookup"><span data-stu-id="fccab-139">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="fccab-140">他們會透過存取其管理資訊來加以監控和控制。</span><span class="sxs-lookup"><span data-stu-id="fccab-140">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="fccab-141">管理通訊協定（SNMP）是用來在管理工作站和代理程式之間交流管理資訊。</span><span class="sxs-lookup"><span data-stu-id="fccab-141">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="fccab-142">管理資訊指的是即時于虛擬資訊儲存區（稱為「管理資訊基底 (MIB) ）中的受管理物件集合。</span><span class="sxs-lookup"><span data-stu-id="fccab-142">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fccab-143">以上提供協力廠商網路監視解決方案的範例。</span><span class="sxs-lookup"><span data-stu-id="fccab-143">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="fccab-144">此清單並不是明確的，Microsoft 不會優選任何特定的廠商解決方案。</span><span class="sxs-lookup"><span data-stu-id="fccab-144">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="fccab-145">請與網路服務提供者和您的各技術供應商協商，以判斷貴組織的最佳網路監控解決方案。</span><span class="sxs-lookup"><span data-stu-id="fccab-145">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="fccab-146">監視個別伺服器網路效能的工具</span><span class="sxs-lookup"><span data-stu-id="fccab-146">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="fccab-147">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="fccab-147">System Center Operations Manager 2012</span></span>

<span data-ttu-id="fccab-148">System Center Operations Manager 2012 可讓系統管理員透過 Windows Server 2012 管理元件來查看個別伺服器的網路效能： Windows Server 作業系統管理元件包括「效能」管理元件，可讓系統管理員監視網路介面卡的效能和配接器健康情況。</span><span class="sxs-lookup"><span data-stu-id="fccab-148">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="fccab-149">Windows 網路監視器</span><span class="sxs-lookup"><span data-stu-id="fccab-149">Windows Network Monitor</span></span>

<span data-ttu-id="fccab-150">會收集、顯示、分析伺服器上的資源使用狀況，並測量網路流量。</span><span class="sxs-lookup"><span data-stu-id="fccab-150">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="fccab-151">網路監視器會以獨佔方式監視網路活動。</span><span class="sxs-lookup"><span data-stu-id="fccab-151">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="fccab-152">透過捕獲和分析網路資料，並使用這些資料搭配效能記錄，您可以判斷網路使用量、識別網路問題，以及預測未來的網路需求。</span><span class="sxs-lookup"><span data-stu-id="fccab-152">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="fccab-153">如需網路監視器3.4 的詳細資訊，以及若要瞭解如何安裝及設定網路監視器及捕獲和分析資料，請複查此會話：網路監視器3.3 簡介。</span><span class="sxs-lookup"><span data-stu-id="fccab-153">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="fccab-154">此外，請複查 [網路監視器博客](https://blogs.technet.com/b/netmon/)。</span><span class="sxs-lookup"><span data-stu-id="fccab-154">Also, review the [Network Monitor blog](https://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

