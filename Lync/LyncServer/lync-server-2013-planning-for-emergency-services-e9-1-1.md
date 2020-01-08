---
title: Lync Server 2013：規劃緊急服務 (E9-1-1)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for emergency services (E9-1-1)
ms:assetid: 0a76f97b-474a-4bc1-8cd3-28c7e2bb57b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398154(v=OCS.15)
ms:contentKeyID: 48183363
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98479ec674627cd663eb0d83fc670eb3feb5a8b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-emergency-services-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="2ea99-102">在 Lync Server 2013 中規劃緊急服務 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="2ea99-102">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ea99-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="2ea99-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="2ea99-104">Lync Server 2013 支援在美國內增強9-1-1 （E9-1）服務，成為企業語音部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="2ea99-104">Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) services within the United States as part of an Enterprise Voice deployment.</span></span> <span data-ttu-id="2ea99-105">E9-1-1 是一個緊急派單功能，它會將9-1-1 通話與由市政（也就是街道）位址及其他更多特定位置資訊（例如底價編號）組成的緊急回應位置（例如，來自 office 建築物的通話）進行關聯以及其他多租戶功能。</span><span class="sxs-lookup"><span data-stu-id="2ea99-105">E9-1-1 is an emergency dispatch feature that associates a 9-1-1 call with an Emergency Response Location (ERL) that consists of civic (that is, street) addresses and other more specific location information, such as floor numbers, for calls from office buildings and other multitenant facilities.</span></span> <span data-ttu-id="2ea99-106">透過使用隨附的 ERL，公用安全應答點（PSAP）可立即在 distress 中將第一次回應程式傳送給來電者，但不小心會將回應方定向到不正確或不明確的位置。</span><span class="sxs-lookup"><span data-stu-id="2ea99-106">By using the provided ERL, a Public Safety Answering Point (PSAP) can immediately dispatch first responders to the caller in distress with reduced risk of inadvertently directing the responder to an incorrect or ambiguous location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ea99-107">Lync Server 有三個高級企業語音功能： [通話許可控制]、[緊急服務] （E9-1-1），以及 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="2ea99-107">Lync Server has three advanced Enterprise Voice features: call admission control, emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="2ea99-108">如需所有這三項功能共有的規劃資訊的概覽，請參閱<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的 [高級企業語音功能] 的網路設定</A>。</span><span class="sxs-lookup"><span data-stu-id="2ea99-108">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2ea99-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="2ea99-109">In This Section</span></span>

  - [<span data-ttu-id="2ea99-110">Lync Server 2013 中的 E9-1-1 概觀</span><span class="sxs-lookup"><span data-stu-id="2ea99-110">Overview of E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-overview-of-e9-1-1.md)

  - [<span data-ttu-id="2ea99-111">在 Lync Server 2013 中定義緊急通話需求</span><span class="sxs-lookup"><span data-stu-id="2ea99-111">Defining your requirements for emergency calls in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-emergency-calls.md)

  - [<span data-ttu-id="2ea99-112">Lync Server 2013 的 E9 部署檢查清單-1-1</span><span class="sxs-lookup"><span data-stu-id="2ea99-112">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-e9-1-1.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

