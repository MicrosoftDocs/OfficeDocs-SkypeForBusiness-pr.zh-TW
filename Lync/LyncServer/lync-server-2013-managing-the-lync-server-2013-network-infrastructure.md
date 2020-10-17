---
title: Lync Server 2013：管理 Lync Server 2013 網路基礎結構
description: Lync Server 2013：管理 Lync Server 2013 網路基礎結構。
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
ms.openlocfilehash: ab1b5c6fe52374b012063ac26640e9bb25496ad7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564099"
---
# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="5f107-103">管理 Lync Server 2013 網路基礎結構</span><span class="sxs-lookup"><span data-stu-id="5f107-103">Managing the Lync Server 2013 network infrastructure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f107-104">_**主題上次修改日期：** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="5f107-104">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="5f107-105">Microsoft Lync Server 2013 包括 (CAC) 和媒體旁路的通話許可控制支援。</span><span class="sxs-lookup"><span data-stu-id="5f107-105">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="5f107-106">若要執行這些功能，您必須設定區域的網路、網站、子網等等，這樣您就可以在需要限制音訊和視頻傳輸的情況下管理頻寬。</span><span class="sxs-lookup"><span data-stu-id="5f107-106">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="5f107-107">您也可以使用 [服務品質 (] QoS) 網路技術，以協助為音訊和影片通訊提供最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="5f107-107">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="5f107-108">您可以使用 Lync Server 控制台來設定及管理 CAC、媒體旁路和 QoS。</span><span class="sxs-lookup"><span data-stu-id="5f107-108">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="5f107-109">下列主題提供如何執行此作業的步驟。</span><span class="sxs-lookup"><span data-stu-id="5f107-109">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f107-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="5f107-110">In This Section</span></span>

  - [<span data-ttu-id="5f107-111">在 Lync Server 2013 中管理服務品質 (QoS) </span><span class="sxs-lookup"><span data-stu-id="5f107-111">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="5f107-112">在 Lync Server 2013 中管理通話許可控制</span><span class="sxs-lookup"><span data-stu-id="5f107-112">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="5f107-113">Lync Server 2013 網路介面</span><span class="sxs-lookup"><span data-stu-id="5f107-113">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="5f107-114">避免伺服器維護的新連線至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f107-114">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="5f107-115">Lync Server 2013 中的 lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="5f107-115">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="5f107-116">Lync Server 2013 中的主要健康情況指示器</span><span class="sxs-lookup"><span data-stu-id="5f107-116">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

