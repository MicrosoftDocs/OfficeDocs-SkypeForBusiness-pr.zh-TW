---
title: Lync Server 2013：管理 Lync Server 2013 網路基礎結構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8663c5837b118bc35c889dac34196a05a76dd63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="a2d7a-102">管理 Lync Server 2013 網路基礎結構</span><span class="sxs-lookup"><span data-stu-id="a2d7a-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2d7a-103">_**主題上次修改日期：** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="a2d7a-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="a2d7a-104">Microsoft Lync Server 2013 包含對通話許可控制（CAC）和媒體旁路的支援。</span><span class="sxs-lookup"><span data-stu-id="a2d7a-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="a2d7a-105">若要實現這些功能，您必須設定一個區域網路、網站、子網等等，這樣就能在需要限制音訊及視頻傳輸的情況下，管理頻寬。</span><span class="sxs-lookup"><span data-stu-id="a2d7a-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="a2d7a-106">您也可以使用 [服務品質（QoS）] 網路技術，協助提供最佳的音訊和視頻通訊使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="a2d7a-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="a2d7a-107">您可以使用 Lync Server [控制台] 來設定和管理 CAC、媒體旁路及 QoS。</span><span class="sxs-lookup"><span data-stu-id="a2d7a-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="a2d7a-108">下列主題提供如何執行此動作的步驟。</span><span class="sxs-lookup"><span data-stu-id="a2d7a-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2d7a-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="a2d7a-109">In This Section</span></span>

  - [<span data-ttu-id="a2d7a-110">管理 Lync Server 2013 中的服務品質（QoS）</span><span class="sxs-lookup"><span data-stu-id="a2d7a-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="a2d7a-111">在 Lync Server 2013 中管理呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="a2d7a-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="a2d7a-112">Lync Server 2013 網路介面</span><span class="sxs-lookup"><span data-stu-id="a2d7a-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="a2d7a-113">防止新連線至 Lync Server 2013 以進行伺服器維護</span><span class="sxs-lookup"><span data-stu-id="a2d7a-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="a2d7a-114">Lync Server 2013 中的 lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="a2d7a-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="a2d7a-115">Lync Server 2013 中的主要健康情況指示</span><span class="sxs-lookup"><span data-stu-id="a2d7a-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

