---
title: Lync Server 2013： 定義用於判斷位置的網路元素
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6578c0cca54c41f079c682862b9e96a54e3d456
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="def1a-102">定義用來判斷在 Lync Server 2013 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="def1a-102">Defining the network elements used to determine location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="def1a-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="def1a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="def1a-104">如果您正在設定您的 Lync Server 基礎結構，以支援自動用戶端位置偵測，您必須先決定哪些網路即將要用於將來電者對應至位置的項目。</span><span class="sxs-lookup"><span data-stu-id="def1a-104">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="def1a-105">在 Lync Server 2013 中，您可以在下列的第 2 層和第 3 層網路元素關聯位置：</span><span class="sxs-lookup"><span data-stu-id="def1a-105">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="def1a-106">無線存取點 (WAP) 基本服務組識別碼 (BSSID) 位址 (第 2 層)</span><span class="sxs-lookup"><span data-stu-id="def1a-106">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="def1a-107">LLDP 交換器連接埠 (第 2 層)</span><span class="sxs-lookup"><span data-stu-id="def1a-107">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="def1a-108">LLDP 交換器底座識別碼 (第 2 層)</span><span class="sxs-lookup"><span data-stu-id="def1a-108">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="def1a-109">IP 子網路 (第 3 層)</span><span class="sxs-lookup"><span data-stu-id="def1a-109">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="def1a-110">用戶端 MAC 位址 (第 2 層)</span><span class="sxs-lookup"><span data-stu-id="def1a-110">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="def1a-111">網路元素會依照優先順序列出。</span><span class="sxs-lookup"><span data-stu-id="def1a-111">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="def1a-112">如果用戶端可以藉由使用多個網路元素找到，Lync Server 會使用的優先順序，決定要使用哪一個機制。</span><span class="sxs-lookup"><span data-stu-id="def1a-112">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="def1a-113">下列各節會詳細說明每個網路元素的使用方式。</span><span class="sxs-lookup"><span data-stu-id="def1a-113">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="def1a-114">當您使用網路元素，將來電者對應至位置時，它是責您保留位置資訊服務資料庫最新狀態。</span><span class="sxs-lookup"><span data-stu-id="def1a-114">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="def1a-115">例如，如果您新增或變更網路元素 (如新增 WAP)，則必須在位置資料庫中刪除舊項目並增加新項目。</span><span class="sxs-lookup"><span data-stu-id="def1a-115">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="def1a-116">無線存取點</span><span class="sxs-lookup"><span data-stu-id="def1a-116">Wireless Access Point</span></span>

<span data-ttu-id="def1a-117">當用戶端連線至無線網路時，「位置要求」會使用 WAP 的 BSSID 位址來判斷位置。</span><span class="sxs-lookup"><span data-stu-id="def1a-117">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="def1a-118">如果用戶端使用漫遊，所指出的 WAP 可能不是最接近的 WAP，甚至有可能會挑出在建築物中其他樓層的 WAP。</span><span class="sxs-lookup"><span data-stu-id="def1a-118">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="def1a-119">若要指出位置是相近的，可在前面以 Near 或 Close to 描述項加上位置值。</span><span class="sxs-lookup"><span data-stu-id="def1a-119">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="def1a-120">此位置方法會假定每個 WAP 的 BSSID 為靜態。</span><span class="sxs-lookup"><span data-stu-id="def1a-120">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="def1a-121">但是，如果您的 WAP 廠商使用動態指派的 BSSID，從 WAP 取得的 BSSID 可能會產生變更 (可能發生在 WAP 設定變更之後)，無線用戶端在無法接收位置的情況之下可能會離開。</span><span class="sxs-lookup"><span data-stu-id="def1a-121">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="def1a-122">若要避免這種可能性，您需要的每個 WAP 所使用的所有可能 BSSID 位址 Erl 位置資訊服務資料庫中填入。</span><span class="sxs-lookup"><span data-stu-id="def1a-122">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="def1a-123">LLDP 連接埠和交換器</span><span class="sxs-lookup"><span data-stu-id="def1a-123">LLDP Ports and Switches</span></span>

<span data-ttu-id="def1a-p106">支援 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 之受管理的乙太網路交換器，可將其識別碼及連接埠資訊公告至相容於 LLDP-MED 的用戶端，您可依位置資料庫查詢用戶端以提供裝置的位置。您可以僅在交換器底座辨識碼上建立 ERL 的關聯，或者可將其對應至連接埠層級。</span><span class="sxs-lookup"><span data-stu-id="def1a-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="def1a-126">Lync Server 2013 支援使用 LLDP-MED 決定只有 Lync Phone Edition 裝置和 Windows 8 上執行的 Lync 2013 的位置。</span><span class="sxs-lookup"><span data-stu-id="def1a-126">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="def1a-127">如果您需要使用參數層級來決定的其他位置的第 2 層資料有線 PC 型 Lync 用戶端，您需要使用的用戶端 MAC 位址方法。</span><span class="sxs-lookup"><span data-stu-id="def1a-127">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="def1a-128">子網路</span><span class="sxs-lookup"><span data-stu-id="def1a-128">Subnet</span></span>

<span data-ttu-id="def1a-129">第 3 層 IP 子網路會提供可以用來自動偵測用戶端位置的所有 Lync Server 用戶端所支援的機制。</span><span class="sxs-lookup"><span data-stu-id="def1a-129">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="def1a-130">使用 IP 子網路是設定與管理有線用戶端之最容易的方法。</span><span class="sxs-lookup"><span data-stu-id="def1a-130">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="def1a-131">決定使用子網路前，請先詢問自己下列問題來判斷子網路的位置是否明確到足以正確定位用戶端：</span><span class="sxs-lookup"><span data-stu-id="def1a-131">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="def1a-132">一個或多個用戶端子網路是否涵蓋多個樓層？</span><span class="sxs-lookup"><span data-stu-id="def1a-132">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="def1a-133">一個或多個子網路是否涵蓋多棟建築？</span><span class="sxs-lookup"><span data-stu-id="def1a-133">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="def1a-134">每個用戶端子網路涵蓋多少樓層空間？</span><span class="sxs-lookup"><span data-stu-id="def1a-134">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="def1a-p109">如果子網路涵蓋的區域太廣，您可能必須使用其他機制尋找用戶端。但是，以實際應用而言，建議您重新組織其 IP 子網路連線以符合 ERL 位置的精確性需求，才不會提高協力廠商 SNMP 解決方案的成本和複雜性。</span><span class="sxs-lookup"><span data-stu-id="def1a-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="def1a-137">用戶端 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="def1a-137">Client MAC Address</span></span>

<span data-ttu-id="def1a-138">若要使用用戶端電腦的 MAC 位址尋找來電者，您需要受管理的乙太網路交換器，而且必須部署可探索連線至 (或通過) 這些交換器之 Lync 用戶端 MAC 位址的協力廠商 SNMP 解決方案。</span><span class="sxs-lookup"><span data-stu-id="def1a-138">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="def1a-139">SNMP 解決方案會持續輪詢受管理交換器以取得連線至每個連接埠之端點 MAC 位址目前的對應，以及取得對應的連接埠識別碼。</span><span class="sxs-lookup"><span data-stu-id="def1a-139">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="def1a-140">期間的 Lync 用戶端的位置資訊服務要求，將位置資訊服務所使用的用戶端 MAC 位址，查詢的協力廠商應用程式，並則會傳回任何相符的參數 IP 位址及連接埠識別碼。</span><span class="sxs-lookup"><span data-stu-id="def1a-140">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="def1a-141">位置資訊服務使用此資訊來查詢比對記錄其已發佈層級 2 接線圖，並傳回給用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="def1a-141">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="def1a-142">如果您使用此選項，請確認 SNMP 應用程式以及已發行的位置資料庫記錄之間的交換器連接埠識別項是一致的。</span><span class="sxs-lookup"><span data-stu-id="def1a-142">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="def1a-143">部分協力廠商 SNMP 解決方案可支援未受管理的存取交換器；如果為 Lync 用戶端提供服務的交換器未受管理，但受管理的發佈交換器具有上行連結，該受管理之交換器可將連線至存取交換器的 MAC 位址回報至 SNMP 應用程式。</span><span class="sxs-lookup"><span data-stu-id="def1a-143">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="def1a-144">這項資訊會啟用位置資訊服務，來識別使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="def1a-144">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="def1a-145">不過，可能只會將單一 ERL 指派至未受管理之交換器上的所有連接埠，所以只有在存取交換器的底座層級才能取得明確的位置，而非連接埠層級。</span><span class="sxs-lookup"><span data-stu-id="def1a-145">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

