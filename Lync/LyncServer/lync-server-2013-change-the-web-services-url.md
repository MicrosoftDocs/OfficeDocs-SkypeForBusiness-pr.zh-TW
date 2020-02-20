---
title: Lync Server 2013： 變更 Web 服務 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed7e61d62857f11c780798a8704aa5aa9fe808a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="81096-102">變更 Lync Server 2013 中的 Web 服務 URL</span><span class="sxs-lookup"><span data-stu-id="81096-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81096-103">_**主題上次修改日期：** 2015 年 11-16_</span><span class="sxs-lookup"><span data-stu-id="81096-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="81096-104">當您設定前端集區和 Standard Edition Server 時，可以選擇設定外部 Web 伺服器陣列完整網域名稱 (FQDN) 和相關聯的連接埠。</span><span class="sxs-lookup"><span data-stu-id="81096-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="81096-105">如果您未設定此 URL 當您執行 Lync Server 部署精靈時，您需要手動設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="81096-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="81096-106">系統管理員通常不需要修改這些設定，因為這些是建議值和預設連接埠。</span><span class="sxs-lookup"><span data-stu-id="81096-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81096-107">下列螢幕擷取畫面所採取的設定 Standard Edition 伺服器，讓覆寫 FQDN 停用此選項。</span><span class="sxs-lookup"><span data-stu-id="81096-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="81096-108">在前端集區中設定 Enterprise Edition server 時，會啟用該選項。</span><span class="sxs-lookup"><span data-stu-id="81096-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="81096-109">![編輯 Web 服務集區設定](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "編輯 Web 服務集區設定")</span><span class="sxs-lookup"><span data-stu-id="81096-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="81096-110">若要設定 web 服務</span><span class="sxs-lookup"><span data-stu-id="81096-110">To configure web services</span></span>

1.  <span data-ttu-id="81096-111">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="81096-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="81096-112">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="81096-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="81096-113">在拓撲產生器， **Standard Edition 前端伺服器**] 下的主控台樹狀目錄中**Enterprise Edition 前端集區**，以及**目錄集區**，選取 [集區名稱。</span><span class="sxs-lookup"><span data-stu-id="81096-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="81096-114">用滑鼠右鍵按一下名稱，然後依序按一下 **[編輯內容]** 和 **[Web 服務]**。</span><span class="sxs-lookup"><span data-stu-id="81096-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="81096-115">新增或編輯 **[外部 Web 服務 FQDN]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81096-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="81096-116">如果您有一個以上的前端集區或前端伺服器的外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="81096-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="81096-117">例如，如果您定義的外部 Web 服務的前端伺服器 FQDN 為<STRONG>pool01.contoso.com</STRONG>，您無法使用<STRONG>pool01.contoso.com</STRONG>另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="81096-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="81096-118">如果您也要部署 Director、 外部 Web 服務 FQDN 定義任何 director 或 Director 集區必須是唯一的任何其他 Director 集區也為任何前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="81096-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="81096-119">確認環境中已正確設定聆聽和發行的連接埠。</span><span class="sxs-lookup"><span data-stu-id="81096-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="81096-120">針對環境中的所有 Standard Edition Server、前端集區和 Director 集區，重複執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="81096-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="81096-121">在主控台樹狀目錄中，按一下 **[Lync Server 2013]**，然後在 **[動作]** 窗格中，按一下 **[發行拓撲]**。</span><span class="sxs-lookup"><span data-stu-id="81096-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="81096-122">設定聆聽和發行連接埠時，有一些需求應注意：</span><span class="sxs-lookup"><span data-stu-id="81096-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="81096-123">顯示的聆聽連接埠是每部前端伺服器上的 Internet Information Server (IIS) 所設定的連接埠。</span><span class="sxs-lookup"><span data-stu-id="81096-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="81096-p105">IIS 的內部和外部聆聽連接埠必須不同。以外部聆聽連接埠而言，這些通常相同，因為一個代表內部 Web 流量的硬體負載平衡器，另一個代表外部 Web 流量的反向 Proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="81096-p105">The internal and external listening ports must be different for IIS. For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="81096-126">您可以覆寫內部 web 服務上的前端集區、 Director 或 Director 集區，並定義您自己的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="81096-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="81096-127">如果您決定要覆寫內部 web 服務以自我定義的 FQDN，每個 FQDN 必須是唯一的因任何其他的前端集區、 Director 或 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="81096-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="81096-128">在反向 Proxy 或硬體負載平衡器上，必須設定發行的連接埠作為聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="81096-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="81096-p106">以前端集區而言 (範例中未顯示)，內部 SIP 集區 FQDN 與內部 Web 服務 FQDN 必須不同，因為 Web 流量是經過硬體負載平衡器而來，而內部 SIP 流量則是經過 DNS 負載平衡器而來。必須符合此需求。</span><span class="sxs-lookup"><span data-stu-id="81096-p106">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer. This requirement must be met.</span></span>

  - <span data-ttu-id="81096-131">Lync Server Standard Edition 部署不需要或允許內部 web 服務 FQDN 來覆寫，因為此伺服器無法受到平衡負載。</span><span class="sxs-lookup"><span data-stu-id="81096-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="81096-132">如果您使用的兩個內部 SIP 和 web 流量，[拓撲產生器無法加以區別您環境中有硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="81096-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="81096-133">Web 服務 Fqdn 應從另一個; 輕鬆區別可協助確保該 URL 重新導向點用戶端向適當的伺服器。</span><span class="sxs-lookup"><span data-stu-id="81096-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="81096-134">例如，如果您有兩個 Fqdn 您可能會考慮命名一個 meeting.contoso.com 和其他 conferencing.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="81096-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="81096-135">如果您有多類似的名稱，例如 meet1.contoso.com 和 meet2.contoso.com Fqdn，您可能無法執行發生重新導向問題。</span><span class="sxs-lookup"><span data-stu-id="81096-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="81096-136">外部 Web 服務會搭配周邊網路中的反向 Proxy 一起運作。</span><span class="sxs-lookup"><span data-stu-id="81096-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="81096-137">它提供用戶端的外部存取使用這些 web 服務。</span><span class="sxs-lookup"><span data-stu-id="81096-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="81096-138">此處設定的 FQDN 會在用戶端登入時傳送給用戶端，並在進行遠端連線時用來建立連回反向 Proxy 的 HTTPS 連線。</span><span class="sxs-lookup"><span data-stu-id="81096-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="81096-139">反向 Proxy 伺服器會將外部 Web 服務 FQDN 轉到內部硬體負載平衡器，或直接轉到集區。</span><span class="sxs-lookup"><span data-stu-id="81096-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="81096-140">反向 Proxy 必須能夠將外部 Web 服務 FQDN 解析為內部 Web 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="81096-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="81096-141">外部 Web 服務 FDQN 必須可在公用網際網路中受到解析。</span><span class="sxs-lookup"><span data-stu-id="81096-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="81096-142">如果您的內部伺服器為 Standard Edition server，內部 FQDN 為 Standard Edition 伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="81096-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="81096-143">如果內部伺服器是前端集區，則 FQDN 是會對內部 Web 伺服陣列伺服器進行負載平衡的硬體負載平衡器虛擬 IP (VIP)。</span><span class="sxs-lookup"><span data-stu-id="81096-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="81096-144">在具有多部 Enterprise Edition Server 的前端集區中，需要硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="81096-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="81096-145">Standard Edition Server 或單一 Enterprise Edition 前端伺服器則不需要負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="81096-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

