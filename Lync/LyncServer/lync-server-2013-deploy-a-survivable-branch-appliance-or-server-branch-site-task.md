---
title: 部署 Survivable 分支裝置或伺服器-分支網站工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 835de118f46dba61fe86ee3f412c55d945dfb2a9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521650"
---
# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="9767e-102">使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器-分支網站工作</span><span class="sxs-lookup"><span data-stu-id="9767e-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9767e-103">_**主題上次修改日期：** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="9767e-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="9767e-104">在分支網站上執行下列兩個程式中所述的一項，在 [使用 Lync Server 2013-中央網站工作順利完成部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)的工作之後。</span><span class="sxs-lookup"><span data-stu-id="9767e-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9767e-105">您必須是 RTCUniversalSBATechnicians 群組的成員，才能執行這項程序。</span><span class="sxs-lookup"><span data-stu-id="9767e-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="9767e-106">若要部署 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="9767e-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="9767e-107">Survivable 分支裝置部署是由 Survivable Branch 裝置廠商透過 web 使用者介面 (UI) 來啟用。</span><span class="sxs-lookup"><span data-stu-id="9767e-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="9767e-108">如需部署 Survivable 分支裝置的詳細資訊，請參閱 Survivable Branch 裝置廠商檔。</span><span class="sxs-lookup"><span data-stu-id="9767e-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="9767e-109">若要部署 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="9767e-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="9767e-110">在執行 Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 的電腦上安裝 Lync Server 2013，就像安裝任何其他 Lync Server 2013 Server 角色一樣。</span><span class="sxs-lookup"><span data-stu-id="9767e-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9767e-111">如需安裝 Lync Server 的相關資訊，請參閱部署檔中的 <A href="lync-server-2013-deploying-lync-server.md">部署 Lync server 2013</A> 。</span><span class="sxs-lookup"><span data-stu-id="9767e-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="9767e-112">**後續步驟**： [在 Lync Server 2013 中為分支網站恢復設定使用者](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="9767e-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9767e-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9767e-113">See Also</span></span>


[<span data-ttu-id="9767e-114">附錄 A：在 Lync Server 2013 中使用 Cmdlet 部署 Survivable Branch 裝置</span><span class="sxs-lookup"><span data-stu-id="9767e-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

