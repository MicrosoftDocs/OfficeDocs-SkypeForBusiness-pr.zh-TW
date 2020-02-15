---
title: Lync Server 2013： 的元件和拓撲內部部署整合通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94a22348ca5b0f17415edf0a4f259d5c58d473a9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="31280-102">Lync Server 2013 中整合通訊的內部部署的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="31280-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31280-103">_**主題上次修改日期：** 2012年-09-25_</span><span class="sxs-lookup"><span data-stu-id="31280-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="31280-104">本主題說明提供 Lync Server 2013 部署的 Exchange 整合通訊 (UM) 功能所需的 Microsoft Exchange Server 2013 元件。</span><span class="sxs-lookup"><span data-stu-id="31280-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="31280-105">它也說明內部部署 Exchange UM 整合支援的拓撲。</span><span class="sxs-lookup"><span data-stu-id="31280-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="31280-106">Exchange Server 元件</span><span class="sxs-lookup"><span data-stu-id="31280-106">Exchange Server Components</span></span>

<span data-ttu-id="31280-107">若要提供給您組織中的 Enterprise Voice 使用者所述[的整合式 Unified Messaging 和 Lync Server 2013 功能](lync-server-2013-features-of-integrated-unified-messaging.md)服務與 Exchange UM 功能，您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取伺服器，裝載使用者信箱，並提供單一的儲存位置的電子郵件及語音信箱。</span><span class="sxs-lookup"><span data-stu-id="31280-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="31280-108">Exchange UM 以服務方式執行 Exchange 信箱與用戶端存取伺服器上。</span><span class="sxs-lookup"><span data-stu-id="31280-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="31280-109">如需 Microsoft Exchange Server 2007 與 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱部署文件中的[部署內部部署 Exchange UM 以提供 Lync Server 2013 語音信箱](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="31280-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="31280-110">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="31280-110">Supported Topologies</span></span>

<span data-ttu-id="31280-111">您可以部署 Lync Server 2013 和 Exchange 整合通訊 (UM) 在相同的樹系或多個樹系中。</span><span class="sxs-lookup"><span data-stu-id="31280-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="31280-112">如果部署跨越多個樹系，您必須針對每個 Exchange UM 樹系執行 Exchange 整合步驟。</span><span class="sxs-lookup"><span data-stu-id="31280-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="31280-113">此外，您必須設定為信任的 Lync Server 2013 樹系的每個 Microsoft Exchange 樹系和 Lync Server 2013 樹系信任每個 Exchange UM 樹系。</span><span class="sxs-lookup"><span data-stu-id="31280-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="31280-114">除了此樹系信任，必須在 Lync Server 2013 樹系中的使用者物件上設定的所有使用者的 Exchange UM 設定。</span><span class="sxs-lookup"><span data-stu-id="31280-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="31280-115">Lync Server 2013 的 Exchange UM 整合支援下列拓撲：</span><span class="sxs-lookup"><span data-stu-id="31280-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="31280-116">單一樹系</span><span class="sxs-lookup"><span data-stu-id="31280-116">Single forest</span></span>

  - <span data-ttu-id="31280-117">單一網域 (亦即單一樹系搭配單一網域)。</span><span class="sxs-lookup"><span data-stu-id="31280-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="31280-118">Lync Server 2013、 Microsoft Exchange 和位於相同網域中所有的使用者。</span><span class="sxs-lookup"><span data-stu-id="31280-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="31280-119">多重網域 (亦即，一個根網域搭配一或多個子網域)。</span><span class="sxs-lookup"><span data-stu-id="31280-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="31280-120">從您在其中建立使用者的網域不同網域中部署 Lync Server 2013 和 Microsoft Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="31280-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="31280-121">可以從其所支援的 Lync Server 2013 集區不同網域中部署 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="31280-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="31280-122">多重樹系 (亦即資源樹系)。</span><span class="sxs-lookup"><span data-stu-id="31280-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="31280-123">Lync Server 2013 部署在單一樹系中，並再將使用者分配到多個樹系。</span><span class="sxs-lookup"><span data-stu-id="31280-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="31280-124">Exchange UM 使用者的屬性必須透過複寫到 Lync Server 2013 的樹系。</span><span class="sxs-lookup"><span data-stu-id="31280-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31280-125">Exchange 可以部署在多個樹系中。</span><span class="sxs-lookup"><span data-stu-id="31280-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="31280-126">每個 Exchange 組織可以 Exchange UM 提供給其使用者，或 Exchange UM 可以在 Lync Server 2013 相同的樹系中部署。</span><span class="sxs-lookup"><span data-stu-id="31280-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

