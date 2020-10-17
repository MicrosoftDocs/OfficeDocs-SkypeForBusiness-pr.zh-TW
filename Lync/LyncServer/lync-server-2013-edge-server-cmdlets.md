---
title: Lync Server 2013： Edge Server Cmdlet
description: Lync Server 2013： Edge Server Cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b73172331ddcde76672cccda682669f71dd7262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551669"
---
# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6bf92-103">Lync Server 2013 中的 Edge Server Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6bf92-103">Edge Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bf92-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="6bf92-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="6bf92-105">Edge server 提供一種方法，讓您可以將 Microsoft Lync Server 2013 的功能延伸至未登入您的內部網路的人員。</span><span class="sxs-lookup"><span data-stu-id="6bf92-105">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="6bf92-106">例如，如果您有透過網際網路（而不是透過內部網路）登入 Lync Server 2013 的遠端使用者驗證使用者--您將需要設定執行 Lync Server Access Edge service 的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="6bf92-106">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="6bf92-107">此外，如果您想要建立與另一個組織的同盟，或是您想要讓使用者能夠與具有「公用立即訊息服務」（如 Yahoo \! 、AOL 或 MSN）的使用者進行通訊的許可權，則需要 Edge server。</span><span class="sxs-lookup"><span data-stu-id="6bf92-107">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="6bf92-108">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="6bf92-108">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="6bf92-109">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="6bf92-109">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="6bf92-110">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="6bf92-110">Messenger until the service shut down date.</span></span> <span data-ttu-id="6bf92-111">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="6bf92-111">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="6bf92-112">已宣告。</span><span class="sxs-lookup"><span data-stu-id="6bf92-112">has been announced.</span></span> <span data-ttu-id="6bf92-113">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="6bf92-113">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="6bf92-114">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="6bf92-114">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="6bf92-115">信使。</span><span class="sxs-lookup"><span data-stu-id="6bf92-115">Messenger.</span></span> <span data-ttu-id="6bf92-116">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="6bf92-116">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="6bf92-117">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="6bf92-117">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="6bf92-118">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="6bf92-118">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="6bf92-119">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="6bf92-119">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="6bf92-120">Edge Server Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6bf92-120">Edge Server Cmdlets</span></span>

<span data-ttu-id="6bf92-121">下表列出的 Cmdlet 與管理 Edge Server 直接相關：</span><span class="sxs-lookup"><span data-stu-id="6bf92-121">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="6bf92-122">**Edge Server**</span><span class="sxs-lookup"><span data-stu-id="6bf92-122">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="6bf92-123">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bf92-123">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bf92-124">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bf92-124">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6bf92-125">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bf92-125">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bf92-126">[新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bf92-126">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bf92-127">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bf92-127">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bf92-128">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bf92-128">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6bf92-129">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bf92-129">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6bf92-130">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bf92-130">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6bf92-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6bf92-131">See Also</span></span>


[<span data-ttu-id="6bf92-132">Lync Server PowerShell 的博客</span><span class="sxs-lookup"><span data-stu-id="6bf92-132">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

