---
title: Lync Server 2013：部署 Survivable Branch Appliance 或 Survivable Branch Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7cf894fe6650ff3c06eaaa37f6ba05d70f50eeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="ccf13-102">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="ccf13-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccf13-103">_**主題上次修改日期：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="ccf13-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="ccf13-104">彈性企業語音指的是分支網站復原功能，也就是，在中央網站連結無法使用的情況下，提供連續的企業語音服務來分支網站使用者。</span><span class="sxs-lookup"><span data-stu-id="ccf13-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="ccf13-105">針對中小型及中型分支網站（有25至1000個使用者的分支網站），我們建議您部署 Survivable 分支裝置，這將會使用其內建 PSTN 閘道或 SIP 主幹來終止公用交換電話網絡（PSTN）通話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="ccf13-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ccf13-106">Survivable 分支裝置是協力廠商裝置，其中包含執行 Windows Server 2008 R2 作業系統、Lync Server 2013 註冊機構、中繼伺服器軟體和 PSTN 閘道的刀片伺服器，全都在單一裝置主機殼中。</span><span class="sxs-lookup"><span data-stu-id="ccf13-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="ccf13-107">針對1000至5000使用者且沒有彈性 WAN 的分支網站，我們建議將 Survivable 分支伺服器連線至 PSTN 閘道或 SIP 幹線至電話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="ccf13-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ccf13-108">Survivable 分支伺服器是 Windows Server 電腦，其中安裝了註冊機構和轉送伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="ccf13-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ccf13-109">對於超過5000個使用者和專用 Lync Server 系統管理員的分支網站，我們建議使用完整的 Lync Server 2013 部署，並與中央網站不同。</span><span class="sxs-lookup"><span data-stu-id="ccf13-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="ccf13-110">如需針對貴組織中的分支網站選擇最佳復原方案的詳細資料，包括先決條件及規劃考慮，請參閱規劃檔中<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支網站復原需求</A>。</span><span class="sxs-lookup"><span data-stu-id="ccf13-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ccf13-111">駐留在 Lync Server Survivable 分支裝置上的使用者無法建立新的聊天室，或無法查看現有聊天室的聊天室卡片。</span><span class="sxs-lookup"><span data-stu-id="ccf13-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ccf13-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="ccf13-112">In This Section</span></span>

  - [<span data-ttu-id="ccf13-113">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央網站工作</span><span class="sxs-lookup"><span data-stu-id="ccf13-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="ccf13-114">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Server - 分支網站工作</span><span class="sxs-lookup"><span data-stu-id="ccf13-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="ccf13-115">在 Lync Server 2013 中為分支網站恢復設定使用者</span><span class="sxs-lookup"><span data-stu-id="ccf13-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="ccf13-116">在 Lync Server 2013 中將使用者隸屬於 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="ccf13-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="ccf13-117">Lync Server 2013 中的附錄：Survivable Branch Appliance 和 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="ccf13-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ccf13-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="ccf13-118">See Also</span></span>


[<span data-ttu-id="ccf13-119">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccf13-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

