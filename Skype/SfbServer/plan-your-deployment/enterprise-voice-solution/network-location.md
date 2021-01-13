---
title: 定義用來判斷商務用 Skype Server 中的位置的網路元素
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 規劃用於將來電者對應至 E9-1-1 部署中商務用 Skype Server Enterprise Voice 之位置的網路元件時所需的決策。
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813633"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a><span data-ttu-id="0bedc-103">定義用來判斷商務用 Skype Server 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="0bedc-103">Define the network elements used to determine location in Skype for Business Server</span></span>
 
<span data-ttu-id="0bedc-104">規劃用於將來電者對應至 E9-1-1 部署中商務用 Skype Server Enterprise Voice 之位置的網路元件時所需的決策。</span><span class="sxs-lookup"><span data-stu-id="0bedc-104">Decisions necessary for planning which network components you will use to map callers to locations for E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0bedc-105">如果您設定商務用 Skype Server 基礎結構以支援自動用戶端位置偵測，您必須先決定要用來將來電者對應至位置的網路元素。</span><span class="sxs-lookup"><span data-stu-id="0bedc-105">If you are setting up your Skype for Business Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="0bedc-106">在商務用 Skype Server 中，您可以將下列 Layer 2 和 Layer 3 網路元素與位置相關聯：</span><span class="sxs-lookup"><span data-stu-id="0bedc-106">In Skype for Business Server, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>
  
- <span data-ttu-id="0bedc-107">無線存取點 (WAP) 基本服務組識別碼 (BSSID) 位址 (第 2 層)</span><span class="sxs-lookup"><span data-stu-id="0bedc-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>
    
- <span data-ttu-id="0bedc-108">LLDP 交換器連接埠 (第 2 層)</span><span class="sxs-lookup"><span data-stu-id="0bedc-108">LLDP switch port (Layer 2)</span></span>
    
- <span data-ttu-id="0bedc-109">LLDP 交換器底座識別碼 (第 2 層)</span><span class="sxs-lookup"><span data-stu-id="0bedc-109">LLDP switch chassis IDs (Layer 2)</span></span>
    
- <span data-ttu-id="0bedc-110">IP 子網路 (第 3 層)</span><span class="sxs-lookup"><span data-stu-id="0bedc-110">IP subnets (Layer 3)</span></span>
    
- <span data-ttu-id="0bedc-111">用戶端 MAC 位址 (第 2 層)</span><span class="sxs-lookup"><span data-stu-id="0bedc-111">Client MAC addresses (Layer 2)</span></span>
    
<span data-ttu-id="0bedc-112">網路元素會依照優先順序列出。</span><span class="sxs-lookup"><span data-stu-id="0bedc-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="0bedc-113">如果使用一個以上的網元可以找到用戶端，商務用 Skype 伺服器會使用優先順序的順序來決定要使用的機制。</span><span class="sxs-lookup"><span data-stu-id="0bedc-113">If a client can be located by using more than one network element, Skype for Business Server uses the order of precedence to determine which mechanism to use.</span></span> 
  
<span data-ttu-id="0bedc-114">下列各節會詳細說明每個網路元素的使用方式。</span><span class="sxs-lookup"><span data-stu-id="0bedc-114">The following sections provide more details for using each network element.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0bedc-115">當您使用網元將來電者對應至位置時，將位置資訊服務資料庫保持在最新狀態，這會是最為重要的。</span><span class="sxs-lookup"><span data-stu-id="0bedc-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="0bedc-116">例如，如果您新增或變更網路元素 (如新增 WAP)，則必須在位置資料庫中刪除舊項目並增加新項目。</span><span class="sxs-lookup"><span data-stu-id="0bedc-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span> 
  
## <a name="wireless-access-point"></a><span data-ttu-id="0bedc-117">無線存取點</span><span class="sxs-lookup"><span data-stu-id="0bedc-117">Wireless Access Point</span></span>

<span data-ttu-id="0bedc-118">當用戶端連線至無線網路時，「位置要求」會使用 WAP 的 BSSID 位址來判斷位置。</span><span class="sxs-lookup"><span data-stu-id="0bedc-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="0bedc-119">如果用戶端是漫遊，則表示的 WAP 可能不是最接近的狀態，而且也可以拾取位於不同的大樓地板的 WAP。</span><span class="sxs-lookup"><span data-stu-id="0bedc-119">If the client is roaming, the WAP indicated may not be the closest one, and it's even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="0bedc-120">若要指出位置是大致的，您可以在 location 值的前面加上 **[Near]** 或 **[Closeto]** 描述項。</span><span class="sxs-lookup"><span data-stu-id="0bedc-120">To indicate that the location is approximate, you can prepend the location value with a **[Near]** or **[Closeto]** descriptor.</span></span>
  
<span data-ttu-id="0bedc-121">此位置方法會假定每個 WAP 的 BSSID 為靜態。</span><span class="sxs-lookup"><span data-stu-id="0bedc-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="0bedc-122">不過，如果您的 WAP 廠商使用的是以動態方式指派的 BSSIDs，則從 WAP 取得的 BSSID 可能會變更 (在 WAP 設定變更) 之後可能會發生此情況，而且無線用戶端可能會在不會收到位置的情況下留下。</span><span class="sxs-lookup"><span data-stu-id="0bedc-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don't receive a location.</span></span> <span data-ttu-id="0bedc-123">若要避免這種可能性，您必須使用 Erl 填入 Location 資訊服務資料庫，以取得每個 WAP 所使用的所有可能的 BSSID 位址。</span><span class="sxs-lookup"><span data-stu-id="0bedc-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span> 
  
## <a name="lldp-ports-and-switches"></a><span data-ttu-id="0bedc-124">LLDP 連接埠和交換器</span><span class="sxs-lookup"><span data-stu-id="0bedc-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="0bedc-p106">支援 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 之受管理的乙太網路交換器，可將其識別碼及連接埠資訊公告至相容於 LLDP-MED 的用戶端，您可依位置資料庫查詢用戶端以提供裝置的位置。您可以僅在交換器底座辨識碼上建立 ERL 的關聯，或者可將其對應至連接埠層級。</span><span class="sxs-lookup"><span data-stu-id="0bedc-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0bedc-127">商務用 Skype Server 支援使用 LLDP-MED，判斷只有 Lync Phone Edition 裝置和在 Windows 8 上執行之商務用 Skype 用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="0bedc-127">Skype for Business Server supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Skype for Business clients running on Windows 8.</span></span> <span data-ttu-id="0bedc-128">如果您需要使用交換器層級2資料來判斷其他有線電腦型商務用 Skype Server 用戶端的位置，您必須使用用戶端 MAC 位址方法。</span><span class="sxs-lookup"><span data-stu-id="0bedc-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Skype for Business Server clients, you need to use the client MAC address method.</span></span> 
  
## <a name="subnet"></a><span data-ttu-id="0bedc-129">子網路</span><span class="sxs-lookup"><span data-stu-id="0bedc-129">Subnet</span></span>

<span data-ttu-id="0bedc-130">第3層 IP 子網可提供所有商務用 Skype Server 用戶端所支援的機制，以自動偵測用戶端位置。</span><span class="sxs-lookup"><span data-stu-id="0bedc-130">Layer 3 IP subnets provide a mechanism supported by all Skype for Business Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="0bedc-131">使用 IP 子網路是設定與管理有線用戶端之最容易的方法。</span><span class="sxs-lookup"><span data-stu-id="0bedc-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="0bedc-132">決定使用子網路前，請先詢問自己下列問題來判斷子網路的位置是否明確到足以正確定位用戶端：</span><span class="sxs-lookup"><span data-stu-id="0bedc-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>
  
- <span data-ttu-id="0bedc-133">一個或多個用戶端子網路是否涵蓋多個樓層？</span><span class="sxs-lookup"><span data-stu-id="0bedc-133">Do one or more client subnets cover multiple floors?</span></span>
    
- <span data-ttu-id="0bedc-134">一個或多個子網路是否涵蓋多棟建築？</span><span class="sxs-lookup"><span data-stu-id="0bedc-134">Do one or more subnets cover more than one building?</span></span>
    
- <span data-ttu-id="0bedc-135">每個用戶端子網路涵蓋多少樓層空間？</span><span class="sxs-lookup"><span data-stu-id="0bedc-135">How much floor space is covered by each client subnet?</span></span>
    
<span data-ttu-id="0bedc-p109">如果子網路涵蓋的區域太廣，您可能必須使用其他機制尋找用戶端。但是，以實際應用而言，建議您重新組織其 IP 子網路連線以符合 ERL 位置的精確性需求，才不會提高協力廠商 SNMP 解決方案的成本和複雜性。</span><span class="sxs-lookup"><span data-stu-id="0bedc-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>
  
## <a name="client-mac-address"></a><span data-ttu-id="0bedc-138">用戶端 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="0bedc-138">Client MAC Address</span></span>

<span data-ttu-id="0bedc-139">若要使用用戶端電腦的 MAC 位址來尋找來電者，您需要受管理的乙太網參數，而且您必須部署協力廠商的 SNMP 解決方案，以探索連線至 (或透過) 那些參數的商務用 Skype 用戶端 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="0bedc-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Skype for Business clients connected to (or through) those switches.</span></span> <span data-ttu-id="0bedc-140">SNMP 解決方案會持續輪詢受管理交換器以取得連線至每個連接埠之端點 MAC 位址目前的對應，以及取得對應的連接埠識別碼。</span><span class="sxs-lookup"><span data-stu-id="0bedc-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="0bedc-141">在商務用 Skype 用戶端對位置資訊服務的要求中，位置資訊服務會使用用戶端的 MAC 位址查詢協力廠商應用程式，然後傳回任何相符的交換器 IP 位址和埠 IDs。</span><span class="sxs-lookup"><span data-stu-id="0bedc-141">During a Skype for Business client's request to the Location Information service, the Location Information service queries the third-party application by using the client's MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="0bedc-142">位置資訊服務使用此資訊來查詢其發佈的第2層線路圖，以取得相符的記錄，並將位置傳回給用戶端。</span><span class="sxs-lookup"><span data-stu-id="0bedc-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="0bedc-143">如果您使用此選項，請確認 SNMP 應用程式以及已發行的位置資料庫記錄之間的交換器連接埠識別項是一致的。</span><span class="sxs-lookup"><span data-stu-id="0bedc-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0bedc-144">某些協力廠商的 SNMP 解決方案可支援未受管理的存取參數;如果服務商務用 Skype 用戶端的參數未受管理，但有連結至受管理的發行參數，則受管理的參數可以傳回 SNMP 應用程式連接至 access 參數的用戶端 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="0bedc-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Skype for Business client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="0bedc-145">此資訊可讓位置資訊服務識別使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="0bedc-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="0bedc-146">不過，可能只會將單一 ERL 指派至未受管理之交換器上的所有連接埠，所以只有在存取交換器的底座層級才能取得明確的位置，而非連接埠層級。</span><span class="sxs-lookup"><span data-stu-id="0bedc-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span> 
  

