---
title: 主控 Exchange UM 整合的 Lync Server 2013 支援
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
ms.openlocfilehash: e0625d983f05e5b9b22bf5086d0689c117b2ecda
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="39793-102">主控 Exchange UM 整合的 Lync Server 2013 中的支援</span><span class="sxs-lookup"><span data-stu-id="39793-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39793-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="39793-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="39793-104">Lync Server 2013 ExUM Routing 應用程式在內部部署環境中，Lync Server 2013 與 Exchange UM 已同時安裝在本機上您企業內或使用 [Exchange UM 所主控支援整合與 Exchange 整合通訊 (UM)服務提供者，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="39793-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="39793-105">![內部部署 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")</span><span class="sxs-lookup"><span data-stu-id="39793-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="39793-106">支援下列模式：</span><span class="sxs-lookup"><span data-stu-id="39793-106">The following modes are supported:</span></span>

  - <span data-ttu-id="39793-107">**內部模式**   Lync Server 2013 和 Exchange UM 都部署於您企業內的本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="39793-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="39793-108">**跨部署模式**   Lync Server 2013 部署在您企業內的本機伺服器上，而 Exchange UM 裝載於線上服務提供者的設備，例如 Microsoft Exchange 線上資料中心。</span><span class="sxs-lookup"><span data-stu-id="39793-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="39793-109">**使用混合模式**   您的 Lync Server 2013 部署中，有一些使用者信箱位於執行 Microsoft Exchange Server，在您的企業和部分信箱位於託管式 Exchange 服務資料中心的本機伺服器。</span><span class="sxs-lookup"><span data-stu-id="39793-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39793-110">混合的模式可當作過渡時期解決方案期間評估及逐步移轉使用者至裝載的 Exchange UM，或當作永久解決方案如果您選擇將某些使用者的 Exchange UM 服務內部之後移轉其他人。</span><span class="sxs-lookup"><span data-stu-id="39793-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="39793-111">若要與裝載 Exchange UM 整合 Lync Server 2013，您必須設定*共用的 SIP 位址空間*（也稱為*分割網域*）。</span><span class="sxs-lookup"><span data-stu-id="39793-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="39793-112">在此組態中，Lync Server 2013 和協力廠商主控的 Exchange UM 服務提供者可以存取相同的 SIP 網域位址空間。</span><span class="sxs-lookup"><span data-stu-id="39793-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="39793-113">如需詳細資訊，請參閱[主控 Exchange UM 整合架構 Lync Server 2013 中的](lync-server-2013-hosted-exchange-um-integration-architecture.md)規劃文件。</span><span class="sxs-lookup"><span data-stu-id="39793-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

