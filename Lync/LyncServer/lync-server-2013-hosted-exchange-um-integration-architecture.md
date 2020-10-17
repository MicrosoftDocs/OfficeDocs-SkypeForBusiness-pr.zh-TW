---
title: Lync Server 2013：主控 Exchange UM 整合架構
description: Lync Server 2013：主控 Exchange UM 整合架構。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2399fa421b59a5ea1fd83b1a86225fc12de1f2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552459"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="2edb9-103">Lync Server 2013 中的主控 Exchange UM 整合架構</span><span class="sxs-lookup"><span data-stu-id="2edb9-103">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2edb9-104">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="2edb9-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="2edb9-105">Lync Server 2013 ExUM 路由應用程式支援與內部部署 Exchange 整合通訊 (UM) 部署，Exchange UM 是由服務提供者所主控，或是結合兩者的組合。</span><span class="sxs-lookup"><span data-stu-id="2edb9-105">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="2edb9-106">下圖顯示所有三種可能性。</span><span class="sxs-lookup"><span data-stu-id="2edb9-106">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="2edb9-107">**與內部部署 Exchange UM 和兩個託管式 Exchange 提供者整合**</span><span class="sxs-lookup"><span data-stu-id="2edb9-107">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="2edb9-108">![內部部署 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")</span><span class="sxs-lookup"><span data-stu-id="2edb9-108">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="2edb9-109">支援下列模式：</span><span class="sxs-lookup"><span data-stu-id="2edb9-109">The following modes are supported:</span></span>

  - <span data-ttu-id="2edb9-110">**內部部署：** Lync Server 2013 和 Exchange UM 都部署于您企業內的本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="2edb9-110">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="2edb9-111">**跨部署部署：** Lync Server 2013 部署于您企業內的本機伺服器上，而 Exchange UM 是以線上服務提供者的功能（例如 Microsoft Exchange Online 資料中心）主控。</span><span class="sxs-lookup"><span data-stu-id="2edb9-111">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="2edb9-112">**混合式部署：** 您的 Lync Server 2013 部署的某些使用者信箱位於您企業內部的本地 Exchange 伺服器上，而某些信箱位於裝載的 Exchange 服務資料中心。</span><span class="sxs-lookup"><span data-stu-id="2edb9-112">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2edb9-113">混合部署可以作為過渡解決方案 (例如進行評估以及將使用者分階段移轉至託管式 Exchange UM 的期間) 或永久解決方案 (如果您在進行部分移轉後，決定將其餘使用者的 Exchange UM 服務繼續留在內部部署)。</span><span class="sxs-lookup"><span data-stu-id="2edb9-113">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="2edb9-114">共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="2edb9-114">Shared SIP Address Space</span></span>

<span data-ttu-id="2edb9-115">若要整合 Lync Server 2013 與內部部署 Exchange UM 部署，您可以授與 Lync Server 2013 讀取 Exchange UM Active Directory 網域服務物件的許可權。</span><span class="sxs-lookup"><span data-stu-id="2edb9-115">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="2edb9-116">不過，此方法不適用於與主控 Exchange UM 整合，但由於 Lync Server 2013 和 Exchange UM 安裝在不同的樹系中，且彼此之間並無任何信任。</span><span class="sxs-lookup"><span data-stu-id="2edb9-116">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="2edb9-117">若要整合 Lync Server 2013 與主控 Exchange UM，您必須設定 *共用 SIP 位址空間*。</span><span class="sxs-lookup"><span data-stu-id="2edb9-117">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="2edb9-118">在此設定中，Lync Server 2013 和主控 Exchange UM 服務提供者也可以使用相同的 SIP 網域位址空間。</span><span class="sxs-lookup"><span data-stu-id="2edb9-118">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2edb9-119">共用 SIP 位址空間的使用方式類似于跨部署 Lync Server 2013 環境中所使用的方法，在此環境中，有些使用者是位於內部部署的部署中，有些則是駐留在主控部署 (例如 Lync Online) 中。</span><span class="sxs-lookup"><span data-stu-id="2edb9-119">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="2edb9-120">SIP 網域被這兩者分割。</span><span class="sxs-lookup"><span data-stu-id="2edb9-120">The SIP domain is split between them.</span></span> <span data-ttu-id="2edb9-121">當您整合 Lync Server 2013 與主控 Exchange UM 時，請確定您在共用 SIP 位址空間中包含 Exchange UM 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="2edb9-121">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="2edb9-122">若要設定共用 SIP 位址空間以便與 Exchange UM 服務提供者整合，您必須如下設定 Edge Server：</span><span class="sxs-lookup"><span data-stu-id="2edb9-122">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="2edb9-123">設定 Edge Server 進行同盟，作法為執行 **Set-CsAccessEdgeConfiguration** Cmdlet 以設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="2edb9-123">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="2edb9-124">**UseDnsSrvRouting** 指定 Edge Server 傳送和接收同盟要求時將依賴 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="2edb9-124">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="2edb9-p105">**AllowFederatedUsers** 指定是否允許內部使用者與同盟網域的使用者進行通訊。此屬性也會判斷內部使用者是否可與分割網域案例中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="2edb9-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="2edb9-127">**EnablePartnerDiscovery** 指定 Lync Server 2013 是否會使用 DNS 記錄，嘗試探索 Active Directory 允許的網域清單中未列出的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="2edb9-127">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="2edb9-128">若為 False，Lync Server 2013 只會與在允許的網域清單上找到的網域進行同盟。</span><span class="sxs-lookup"><span data-stu-id="2edb9-128">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="2edb9-129">如果使用 DNS 服務路由，則需要此參數。</span><span class="sxs-lookup"><span data-stu-id="2edb9-129">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="2edb9-130">在大多數部署中，此值設定為 False，以免對所有合作夥伴開放同盟。</span><span class="sxs-lookup"><span data-stu-id="2edb9-130">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="2edb9-131">將中央管理存放區複製到 Edge Server 並確認複寫。</span><span class="sxs-lookup"><span data-stu-id="2edb9-131">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="2edb9-132">如需詳細資訊，請參閱部署檔中的 [匯出 Lync Server 2013 拓撲並將其複製到 edge 安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) 。</span><span class="sxs-lookup"><span data-stu-id="2edb9-132">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="2edb9-133">在 Edge Server 上設定 *「裝載提供者」*，作法是執行 **New-CsHostingProvider** Cmdlet 以設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="2edb9-133">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="2edb9-134">**Identity** 為所建立的裝載提供者指定唯一的字串值識別碼，例如 **Hosted Exchange UM**。</span><span class="sxs-lookup"><span data-stu-id="2edb9-134">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="2edb9-p108">**Enabled** 指出網域與裝載提供者之間的網路連線是否已啟用。必須設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="2edb9-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="2edb9-p109">**EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。必須設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="2edb9-p109">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="2edb9-139">**HostsOCSUsers** 會指出裝載提供者是否是用來裝載 Lync Server 2013 帳戶。</span><span class="sxs-lookup"><span data-stu-id="2edb9-139">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="2edb9-140">必須設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="2edb9-140">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="2edb9-141">**ProxyFQDN** 指定裝載提供者所使用之 Proxy 伺服器的完整網域名稱 (FQDN)，例如 **proxyserver.fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="2edb9-141">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="2edb9-142">如需此資訊，請與您的裝載提供者連絡。</span><span class="sxs-lookup"><span data-stu-id="2edb9-142">Contact your hosting provider for this information.</span></span> <span data-ttu-id="2edb9-143">您無法修改此值。</span><span class="sxs-lookup"><span data-stu-id="2edb9-143">This value cannot be modified.</span></span> <span data-ttu-id="2edb9-144">如果裝載提供者變更其 Proxy 伺服器，您必須刪除再重新建立該提供者的項目。</span><span class="sxs-lookup"><span data-stu-id="2edb9-144">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="2edb9-145">**IsLocal** 指出主控提供者所使用的 proxy 伺服器是否包含在您的 Lync server 2013 拓撲中。</span><span class="sxs-lookup"><span data-stu-id="2edb9-145">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="2edb9-146">必須設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="2edb9-146">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

