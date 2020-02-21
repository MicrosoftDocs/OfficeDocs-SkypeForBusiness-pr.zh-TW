---
title: Lync Server 2013： 設定的電話撥入會議的位置型路由
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
ms.openlocfilehash: 7bc901b9ef1b4b358771427f44d220631e4a40ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="df881-102">Lync Server 2013 中的會議位置型路由的組態</span><span class="sxs-lookup"><span data-stu-id="df881-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df881-103">_**上次修改主題：** 2013年-09-11_</span><span class="sxs-lookup"><span data-stu-id="df881-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="df881-104">位置型路由會議應用程式依賴 Lync Server 2013 Location-Based 路由的組態。</span><span class="sxs-lookup"><span data-stu-id="df881-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="df881-105">主要的設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="df881-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="df881-106">參與者加入會議的位置取決於其網站。</span><span class="sxs-lookup"><span data-stu-id="df881-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="df881-107">網站和其相關聯的網路子網路必須定義在 Lync Server 以強制執行位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="df881-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="df881-108">若要強制的會議位置型路由，Lync 參與者必須啟用位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="df881-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="df881-109">若要強制位置型路由的加入會議的 PSTN 端點，用來連線的 PSTN 端點 SIP 主幹必須針對位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="df881-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="df881-110">如需有關部署和設定 Lync Server 2013 Location-Based 路由的詳細資訊，請參閱設定[位置型的路由](lync-server-2013-configuring-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="df881-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="df881-111">啟用位置型路由的會議應用程式</span><span class="sxs-lookup"><span data-stu-id="df881-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="df881-112">預設會停用位置型路由會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="df881-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="df881-113">之前啟用此應用程式，您必須決定要指派給應用程式的正確優先順序。</span><span class="sxs-lookup"><span data-stu-id="df881-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="df881-114">若要判斷此優先順序，請在 Lync Server 管理命令介面中執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="df881-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="df881-115">Get-csserverapplication-Identity Service: Registrar:\<集區 FQDN\></span><span class="sxs-lookup"><span data-stu-id="df881-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="df881-116">此指令程式，\<集區 FQDN\>是啟用位置型路由會議應用程式集區。</span><span class="sxs-lookup"><span data-stu-id="df881-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="df881-117">此 cmdlet 會傳回由 Lync Server 和優先順序值給個別使用者主控應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="df881-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="df881-118">位置型路由會議應用程式需要被指派大於 「 UdcAgent 」 應用程式且小於 「 DefaultRouting 」、 「 ExumRouting 」 及 「 OutboundRouting 」 應用程式的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="df881-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="df881-119">我們建議您指派的位置型路由會議應用程式是一個點的優先順序值高於 「 UdcAgent 」 應用程式的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="df881-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="df881-120">例如，如果 「 UdcAgent 」 應用程式都有優先順序值為"2"，「 DefaultRouting 」 應用程式都有優先順序值為"8"、 「 ExumRouting 」 應用程式都有優先順序值為"9"且 「 OutboundRouting 」 應用程式優先順序值為"10"然後您應該將位置型路由會議應用程式指派優先順序值為"3"。</span><span class="sxs-lookup"><span data-stu-id="df881-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="df881-121">這樣會將應用程式的優先順序，依下列順序： 其他應用程式 (優先順序： 0 到 1)，「 UdcAgent 」 (優先順序： 2)、 位置型路由會議應用程式 (優先順序： 3)，其他應用程式 (優先順序： 4 到 8)，」DefaultRouting 」 (Priority: 9)，「 ExumRouting 」 (優先順序： 10) 和 「 OutboundRouting 」 (優先順序： 11)。</span><span class="sxs-lookup"><span data-stu-id="df881-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="df881-122">您尋找正確的優先順序值的位置型路由會議應用程式後，請輸入每個前端集區或 Standard Edition Server 主控的使用者啟用位置型路由的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="df881-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="df881-123">New-csserverapplication-Identity Service: Registrar:\<集區 FQDN\>/LBRouting-優先順序\<應用程式的優先順序\>-啟用 $true-重要 $true Urihttps://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="df881-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri https://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="df881-124">例如：</span><span class="sxs-lookup"><span data-stu-id="df881-124">For example:</span></span>

<span data-ttu-id="df881-125">New-csserverapplication-Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-優先順序 3-啟用的 $true-重要 $true Urihttps://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="df881-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri https://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="df881-126">使用此 cmdlet 之後, 重新啟動集區或 Standard Edition 伺服器已啟用位置型路由會議應用程式中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="df881-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df881-127">會議或諮詢轉接位置型路由 enforcements 不會強制執行直到所有前端伺服器中適用的集區或 Standard Edition 伺服器重新啟動。</span><span class="sxs-lookup"><span data-stu-id="df881-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="df881-128">一旦成功啟用位置型路由會議應用程式及所有適用的 Lync 伺服器重新啟動後，可防止 PSTN 通話費略過監視啟用位置型路由的 Lync 使用者所召集的所有會議</span><span class="sxs-lookup"><span data-stu-id="df881-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

