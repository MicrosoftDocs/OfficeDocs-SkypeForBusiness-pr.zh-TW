---
title: 部署 Survivable Branch Appliance 或 Server-分支網站工作
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
ms.openlocfilehash: 30f4eaf2bcac00260cd14dd8b1e58f41e53ddd3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="c4d92-102">部署 Survivable Branch Appliance 或 Server 與 Lync Server 2013-分支網站工作</span><span class="sxs-lookup"><span data-stu-id="c4d92-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4d92-103">_**上次修改主題：** 2014年-10-28_</span><span class="sxs-lookup"><span data-stu-id="c4d92-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="c4d92-104">執行下列其中一個順利完成[部署 Survivable Branch Appliance 或 survivable branch Server 與 Lync Server 2013-中央網站工作](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)中的工作之後分支網站，本主題所述的兩個程序。</span><span class="sxs-lookup"><span data-stu-id="c4d92-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c4d92-105">您必須是 RTCUniversalSBATechnicians 群組的成員，才能執行這項程序。</span><span class="sxs-lookup"><span data-stu-id="c4d92-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="c4d92-106">若要部署 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="c4d92-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="c4d92-107">Survivable Branch Appliance 部署已由 Survivable Branch Appliance 供應商透過 web 使用者介面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="c4d92-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="c4d92-108">如需部署 Survivable Branch Appliance 的相關資訊，請參閱您 Survivable Branch Appliance 廠商文件。</span><span class="sxs-lookup"><span data-stu-id="c4d92-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="c4d92-109">若要部署 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="c4d92-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="c4d92-110">如同安裝任何其他的 Lync Server 2013 伺服器角色，請在執行 Windows Server 2008 R2、 Windows Server 2012 或 Windows Server 2012 R2 的電腦上安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c4d92-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c4d92-111">如需安裝 Lync Server 的相關資訊，請參閱部署文件中的<A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> 。</span><span class="sxs-lookup"><span data-stu-id="c4d92-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="c4d92-112">**下一步**： [Configuring 使用者在 Lync Server 2013 中的分支網站恢復能力](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="c4d92-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4d92-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c4d92-113">See Also</span></span>


[<span data-ttu-id="c4d92-114">附錄 a： 使用 cmdlet 部署 Survivable Branch Appliance Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="c4d92-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

