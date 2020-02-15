---
title: Lync Server 2013： 略過媒體的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b962905870287ef6765ecb6e7ee9b3e321ac6a8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="f1f48-102">Lync Server 2013 中略過媒體的技術需求</span><span class="sxs-lookup"><span data-stu-id="f1f48-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1f48-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="f1f48-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f1f48-104">中繼伺服器 PSTN 每次呼叫，決定是否可以透過從原點的 Lync 端點的媒體直接到中繼伺服器對等網路傳送而周遊中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1f48-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="f1f48-105">對等可以是 PSTN 閘道、IP-PBX 或網際網路電話服務提供者 (ITSP) 上的工作階段邊界控制器 (SBC) 與路由通話之中繼伺服器之間的主幹關聯。</span><span class="sxs-lookup"><span data-stu-id="f1f48-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="f1f48-106">符合下列需求時，可以使用媒體旁路：</span><span class="sxs-lookup"><span data-stu-id="f1f48-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="f1f48-107">中繼伺服器對等網路必須支援媒體旁路，最重要的是能夠處理 （又稱為 「 早期對話 」） 的多個 invite 的分支回應的必要功能。</span><span class="sxs-lookup"><span data-stu-id="f1f48-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="f1f48-108">請連絡閘道或 PBX 製造商或是 ITSP，以取得閘道、PBX 或 SBC 可以接受的早期對話數上限值。</span><span class="sxs-lookup"><span data-stu-id="f1f48-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="f1f48-109">中繼伺服器對等網路必須接受直接從 Lync 端點的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="f1f48-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="f1f48-110">許多 ITSPs 允許他們只從中繼伺服器接收流量的 SBC。</span><span class="sxs-lookup"><span data-stu-id="f1f48-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="f1f48-111">請連絡 ITSP 來判斷其 SBC 是否接受直接從 Lync 端點的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="f1f48-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="f1f48-112">Lync 用戶端和對等網路連線必須良好，這表示他們可以都位於相同的網路地區，或在網路透過 WAN 連線到該區域的站台連結的中繼伺服器有無頻寬限制</span><span class="sxs-lookup"><span data-stu-id="f1f48-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f1f48-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f1f48-113">See Also</span></span>


[<span data-ttu-id="f1f48-114">媒體旁路模式的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1f48-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="f1f48-115">媒體旁路和 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="f1f48-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

