---
title: Lync Server 2013：設定網頁伺服器陣列 Fqdn
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
ms.openlocfilehash: 37799ed65cca468ea7bac18956ed08783c9b6a1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520130"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="79f8b-102">設定 Lync Server 2013 的 web 伺服器陣列 Fqdn</span><span class="sxs-lookup"><span data-stu-id="79f8b-102">Configure web farm FQDNs for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79f8b-103">_**主題上次修改日期：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="79f8b-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="79f8b-104">當您在拓撲產生器中定義 Standard Edition server、前端集區、Director 或 Director 集區的設定時，會將 [外部 web 服務] 完整功能變數名稱設定 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="79f8b-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="79f8b-105">在駐留在 Standard Edition server 或前端集區中的用戶端登入過程中，設定的 web 服務 Fqdn 是透過帶內布建的方式傳送。</span><span class="sxs-lookup"><span data-stu-id="79f8b-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="79f8b-106">如果您需要新增或變更 [外部 web 服務] URL，請使用拓撲產生器來設定或重新設定 web 服務設定，使用本主題中的程式。</span><span class="sxs-lookup"><span data-stu-id="79f8b-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="79f8b-107">設定 web 服務的外部集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="79f8b-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="79f8b-108">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="79f8b-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="79f8b-109">在 [拓撲產生器] 的 [ **Standard Edition 前端**]、[ **Enterprise edition 前端**] 及 [ **director**] 下的主控台樹中，以滑鼠右鍵按一下您需要編輯的集區名稱，然後按一下 [ **編輯**內容]。</span><span class="sxs-lookup"><span data-stu-id="79f8b-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="79f8b-110">在 [ **Web 服務** ] 區段中，新增或編輯 [ **外部 Web 服務 FQDN**]。</span><span class="sxs-lookup"><span data-stu-id="79f8b-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="79f8b-111">檢查並調整 HTTP 和 HTTPS 的 **聆聽埠** 。</span><span class="sxs-lookup"><span data-stu-id="79f8b-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="79f8b-112">預設值將會是：</span><span class="sxs-lookup"><span data-stu-id="79f8b-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="79f8b-113">**聆聽埠：** HTTP 8080，HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="79f8b-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="79f8b-114">**已發佈的埠：** HTTP 80，HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="79f8b-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="79f8b-115">其中， **收聽埠** 是外部 web 服務將設定為接收反向 proxy 之要求的埠，而 **已發佈的埠** 是反向 proxy 外部發佈的埠，而且會在頻帶內布建期間傳遞給用戶端。</span><span class="sxs-lookup"><span data-stu-id="79f8b-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="79f8b-116">當您完成新增和更新時，請按一下 **[確定]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="79f8b-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="79f8b-117">以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [ **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="79f8b-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="79f8b-118">順利發行完成後，可能會出現連結，通知您有需要採取的其他步驟。</span><span class="sxs-lookup"><span data-stu-id="79f8b-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="79f8b-119">連結（如果已按一下）會開啟受拓撲產生器所進行之變更影響的伺服器清單，該清單會要求您在所列的每個伺服器上重新執行 Lync Server 部署嚮導，以更新新增、移除或變更的元件的設定。</span><span class="sxs-lookup"><span data-stu-id="79f8b-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="79f8b-120">針對組織中的每個 Standard Edition server、前端集區、Director 或 Director 集區，重複執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="79f8b-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

