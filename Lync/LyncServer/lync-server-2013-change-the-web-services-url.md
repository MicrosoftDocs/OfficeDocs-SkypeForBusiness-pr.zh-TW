---
title: Lync Server 2013：變更 Web 服務 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="82ece-102">在 Lync Server 2013 中變更 Web 服務 URL</span><span class="sxs-lookup"><span data-stu-id="82ece-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82ece-103">_**主題上次修改日期：** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="82ece-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="82ece-104">在您設定前端池和標準版伺服器時，您可以選擇設定外部的網路集群集完全限定功能變數名稱（FQDN）及相關聯的埠。</span><span class="sxs-lookup"><span data-stu-id="82ece-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="82ece-105">如果您在執行 Lync Server 部署嚮導時未設定此 URL，您必須手動設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="82ece-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="82ece-106">系統管理員通常不需要修改這些設定，因為這些是建議的和預設的埠。</span><span class="sxs-lookup"><span data-stu-id="82ece-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82ece-107">在設定標準版伺服器時，會進行下列螢幕擷取畫面，因此停用覆寫 FQDN 選項。</span><span class="sxs-lookup"><span data-stu-id="82ece-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="82ece-108">在前端池中設定企業版伺服器時，會啟用該選項。</span><span class="sxs-lookup"><span data-stu-id="82ece-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="82ece-109">![編輯 Web 服務池設定][(images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "編輯 Web 服務] 池設定")</span><span class="sxs-lookup"><span data-stu-id="82ece-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="82ece-110">若要設定 web 服務</span><span class="sxs-lookup"><span data-stu-id="82ece-110">To configure web services</span></span>

1.  <span data-ttu-id="82ece-111">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="82ece-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="82ece-112">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="82ece-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="82ece-113">在拓撲建立器中，在 [**標準版前端伺服器**]、[**企業版前端池**] 和 [**目錄池**] 底下的 [主控台] 樹狀結構中，選取 [池名稱]。</span><span class="sxs-lookup"><span data-stu-id="82ece-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="82ece-114">以滑鼠右鍵按一下名稱，按一下 [**編輯屬性**]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="82ece-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="82ece-115">新增或編輯**外部 Web 服務 FQDN**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="82ece-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="82ece-116">如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="82ece-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="82ece-117">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端池或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="82ece-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="82ece-118">如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="82ece-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="82ece-119">確認已針對您的環境正確設定聆聽與已發佈的埠。</span><span class="sxs-lookup"><span data-stu-id="82ece-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="82ece-120">針對您環境中的所有標準版伺服器、前端池及控制器池，重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="82ece-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="82ece-121">在主控台樹中，按一下 [ **Lync Server 2013**]，然後在 [**動作**] 窗格中按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="82ece-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="82ece-122">當您設定聆聽與發佈埠時，必須注意幾個需求：</span><span class="sxs-lookup"><span data-stu-id="82ece-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="82ece-123">所顯示的偵聽埠是針對每個前端伺服器上的網際網路 Information Server （IIS）設定的埠。</span><span class="sxs-lookup"><span data-stu-id="82ece-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="82ece-124">對於 IIS，內部和外部的偵聽埠必須不同。</span><span class="sxs-lookup"><span data-stu-id="82ece-124">The internal and external listening ports must be different for IIS.</span></span> <span data-ttu-id="82ece-125">針對外部的偵聽埠，它們通常都是相同的，因為它代表內部網路流量的硬體負載平衡器，另一個代表外部網路流量的反向 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="82ece-125">For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="82ece-126">您可以覆寫前部端池、導演或主管池上的內部 web 服務，並定義您自己的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="82ece-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="82ece-127">如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須是與任何其他的前端池、控制器或主管池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="82ece-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="82ece-128">已發佈的埠必須在反向 proxy 或硬體負載平衡器上設定為偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="82ece-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="82ece-129">對於前端池（範例中未顯示），內部 SIP 池 FQDN 必須與內部 web 服務 FQDN 不同，因為 web 流量是透過硬體負載平衡器所產生，而內部 SIP 池流量則是透過 DNS 負載平衡器進行.</span><span class="sxs-lookup"><span data-stu-id="82ece-129">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer.</span></span> <span data-ttu-id="82ece-130">必須符合此需求。</span><span class="sxs-lookup"><span data-stu-id="82ece-130">This requirement must be met.</span></span>

  - <span data-ttu-id="82ece-131">Lync Server 標準版部署不需要或允許覆蓋內部 web 服務 FQDN，因為此伺服器無法進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="82ece-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="82ece-132">如果您的環境中有硬體負載平衡器，同時適用于內部 SIP 和網路流量，拓撲建立器就無法進行區別。</span><span class="sxs-lookup"><span data-stu-id="82ece-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="82ece-133">Web 服務 Fqdn 應該能輕鬆地彼此區別;這有助於確保 URL 重新導向用戶端傳到適當的伺服器。</span><span class="sxs-lookup"><span data-stu-id="82ece-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="82ece-134">例如，如果您有兩個 Fqdn，您可以考慮將一個 meeting.contoso.com 命名為另一個 conferencing.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="82ece-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="82ece-135">如果您有 Fqdn 有更相似的名稱（例如 meet1.contoso.com 和 meet2.contoso.com），您可能會遇到重新導向問題。</span><span class="sxs-lookup"><span data-stu-id="82ece-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="82ece-136">外部 web 服務與周邊網路中的反向 proxy 搭配運作。</span><span class="sxs-lookup"><span data-stu-id="82ece-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="82ece-137">它透過使用這些 web 服務，為用戶端提供外部存取。</span><span class="sxs-lookup"><span data-stu-id="82ece-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="82ece-138">在這裡設定的 Fqdn 會在使用者登入時傳送給用戶端，並用於在遠端連線時，將 HTTPS 連線回反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="82ece-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="82ece-139">反向 proxy 伺服器會將外部 web 服務 FQDN 轉寄到內部硬體負載平衡器，或直接傳送到該池。</span><span class="sxs-lookup"><span data-stu-id="82ece-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="82ece-140">反向 proxy 必須能夠將外部 web 服務 FQDN 解析為內部 Web 服務器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="82ece-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="82ece-141">外部 web 服務 FDQN 在公用網際網路中必須是可解析的。</span><span class="sxs-lookup"><span data-stu-id="82ece-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="82ece-142">如果您的內部伺服器是標準版伺服器，則內部 FQDN 是標準版伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="82ece-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="82ece-143">如果您的內部伺服器是 [前端] 池，FQDN 就是硬體負載平衡器虛擬 IP （VIP），負載平衡內部的網路伺服器陣列伺服器。</span><span class="sxs-lookup"><span data-stu-id="82ece-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="82ece-144">在有一個以上的企業版伺服器的前端池中需要硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="82ece-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="82ece-145">標準版伺服器或單一的企業版前端伺服器不需要負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="82ece-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

