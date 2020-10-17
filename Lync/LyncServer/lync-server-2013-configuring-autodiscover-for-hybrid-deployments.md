---
title: Lync Server 2013：設定混合式部署的自動探索
description: Lync Server 2013：設定混合式部署的自動探索。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6797e3f6b77e3016f6cef87f2a930f5a7c1fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562489"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="c914a-103">在 Lync Server 2013 中設定自動探索以進行混合部署</span><span class="sxs-lookup"><span data-stu-id="c914a-103">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c914a-104">_**主題上次修改日期：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="c914a-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="c914a-105">混合式部署是使用 Microsoft Lync Online cloud service 和內部部署的設定。</span><span class="sxs-lookup"><span data-stu-id="c914a-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="c914a-106">在此類型的設定中，自動探索服務必須能夠找到使用者實際所在的位置。</span><span class="sxs-lookup"><span data-stu-id="c914a-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="c914a-107">也就是說，「自動探索」會協助您尋找使用者帳戶，以及主控使用者帳戶之伺服器的所在位置，不論它位於內部部署或 Lync Online 部署中。</span><span class="sxs-lookup"><span data-stu-id="c914a-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="c914a-108">例如，如果使用者的帳戶是在 Lync Online 中的伺服器上主控，則嘗試尋找使用者的方法如下 *所示，* 在稱為「可探索」的程式中：</span><span class="sxs-lookup"><span data-stu-id="c914a-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="c914a-109">使用者發起對內部部署 **contoso.com**的連線嘗試。</span><span class="sxs-lookup"><span data-stu-id="c914a-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="c914a-110">嘗試會傳送至 lyncdiscover.contoso.com，這是與自動探索服務相關聯的 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="c914a-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="c914a-111">自動探索是指在 contoso.com 內部部署部署中假設的報名者集區，並且提供使用者實際主控伺服器主控于 Lync Online 的資訊。</span><span class="sxs-lookup"><span data-stu-id="c914a-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="c914a-112">自動探索接著會傳送使用者對 **lync.com** online 自動探索服務的參照。</span><span class="sxs-lookup"><span data-stu-id="c914a-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="c914a-113">使用者對 lync.com 線上自動探索服務發起連線嘗試，而且可以尋找使用者的帳戶和使用者的主伺服器。</span><span class="sxs-lookup"><span data-stu-id="c914a-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="c914a-114">若要讓用戶端能夠探索使用者主伺服器所在的部署，您必須使用新的統一資源定位器 (URL) 來設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="c914a-114">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="c914a-115">請執行下列動作來設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="c914a-115">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="c914a-116">設定混合部署的自動探索</span><span class="sxs-lookup"><span data-stu-id="c914a-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="c914a-117">在 [ [Lync Server 2013 的自動探索服務需求](lync-server-2013-autodiscover-service-requirements.md)] 中，您可以使用 Get-CsHostingProvider 來 ProxyFQDN 屬性中取得屬性值。</span><span class="sxs-lookup"><span data-stu-id="c914a-117">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="c914a-118">從 Lync Server 管理命令介面中，輸入</span><span class="sxs-lookup"><span data-stu-id="c914a-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="c914a-119">\[ \] 以共用 SIP 位址空間的功能變數名稱取代識別。</span><span class="sxs-lookup"><span data-stu-id="c914a-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c914a-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c914a-120">See Also</span></span>


[<span data-ttu-id="c914a-121">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="c914a-121">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="c914a-122">Get-cshostingprovider</span><span class="sxs-lookup"><span data-stu-id="c914a-122">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

