---
title: Lync Server 2013：安裝選用軟體
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f56d856aa0a97125812f68ede9a2bff5b49f036
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498530"
---
# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="a5080-102">在 Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="a5080-102">Installing optional software in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5080-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a5080-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a5080-104">規劃工具是設計用來匯出至 Microsoft Excel 和 Microsoft Visio 的 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a5080-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="a5080-105">雖然不需要在規劃工具作業時執行這些應用程式，但是會為部署和設計的檔增加重要的價值。</span><span class="sxs-lookup"><span data-stu-id="a5080-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="a5080-106">選用軟體</span><span class="sxs-lookup"><span data-stu-id="a5080-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="a5080-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="a5080-107">Microsoft Excel</span></span>

<span data-ttu-id="a5080-108">將設計匯出至 Microsoft Excel 會建立一個報告，該報告會顯示試算表中的七個索引標籤：</span><span class="sxs-lookup"><span data-stu-id="a5080-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="a5080-109">摘要–顯示網站設定的資訊，包括使用者計數、容量設定和伺服器設定檔資訊。</span><span class="sxs-lookup"><span data-stu-id="a5080-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="a5080-110">硬體設定檔–針對拓撲中指定的伺服器（包括 CPU、記憶體、磁片及網路介面），顯示建議硬體設定的報告。</span><span class="sxs-lookup"><span data-stu-id="a5080-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="a5080-111">此外，也包含伺服器元件的數量和建議規格。</span><span class="sxs-lookup"><span data-stu-id="a5080-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="a5080-112">此外，每個伺服器都是由網站定義，以透過網站提供伺服器需求的完整標記法。</span><span class="sxs-lookup"><span data-stu-id="a5080-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="a5080-113">埠需求–顯示所有已啟用的埠報告，以及與網域名稱系統負載平衡 (DNS LB) 和硬體負載平衡器 (HLB) 的關聯。</span><span class="sxs-lookup"><span data-stu-id="a5080-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="a5080-114">您應該使用此報告規劃您的防火牆和 DNS LB 和 HLB 設定。</span><span class="sxs-lookup"><span data-stu-id="a5080-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="a5080-115">摘要報告–顯示設定 Edge Server 網路所需之設定的一般摘要。</span><span class="sxs-lookup"><span data-stu-id="a5080-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="a5080-116">憑證報告–顯示取得執行 Edge Server 所需之憑證所需的主體名稱和主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="a5080-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="a5080-117">防火牆報告–顯示外部及內部介面的來源和目的地埠及 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a5080-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="a5080-118">DNS 報告–顯示您所建立之每個 DNS 專案所需的完整功能變數名稱 (FQDN) 和 IP/VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a5080-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="a5080-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="a5080-119">Microsoft Visio</span></span>

<span data-ttu-id="a5080-120">將您的設計匯出至 Microsoft Visio，會建立圖表，以供您設定的拓撲和基礎結構的檔目的使用。</span><span class="sxs-lookup"><span data-stu-id="a5080-120">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="a5080-121">您可以編輯並重新排列已匯入的圖表，以符合您的檔需求。</span><span class="sxs-lookup"><span data-stu-id="a5080-121">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="a5080-122">典型的 Visio 圖表會包含：</span><span class="sxs-lookup"><span data-stu-id="a5080-122">The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5080-123">如果您的設計足夠大，需要超過三部前端伺服器，則會為前端集區、前端伺服器、執行 SQL Server 的電腦、IP 位址和 Fqdn 建立額外的頁面。</span><span class="sxs-lookup"><span data-stu-id="a5080-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="a5080-124">通用拓撲–設定的 Lync Server 2013 網站圖表。</span><span class="sxs-lookup"><span data-stu-id="a5080-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="a5080-125">[網站名稱] 索引標籤–顯示與 Edge Server、防火牆、公用交換電話網路 (PSTN) 搭配閘道和內部伺服器部署的網站設定拓撲。</span><span class="sxs-lookup"><span data-stu-id="a5080-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="a5080-126">內部部署包含已設定的伺服器及集區，包括前端集區、SQL Server 型伺服器、Active Directory 網域服務、Director、Exchange 整合通訊 (UM) 伺服器、Exchange 信箱伺服器、Office Web Apps Server、轉送伺服器及 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="a5080-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="a5080-127">Edge Network 圖表–詳述具有關聯之 IP 位址和 Fqdn 之 Edge Server 設定的圖表。</span><span class="sxs-lookup"><span data-stu-id="a5080-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="a5080-128">此外，也包含 DNS 負載平衡與硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="a5080-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="a5080-129">此外，會顯示 Director 和前端伺服器或前端集區，並有相關聯的 DNS LB 或 HLB，以及已指派的 IP 位址 (規劃工具可同時支援 IPv4 和 IPv6 位址) 和 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a5080-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5080-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a5080-130">See Also</span></span>


[<span data-ttu-id="a5080-131">在 Lync Server 2013 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="a5080-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

