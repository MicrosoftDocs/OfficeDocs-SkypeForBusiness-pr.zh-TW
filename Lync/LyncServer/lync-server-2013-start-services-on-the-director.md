---
title: Lync Server 2013：在 Director 上啟動服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start services on the Director
ms:assetid: 095b13e1-e788-4b80-93fa-5c5e7498678b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398146(v=OCS.15)
ms:contentKeyID: 48183351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3716d53951c662ec4df7e634aa5548bc8cd72b4b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-the-director-in-lync-server-2013"></a><span data-ttu-id="8b31a-102">在 Lync Server 2013 中的 Director 上啟動服務</span><span class="sxs-lookup"><span data-stu-id="8b31a-102">Start services on the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b31a-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8b31a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8b31a-104">安裝本機配置存放區後，安裝 Lync Server 元件，並在 Director 上設定憑證之後，您必須在伺服器上啟動 Lync Server services。</span><span class="sxs-lookup"><span data-stu-id="8b31a-104">After you install the Local Configuration Store, install the Lync Server Components, and configure certificates on a Director, you must start the Lync Server services on the server.</span></span> <span data-ttu-id="8b31a-105">您可以使用下列程式，在您的部署中的每個控制器上啟動服務。</span><span class="sxs-lookup"><span data-stu-id="8b31a-105">You can use the following procedure to start services on each Director in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-director"></a><span data-ttu-id="8b31a-106">在主管上啟動服務</span><span class="sxs-lookup"><span data-stu-id="8b31a-106">To start services on a Director</span></span>

1.  <span data-ttu-id="8b31a-107">在 Lync Server 部署嚮導中，在 [ **Lync server 2013** ] 頁面上，按一下 [**步驟4：啟動服務**] 旁的 [**執行**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="8b31a-107">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click the **Run** button next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="8b31a-108">在 [**啟動服務**] 頁面上，按一下 **[下一步]** ，即可在伺服器上啟動 Lync Server Services。</span><span class="sxs-lookup"><span data-stu-id="8b31a-108">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="8b31a-109">在 [**執行命令**] 頁面上，已成功啟動所有服務之後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8b31a-109">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>

4.  <span data-ttu-id="8b31a-110">在**步驟4：啟動服務**，按一下 **[服務狀態] （選用）**。</span><span class="sxs-lookup"><span data-stu-id="8b31a-110">Below **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="8b31a-111">在伺服器上的 [**服務**Microsoft Management CONSOLE （MMC）] 中，確認所有的 Lync server 2013 服務都在執行中。</span><span class="sxs-lookup"><span data-stu-id="8b31a-111">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

