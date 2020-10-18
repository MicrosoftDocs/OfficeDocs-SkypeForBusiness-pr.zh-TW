---
title: Lync Server 2013：新的 Enterprise Voice 功能
description: Lync Server 2013：新的 Enterprise Voice 功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1fc0c0970fe22fb6a56eaf0d950f1d49d210826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578829"
---
# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="7c953-103">Lync Server 2013 中新的 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="7c953-103">New Enterprise Voice features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c953-104">_**主題上次修改日期：** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="7c953-104">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="7c953-105">Lync Server 2013 引進數種可增強 Enterprise Voice 的新路由和通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="7c953-105">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="7c953-106">Lync Server 2013 支援轉送伺服器和閘道之間的多個主幹。</span><span class="sxs-lookup"><span data-stu-id="7c953-106">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="7c953-107">*主幹*是埠號碼與轉送伺服器與埠號碼及閘道之間的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="7c953-107">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="7c953-108">這表示轉送伺服器可以有多個主幹至不同的閘道，而閘道可以有多個主幹至不同的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="7c953-108">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="7c953-109">主幹間路由可讓 Lync Server 2013 將 IP-PBX 與公用交換電話網路 (PSTN) 閘道或互連多個 IP-PBX 系統的網路互連。</span><span class="sxs-lookup"><span data-stu-id="7c953-109">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="7c953-110">Lync Server 2013 充當粘附 (，也就是不同電話語音系統之間的相互互連) 。</span><span class="sxs-lookup"><span data-stu-id="7c953-110">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="7c953-111">Microsoft Lync Server 2013 可改進「來電轉接」、「同時震鈴」、「語音信箱處理」及「來電者識別碼」簡報的功能。</span><span class="sxs-lookup"><span data-stu-id="7c953-111">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="7c953-112">這些功能豐富了企業語音通話體驗。</span><span class="sxs-lookup"><span data-stu-id="7c953-112">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="7c953-113">Lync Server 2013 引進了下列新的 Enterprise Voice 增強功能：</span><span class="sxs-lookup"><span data-stu-id="7c953-113">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="7c953-114">Lync Server 2013 中的新通話功能</span><span class="sxs-lookup"><span data-stu-id="7c953-114">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="7c953-115">Lync Server 2013 中的新來電者識別碼功能</span><span class="sxs-lookup"><span data-stu-id="7c953-115">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="7c953-116">Lync Server 2013 中的新語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="7c953-116">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="7c953-117">Lync Server 2013 中的新主幹功能</span><span class="sxs-lookup"><span data-stu-id="7c953-117">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="7c953-118">Lync Server 2013 中的新主幹間功能</span><span class="sxs-lookup"><span data-stu-id="7c953-118">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="7c953-119">Lync Server 2013 中的新通話管理功能</span><span class="sxs-lookup"><span data-stu-id="7c953-119">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

