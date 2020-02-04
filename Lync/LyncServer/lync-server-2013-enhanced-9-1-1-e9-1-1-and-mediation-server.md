---
title: Lync Server 2013：增強型 9-1-1 (E9-1-1) 和中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac6d6d7c9dd533d26f2cbf5c5116db7af4424ffe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="b40f5-102">Lync Server 2013 中的增強型 9-1-1 (E9-1-1) 和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="b40f5-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b40f5-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="b40f5-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="b40f5-104">中繼伺服器擁有延伸的功能，讓它能夠正確地與增強型9-1-1 （E9-1）服務提供者互動。</span><span class="sxs-lookup"><span data-stu-id="b40f5-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="b40f5-105">在中繼伺服器上不需要特殊設定;根據預設，E9-1-1 互動所需的 SIP 延伸是包含在與閘道對等方（PSTN 閘道、IP PBX 或網際網路電話服務提供者的 SBC，包括 E9-1-1 服務）的互動。介面</span><span class="sxs-lookup"><span data-stu-id="b40f5-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="b40f5-106">在現有的轉送伺服器池中，或需要獨立的中繼伺服器的 SIP 主幹是否可在現有的中繼伺服器池上終止，或是否需要獨立的中繼伺服器，取決於 E9 SBC 是否可與中繼伺服器的池互動。</span><span class="sxs-lookup"><span data-stu-id="b40f5-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="b40f5-107">如需詳細資訊，請參閱[Lync Server 2013 中的 M:N 幹線](lync-server-2013-m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="b40f5-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

