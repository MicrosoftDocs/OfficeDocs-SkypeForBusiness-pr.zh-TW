---
title: Lync Server 2013 主控 Exchange UM 整合支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="dc943-102">Lync Server 2013 中的主控 Exchange UM 整合支援</span><span class="sxs-lookup"><span data-stu-id="dc943-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc943-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dc943-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dc943-104">Lync Server 2013 ExUM 路由應用程式支援在內部部署環境中與 Exchange 整合通訊（UM）整合，其中 Lync Server 2013 與 Exchange UM 都安裝在您的企業內部，或由 a 託管的 Exchange UM服務提供者，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="dc943-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="dc943-105">內部部署 lync ![Server EXCHANGE Um 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 LYNC Server exchange um 部署")</span><span class="sxs-lookup"><span data-stu-id="dc943-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="dc943-106">支援下列模式：</span><span class="sxs-lookup"><span data-stu-id="dc943-106">The following modes are supported:</span></span>

  - <span data-ttu-id="dc943-107">**[內部部署模式]**   Lync Server 2013 和 Exchange UM 都部署在企業中的本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="dc943-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="dc943-108">**[跨內部部署模式]**   Lync Server 2013 是在企業內部的本機伺服器上部署，Exchange UM 是在線上服務提供者的功能（例如 Microsoft Exchange online 資料中心）中託管。</span><span class="sxs-lookup"><span data-stu-id="dc943-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="dc943-109">**混合模式**   您的 Lync Server 2013 部署會有一些使用者信箱駐留在您企業內部的本機伺服器上，而某些信箱則駐留在託管 Exchange 服務資料中心。</span><span class="sxs-lookup"><span data-stu-id="dc943-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc943-110">您可以在評估與 stepwise 使用者遷移至託管 Exchange UM 的過程中，將混合模式做為過渡式解決方案，或者，如果您選擇在遷移其他使用者的 Exchange UM 服務之後，就將它保留為永久方案。</span><span class="sxs-lookup"><span data-stu-id="dc943-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="dc943-111">若要整合 Lync Server 2013 與託管 Exchange UM，您必須設定*共用的 SIP 位址空間*（也稱為*分割網域*）。</span><span class="sxs-lookup"><span data-stu-id="dc943-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="dc943-112">在此設定中，Lync Server 2013 和協力廠商託管的 Exchange UM 服務提供者都可以存取相同的 SIP 網域位址空間。</span><span class="sxs-lookup"><span data-stu-id="dc943-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="dc943-113">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中託管 EXCHANGE UM 整合架構](lync-server-2013-hosted-exchange-um-integration-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="dc943-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

