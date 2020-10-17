---
title: Lync Server 2013：在 Director 上啟動服務
description: Lync Server 2013：在 Director 上啟動服務。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on the Director
ms:assetid: 095b13e1-e788-4b80-93fa-5c5e7498678b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398146(v=OCS.15)
ms:contentKeyID: 48183351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c134099fb328b8647ed7a9176987c06eeb8070
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541809"
---
# <a name="start-services-on-the-director-in-lync-server-2013"></a><span data-ttu-id="71b8b-103">在 Lync Server 2013 中的 Director 上啟動服務</span><span class="sxs-lookup"><span data-stu-id="71b8b-103">Start services on the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71b8b-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="71b8b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="71b8b-105">安裝本機設定存放區、安裝 Lync Server 元件及設定 Director 上的憑證之後，您必須在伺服器上啟動 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="71b8b-105">After you install the Local Configuration Store, install the Lync Server Components, and configure certificates on a Director, you must start the Lync Server services on the server.</span></span> <span data-ttu-id="71b8b-106">您可以使用下列程序，在您部署中的每個 Director 上啟動服務。</span><span class="sxs-lookup"><span data-stu-id="71b8b-106">You can use the following procedure to start services on each Director in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-director"></a><span data-ttu-id="71b8b-107">若要在 Director 上啟動服務</span><span class="sxs-lookup"><span data-stu-id="71b8b-107">To start services on a Director</span></span>

1.  <span data-ttu-id="71b8b-108">在 [Lync Server 部署嚮導] 的 [ **Lync server 2013** ] 頁面上，按一下 [**步驟4：啟動服務**] 旁邊的 [**執行**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="71b8b-108">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click the **Run** button next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="71b8b-109">在 [ **啟動服務** ] 頁面上，按一下 **[下一步]** 以啟動伺服器上的 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="71b8b-109">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="71b8b-110">在「執行命令」\*\*\*\* 頁面上順利啟動所有服務之後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="71b8b-110">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>

4.  <span data-ttu-id="71b8b-111">在 **[步驟 4：啟動服務]** 下，按一下 **[服務狀態 (選擇性)]**。</span><span class="sxs-lookup"><span data-stu-id="71b8b-111">Below **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="71b8b-112">在伺服器上的 [ **服務** ] Microsoft Management CONSOLE (MMC) 中，確認所有的 Lync server 2013 服務都在執行中。</span><span class="sxs-lookup"><span data-stu-id="71b8b-112">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

