---
title: 將 Edge Server 設定為與主控 Exchange UM 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a801ba4bf5f67eeda2eb760b3f639bac4cd13b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="50e43-102">將 Edge Server 設定為與主控 Exchange UM 整合</span><span class="sxs-lookup"><span data-stu-id="50e43-102">Configure the Edge Server for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50e43-103">_**主題上次修改日期：** 2015-01-23_</span><span class="sxs-lookup"><span data-stu-id="50e43-103">_**Topic Last Modified:** 2015-01-23_</span></span>

<span data-ttu-id="50e43-104">若要為您的 Lync Server 2013 使用者提供託管 Exchange 整合訊息（UM）上的語音信箱功能，您必須在 Edge 伺服器上執行下列設定工作：</span><span class="sxs-lookup"><span data-stu-id="50e43-104">To provide your Lync Server 2013 users with voice mail capabilities on hosted Exchange Unified Messaging (UM), you must perform the following configuration tasks on the Edge Server:</span></span>

  - <span data-ttu-id="50e43-105">設定同盟的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="50e43-105">Configure the Edge Server for federation.</span></span>

  - <span data-ttu-id="50e43-106">將中央管理儲存資料複製到 Edge 伺服器並驗證複製。</span><span class="sxs-lookup"><span data-stu-id="50e43-106">Replicate Central Management store data to the Edge Server and verify the replication.</span></span>

  - <span data-ttu-id="50e43-107">在 Edge Server 上建立裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="50e43-107">Create a hosting provider on the Edge Server.</span></span>

<span data-ttu-id="50e43-108">如需詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="50e43-108">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="50e43-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="50e43-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="50e43-110">[新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="50e43-110">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="50e43-111">您必須針對裝載的 Exchange 服務建立外部 DNS SRV 記錄，再執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="50e43-111">You must create an external DNS SRV record for the hosting Exchange service before you perform these steps.</span></span> <span data-ttu-id="50e43-112">如需詳細資訊，請參閱<A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">建立與託管 EXCHANGE UM 整合的 DNS SRV 記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="50e43-112">For details, see <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Create a DNS SRV record for integration with hosted Exchange UM</A>.</span></span>



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a><span data-ttu-id="50e43-113">若要設定同盟的 Edge Server</span><span class="sxs-lookup"><span data-stu-id="50e43-113">To configure the Edge Server for federation</span></span>

1.  <span data-ttu-id="50e43-114">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="50e43-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="50e43-p102">執行 Set-CsAccessEdgeConfiguration Cmdlet 設定同盟的伺服器。例如，執行：</span><span class="sxs-lookup"><span data-stu-id="50e43-p102">Run the Set-CsAccessEdgeConfiguration cmdlet to configure the server for federation. For example, run:</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    <span data-ttu-id="50e43-117">上述範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="50e43-117">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="50e43-118">\*\*UseDnsSrvRouting \*\* 指定 Edge Server 傳送和接收同盟要求時將依賴 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="50e43-118">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="50e43-p103">\*\*AllowFederatedUsers \*\* 指定是否允許內部使用者與同盟網域的使用者進行通訊。此屬性也會判斷內部使用者是否可與分割網域案例中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="50e43-p103">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="50e43-121">**EnablePartnerDiscovery**指定 Lync Server 是否將使用 DNS 記錄來嘗試探索未列在 Active Directory 允許網域清單中的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="50e43-121">**EnablePartnerDiscovery** specifies whether Lync Server will use DNS records to try to discover partner domains not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="50e43-122">如果是 False，Lync Server 2013 將只會與在 [允許的網域] 清單中找到的網域聯盟。</span><span class="sxs-lookup"><span data-stu-id="50e43-122">If False, Lync Server 2013 will only federate with domains found on the allowed domains list.</span></span> <span data-ttu-id="50e43-123">如果使用 DNS 服務路由，則需要此參數。</span><span class="sxs-lookup"><span data-stu-id="50e43-123">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="50e43-124">在大多數部署中，此值設定為 False，以免對所有合作夥伴開放同盟。</span><span class="sxs-lookup"><span data-stu-id="50e43-124">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a><span data-ttu-id="50e43-125">若要將資料複寫到 Edge Server 並確認複寫</span><span class="sxs-lookup"><span data-stu-id="50e43-125">To replicate data to the Edge Server and verify the replication</span></span>

  - <span data-ttu-id="50e43-126">確認複寫至 Edge Server 的作業已完成。</span><span class="sxs-lookup"><span data-stu-id="50e43-126">Verify that the replication to the Edge Server is complete.</span></span> <span data-ttu-id="50e43-127">如需程式，請參閱[在 Lync Server 2013 中驗證內部伺服器與邊緣伺服器之間](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)的連線。</span><span class="sxs-lookup"><span data-stu-id="50e43-127">For the procedure, see [Verify connectivity between internal servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span></span>

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="50e43-128">若要在 Edge Server 上建立裝載提供者</span><span class="sxs-lookup"><span data-stu-id="50e43-128">To create a hosting provider on the Edge Server</span></span>

1.  <span data-ttu-id="50e43-129">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="50e43-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="50e43-130">執行 **New-CsHostingProvider** Cmdlet 以設定裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="50e43-130">Run the **New-CsHostingProvider** cmdlet to configure the hosting provider.</span></span> <span data-ttu-id="50e43-131">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="50e43-131">For example, run:</span></span>
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="50e43-132">上述範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="50e43-132">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="50e43-p107">\*\*Identity \*\* 會為您建立的裝載提供者指定唯一字串值識別碼，此範例中為 \*\*Fabrikam.com \*\*。請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。</span><span class="sxs-lookup"><span data-stu-id="50e43-p107">**Identity** specifies a unique string value identifier for the hosting provider you are creating, in this example, **Fabrikam.com**. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="50e43-p108">\*\*Enabled \*\* 指出網域與裝載提供者之間的網路連線是否已啟用。只有將此值設為 \*\*True \*\*，才能在兩個組織之間交換訊息。</span><span class="sxs-lookup"><span data-stu-id="50e43-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="50e43-137">\*\*EnabledSharedAddressSpace \*\* 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。</span><span class="sxs-lookup"><span data-stu-id="50e43-137">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="50e43-138">在您設定<CODE>EnableSharedAddressSpace</CODE>為 True 之前，請先嘗試在內部解析同盟 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="50e43-138">Before you set <CODE>EnableSharedAddressSpace</CODE> to True, try to resolve the Federation SRV record internally.</span></span> <span data-ttu-id="50e43-139">如果您無法在內部解析此記錄，則需要建立記錄，_sipfederationtls。 _tcp。&lt;網域&gt;和 _sip _tls。&lt;內部&gt; DNS 中的網域。</span><span class="sxs-lookup"><span data-stu-id="50e43-139">If this record cannot be resolved internally, then you need to create the records, _sipfederationtls._tcp.&lt;domain&gt; and _sip._tls.&lt;domain&gt; in the internal DNS.</span></span> <span data-ttu-id="50e43-140">這些記錄應指向 Edge Server 的 Access 介面的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="50e43-140">These records should point to the external IP address of the Access Interface of the Edge Server.</span></span>

        
        </div>
    
      - <span data-ttu-id="50e43-141">**HostsOCSUsers**指出主機服務提供者是否是用來託管 Lync Server 2013 帳戶。</span><span class="sxs-lookup"><span data-stu-id="50e43-141">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="50e43-142">如果為 \*\*False \*\*，則提供者會裝載其他帳戶類型，例如 Microsoft Exchange 帳戶。</span><span class="sxs-lookup"><span data-stu-id="50e43-142">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="50e43-p111">\*\*ProxyFQDN \*\* 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)，此範例中為 \*\*proxyserver.fabrikam.com \*\*。您無法修改此值。如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。</span><span class="sxs-lookup"><span data-stu-id="50e43-p111">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, in this example, **proxyserver.fabrikam.com**. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="50e43-146">**IsLocal**會指出主機服務提供者所使用的 proxy 伺服器是否包含在您的 Lync server 2013 拓撲中。</span><span class="sxs-lookup"><span data-stu-id="50e43-146">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span>
    
      - <span data-ttu-id="50e43-147">\*\*VerficationLevel \*\* 指出傳送至裝載提供者或從裝載提供者發出之訊息的允許驗證層級。</span><span class="sxs-lookup"><span data-stu-id="50e43-147">**VerficationLevel** indicates the allowed verification level for messages sent to and from the hosted provider.</span></span> <span data-ttu-id="50e43-148">指定 **UseSourceVerification**，其依賴包含在裝載提供者發出之訊息內的驗證層級。</span><span class="sxs-lookup"><span data-stu-id="50e43-148">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="50e43-149">如果沒有指定這個層級，訊息會視為無法驗證而被拒絕。</span><span class="sxs-lookup"><span data-stu-id="50e43-149">If this level is not specified, then the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50e43-150">請參閱</span><span class="sxs-lookup"><span data-stu-id="50e43-150">See Also</span></span>


[<span data-ttu-id="50e43-151">匯出 Lync Server 2013 拓撲並將拓撲複製到 Edge 安裝的外部媒體</span><span class="sxs-lookup"><span data-stu-id="50e43-151">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[<span data-ttu-id="50e43-152">在 Lync Server 2013 中驗證內部伺服器和 Edge Server 之間的連線</span><span class="sxs-lookup"><span data-stu-id="50e43-152">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


<span data-ttu-id="50e43-153">[新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="50e43-153">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

