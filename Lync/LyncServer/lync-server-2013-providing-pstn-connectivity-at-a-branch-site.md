---
title: Lync Server 2013：在分支網站提供 PSTN 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7ba3c77c789d10e80319542cd163186eef2d4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="cfc21-102">使用 Lync Server 2013 在分支網站提供 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="cfc21-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfc21-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="cfc21-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="cfc21-104">我們建議您使用 Microsoft Lync Server 2013、規劃工具，將分支網站新增至您的拓撲結構，並在分支網站中設定您的語音結構。</span><span class="sxs-lookup"><span data-stu-id="cfc21-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="cfc21-105">如果您不是使用規劃工具，請先使用本節主題中的程式來新增分支網站，然後再透過定義 IP/公開交換電話網絡（PSTN）閘道及/或設定 SIP 幹線（無論是否有媒體旁路）來設定您的語音結構。</span><span class="sxs-lookup"><span data-stu-id="cfc21-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="cfc21-106">將私人分支 exchange （PBX）連線至分支網站是另一個選項。</span><span class="sxs-lookup"><span data-stu-id="cfc21-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cfc21-107">如果您想要提供分支網站復原能力，您必須在分支網站上部署 Survivable 分支裝置、Survivable 分支伺服器或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="cfc21-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="cfc21-108">如需詳細資訊，請參閱部署檔中的 [<A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">使用 Lync server 2013 部署 Survivable 分支裝置或伺服器</A>] 或 [<A href="lync-server-2013-deploying-lync-server.md">部署 lync server 2013</A>]。</span><span class="sxs-lookup"><span data-stu-id="cfc21-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cfc21-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="cfc21-109">In This Section</span></span>

  - [<span data-ttu-id="cfc21-110">在 Lync Server 2013 中新增分支網站至拓撲</span><span class="sxs-lookup"><span data-stu-id="cfc21-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="cfc21-111">在 Lync Server 2013 中定義分支網站的 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="cfc21-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - <span data-ttu-id="cfc21-112">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="cfc21-112">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>

  - [<span data-ttu-id="cfc21-113">在 Lync Server 2013 中設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="cfc21-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cfc21-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="cfc21-114">See Also</span></span>


[<span data-ttu-id="cfc21-115">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="cfc21-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="cfc21-116">在 Lync Server 2013 規劃 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="cfc21-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

