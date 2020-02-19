---
title: Lync Server 2013： 新 Enterprise Voice 功能
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
ms.openlocfilehash: cf51e5d06241ece778d5bdb6dc41691e64682f18
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="b6bdd-102">Lync Server 2013 中的新 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="b6bdd-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6bdd-103">_**上次修改主題：** 2013年-05-01_</span><span class="sxs-lookup"><span data-stu-id="b6bdd-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="b6bdd-104">Lync Server 2013 引進數種新路由與電話管理功能可增強 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="b6bdd-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="b6bdd-105">Lync Server 2013 支援中繼伺服器和閘道之間的多個主幹。</span><span class="sxs-lookup"><span data-stu-id="b6bdd-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="b6bdd-106">*主幹*是連接埠號碼和中繼伺服器之間的連接埠號碼和閘道邏輯的關聯。</span><span class="sxs-lookup"><span data-stu-id="b6bdd-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="b6bdd-107">這表示中繼伺服器可以有不同的閘道，多個主幹和閘道可以有多個主幹至不同的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6bdd-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="b6bdd-108">主幹相互路由功能，可讓 Lync Server 2013 相互連線至公用交換的電話網路 (PSTN) 閘道 IP PBX 或 interconnect 多個 IP PBX 系統。</span><span class="sxs-lookup"><span data-stu-id="b6bdd-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="b6bdd-109">Lync Server 2013 會當做不同的電話語音系統之間的黏附 （亦即互相連線）。</span><span class="sxs-lookup"><span data-stu-id="b6bdd-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="b6bdd-110">Microsoft Lync Server 2013 可改善各方面的來電轉接、 同時響鈴、 語音郵件處理和來電者 ID 呈現方式。</span><span class="sxs-lookup"><span data-stu-id="b6bdd-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="b6bdd-111">這些功能豐富的 Enterprise Voice 通話體驗。</span><span class="sxs-lookup"><span data-stu-id="b6bdd-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="b6bdd-112">Lync Server 2013 引進下列新的增強功能 Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="b6bdd-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="b6bdd-113">Lync Server 2013 中的新通話功能</span><span class="sxs-lookup"><span data-stu-id="b6bdd-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="b6bdd-114">Lync Server 2013 中新的來電者識別碼功能</span><span class="sxs-lookup"><span data-stu-id="b6bdd-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="b6bdd-115">Lync Server 2013 中新的語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="b6bdd-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="b6bdd-116">Lync Server 2013 中的新主幹功能</span><span class="sxs-lookup"><span data-stu-id="b6bdd-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="b6bdd-117">Lync Server 2013 中的新主幹間功能</span><span class="sxs-lookup"><span data-stu-id="b6bdd-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="b6bdd-118">Lync Server 2013 中的新通話管理功能</span><span class="sxs-lookup"><span data-stu-id="b6bdd-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

