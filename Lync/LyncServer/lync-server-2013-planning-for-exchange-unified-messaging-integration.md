---
title: Lync Server 2013：規劃 Exchange 整合通訊整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 298e0f2667707c0ff73819b6fdd38ab105474d91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522240"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="c961d-102">在 Lync Server 2013 中規劃 Exchange 整合通訊整合</span><span class="sxs-lookup"><span data-stu-id="c961d-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c961d-103">_**主題上次修改日期：** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="c961d-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="c961d-104">Lync Server 2013 支援與 Exchange 整合通訊 (UM) 整合，以結合語音訊息與電子郵件訊息到單一郵件基礎結構。</span><span class="sxs-lookup"><span data-stu-id="c961d-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="c961d-105">在 Microsoft Exchange Server 2007 Service Pack 1 (SP1) 和 Microsoft Exchange Server 2010 中，Exchange 整合通訊 (UM) 是您可以安裝及設定數個 Exchange Server role 中的其中一個。</span><span class="sxs-lookup"><span data-stu-id="c961d-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="c961d-106">在 Microsoft Exchange Server 2013 中，Exchange UM 在 Exchange 信箱伺服器上以服務的身分執行。</span><span class="sxs-lookup"><span data-stu-id="c961d-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="c961d-107">在 Lync Server 2013 Enterprise Voice 部署中，整合通訊會將語音訊息與電子郵件合併到單一存放區，可從電話 (Outlook 語音存取) 或電腦上。</span><span class="sxs-lookup"><span data-stu-id="c961d-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="c961d-108">整合通訊和 Lync Server 2013 可搭配合作，為 Enterprise Voice 的使用者提供呼叫回應、Outlook Voice Access 和自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="c961d-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="c961d-109">如需 Microsoft Exchange Server 2013 中架構變更的詳細資訊，請參閱《 Microsoft Exchange Server 2013 檔》中的「語音架構變更」 [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) 。</span><span class="sxs-lookup"><span data-stu-id="c961d-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="c961d-110">若要在內部部署 Exchange UM 部署中支援這些功能，您必須執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c961d-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="c961d-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) 或最新的 service pack</span><span class="sxs-lookup"><span data-stu-id="c961d-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="c961d-112">Microsoft Exchange Server 2010 或最新的 service pack</span><span class="sxs-lookup"><span data-stu-id="c961d-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="c961d-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="c961d-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c961d-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c961d-114">In This Section</span></span>

  - [<span data-ttu-id="c961d-115">整合整合通訊和 Lync Server 2013 的功能</span><span class="sxs-lookup"><span data-stu-id="c961d-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="c961d-116">Lync Server 2013 中內部部署整合通訊的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="c961d-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="c961d-117">整合內部部署整合通訊和 Lync Server 2013 的指導方針</span><span class="sxs-lookup"><span data-stu-id="c961d-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="c961d-118">整合內部部署整合通訊和 Lync Server 2013 的部署程式</span><span class="sxs-lookup"><span data-stu-id="c961d-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

