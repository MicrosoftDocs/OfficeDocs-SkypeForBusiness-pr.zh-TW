---
title: Lync Server 2013：主控 Exchange UM 整合架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="38b5f-102">Lync Server 2013 中的主控 Exchange UM 整合架構</span><span class="sxs-lookup"><span data-stu-id="38b5f-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38b5f-103">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="38b5f-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="38b5f-104">Lync Server 2013 ExUM 路由應用程式支援與內部部署 Exchange 整合通訊（UM）部署、由服務提供者託管 Exchange UM，或是結合兩個。</span><span class="sxs-lookup"><span data-stu-id="38b5f-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="38b5f-105">下圖顯示所有這三種可能性。</span><span class="sxs-lookup"><span data-stu-id="38b5f-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="38b5f-106">**與內部部署 Exchange UM 部署和兩個託管的 Exchange 提供者整合**</span><span class="sxs-lookup"><span data-stu-id="38b5f-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="38b5f-107">內部部署 lync ![Server EXCHANGE Um 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 LYNC Server exchange um 部署")</span><span class="sxs-lookup"><span data-stu-id="38b5f-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="38b5f-108">支援下列模式：</span><span class="sxs-lookup"><span data-stu-id="38b5f-108">The following modes are supported:</span></span>

  - <span data-ttu-id="38b5f-109">**內部部署：** Lync Server 2013 和 Exchange UM 都部署在企業中的本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="38b5f-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="38b5f-110">**跨內部部署：** Lync Server 2013 是部署在企業內部的本機伺服器上，而 Exchange UM 是在線上服務提供者的功能（例如 Microsoft Exchange Online 資料中心）中託管。</span><span class="sxs-lookup"><span data-stu-id="38b5f-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="38b5f-111">**混合式部署：** 您的 Lync Server 2013 部署會有一些使用者信箱駐留在企業內部的本機 Exchange 伺服器上，而某些信箱則駐留在託管 Exchange 服務資料中心。</span><span class="sxs-lookup"><span data-stu-id="38b5f-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38b5f-112">如果您在轉移其他使用者的 Exchange UM 服務之後，您選擇將混合式部署作為過渡式解決方案，在使用者的評估與分階段遷移期間，就可以使用。</span><span class="sxs-lookup"><span data-stu-id="38b5f-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="38b5f-113">共用的 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="38b5f-113">Shared SIP Address Space</span></span>

<span data-ttu-id="38b5f-114">若要將 Lync Server 2013 與內部部署 Exchange UM 部署整合，您必須授與 Lync Server 2013 許可權，才能讀取 Exchange UM Active Directory 網域服務物件。</span><span class="sxs-lookup"><span data-stu-id="38b5f-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="38b5f-115">不過，這個方法不適用於與託管 Exchange UM 整合，因為 Lync Server 2013 和 Exchange UM 已安裝在不同的林中，且不受信任。</span><span class="sxs-lookup"><span data-stu-id="38b5f-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="38b5f-116">若要整合 Lync Server 2013 與託管 Exchange UM，您必須設定*共用的 SIP 位址空間*。</span><span class="sxs-lookup"><span data-stu-id="38b5f-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="38b5f-117">在此設定中，Lync Server 2013 和託管 Exchange UM 服務提供者都能使用相同的 SIP 網域位址空間。</span><span class="sxs-lookup"><span data-stu-id="38b5f-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38b5f-118">使用共用的 SIP 位址空間與跨平臺 Lync Server 2013 環境中使用的方法類似，在這種情況下，有些使用者是駐留在內部部署的部署中，而有些則是駐留在託管部署（例如 Lync Online）中。</span><span class="sxs-lookup"><span data-stu-id="38b5f-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="38b5f-119">SIP 網域是在它們之間分割。</span><span class="sxs-lookup"><span data-stu-id="38b5f-119">The SIP domain is split between them.</span></span> <span data-ttu-id="38b5f-120">當您將 Lync Server 2013 與託管 Exchange UM 整合時，請確定您在共用的 SIP 位址空間中包含 Exchange UM 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="38b5f-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="38b5f-121">若要設定共用的 SIP 位址空間以與 Exchange UM 服務提供者整合，您需要設定 Edge 伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="38b5f-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="38b5f-122">您可以執行**CsAccessEdgeConfiguration** Cmdlet 來設定下列參數，為同盟設定 Edge 伺服器：</span><span class="sxs-lookup"><span data-stu-id="38b5f-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="38b5f-123">\*\*UseDnsSrvRouting \*\* 指定 Edge Server 傳送和接收同盟要求時將依賴 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="38b5f-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="38b5f-p105">\*\*AllowFederatedUsers \*\* 指定是否允許內部使用者與同盟網域的使用者進行通訊。此屬性也會判斷內部使用者是否可與分割網域案例中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="38b5f-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="38b5f-126">**EnablePartnerDiscovery**指定 Lync Server 2013 是否會使用 DNS 記錄來嘗試探索未列在 Active Directory 允許網域清單中的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="38b5f-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="38b5f-127">如果是 False，Lync Server 2013 將只會與在 [允許的網域] 清單中找到的網域進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="38b5f-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="38b5f-128">如果使用 DNS 服務路由，則需要此參數。</span><span class="sxs-lookup"><span data-stu-id="38b5f-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="38b5f-129">在大多數部署中，此值設定為 False，以免對所有合作夥伴開放同盟。</span><span class="sxs-lookup"><span data-stu-id="38b5f-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="38b5f-130">將中央管理存儲複製到 Edge 伺服器並驗證複製。</span><span class="sxs-lookup"><span data-stu-id="38b5f-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="38b5f-131">如需詳細資訊，請參閱[匯出 Lync Server 2013 拓撲，並將其複製到外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)，以在部署檔中進行 edge 安裝。</span><span class="sxs-lookup"><span data-stu-id="38b5f-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="38b5f-132">若要在 Edge 伺服器上設定*主機服務提供者*，請執行**新的 CsHostingProvider** Cmdlet 來設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="38b5f-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="38b5f-133">身分**識別**會為您建立的主機服務提供者（例如，**託管 Exchange UM**）指定唯一的字串值識別碼。</span><span class="sxs-lookup"><span data-stu-id="38b5f-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="38b5f-134">\*\*Enabled \*\* 指出網域與裝載提供者之間的網路連線是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="38b5f-134">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="38b5f-135">必須設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="38b5f-135">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="38b5f-136">**EnabledSharedAddressSpace**表示主機服務提供者是否將用於共用的 SIP 位址空間案例中。</span><span class="sxs-lookup"><span data-stu-id="38b5f-136">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="38b5f-137">必須設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="38b5f-137">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="38b5f-138">**HostsOCSUsers**指出主機服務提供者是否是用來託管 Lync Server 2013 帳戶。</span><span class="sxs-lookup"><span data-stu-id="38b5f-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="38b5f-139">必須設為**False**。</span><span class="sxs-lookup"><span data-stu-id="38b5f-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="38b5f-140">**ProxyFQDN**會指定主機服務提供者所使用之 proxy 伺服器的完整功能變數名稱（FQDN），例如**proxyserver.fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="38b5f-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="38b5f-141">請與您的主機提供者聯繫以取得此資訊。</span><span class="sxs-lookup"><span data-stu-id="38b5f-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="38b5f-142">您無法修改此值。</span><span class="sxs-lookup"><span data-stu-id="38b5f-142">This value cannot be modified.</span></span> <span data-ttu-id="38b5f-143">如果主機服務提供者變更其 proxy 伺服器，您將需要刪除該提供者的專案，然後重新建立。</span><span class="sxs-lookup"><span data-stu-id="38b5f-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="38b5f-144">**IsLocal**會指出主機服務提供者所使用的 proxy 伺服器是否包含在您的 Lync server 2013 拓撲中。</span><span class="sxs-lookup"><span data-stu-id="38b5f-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="38b5f-145">必須設為**False**。</span><span class="sxs-lookup"><span data-stu-id="38b5f-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

