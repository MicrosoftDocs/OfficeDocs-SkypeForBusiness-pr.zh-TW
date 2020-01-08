---
title: Lync Server 2013：增強型 9-1-1 (E9-1-1) 和中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a4d8ba329d55c916b089437d4c63804c592c0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="8b309-102">Lync Server 2013 中的增強型 9-1-1 (E9-1-1) 和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="8b309-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b309-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="8b309-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="8b309-104">中繼伺服器擁有延伸的功能，讓它能夠正確地與增強型9-1-1 （E9-1）服務提供者互動。</span><span class="sxs-lookup"><span data-stu-id="8b309-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="8b309-105">在中繼伺服器上不需要特殊設定;根據預設，E9-1-1 互動所需的 SIP 延伸是包含在與閘道對等方（PSTN 閘道、IP PBX 或網際網路電話服務提供者的 SBC，包括 E9-1-1 服務）的互動。介面</span><span class="sxs-lookup"><span data-stu-id="8b309-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="8b309-106">在現有的轉送伺服器池中，或需要獨立的中繼伺服器的 SIP 主幹是否可在現有的中繼伺服器池上終止，或是否需要獨立的中繼伺服器，取決於 E9 SBC 是否可與中繼伺服器的池互動。</span><span class="sxs-lookup"><span data-stu-id="8b309-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="8b309-107">如需詳細資訊，請參閱[Lync Server 2013 中的 M:N 幹線](lync-server-2013-m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="8b309-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

