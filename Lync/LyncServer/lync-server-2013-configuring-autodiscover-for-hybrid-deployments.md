---
title: Lync Server 2013：針對混合式部署設定自動探索
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
ms.openlocfilehash: 8924194d89eafb75c06ff78ed3b765699e36b196
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="c326c-102">在 Lync Server 2013 中設定自動探索以進行混合式部署</span><span class="sxs-lookup"><span data-stu-id="c326c-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c326c-103">_**主題上次修改日期：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="c326c-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="c326c-104">混合式部署是使用 Microsoft Lync Online 雲端服務和內部部署部署的配置。</span><span class="sxs-lookup"><span data-stu-id="c326c-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="c326c-105">在此類型的設定中，自動探索服務必須能夠找出使用者實際所處的位置。</span><span class="sxs-lookup"><span data-stu-id="c326c-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="c326c-106">那就是說，「自動探索」會尋找使用者帳戶，以及主持使用者帳戶的伺服器所在的位置，而不考慮它是在內部部署還是在 Lync Online 部署中。</span><span class="sxs-lookup"><span data-stu-id="c326c-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="c326c-107">例如，如果使用者的帳戶是駐留在 Lync Online 的伺服器上，則在稱為「探索」的程式中，嘗試尋找使用者的操作會如下所*示：*</span><span class="sxs-lookup"><span data-stu-id="c326c-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="c326c-108">使用者啟動到內部部署部署的連線嘗試，請**contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="c326c-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="c326c-109">該嘗試會傳送至 lyncdiscover.contoso.com，即與自動探索服務相關聯的 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="c326c-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="c326c-110">自動探索會參照 contoso.com 內部部署部署的假設註冊機構池，並提供使用者在 Lync Online 中託管之實際主伺服器的資訊。</span><span class="sxs-lookup"><span data-stu-id="c326c-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="c326c-111">自動探索接著會將對**lync.com** online 自動探索服務的參照傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="c326c-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="c326c-112">使用者初始化 lync.com online 自動探索服務的連線嘗試，而且可以找到使用者的帳戶和使用者的主伺服器。</span><span class="sxs-lookup"><span data-stu-id="c326c-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="c326c-113">若要讓用戶端發現使用者主伺服器所在的部署，您必須使用新的統一資源定位器（URL）來設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="c326c-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="c326c-114">請執行下列動作來設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="c326c-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="c326c-115">針對混合式部署設定自動探索</span><span class="sxs-lookup"><span data-stu-id="c326c-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="c326c-116">在[Lync Server 2013 的自動探索服務需求](lync-server-2013-autodiscover-service-requirements.md)主題中，您可以使用 CsHostingProvider 來取得屬性 ProxyFQDN 的值。</span><span class="sxs-lookup"><span data-stu-id="c326c-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="c326c-117">從 Lync Server 管理命令介面輸入</span><span class="sxs-lookup"><span data-stu-id="c326c-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="c326c-118">使用\[共用\] SIP 位址空間的功能變數名稱取代身分識別的位置。</span><span class="sxs-lookup"><span data-stu-id="c326c-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c326c-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="c326c-119">See Also</span></span>


[<span data-ttu-id="c326c-120">CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="c326c-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="c326c-121">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="c326c-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

