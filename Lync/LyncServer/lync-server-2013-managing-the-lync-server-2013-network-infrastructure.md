---
title: Lync Server 2013： 管理 Lync Server 2013 網路基礎結構
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
ms.openlocfilehash: a228ccf207a0197e1eb74c1f8f733df1f7912f6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="7a346-102">管理 Lync Server 2013 網路基礎結構</span><span class="sxs-lookup"><span data-stu-id="7a346-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a346-103">_**上次修改主題：** 2014年-02-11_</span><span class="sxs-lookup"><span data-stu-id="7a346-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="7a346-104">Microsoft Lync Server 2013 包含通話許可控制 (CAC) 的支援，以及媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="7a346-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="7a346-105">若要實作這些功能中，您必須設定的網路地區、 網站、 子網路，而等等，可讓您管理頻寬的情況下，其中音訊及視訊的傳輸需要加以限制。</span><span class="sxs-lookup"><span data-stu-id="7a346-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="7a346-106">您也可以使用的服務品質 (QoS) 網路技術，以協助提供最佳使用者經驗的音訊及視訊通訊。</span><span class="sxs-lookup"><span data-stu-id="7a346-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="7a346-107">您可以使用 Lync Server Control Panel 設定及管理 CAC、 媒體旁路和 QoS。</span><span class="sxs-lookup"><span data-stu-id="7a346-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="7a346-108">下列主題提供如何進行此作業的步驟。</span><span class="sxs-lookup"><span data-stu-id="7a346-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7a346-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="7a346-109">In This Section</span></span>

  - [<span data-ttu-id="7a346-110">管理服務的品質 (QoS 在 Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="7a346-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="7a346-111">管理 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="7a346-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="7a346-112">Lync Server 2013 網路介面</span><span class="sxs-lookup"><span data-stu-id="7a346-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="7a346-113">防止新連線至 Lync Server 2013 進行伺服器維護</span><span class="sxs-lookup"><span data-stu-id="7a346-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="7a346-114">Lync Server 2013 中的 Lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="7a346-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="7a346-115">Lync Server 2013 中的索引鍵的健康狀態指標</span><span class="sxs-lookup"><span data-stu-id="7a346-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

