---
title: Lync Server 2013：增強型 9-1-1 (E9-1-1) 和轉送伺服器
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
ms.openlocfilehash: 3a84b9eb5579a1f0931f3363e2e4071ea7c8ac5e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="cd984-102">Lync Server 2013 中的增強型 9-1-1 (E9-1-1) 和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="cd984-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd984-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="cd984-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="cd984-104">轉送伺服器具有擴充的功能，可與增強型 9-1-1 (E9-1-1) 服務提供者正確互動。</span><span class="sxs-lookup"><span data-stu-id="cd984-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="cd984-105">轉送伺服器上不需要特殊設定;E9-1-1 互動所需的 SIP 擴充預設會包含在轉送伺服器的 SIP 通訊協定中，以用於與閘道對等 (PSTN 閘道、IP-PBX 或內部網際網路電話語音服務提供者（包括 E9-1-1）服務提供者的 SBC 進行互動) </span><span class="sxs-lookup"><span data-stu-id="cd984-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="cd984-106">E9-1-1 服務提供者的 SIP 主幹是否可在現有的轉送伺服器集區上終止，或是否需要獨立轉送伺服器，取決於 E9-1-1 SBC 是否可以與轉送伺服器集區互動。</span><span class="sxs-lookup"><span data-stu-id="cd984-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="cd984-107">如需詳細資訊，請參閱[M:N 主幹 In Lync Server 2013](lync-server-2013-m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="cd984-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

