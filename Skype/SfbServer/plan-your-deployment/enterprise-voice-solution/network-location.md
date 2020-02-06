---
title: 定義用來判斷商務用 Skype Server 中的位置的網路元素
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: 規劃您在商務用 Skype Server Enterprise Voice 中，要將哪些網路元件對應至 E9 的位置，以進行部署。
ms.openlocfilehash: 404ac2d151f367ad391e4d5426090f20448cc383
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802663"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a><span data-ttu-id="e6cd5-103">定義用來判斷商務用 Skype Server 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="e6cd5-103">Define the network elements used to determine location in Skype for Business Server</span></span>
 
<span data-ttu-id="e6cd5-104">規劃您在商務用 Skype Server Enterprise Voice 中，要將哪些網路元件對應至 E9 的位置，以進行部署。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-104">Decisions necessary for planning which network components you will use to map callers to locations for E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e6cd5-105">如果您要設定商務用 Skype 伺服器基礎結構以支援自動用戶端位置偵測，您必須首先決定要使用哪些網路元素將呼叫者對應至位置。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-105">If you are setting up your Skype for Business Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="e6cd5-106">在商務用 Skype Server 中，您可以將下列第2層和第3層網路元素與位置建立關聯：</span><span class="sxs-lookup"><span data-stu-id="e6cd5-106">In Skype for Business Server, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>
  
- <span data-ttu-id="e6cd5-107">無線存取點（WAP）基本服務集標識（BSSID）位址（第2層）</span><span class="sxs-lookup"><span data-stu-id="e6cd5-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>
    
- <span data-ttu-id="e6cd5-108">LLDP 切換埠（第2層）</span><span class="sxs-lookup"><span data-stu-id="e6cd5-108">LLDP switch port (Layer 2)</span></span>
    
- <span data-ttu-id="e6cd5-109">LLDP 切換主機殼識別碼（第2層）</span><span class="sxs-lookup"><span data-stu-id="e6cd5-109">LLDP switch chassis IDs (Layer 2)</span></span>
    
- <span data-ttu-id="e6cd5-110">IP 子網（第3層）</span><span class="sxs-lookup"><span data-stu-id="e6cd5-110">IP subnets (Layer 3)</span></span>
    
- <span data-ttu-id="e6cd5-111">用戶端 MAC 位址（第2層）</span><span class="sxs-lookup"><span data-stu-id="e6cd5-111">Client MAC addresses (Layer 2)</span></span>
    
<span data-ttu-id="e6cd5-112">網路元素會依優先順序順序列出。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="e6cd5-113">如果您可以使用一個以上的網路元素來找出用戶端，商務用 Skype Server 會使用優先順序順序來決定要使用哪種機制。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-113">If a client can be located by using more than one network element, Skype for Business Server uses the order of precedence to determine which mechanism to use.</span></span> 
  
<span data-ttu-id="e6cd5-114">下列各節提供使用每個網元的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-114">The following sections provide more details for using each network element.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e6cd5-115">當您使用網路元素將呼叫者對應到位置時，將位置資訊服務資料庫保持在最新狀態，這是一項非常重要的重要性。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="e6cd5-116">例如，如果您新增或變更網路元素（例如新增 WAP），則必須刪除舊專案，並在位置資料庫中新增新的專案。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span> 
  
## <a name="wireless-access-point"></a><span data-ttu-id="e6cd5-117">無線存取點</span><span class="sxs-lookup"><span data-stu-id="e6cd5-117">Wireless Access Point</span></span>

<span data-ttu-id="e6cd5-118">當用戶端以無線方式連線到網路時，位置要求會使用 WAP 的 BSSID 位址來決定其位置。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="e6cd5-119">如果用戶端是漫遊，則所指示的 WAP 可能不是最接近的物件，而且您甚至可以在建築物的不同基底，挑選一個 WAP。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-119">If the client is roaming, the WAP indicated may not be the closest one, and it's even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="e6cd5-120">若要指出位置是近似值，您可以在 location 值前面加上 **[Near]** 或 **[Closeto]** 描述項。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-120">To indicate that the location is approximate, you can prepend the location value with a **[Near]** or **[Closeto]** descriptor.</span></span>
  
<span data-ttu-id="e6cd5-121">這個位置方法假設每個 WAP 的 BSSID 都是靜態的。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="e6cd5-122">不過，如果您的 WAP 供應商使用的是動態指派的 BSSIDs，則從 WAP 取得的 BSSID 可能會變更（在 WAP 設定變更之後，可能會發生這種情況），而且無線用戶端可能不會收到位置。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don't receive a location.</span></span> <span data-ttu-id="e6cd5-123">若要防止這種可能性，您必須使用 ERLs，為每個 WAP 所使用的所有可能的 BSSID 位址填入位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span> 
  
## <a name="lldp-ports-and-switches"></a><span data-ttu-id="e6cd5-124">LLDP 埠和交換器</span><span class="sxs-lookup"><span data-stu-id="e6cd5-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="e6cd5-125">支援連結層探索通訊協定的受管理乙太網交換器：媒體端點探索（LLDP-MED-V）可將其身分識別和埠資訊宣告至 LLDP 相容的用戶端，然後可以針對 location 資料庫進行查詢，以提供裝置的位置。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-125">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device.</span></span> <span data-ttu-id="e6cd5-126">您可以將 ERLs 完全與交換器主機殼識別碼相關聯，或者您可以將它們對應到埠層級。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-126">You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6cd5-127">商務用 Skype 伺服器支援使用 LLDP-MED-V 來判斷只有 Lync Phone Edition 裝置和商務用 Skype 用戶端在 Windows 8 上執行的位置。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-127">Skype for Business Server supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Skype for Business clients running on Windows 8.</span></span> <span data-ttu-id="e6cd5-128">如果您需要使用交換器層級的第2層資料來判斷其他有線電腦版商務用 Skype Server 用戶端的位置，您必須使用用戶端 MAC 位址方法。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Skype for Business Server clients, you need to use the client MAC address method.</span></span> 
  
## <a name="subnet"></a><span data-ttu-id="e6cd5-129">子網路</span><span class="sxs-lookup"><span data-stu-id="e6cd5-129">Subnet</span></span>

<span data-ttu-id="e6cd5-130">第3層 IP 子網提供所有商務用 Skype Server 用戶端所支援的機制，可讓您自動偵測用戶端位置。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-130">Layer 3 IP subnets provide a mechanism supported by all Skype for Business Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="e6cd5-131">使用 IP 子網是設定及管理有線用戶端最簡單的位置方法。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="e6cd5-132">不過，在您決定要使用子網之前，請先使用下列問題來協助判斷子網的位置是否正確，才能準確找到用戶端：</span><span class="sxs-lookup"><span data-stu-id="e6cd5-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>
  
- <span data-ttu-id="e6cd5-133">一或多個用戶端子網涵蓋多個地面嗎？</span><span class="sxs-lookup"><span data-stu-id="e6cd5-133">Do one or more client subnets cover multiple floors?</span></span>
    
- <span data-ttu-id="e6cd5-134">一個或多個子網是否涵蓋了多個建築物？</span><span class="sxs-lookup"><span data-stu-id="e6cd5-134">Do one or more subnets cover more than one building?</span></span>
    
- <span data-ttu-id="e6cd5-135">每個用戶端子網上所覆蓋的占地空間是多少？</span><span class="sxs-lookup"><span data-stu-id="e6cd5-135">How much floor space is covered by each client subnet?</span></span>
    
<span data-ttu-id="e6cd5-136">如果子網覆蓋範圍太寬，您可能需要使用其他機制來尋找用戶端。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-136">If the subnet covers too broad an area, you may need to use another mechanism to locate clients.</span></span> <span data-ttu-id="e6cd5-137">不過，如果您有任何實際的情況，我們建議客戶重組其 IP 子網，以符合 ERL 位置的具體需求，而不是產生協力廠商 SNMP 解決方案的成本與複雜性。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-137">However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>
  
## <a name="client-mac-address"></a><span data-ttu-id="e6cd5-138">用戶端 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="e6cd5-138">Client MAC Address</span></span>

<span data-ttu-id="e6cd5-139">若要使用用戶端電腦的 MAC 位址來尋找來電者，您需要受管理的乙太網交換器，而且您必須部署可探索連線至（或透過）這些交換器之商務用 Skype 用戶端的 MAC 位址的協力廠商 SNMP 解決方案。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Skype for Business clients connected to (or through) those switches.</span></span> <span data-ttu-id="e6cd5-140">SNMP 解決方案會持續輪詢受管理的交換器，以取得連線至每個埠的端點 MAC 位址的目前對應，並取得對應的埠識別碼。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="e6cd5-141">在商務用 Skype 用戶端的位置資訊服務要求期間，位置資訊服務會使用用戶端的 MAC 位址來查詢協力廠商應用程式，然後傳回任何相符的切換 IP 位址和埠識別碼。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-141">During a Skype for Business client's request to the Location Information service, the Location Information service queries the third-party application by using the client's MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="e6cd5-142">位置資訊服務會使用此資訊來針對相符記錄查詢其發佈的 Layer 2 wiremap，並將位置傳回給用戶端。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="e6cd5-143">如果您使用這個選項，請確認 SNMP 應用程式與發佈的位置資料庫記錄之間的切換埠識別碼一致。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6cd5-144">某些協力廠商 SNMP 解決方案可以支援未受管理的存取交換器;如果服務商務用 Skype 用戶端的開關是未受管理的，但有一個上行連結到受管理的發佈交換器，則受管理的交換器可以向 SNMP 應用程式傳回連接至 access 開關之用戶端的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Skype for Business client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="e6cd5-145">此資訊可讓位置資訊服務識別使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="e6cd5-146">不過，您可以只將單一 ERL 指派給非託管交換器上的所有埠，因此只有在存取開關的主機殼層級（而非埠層級）才能使用位置的最高值。</span><span class="sxs-lookup"><span data-stu-id="e6cd5-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span> 
  

