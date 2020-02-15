---
title: Lync Server 2013： 提供在分支網站的 PSTN 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9fe25fc10da3ffc27b882b7d41aac0ad97677f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="d9d84-102">提供在分支網站 Lync Server 2013 中的 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="d9d84-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9d84-103">_**主題上次修改日期：** 2012年-10-05_</span><span class="sxs-lookup"><span data-stu-id="d9d84-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d9d84-104">我們建議使用 Microsoft Lync Server 2013 規劃工具，將分支網站新增至您的拓撲，並在分支網站中設定語音基礎結構。</span><span class="sxs-lookup"><span data-stu-id="d9d84-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="d9d84-105">如果您不使用規劃工具，使用本節中這一節中的主題，首先，新增分支網站，並接著，設定您的語音基礎結構所定義的 IP/公用交換電話網路 (PSTN) 閘道及/或藉由設定 SIP 主幹，（含或不透過媒體旁路）。</span><span class="sxs-lookup"><span data-stu-id="d9d84-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="d9d84-106">連線至分支網站的專用交換機 (PBX) 是另一個選項。</span><span class="sxs-lookup"><span data-stu-id="d9d84-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9d84-107">如果您想要提供分支網站恢復能力，您必須部署 Survivable Branch Appliance、 Survivable Branch Server 或 Standard Edition server 分支網站。</span><span class="sxs-lookup"><span data-stu-id="d9d84-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="d9d84-108">如需詳細資訊，請參閱<A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">部署 Survivable Branch Appliance 或 survivable branch Server 與 Lync Server 2013</A>或<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>中，適當地部署文件中。</span><span class="sxs-lookup"><span data-stu-id="d9d84-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d9d84-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d9d84-109">In This Section</span></span>

  - [<span data-ttu-id="d9d84-110">將分支網站新增至您在 Lync Server 2013 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="d9d84-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="d9d84-111">在 Lync Server 2013 中定義 PSTN 閘道的分支網站</span><span class="sxs-lookup"><span data-stu-id="d9d84-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="d9d84-112">設定與 Lync Server 2013 中的媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="d9d84-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="d9d84-113">沒有媒體旁路 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="d9d84-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9d84-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d9d84-114">See Also</span></span>


[<span data-ttu-id="d9d84-115">規劃 Lync Server 2013 中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="d9d84-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="d9d84-116">規劃 Lync Server 2013 中的 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="d9d84-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

