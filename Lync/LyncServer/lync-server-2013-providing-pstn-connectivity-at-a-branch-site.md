---
title: Lync Server 2013：在分支網站提供 PSTN 連線能力
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
ms.openlocfilehash: 38c76d378db31cb8a6619a18072ec0218260843e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513170"
---
# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="6c57b-102">在 Lync Server 2013 的分支網站提供 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="6c57b-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c57b-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6c57b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6c57b-104">我們建議使用 Microsoft Lync Server 2013 （計畫工具）將分支網站新增至您的拓撲，並在分支網站中設定語音基礎結構。</span><span class="sxs-lookup"><span data-stu-id="6c57b-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="6c57b-105">如果您不是使用規劃工具，請先使用本節的主題中的程式，以新增分支網站，然後再透過定義 IP/公用交換電話網路 (PSTN) 閘道和/或設定 SIP 主幹 (設定或不使用媒體旁路) 來設定語音基礎結構。</span><span class="sxs-lookup"><span data-stu-id="6c57b-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="6c57b-106">將專用交換機 exchange (PBX) 連接至分支網站是另一個選項。</span><span class="sxs-lookup"><span data-stu-id="6c57b-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c57b-107">如果您想要提供分支網站恢復能力，您必須在分支網站上部署 Survivable 分支裝置、Survivable 分支伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="6c57b-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="6c57b-108">如需詳細資訊，請參閱部署檔中的部署 <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Survivable 分支裝置或具有 Lync server 2013</A> 或 <A href="lync-server-2013-deploying-lync-server.md">部署 lync Server 2013</A>的伺服器。</span><span class="sxs-lookup"><span data-stu-id="6c57b-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6c57b-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6c57b-109">In This Section</span></span>

  - [<span data-ttu-id="6c57b-110">將分支網站新增至您在 Lync Server 2013 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="6c57b-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="6c57b-111">在 Lync Server 2013 中定義分支網站的 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="6c57b-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="6c57b-112">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="6c57b-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="6c57b-113">在 Lync Server 2013 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="6c57b-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c57b-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6c57b-114">See Also</span></span>


[<span data-ttu-id="6c57b-115">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="6c57b-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="6c57b-116">在 Lync Server 2013 中規劃 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="6c57b-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

