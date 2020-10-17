---
title: Lync Server 2013 支援主控 Exchange UM 整合
description: Lync Server 2013 支援主控 Exchange UM 整合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88920667d703bc634921903e8e3995cb65db6873
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546318"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="f0323-103">Lync Server 2013 中的主控 Exchange UM 整合支援</span><span class="sxs-lookup"><span data-stu-id="f0323-103">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0323-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f0323-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f0323-105">Lync Server 2013 ExUM 路由應用程式可在內部部署環境中與 Exchange 整合通訊 (UM) 進行整合，其中，Lync Server 2013 和 Exchange UM 皆安裝于您企業內的本機，或 Exchange UM 是由服務提供者所主控，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="f0323-105">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="f0323-106">![內部部署 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")</span><span class="sxs-lookup"><span data-stu-id="f0323-106">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="f0323-107">支援下列模式：</span><span class="sxs-lookup"><span data-stu-id="f0323-107">The following modes are supported:</span></span>

  - <span data-ttu-id="f0323-108">**內部部署模式**    Lync Server 2013 和 Exchange UM 都部署于您企業內的本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="f0323-108">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="f0323-109">**跨部署模式**    Lync Server 2013 部署于您企業內的本機伺服器上，而 Exchange UM 是以線上服務提供者的功能（例如 Microsoft Exchange Online 資料中心）主控。</span><span class="sxs-lookup"><span data-stu-id="f0323-109">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="f0323-110">**混合模式**    您的 Lync Server 2013 部署中有一些使用者信箱位於執行 Microsoft Exchange Server 內部的本機伺服器上，而部分信箱位於裝載的 Exchange 服務資料中心。</span><span class="sxs-lookup"><span data-stu-id="f0323-110">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0323-111">混合模式可以做為進行評估和逐步遷移至主控 Exchange UM 時的過渡方案，如果您選擇在遷移其他使用者後，將某些使用者的 Exchange UM 服務保留在內部部署，則可以做為永久解決方案。</span><span class="sxs-lookup"><span data-stu-id="f0323-111">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="f0323-112">若要整合 Lync Server 2013 與主控 Exchange UM，您必須設定 *共用 SIP 位址空間* ， (也稱為 *分割網域*) 。</span><span class="sxs-lookup"><span data-stu-id="f0323-112">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="f0323-113">在此設定中，Lync Server 2013 和協力廠商託管的 Exchange UM 服務提供者可以存取相同的 SIP 網域位址空間。</span><span class="sxs-lookup"><span data-stu-id="f0323-113">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="f0323-114">如需詳細資訊，請參閱規劃檔中的 [主控 EXCHANGE UM 整合架構（Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) ）。</span><span class="sxs-lookup"><span data-stu-id="f0323-114">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

