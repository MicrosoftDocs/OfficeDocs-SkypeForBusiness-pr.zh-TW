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
ms.openlocfilehash: 7d276dfdedacdcb00b4cc19a486fea1103c0bc8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532960"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="04800-102">在 Lync Server 2013 的伺服器上啟動服務</span><span class="sxs-lookup"><span data-stu-id="04800-102">Start services on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04800-103">_**主題上次修改日期：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="04800-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="04800-104">若要順利完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入，或是委派正確的許可權。</span><span class="sxs-lookup"><span data-stu-id="04800-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="04800-105">如需委派許可權的詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)主題。</span><span class="sxs-lookup"><span data-stu-id="04800-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="04800-106">在伺服器上安裝本機設定存放區之後，請安裝 Lync Server 2013 元件，並在前端伺服器或前端伺服器上設定憑證，您必須在伺服器上啟動 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="04800-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="04800-107">使用下列程式可在部署中的每一部前端伺服器上啟動服務。</span><span class="sxs-lookup"><span data-stu-id="04800-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="04800-108">在 Standard Edition 或前端伺服器上啟動服務</span><span class="sxs-lookup"><span data-stu-id="04800-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="04800-109">在 [Lync Server 部署嚮導] 的 [ **Lync server 2013** ] 頁面上，按一下 [執行**步驟4：啟動服務**] 旁邊的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="04800-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="04800-110">在 [ **啟動服務** ] 頁面上，按一下 **[下一步]** 以啟動伺服器上的 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="04800-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="04800-111">在 **[執行命令]** 頁面上順利啟動所有服務之後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="04800-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="04800-112">在伺服器上啟動服務的命令是報告事實上已啟動服務的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="04800-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="04800-113">它可能不會反映服務的實際狀態。</span><span class="sxs-lookup"><span data-stu-id="04800-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="04800-114">建議您使用<STRONG>「</STRONG>逐步<STRONG>服務狀態 (選用) </STRONG>來開啟 MICROSOFT Management Console (MMC) ，並確認已順利啟動服務。</span><span class="sxs-lookup"><span data-stu-id="04800-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="04800-115">如果尚未啟動任何 Lync Server 服務，您可以在 MMC 中以滑鼠右鍵按一下該服務，然後按一下 [ <STRONG>啟動</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="04800-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

