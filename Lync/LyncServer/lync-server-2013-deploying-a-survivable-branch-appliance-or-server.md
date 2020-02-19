---
title: Lync Server 2013： 部署 Survivable Branch Appliance 或 survivable branch 伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 835a12cb49c8474389b8ae3cc26773fcea2e4157
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="0a55f-102">部署 Survivable Branch Appliance 或 survivable branch Server 與 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a55f-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a55f-103">_**上次修改主題：** 2014年-12-10_</span><span class="sxs-lookup"><span data-stu-id="0a55f-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="0a55f-104">彈性的 Enterprise Voice 指的是分支網站恢復能力，也就是能夠繼續提供企業語音服務分支網站使用者的中央網站的連結會變成無法使用。</span><span class="sxs-lookup"><span data-stu-id="0a55f-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="0a55f-105">小型和中型分支網站 （與 25 到 1000 使用者的分支網站），我們建議部署 Survivable Branch Appliance，就會使用它內建的 PSTN 閘道或 SIP 主幹電話終止公用交換的電話網路 (PSTN) 通話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="0a55f-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="0a55f-106">Survivable Branch Appliance 是包含執行 Windows Server 2008 R2 作業系統、 Lync Server 2013 登錄器、 中繼伺服器軟體和 PSTN 閘道，全部在單一 appliance 底座] 刀鋒視窗中伺服器的協力廠商裝置。</span><span class="sxs-lookup"><span data-stu-id="0a55f-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="0a55f-107">對於沒有可恢復的 WAN 1000 到 5000 使用者與分支網站]，我們建議 Survivable Branch 伺服器連線至 PSTN 閘道或 SIP 主幹電話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="0a55f-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="0a55f-108">Survivable Branch Server 是 Windows Server 架構的電腦已安裝在其上的登錄器和中繼伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="0a55f-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a55f-109">針對超過 5000 個使用者與專用的 Lync Server 系統管理員的分支網站，建議您完整的 Lync Server 2013 部署，與中央網站的不同。</span><span class="sxs-lookup"><span data-stu-id="0a55f-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="0a55f-110">如需在您的組織選擇最佳恢復解決方案的分支網站，包括先決條件和規劃考量的詳細資訊，請參閱<A href="lync-server-2013-branch-site-resiliency-requirements.md">分支網站恢復能力需求 Lync Server 2013</A>中規劃文件。</span><span class="sxs-lookup"><span data-stu-id="0a55f-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0a55f-111">位於 Lync Server Survivable Branch Appliance 的使用者將無法建立新聊天室或檢視現有的會議室的會議室卡片。</span><span class="sxs-lookup"><span data-stu-id="0a55f-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a55f-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0a55f-112">In This Section</span></span>

  - [<span data-ttu-id="0a55f-113">部署 Survivable Branch Appliance 或 survivable branch Server 與 Lync Server 2013-中央網站工作</span><span class="sxs-lookup"><span data-stu-id="0a55f-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="0a55f-114">部署 Survivable Branch Appliance 或 Server 與 Lync Server 2013-分支網站工作</span><span class="sxs-lookup"><span data-stu-id="0a55f-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="0a55f-115">在 Lync Server 2013 中設定分支網站恢復能力的使用者</span><span class="sxs-lookup"><span data-stu-id="0a55f-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="0a55f-116">使用者隸屬於 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器</span><span class="sxs-lookup"><span data-stu-id="0a55f-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="0a55f-117">附錄： Survivable Branch Appliance 和 Lync Server 2013 中的伺服器</span><span class="sxs-lookup"><span data-stu-id="0a55f-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a55f-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0a55f-118">See Also</span></span>


[<span data-ttu-id="0a55f-119">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a55f-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

