---
title: Lync Server 2013： 在伺服器上啟動服務
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
ms.openlocfilehash: 7ac91d76cd060adfc9a20ae74da694c9a2cc608a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="f7cb1-102">Lync Server 2013 的伺服器上啟動服務</span><span class="sxs-lookup"><span data-stu-id="f7cb1-102">Start services on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7cb1-103">_**上次修改主題：** 2014年-09-03_</span><span class="sxs-lookup"><span data-stu-id="f7cb1-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="f7cb1-104">若要順利完成此程序您應該記錄的使用者是屬於 RTCUniversalServerAdmins 群組成員身分或具有正確的權限委派。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="f7cb1-105">如需有關委派權限的詳細資訊，請參閱主題[Lync Server 2013 中的委派設定權限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="f7cb1-106">在您的伺服器上安裝本機設定存放區、 安裝 Lync Server 2013 的元件，並在前端伺服器或前端伺服器上設定憑證之後，您必須在伺服器上啟動 Lync Server 2013 服務。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="f7cb1-107">若要啟動服務，每個前端伺服器上部署中使用下列程序。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="f7cb1-108">若要在 Standard Edition 或前端伺服器上啟動服務</span><span class="sxs-lookup"><span data-stu-id="f7cb1-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="f7cb1-109">在 [Lync Server 部署精靈] [ **Lync Server 2013** ] 頁面上，按一下 [**執行**下一步] 為**步驟 4： 啟動服務**。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="f7cb1-110">在 [**啟動服務**] 頁面上，按 [**下一步**若要在伺服器上啟動 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="f7cb1-111">在 **[執行命令]** 頁面上順利啟動所有服務之後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f7cb1-112">在伺服器上啟動服務的命令是報告事實上已啟動服務的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="f7cb1-113">它可能不會反映服務的實際狀態。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="f7cb1-114">我們建議您使用步驟緊接在<STRONG>啟動服務</STRONG>的<STRONG>服務狀態 （選用）</STRONG>若要開啟 Microsoft Management Console (MMC)，並確認已成功啟動服務。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="f7cb1-115">如果任何 Lync Server 服務尚未啟動，您可以在 MMC 中，該服務上按一下滑鼠右鍵，然後按一下 [<STRONG>開始</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="f7cb1-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

