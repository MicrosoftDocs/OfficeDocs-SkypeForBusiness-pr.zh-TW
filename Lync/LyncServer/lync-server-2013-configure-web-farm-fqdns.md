---
title: Lync Server 2013： 設定 web 伺服陣列 Fqdn
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
ms.openlocfilehash: 46cca998a35a7519675cd787f5887f2a65d491c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="8f111-102">設定 web 伺服陣列 Fqdn 的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f111-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f111-103">_**上次修改主題：** 2013年-03-29_</span><span class="sxs-lookup"><span data-stu-id="8f111-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="8f111-104">當您定義 Standard Edition server 的設定時，前端集區、 Director 或 Director 集區拓撲產生器] 中設定外部 web 服務完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="8f111-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="8f111-105">在登入用戶端的程序期間位於 [Standard Edition server 或前端集區，設定的 web 服務 Fqdn 傳送透過頻內佈建。</span><span class="sxs-lookup"><span data-stu-id="8f111-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="8f111-106">如果您需要新增或變更外部 web 服務 URL，您可以使用拓撲產生器來設定或重新設定程序使用本主題中的 web 服務組態。</span><span class="sxs-lookup"><span data-stu-id="8f111-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="8f111-107">若要設定 web 服務的外部集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="8f111-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="8f111-108">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="8f111-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="8f111-109">在拓撲產生器，在主控台樹狀目錄中，在**Standard Edition 前端**]、 [ **Enterprise Edition 前端**] 及 [ **Director**，以滑鼠右鍵按一下您要編輯的集區名稱，然後按一下 [**編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="8f111-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="8f111-110">在 [ **Web 服務**] 區段中，新增或編輯**外部 web 服務 FQDN**。</span><span class="sxs-lookup"><span data-stu-id="8f111-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="8f111-111">檢閱並調整**聆聽連接埠**的 HTTP 和 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="8f111-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="8f111-112">預設值會是：</span><span class="sxs-lookup"><span data-stu-id="8f111-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="8f111-113">**聆聽連接埠：** HTTP 8080、 HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="8f111-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="8f111-114">**發行的連接埠：** HTTP 80、 HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="8f111-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="8f111-115">**聆聽連接埠**所在的外部 web 服務將會設定為接收來自反向 proxy 要求和**發行的連接埠**是連接埠的連接埠都已由反向 proxy 對外發行且頻內佈建期間傳達給用戶端。</span><span class="sxs-lookup"><span data-stu-id="8f111-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="8f111-116">當您完成新增和更新時，請按一下 **[確定]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="8f111-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="8f111-117">**Lync Server 2013**中，以滑鼠右鍵按一下，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="8f111-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8f111-118">發佈成功完成之後，連結可能會出現，通知您有其他需要採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="8f111-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="8f111-119">[] 連結，如果按下，會開啟在拓撲產生器中，會要求您重新執行更新適用於新增、 移除或變更元件設定每個列出的伺服器上的 [Lync Server 部署精靈中所做的變更所影響的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="8f111-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="8f111-120">針對每個 Standard Edition 伺服器，前端集區，重複這些步驟 Director 集區在組織中。</span><span class="sxs-lookup"><span data-stu-id="8f111-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

