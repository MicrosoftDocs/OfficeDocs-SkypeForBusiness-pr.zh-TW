---
title: Lync Server 2013：以位置為基礎的路由會議設定
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
ms.openlocfilehash: d9ea90f30dcd9ec9fdde2e6f4db25e7d27ad12cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="99a69-102">Lync Server 2013 中以位置為基礎的路由會議設定</span><span class="sxs-lookup"><span data-stu-id="99a69-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99a69-103">_**主題上次修改日期：** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="99a69-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="99a69-104">以位置為基礎的路由會議應用程式取決於 Lync Server 2013 位置路由的設定。</span><span class="sxs-lookup"><span data-stu-id="99a69-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="99a69-105">主要配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="99a69-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="99a69-106">加入會議的參與者位置是根據其網路網站來決定。</span><span class="sxs-lookup"><span data-stu-id="99a69-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="99a69-107">您必須在 Lync Server 中定義網路網站及其關聯的網路子網，才能強制執行位置路由。</span><span class="sxs-lookup"><span data-stu-id="99a69-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="99a69-108">若要強制進行依位置路由的會議，必須啟用 Lync 參與者以進行位置路由。</span><span class="sxs-lookup"><span data-stu-id="99a69-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="99a69-109">若要強制對 PSTN 端點的位置路由加入會議，必須針對以位置為基礎的路由設定用來連接 PSTN 端點的 SIP 幹線。</span><span class="sxs-lookup"><span data-stu-id="99a69-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="99a69-110">如需有關部署和設定 Lync Server 2013 位置路由的其他資訊，請參閱設定以[位置為基礎的路由](lync-server-2013-configuring-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="99a69-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="99a69-111">啟用以位置為基礎的路由會議應用程式</span><span class="sxs-lookup"><span data-stu-id="99a69-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="99a69-112">根據預設，會停用 [以位置為基礎的路由會議] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="99a69-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="99a69-113">啟用此應用程式之前，您必須先決定指派給應用程式的正確優先順序。</span><span class="sxs-lookup"><span data-stu-id="99a69-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="99a69-114">若要判斷這個優先順序，請在 Lync Server 管理命令介面中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="99a69-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="99a69-115">CsServerApplication 身分識別服務：註冊機構：\<池 FQDN\></span><span class="sxs-lookup"><span data-stu-id="99a69-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="99a69-116">在這個 Cmdlet 中\<，[\>池 FQDN] 是在其中啟用以位置為基礎的路由會議應用程式的池。</span><span class="sxs-lookup"><span data-stu-id="99a69-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="99a69-117">這個 Cmdlet 會傳回 Lync Server 託管的應用程式清單，以及每個應用程式的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="99a69-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="99a69-118">以位置為基礎的路由會議應用程式必須指派比「UdcAgent」應用程式還要大的優先順序值，並小於「DefaultRouting」、「ExumRouting」和「OutboundRouting」應用程式。</span><span class="sxs-lookup"><span data-stu-id="99a69-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="99a69-119">我們建議您指派 [以位置為基礎的路由會議] 應用程式的優先順序值，該值比 "UdcAgent" 應用程式的 [優先順序] 值高一點。</span><span class="sxs-lookup"><span data-stu-id="99a69-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="99a69-120">例如，如果 "UdcAgent" 應用程式的優先順序值為 "2"，"DefaultRouting" 應用程式的優先順序值為 "8"，"ExumRouting" 應用程式的優先順序值為 "9"，而 "OutboundRouting" 應用程式的優先順序值為 "10"，則您應該將 [以位置為基礎的路由會議] 應用程式指派優先順序值 "3"。</span><span class="sxs-lookup"><span data-stu-id="99a69-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="99a69-121">如此一來，就會按照下列順序來放置應用程式的優先順序：其他應用程式（優先順序：0到1）、"UdcAgent" （優先順序：2）、以位置為基礎的路由會議應用程式（優先順序：4到8），"DefaultRouting "（Priority：9），" ExumRouting "（優先順序：10）和" OutboundRouting "（優先順序：11）。</span><span class="sxs-lookup"><span data-stu-id="99a69-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="99a69-122">當您找到 [以位置為基礎的路由會議] 應用程式的正確優先順序值之後，請針對每個主機使用者啟用位置路由的 [前端] 池或標準版伺服器輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="99a69-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="99a69-123">新-CsServerApplication 身分識別服務：註冊機構\<：池\>FQDN/LBRouting- \<優先順序應用\>程式優先順序-已啟用 $true-重要 $true Urihttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="99a69-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="99a69-124">例如：</span><span class="sxs-lookup"><span data-stu-id="99a69-124">For example:</span></span>

<span data-ttu-id="99a69-125">新的-CsServerApplication 身分識別服務:Registrar:LS2013CU2LBRPool/LBRouting 優先順序 3-啟用的 $true-關鍵性 $true Urihttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="99a69-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="99a69-126">使用這個 Cmdlet 之後，請重新開機在已啟用位置式路由會議應用程式的池中的所有前端伺服器或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="99a69-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="99a69-127">在重新開機適用的池中的所有前端伺服器或標準版伺服器之後，才會強制執行針對會議或顧問式傳送的位置式路由 enforcements。</span><span class="sxs-lookup"><span data-stu-id="99a69-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="99a69-128">在已成功啟用位置式路由會議應用程式且已重新開機所有適用的 Lync 伺服器之後，系統會監視所有針對位置路由啟用的 Lync 使用者所組織的會議，以避免 PSTN 免付費旁路</span><span class="sxs-lookup"><span data-stu-id="99a69-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

