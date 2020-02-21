---
title: Lync Server 2013： 設定自動探索的混合式部署
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
ms.openlocfilehash: d6015603d2c8c151cbe9d9b76410e51708f3ba9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="28b19-102">Lync Server 2013 中設定自動探索的混合式部署</span><span class="sxs-lookup"><span data-stu-id="28b19-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28b19-103">_**主題上次修改日期：** 2012年-12-12_</span><span class="sxs-lookup"><span data-stu-id="28b19-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="28b19-104">混合式部署是使用 Microsoft Lync Online 的雲端服務和內部部署的設定。</span><span class="sxs-lookup"><span data-stu-id="28b19-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="28b19-105">在這種組態，自動探索服務必須能夠找出使用者的實際所在的位置。</span><span class="sxs-lookup"><span data-stu-id="28b19-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="28b19-106">也就是說，自動探索可協助找出的使用者帳戶，而伺服器主控的使用者帳戶是，不論是否在內部部署或 Lync Online 部署中。</span><span class="sxs-lookup"><span data-stu-id="28b19-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="28b19-107">比方說，如果 Lync Online 中的伺服器所架設的使用者帳戶，則嘗試尋找使用者將會發生，如下所示，稱為*可測知性*程序中：</span><span class="sxs-lookup"><span data-stu-id="28b19-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="28b19-108">從使用者起始的嘗試連線到內部部署， **contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="28b19-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="28b19-109">嘗試傳送至 lyncdiscover.contoso.com，自動探索服務相關聯的 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="28b19-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="28b19-110">自動探索指的是在內部部署 contoso.com 假定的登錄器集區，並提供使用者的實際的主伺服器裝載於 Lync Online 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="28b19-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="28b19-111">自動探索再傳送使用者轉介**lync.com**線上自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="28b19-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="28b19-112">使用者會嘗試連線到 lync.com 線上自動探索服務，且能找出使用者的帳戶和使用者的主伺服器。</span><span class="sxs-lookup"><span data-stu-id="28b19-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="28b19-113">若要啟用用戶端探索使用者主伺服器所在的部署，您必須設定自動探索服務與新的統一資源定位器 (URL)。</span><span class="sxs-lookup"><span data-stu-id="28b19-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="28b19-114">依下列方式來設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="28b19-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="28b19-115">設定自動探索的混合式部署</span><span class="sxs-lookup"><span data-stu-id="28b19-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="28b19-116">在主題[Lync Server 2013 的自動探索服務需求](lync-server-2013-autodiscover-service-requirements.md)，您可以使用 Get-cshostingprovider 擷取屬性 ProxyFQDN 的值。</span><span class="sxs-lookup"><span data-stu-id="28b19-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="28b19-117">從 Lync Server 管理命令介面中，輸入</span><span class="sxs-lookup"><span data-stu-id="28b19-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="28b19-118">其中\[identity\]取代共用 SIP 位址空間的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="28b19-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28b19-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28b19-119">See Also</span></span>


[<span data-ttu-id="28b19-120">Get-cshostingprovider</span><span class="sxs-lookup"><span data-stu-id="28b19-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="28b19-121">設定 CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="28b19-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

