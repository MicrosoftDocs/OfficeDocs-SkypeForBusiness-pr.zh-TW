---
title: 移轉中繼伺服器
description: 遷移轉送伺服器。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31cc4c95f0e9c86b48594238218db22f3ec1a387
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570329"
---
# <a name="migrate-mediation-server"></a><span data-ttu-id="89e19-103">移轉中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="89e19-103">Migrate Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89e19-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="89e19-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="89e19-105">當您執行 [合併] 嚮導時，您的轉送伺服器會合並至您的 Lync Server 2013 試驗拓撲。</span><span class="sxs-lookup"><span data-stu-id="89e19-105">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="89e19-106">您可以設定 Lync Server 2013 轉送伺服器，但在遷移所有使用者之後，因為 Office 通訊伺服器 2007 R2 集區無法與 Lync Server 2013 轉送伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="89e19-106">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="89e19-107">在並列遷移期間，Lync Server 2013 集區會與 Office 通訊伺服器 2007 R2 轉送伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="89e19-107">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="89e19-108">當您設定 Lync Server 2013 轉送伺服器時，您也必須升級或取代您的 Office 通訊伺服器 2007 R2 閘道。</span><span class="sxs-lookup"><span data-stu-id="89e19-108">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="89e19-109">Office 通訊伺服器 2007 R2 閘道不支援 Lync Server 2013 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="89e19-109">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="89e19-110">您需要部署已驗證 Lync Server 2013 的閘道，並與 Lync Server 2013 轉送伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="89e19-110">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="89e19-111">您必須先執行此步驟，才能完全解除您的 Office 通訊伺服器 2007 R2 部署。</span><span class="sxs-lookup"><span data-stu-id="89e19-111">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="89e19-112">本節中的主題說明在完成 Lync Server 2013 轉送伺服器的遷移後，需要執行的設定工作。</span><span class="sxs-lookup"><span data-stu-id="89e19-112">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="89e19-113">將組合的轉送伺服器轉換成獨立的轉送伺服器是選用的任務。</span><span class="sxs-lookup"><span data-stu-id="89e19-113">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="89e19-114">設定轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="89e19-114">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="89e19-115">變更語音路由以使用新的 Lync Server 2013 轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="89e19-115">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="89e19-116">將組合的轉送伺服器轉換成獨立轉送伺服器 (選用) </span><span class="sxs-lookup"><span data-stu-id="89e19-116">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

