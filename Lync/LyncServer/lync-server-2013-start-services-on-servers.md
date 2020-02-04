---
title: Lync Server 2013：在伺服器上啟動服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e6474071e7f95228f3c04c4931b4f899df68b40
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="45ccf-102">針對 Lync Server 2013 在伺服器上啟動服務</span><span class="sxs-lookup"><span data-stu-id="45ccf-102">Start services on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ccf-103">_**主題上次修改日期：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="45ccf-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="45ccf-104">若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入，或是委派正確的許可權。</span><span class="sxs-lookup"><span data-stu-id="45ccf-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="45ccf-105">如需委派許可權的詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)主題。</span><span class="sxs-lookup"><span data-stu-id="45ccf-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="45ccf-106">在伺服器上安裝本機配置存放區之後，請安裝 Lync Server 2013 元件，並在前端伺服器或前端伺服器上設定憑證，您必須在伺服器上啟動 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="45ccf-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="45ccf-107">使用下列程式在您部署中的每個前端伺服器上啟動服務。</span><span class="sxs-lookup"><span data-stu-id="45ccf-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="45ccf-108">在標準版或前端伺服器上啟動服務</span><span class="sxs-lookup"><span data-stu-id="45ccf-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="45ccf-109">在 Lync Server 部署嚮導中，在 [ **Lync server 2013** ] 頁面上，按一下 [**步驟4：啟動服務**] 旁的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="45ccf-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="45ccf-110">在 [**啟動服務**] 頁面上，按一下 **[下一步]** ，即可在伺服器上啟動 Lync Server Services。</span><span class="sxs-lookup"><span data-stu-id="45ccf-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="45ccf-111">在 [**執行命令**] 頁面上，已成功啟動所有服務之後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="45ccf-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45ccf-112">在伺服器上啟動服務的命令是一種最佳的方式，可報表服務已開始進行。</span><span class="sxs-lookup"><span data-stu-id="45ccf-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="45ccf-113">它可能不會反映服務的實際狀態。</span><span class="sxs-lookup"><span data-stu-id="45ccf-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="45ccf-114">我們建議您立即使用 [步驟<STRONG>服務狀態] （選用）</STRONG>來開啟 Microsoft 管理主控台（MMC <STRONG>），並</STRONG>確認服務已順利啟動。</span><span class="sxs-lookup"><span data-stu-id="45ccf-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="45ccf-115">如果有任何 Lync Server 服務尚未啟動，您可以在 MMC 中以滑鼠右鍵按一下該服務，然後按一下 [<STRONG>啟動</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="45ccf-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

