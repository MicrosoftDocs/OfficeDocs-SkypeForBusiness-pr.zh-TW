---
title: Lync Server 2013：內部部署 Unified Messaging 的元件和拓撲
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
ms.openlocfilehash: 1739dbb7d603f112af72c78032c46b94470302bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="6c7e3-102">Lync Server 2013 中內部部署 Unified Messaging 的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="6c7e3-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c7e3-103">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="6c7e3-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="6c7e3-104">本主題說明將 Exchange 整合通訊（UM）功能提供給 Lync Server 2013 部署所需的 Microsoft Exchange Server 2013 元件。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="6c7e3-105">它也會說明內部部署 Exchange UM 整合所支援的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="6c7e3-106">Exchange Server 元件</span><span class="sxs-lookup"><span data-stu-id="6c7e3-106">Exchange Server Components</span></span>

<span data-ttu-id="6c7e3-107">若要提供整合式整合[訊息和 Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md)在您組織中的企業語音使用者所描述的 Exchange UM 功能與服務，您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取伺服器（其主機使用者信箱），並提供電子郵件和語音信箱的單一儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="6c7e3-108">Exchange UM 在 Exchange 信箱和用戶端存取伺服器上以服務的方式執行。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="6c7e3-109">如需 Microsoft Exchange Server 2007 和 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱[部署內部部署 EXCHANGE UM，以在部署檔中提供 Lync Server 2013 語音信箱](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="6c7e3-110">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="6c7e3-110">Supported Topologies</span></span>

<span data-ttu-id="6c7e3-111">您可以在同一個目錄林中或多個目錄林中部署 Lync Server 2013 和 Exchange 整合通訊（UM）。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="6c7e3-112">如果部署跨越多個目錄林，您必須針對每個 Exchange UM 目錄林執行 Exchange 整合步驟。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="6c7e3-113">此外，您必須將每個 Microsoft Exchange 林設定為信任 Lync Server 2013 林以及 Lync Server 2013 林，以信任每個 Exchange UM 目錄林。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="6c7e3-114">除了此目錄林信任之外，所有使用者的 Exchange UM 設定都必須在 Lync Server 2013 林中的使用者物件上設定。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="6c7e3-115">Lync Server 2013 支援適用于 Exchange UM 整合的下列拓朴：</span><span class="sxs-lookup"><span data-stu-id="6c7e3-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="6c7e3-116">單一目錄林</span><span class="sxs-lookup"><span data-stu-id="6c7e3-116">Single forest</span></span>

  - <span data-ttu-id="6c7e3-117">單一網域（也就是單一網域的單一林）。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="6c7e3-118">Lync Server 2013、Microsoft Exchange 和使用者都位於同一個網域中。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="6c7e3-119">多個網域（也就是包含一或多個子域的根網域）。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="6c7e3-120">Lync Server 2013 和 Microsoft Exchange 伺服器會從您建立使用者的網域部署在不同的網域中。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="6c7e3-121">Exchange UM 伺服器可從其支援的 Lync Server 2013 池部署到不同的網域。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="6c7e3-122">多個目錄林（也就是資原始目錄林）。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="6c7e3-123">Lync Server 2013 是在單一目錄林中部署，而使用者則是跨多個目錄林分佈。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="6c7e3-124">使用者的 Exchange UM 屬性必須複製到 Lync Server 2013 林。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c7e3-125">Exchange 可以在多個林中部署。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="6c7e3-126">每個 Exchange 組織都可以為其使用者提供 Exchange UM，或者 Exchange UM 可以部署在 Lync Server 2013 所在的林中。</span><span class="sxs-lookup"><span data-stu-id="6c7e3-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

