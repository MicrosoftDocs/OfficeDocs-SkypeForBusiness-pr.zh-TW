---
title: Lync Server 2013：新企業語音功能
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
ms.openlocfilehash: 92c1c264b9ffa5459962b2b6e915ea0fef2cf775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="0ebc2-102">Lync Server 2013 中的新企業語音功能</span><span class="sxs-lookup"><span data-stu-id="0ebc2-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ebc2-103">_**主題上次修改日期：** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="0ebc2-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="0ebc2-104">Lync Server 2013 引進了數種新的路由與通話管理功能，可加強企業語音。</span><span class="sxs-lookup"><span data-stu-id="0ebc2-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="0ebc2-105">Lync Server 2013 支援在中繼伺服器和閘道之間進行多個 trunks。</span><span class="sxs-lookup"><span data-stu-id="0ebc2-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="0ebc2-106">*主幹*是埠號碼與中繼伺服器與埠號碼和閘道之間的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="0ebc2-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="0ebc2-107">這表示中繼伺服器可以有多個 trunks 至不同的閘道，而閘道可以有多個 trunks 至不同的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ebc2-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="0ebc2-108">Intertrunk 路由可讓 Lync Server 2013 將 IP PBX 互連至公用交換式電話網絡（PSTN）閘道，或與多個 IP PBX 系統相互連接。</span><span class="sxs-lookup"><span data-stu-id="0ebc2-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="0ebc2-109">Lync Server 2013 在不同的電話系統之間充當粘附（也就是互連）。</span><span class="sxs-lookup"><span data-stu-id="0ebc2-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="0ebc2-110">Microsoft Lync Server 2013 可改善來電轉接、同時撥打、語音信箱處理及本機號碼簡報等方面的改良功能。</span><span class="sxs-lookup"><span data-stu-id="0ebc2-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="0ebc2-111">這些功能豐富了企業語音通話體驗。</span><span class="sxs-lookup"><span data-stu-id="0ebc2-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="0ebc2-112">Lync Server 2013 引進了下列新的企業語音增強功能：</span><span class="sxs-lookup"><span data-stu-id="0ebc2-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="0ebc2-113">Lync Server 2013 中的新通話功能</span><span class="sxs-lookup"><span data-stu-id="0ebc2-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="0ebc2-114">Lync Server 2013 中的新來電顯示功能</span><span class="sxs-lookup"><span data-stu-id="0ebc2-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="0ebc2-115">Lync Server 2013 中的新語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="0ebc2-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="0ebc2-116">Lync Server 2013 中的新主幹功能</span><span class="sxs-lookup"><span data-stu-id="0ebc2-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="0ebc2-117">Lync Server 2013 中的新主幹間功能</span><span class="sxs-lookup"><span data-stu-id="0ebc2-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="0ebc2-118">Lync Server 2013 中的新通話管理功能</span><span class="sxs-lookup"><span data-stu-id="0ebc2-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

