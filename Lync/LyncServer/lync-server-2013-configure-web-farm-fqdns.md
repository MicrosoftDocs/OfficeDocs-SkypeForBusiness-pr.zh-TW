---
title: Lync Server 2013：設定 Web 伺服陣列 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="355c7-102">針對 Lync Server 2013 設定 Web 伺服陣列 FQDN</span><span class="sxs-lookup"><span data-stu-id="355c7-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="355c7-103">_**主題上次修改日期：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="355c7-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="355c7-104">當您在拓撲建立器中定義標準版 server、前端池、控制器或控制器池的設定時，請設定外部 web 服務完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="355c7-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="355c7-105">在駐留在標準版 server 或 [前端] 池中的用戶端登入程式期間，已設定的 web 服務 Fqdn 是透過以內提供的方式傳送。</span><span class="sxs-lookup"><span data-stu-id="355c7-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="355c7-106">如果您需要新增或變更 [外部 web 服務] URL，您可以使用 [拓撲建立器] 來設定或重新配置 web 服務配置（使用本主題中的程式）。</span><span class="sxs-lookup"><span data-stu-id="355c7-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="355c7-107">針對 web 服務設定外部池 FQDN</span><span class="sxs-lookup"><span data-stu-id="355c7-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="355c7-108">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="355c7-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="355c7-109">在拓撲建立器中，在 [**標準版的前端**]、[**企業版] 前端**和 [**控制器**] 底下的 [主控台] 樹狀結構中，以滑鼠右鍵按一下您要編輯的池名稱，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="355c7-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="355c7-110">在 [ **Web 服務**] 區段中，新增或編輯**外部 Web 服務 FQDN**。</span><span class="sxs-lookup"><span data-stu-id="355c7-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="355c7-111">同時查看和調整 HTTP 和 HTTPS 的**偵聽埠**。</span><span class="sxs-lookup"><span data-stu-id="355c7-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="355c7-112">預設值將會是：</span><span class="sxs-lookup"><span data-stu-id="355c7-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="355c7-113">**偵聽埠：** HTTP 8080，HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="355c7-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="355c7-114">**已發佈的埠：** HTTP 80，HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="355c7-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="355c7-115">在**偵聽埠**是要將外部 web 服務設定為從反向 proxy 接收要求的埠，而**已發佈的埠**是由反向 proxy 在外部發佈的埠，且會在頻帶內設定中傳遞給用戶端。</span><span class="sxs-lookup"><span data-stu-id="355c7-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="355c7-116">當您完成新增和更新時，請按一下 **[確定]** 以繼續進行。</span><span class="sxs-lookup"><span data-stu-id="355c7-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="355c7-117">以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="355c7-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="355c7-118">發佈順利完成後，可能會出現連結，通知您有需要採取的其他步驟。</span><span class="sxs-lookup"><span data-stu-id="355c7-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="355c7-119">如果按一下該連結，則會開啟拓撲建立器所做的變更所影響的伺服器清單，這會要求您在每個列出的伺服器上重新執行 Lync Server 部署嚮導，以更新已新增、已移除或變更的元件的配置。</span><span class="sxs-lookup"><span data-stu-id="355c7-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="355c7-120">針對組織中的每個標準版 server、[前端] 池、[主管] 或 [控制器] 池，重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="355c7-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

