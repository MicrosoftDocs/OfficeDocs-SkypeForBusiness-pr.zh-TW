---
title: 移轉中繼伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7786ecfd72ac32de74c9947f0effa1fad0c9603
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="3952e-102">移轉中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3952e-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3952e-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="3952e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3952e-104">中繼伺服器已合併到 Lync Server 2013 試驗拓撲，當您執行合併列印精靈。</span><span class="sxs-lookup"><span data-stu-id="3952e-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="3952e-105">您設定 Lync Server 2013 中繼伺服器，不過之後所有的使用者完成移轉，因為 Office Communications Server 2007 R2 集區無法與 Lync Server 2013 中繼伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3952e-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="3952e-106">並排顯示在移轉期間，與 Office Communications Server 2007 R2 中繼伺服器進行通訊的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="3952e-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="3952e-107">當您設定您的 Lync Server 2013 中繼伺服器時，您也必須升級，或取代 Office Communications Server 2007 R2 閘道。</span><span class="sxs-lookup"><span data-stu-id="3952e-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="3952e-108">Office Communications Server 2007 R2 閘道不支援 Lync Server 2013 中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="3952e-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="3952e-109">您必須部署 Lync Server 2013 的認證，並與 Lync Server 2013 中繼伺服器產生關聯的閘道。</span><span class="sxs-lookup"><span data-stu-id="3952e-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="3952e-110">您可以完全解除委任 Office Communications Server 2007 R2 部署之前，則需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="3952e-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="3952e-111">本節主題說明您需要執行完成之後，您的 Lync Server 2013 中繼伺服器移轉的組態工作。</span><span class="sxs-lookup"><span data-stu-id="3952e-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="3952e-112">轉換成獨立中繼伺服器組合的中繼伺服器是選用的工作。</span><span class="sxs-lookup"><span data-stu-id="3952e-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="3952e-113">設定中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3952e-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="3952e-114">變更語音路由以使用新的 Lync Server 2013 中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="3952e-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="3952e-115">組合式的中繼伺服器轉換成獨立中繼伺服器 （選用）</span><span class="sxs-lookup"><span data-stu-id="3952e-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

