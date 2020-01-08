---
title: 遷移轉送伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="96c69-102">遷移轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="96c69-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96c69-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="96c69-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="96c69-104">當您執行 [合併] 嚮導時，您的中繼伺服器會合並到 Lync Server 2013 試驗拓撲。</span><span class="sxs-lookup"><span data-stu-id="96c69-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="96c69-105">您可以設定 Lync Server 2013 轉送伺服器，因為 Office 通訊伺服器 2007 R2 池無法與 Lync Server 2013 轉送伺服器通訊，所以在所有使用者都被遷移後。</span><span class="sxs-lookup"><span data-stu-id="96c69-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="96c69-106">在並行遷移期間，Lync Server 2013 pool 會與 Office 通訊伺服器 2007 R2 轉送伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="96c69-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="96c69-107">當您設定 Lync Server 2013 轉送服務伺服器時，您也必須升級或取代您的 Office 通訊伺服器 2007 R2 閘道。</span><span class="sxs-lookup"><span data-stu-id="96c69-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="96c69-108">Office 通訊伺服器 2007 R2 閘道不支援 Lync Server 2013 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="96c69-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="96c69-109">您需要部署認證給 Lync Server 2013 的閘道，並將它們與 Lync Server 2013 轉送伺服器進行關聯。</span><span class="sxs-lookup"><span data-stu-id="96c69-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="96c69-110">您必須先執行此步驟，才能完全解除與您的 Office 通訊伺服器 2007 R2 部署。</span><span class="sxs-lookup"><span data-stu-id="96c69-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="96c69-111">本節中的主題描述在您完成 Lync Server 2013 轉送伺服器的遷移之後，您需要執行的設定任務。</span><span class="sxs-lookup"><span data-stu-id="96c69-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="96c69-112">將 collocated 中繼伺服器轉換成獨立的中繼伺服器是一個選用的工作。</span><span class="sxs-lookup"><span data-stu-id="96c69-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="96c69-113">設定中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="96c69-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="96c69-114">變更語音路由以使用新的 Lync Server 2013 轉送服務伺服器</span><span class="sxs-lookup"><span data-stu-id="96c69-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="96c69-115">將 collocated 中繼伺服器轉換成獨立的中繼伺服器（選用）</span><span class="sxs-lookup"><span data-stu-id="96c69-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

