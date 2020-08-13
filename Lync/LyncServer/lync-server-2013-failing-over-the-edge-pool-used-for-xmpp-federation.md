---
title: Lync Server 2013：容錯移轉用於 XMPP 同盟的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aee795b6f4dd1f3ff1077fb739cad9709b2c8ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="557d2-102">在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="557d2-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="557d2-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="557d2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="557d2-p101">在您的組織中，有一個指定的 Edge 集區是用於 XMPP 同盟的集區。如果此集區失效，您必須先容錯移轉 XMPP 同盟以使用不同的 Edge 集區，讓 XMPP 同盟可以再次運作。</span><span class="sxs-lookup"><span data-stu-id="557d2-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="557d2-106">當您第一次安裝 Edge 集區並啟用 XMPP 同盟時，可以藉由為所有適用於 XMPP 同盟的 Edge 集區 (而不是只針對其中一個) 設定外部 DNS SRV 記錄，來簡化災害復原程序。</span><span class="sxs-lookup"><span data-stu-id="557d2-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="557d2-107">其中的每一個 SRV 記錄都必須設定不同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="557d2-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="557d2-108">所有的 XMPP 同盟流量都會通過優先順序最高且含有 SRV 記錄的集區。</span><span class="sxs-lookup"><span data-stu-id="557d2-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="557d2-109">如需啟用及設定 XMPP 同盟的詳細資訊，請參閱 [在 Lync Server 2013 中設定 XMPP 同盟](lync-server-2013-setting-up-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="557d2-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="557d2-110">在下列程序中，EdgePool1 是原本裝載 XMPP 同盟的集區，而 EdgePool2 是現在裝載 XMPP 同盟的集區。</span><span class="sxs-lookup"><span data-stu-id="557d2-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="557d2-111">容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="557d2-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="557d2-112">如果您尚未部署其他 Edge 集區 (除了目前中斷的這一個集區)，請部署該集區。</span><span class="sxs-lookup"><span data-stu-id="557d2-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="557d2-113">如需詳細資訊，請參閱 [在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="557d2-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="557d2-114">在現在將裝載 XMPP 同盟之新 Edge 集區 (EdgePool2) 中的每個 Edge Server 上，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="557d2-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="557d2-115">執行下列 Cmdlet，將 XMPP 同盟路由重新指向 EdgePool2：</span><span class="sxs-lookup"><span data-stu-id="557d2-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="557d2-116">在此範例中，Site2 為包含現在將裝載 XMPP 同盟路由之 Edge 集區的網站，而 EdgeServer2.contoso.com 為該集區中 Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="557d2-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="557d2-117">在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="557d2-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="557d2-p104">如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。</span><span class="sxs-lookup"><span data-stu-id="557d2-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="557d2-120">確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。</span><span class="sxs-lookup"><span data-stu-id="557d2-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="557d2-121">在現在將裝載 XMPP 同盟之 Edge 集區中的所有 Edge Server 上啟動服務：</span><span class="sxs-lookup"><span data-stu-id="557d2-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

