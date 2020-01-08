---
title: Lync Server 2013：容錯移轉用於 XMPP 同盟的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="3dac5-102">在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="3dac5-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dac5-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3dac5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3dac5-104">在您的組織中，有一個 Edge 池指定為要用於 XMPP 同盟的池。</span><span class="sxs-lookup"><span data-stu-id="3dac5-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="3dac5-105">如果此池向下移動，您必須容錯移轉 XMPP 同盟，才能使用不同的邊緣池，然後 XMPP 同盟才能再次運作。</span><span class="sxs-lookup"><span data-stu-id="3dac5-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="3dac5-106">當您第一次安裝 Edge 池並啟用 XMPP 同盟時，您可以針對所有的邊緣池設定外部 DNS SRV 記錄（而不只是一個），來簡化災害復原程式。</span><span class="sxs-lookup"><span data-stu-id="3dac5-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="3dac5-107">這些 SRV 記錄中的每一個都必須設定不同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="3dac5-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="3dac5-108">所有 XMPP 聯盟流量都是透過擁有最高優先順序的 SRV 記錄的池中進行。</span><span class="sxs-lookup"><span data-stu-id="3dac5-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="3dac5-109">如需啟用及設定 XMPP 同盟的詳細資訊，請參閱[在 Lync Server 2013 中設定 XMPP 同盟](lync-server-2013-setting-up-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="3dac5-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="3dac5-110">在下列程式中，EdgePool1 是最初託管 XMPP 同盟的池，而 EdgePool2 是該池，現在將託管 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="3dac5-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="3dac5-111">針對用於 XMPP 同盟的邊緣池進行容錯移轉</span><span class="sxs-lookup"><span data-stu-id="3dac5-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="3dac5-112">如果您還沒有部署另一個 Edge 池（除了目前已停機），請部署該池。</span><span class="sxs-lookup"><span data-stu-id="3dac5-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="3dac5-113">如需詳細資訊，請參閱[在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3dac5-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="3dac5-114">在新 Edge 池中的每個 Edge 伺服器上，現在將會主控 XMPP 同盟（EdgePool2），請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3dac5-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="3dac5-115">執行下列 Cmdlet，以 repoint XMPP 同盟路由至 EdgePool2：</span><span class="sxs-lookup"><span data-stu-id="3dac5-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="3dac5-116">在這個範例中，Site2 是包含邊緣池的網站，現在將託管 XMPP 同盟路由，而 EdgeServer2.contoso.com 是該池中的邊緣伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3dac5-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="3dac5-117">在外部 DNS 伺服器上，將 XMPP 同盟的 DNS A 記錄變更為指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3dac5-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="3dac5-118">如果您還沒有可解析到 Edge 池的 XMPP 同盟的 DNS SRV 記錄，而該內容現在將託管 XMPP 同盟，您必須新增該記錄，如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="3dac5-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="3dac5-119">這個 SRV 記錄的埠值必須是5269。</span><span class="sxs-lookup"><span data-stu-id="3dac5-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="3dac5-120">確認現在將由 XMPP 同盟託管的邊緣池已在外部開啟埠5269。</span><span class="sxs-lookup"><span data-stu-id="3dac5-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="3dac5-121">在邊緣池中的所有邊緣伺服器上啟動服務，現在將會託管 XMPP federation：</span><span class="sxs-lookup"><span data-stu-id="3dac5-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

