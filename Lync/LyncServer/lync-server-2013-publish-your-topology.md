---
title: Lync Server 2013：發行您的拓撲
description: Lync Server 2013：發行您的拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4d27d2d3644eb1f174e2f3fab47197f2c122a97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571749"
---
# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="80848-103">在 Lync Server 2013 中發行您的拓撲</span><span class="sxs-lookup"><span data-stu-id="80848-103">Publish your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80848-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="80848-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="80848-105">您每次使用拓撲產生器來建立拓撲時，您必須將拓撲發行至中央管理存放區中的資料庫，以便讓資料可用於部署 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="80848-105">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="80848-106">請使用下列程式發行您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="80848-106">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="80848-107">發行拓撲</span><span class="sxs-lookup"><span data-stu-id="80848-107">To publish the topology</span></span>

1.  <span data-ttu-id="80848-108">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="80848-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="80848-109">在 [拓撲產生器] 的主控台樹中，以滑鼠右鍵按一下 [ **Lync 2013**]，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="80848-109">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="80848-110">在嚮導的 [ **歡迎** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="80848-110">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="80848-111">在 [ **拓撲產生器找到 CMS 存放區** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="80848-111">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="80848-112">在 [ **建立其他資料庫** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="80848-112">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="80848-113">當狀態表示已成功建立資料庫時，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="80848-113">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="80848-114">若要查看記錄檔，請按一下 [ **查看記錄**檔]。</span><span class="sxs-lookup"><span data-stu-id="80848-114">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="80848-115">按一下 **[完成]**，關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="80848-115">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="80848-116">如果這是 Edge Server 或 Edge 集區的全新安裝，則必須從現有的前端伺服器、前端集區或 Standard Edition Server 匯出 Edge Server 設定。</span><span class="sxs-lookup"><span data-stu-id="80848-116">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="80848-117">若要匯出設定，請參閱 <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">匯出 Lync Server 2013 拓撲，並將其複製到 edge 安裝的外部媒體</A>。</span><span class="sxs-lookup"><span data-stu-id="80848-117">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="80848-118">您將透過 Lync Server 部署嚮導，在 Edge Server 的安裝與部署階段中匯入外部媒體或網路共用中的設定檔。</span><span class="sxs-lookup"><span data-stu-id="80848-118">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="80848-119">一旦 Edge server 可以運作，而且本機設定管理存放區資料庫是與內部部署進行複製，就會發佈 Lync Server 2013 設定的後續更新，並將其複寫至 Edge server。</span><span class="sxs-lookup"><span data-stu-id="80848-119">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

