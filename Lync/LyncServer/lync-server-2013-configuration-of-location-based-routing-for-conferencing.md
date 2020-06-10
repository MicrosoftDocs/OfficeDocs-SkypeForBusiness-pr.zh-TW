---
title: Lync Server 2013：設定位置基礎路由以進行會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f982f6e484412234c75eadaea925b65ee11bcbb
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="8097f-102">在 Lync Server 2013 中為會議設定位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="8097f-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8097f-103">_**主題上次修改日期：** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="8097f-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="8097f-104">以位置為基礎的路由會議應用程式取決於 Lync Server 2013 位置基礎路由的設定。</span><span class="sxs-lookup"><span data-stu-id="8097f-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="8097f-105">主要設定如下：</span><span class="sxs-lookup"><span data-stu-id="8097f-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="8097f-106">加入會議的參與者位置是根據其網路網站來決定。</span><span class="sxs-lookup"><span data-stu-id="8097f-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="8097f-107">您必須在 Lync Server 中定義網路網站及其相關聯的網路子網，才能強制進行位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="8097f-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="8097f-108">若要強制進行會議的位置基礎路由，必須啟用 Lync 參與者以進行位置基礎路由傳送。</span><span class="sxs-lookup"><span data-stu-id="8097f-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="8097f-109">若要強制執行 PSTN 端點的位置基礎路由加入會議，必須針對位置基礎路由設定用來連接 PSTN 端點的 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="8097f-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="8097f-110">如需部署及設定 Lync Server 2013 位置型路由的詳細資訊，請參閱設定[位置基礎路由](lync-server-2013-configuring-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="8097f-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="8097f-111">啟用以位置為基礎的路由會議應用程式</span><span class="sxs-lookup"><span data-stu-id="8097f-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="8097f-112">以位置為基礎的路由會議應用程式預設為停用。</span><span class="sxs-lookup"><span data-stu-id="8097f-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="8097f-113">在啟用此應用程式之前，您必須決定指派給應用程式的正確優先順序。</span><span class="sxs-lookup"><span data-stu-id="8097f-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="8097f-114">若要決定此優先順序，請在 Lync Server 管理命令介面中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8097f-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

<span data-ttu-id="8097f-115">在此 Cmdlet 中， \<Pool FQDN\> 是要在其中啟用位置基礎路由會議應用程式的集區。</span><span class="sxs-lookup"><span data-stu-id="8097f-115">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="8097f-116">此 Cmdlet 會傳回 Lync Server 所主控之應用程式的清單，以及每個應用程式的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="8097f-116">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="8097f-117">以位置為基礎的路由會議應用程式需要指派優先順序值大於 "UdcAgent" 應用程式，並小於 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8097f-117">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="8097f-118">建議您指派位置為基礎的路由會議應用程式，其優先順序值為比 "UdcAgent" 應用程式的優先順序值高一個點。</span><span class="sxs-lookup"><span data-stu-id="8097f-118">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="8097f-119">例如，如果 "UdcAgent" 應用程式的優先順序值為 "2"，"DefaultRouting" 應用程式的優先順序值為 "8"，"ExumRouting" 應用程式的優先順序值為 "9"，而 "OutboundRouting" 應用程式的優先順序值為 "10"，您應該指派優先順序值為 "3" 的「以位置為基礎的路由會議應用程式」。</span><span class="sxs-lookup"><span data-stu-id="8097f-119">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="8097f-120">這樣做會依照下列順序進行應用程式的優先順序：其他應用程式（優先順序：0到1）、"UdcAgent" （Priority：2）、位置基礎路由會議應用程式（優先順序：3）、其他應用程式（優先順序：4到8）、"DefaultRouting" （優先順序：9）、"ExumRouting" （Priority：10）和 "OutboundRouting" （Priority：11）。</span><span class="sxs-lookup"><span data-stu-id="8097f-120">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="8097f-121">找到位置基礎路由會議應用程式的正確優先順序值後，請為每一個前端集區或 Standard Edition Server 輸入下列 Cmdlet，以供住宅使用者進行位置基礎的路由：</span><span class="sxs-lookup"><span data-stu-id="8097f-121">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="8097f-122">例如：</span><span class="sxs-lookup"><span data-stu-id="8097f-122">For example:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="8097f-123">使用此 Cmdlet 後，請重新開機集區中的所有前端伺服器或啟用位置型路由會議應用程式的 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="8097f-123">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8097f-124">在重新開機適用的集區或 Standard Edition Server 中的所有前端伺服器之前，不會強制執行以位置為基礎的路由 enforcements 至會議或諮詢轉移。</span><span class="sxs-lookup"><span data-stu-id="8097f-124">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="8097f-125">一旦已成功啟用位置式路由會議應用程式，且已重新開機所有適用的 Lync 伺服器，則會監控透過啟用位置路由之 Lync 使用者所組織的所有會議，以避免 PSTN 免付費旁路</span><span class="sxs-lookup"><span data-stu-id="8097f-125">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

