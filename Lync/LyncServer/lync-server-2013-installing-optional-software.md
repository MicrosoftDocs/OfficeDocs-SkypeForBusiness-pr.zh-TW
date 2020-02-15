---
title: Lync Server 2013： 安裝選用軟體
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
ms.openlocfilehash: 080f27b1e01f86d23fd5fd7bf6fdb9e9a05c0742
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="85097-102">Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="85097-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85097-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="85097-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="85097-104">Microsoft Lync Server 2013、 規劃工具的設計匯出至 Microsoft Excel 與 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="85097-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="85097-105">這些應用程式都不是必要的規劃工具的作業時，它們不要加入重大值的部署與您的設計的文件。</span><span class="sxs-lookup"><span data-stu-id="85097-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="85097-106">選用軟體</span><span class="sxs-lookup"><span data-stu-id="85097-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="85097-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="85097-107">Microsoft Excel</span></span>

<span data-ttu-id="85097-108">將您的設計匯出至 Microsoft Excel 會建立一份報告，顯示在試算表中的七個索引標籤：</span><span class="sxs-lookup"><span data-stu-id="85097-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="85097-109">摘要 – 顯示有關網站組態，包括使用者計數、 容量設定，以及伺服器設定檔資訊。</span><span class="sxs-lookup"><span data-stu-id="85097-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="85097-110">硬體設定檔 – 顯示報表上的拓撲，包括 CPU、 記憶體、 磁碟，以及網路介面中指定的伺服器的建議的硬體組態。</span><span class="sxs-lookup"><span data-stu-id="85097-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="85097-111">數量及建議的規格的伺服器元件也會是包含項目。</span><span class="sxs-lookup"><span data-stu-id="85097-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="85097-112">此外，每一部伺服器是由網站，以提供完整的伺服器需求呈現網站所定義。</span><span class="sxs-lookup"><span data-stu-id="85097-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="85097-113">連接埠需求 – 網域名稱系統負載平衡 (DNS LB) 和硬體負載平衡器 (HLB) 將會顯示所有已啟用的連接埠和關聯的報告。</span><span class="sxs-lookup"><span data-stu-id="85097-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="85097-114">您應該使用此報告來規劃您的防火牆和 DNS LB 和 HLB 組態。</span><span class="sxs-lookup"><span data-stu-id="85097-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="85097-115">摘要報告 – 顯示一般，才能設定 Edge Server 網路設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="85097-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="85097-116">憑證報表 – 顯示主旨名稱及所要執行的 Edge 伺服器所需的憑證的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="85097-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="85097-117">防火牆報告 – 顯示來源和目的地連接埠和 IP 位址的外部及內部介面。</span><span class="sxs-lookup"><span data-stu-id="85097-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="85097-118">DNS 報告 – 顯示的完整的網域名稱 (FQDN) 與 IP/VIP 位址所需的每個 DNS 項目，您建立。</span><span class="sxs-lookup"><span data-stu-id="85097-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="85097-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="85097-119">Microsoft Visio</span></span>

<span data-ttu-id="85097-120">將您的設計匯出至 Microsoft Visio 會在您的文件目的，您設定的拓撲和基礎結構中建立用於圖表。</span><span class="sxs-lookup"><span data-stu-id="85097-120">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="85097-121">匯入的圖表可以編輯，而且以符合您的文件需要重新排列。</span><span class="sxs-lookup"><span data-stu-id="85097-121">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="85097-122">會包含在一般的 Visio 圖表：</span><span class="sxs-lookup"><span data-stu-id="85097-122">The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85097-123">如果您的設計規模夠大，需要超過三個前端伺服器，一個額外的頁面會建立前端集區，前端伺服器，執行 SQL Server、 IP 位址和 Fqdn 的電腦。</span><span class="sxs-lookup"><span data-stu-id="85097-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="85097-124">通用拓撲 – 已設定 Lync Server 2013 網站的圖表。</span><span class="sxs-lookup"><span data-stu-id="85097-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="85097-125">網站名稱] 索引標籤 – 顯示站台組態拓撲與 Edge 伺服器、 防火牆、 公用交換電話網路 (PSTN) 閘道，與內部伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="85097-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="85097-126">在內部部署設定的伺服器所組成與集區，包括前端集區，SQL Server 型伺服器、 Active Directory 網域服務、 Director、 Exchange 整合通訊 (UM) 伺服器，Exchange 信箱伺服器，Office Web Apps Server，中繼伺服器和 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="85097-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="85097-127">Edge 網狀圖 – 圖詳述相關聯的 IP 位址和 Fqdn 的 Edge Server 組態。</span><span class="sxs-lookup"><span data-stu-id="85097-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="85097-128">DNS 負載平衡與硬體負載平衡器也會包含。</span><span class="sxs-lookup"><span data-stu-id="85097-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="85097-129">此外，Director 與前端伺服器或前端集區，以顯示相關聯的 DNS LB 或 HLB （規劃工具支援 IPv4 和 IPv6 地址） 指派的 IP 位址和 FQDN。</span><span class="sxs-lookup"><span data-stu-id="85097-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85097-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="85097-130">See Also</span></span>


[<span data-ttu-id="85097-131">Lync Server 2013 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="85097-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

