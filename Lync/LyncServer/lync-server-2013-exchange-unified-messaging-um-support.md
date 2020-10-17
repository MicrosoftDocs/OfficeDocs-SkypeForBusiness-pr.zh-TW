---
title: Lync Server 2013： Exchange 整合通訊 (UM) 支援
description: Lync Server 2013： Exchange 整合通訊 (UM) 支援。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 563517bb72167bbab0b08eba3b1359ae3ab52836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564799"
---
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="697d4-103">Lync Server 2013 中的 Exchange 整合通訊 (UM) 支援</span><span class="sxs-lookup"><span data-stu-id="697d4-103">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="697d4-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="697d4-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="697d4-105">Lync Server 2013 支援與 Exchange 整合通訊 (UM) 整合，以結合語音訊息與電子郵件訊息到單一郵件基礎結構。</span><span class="sxs-lookup"><span data-stu-id="697d4-105">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="697d4-106">在 Exchange 2013 中，Exchange UM 包含在信箱伺服器上安裝和執行的 Exchange UM 服務，以及在用戶端存取伺服器上安裝並執行的 UM 呼叫路由器。</span><span class="sxs-lookup"><span data-stu-id="697d4-106">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="697d4-107">針對 Lync Server 2013 Enterprise Voice 部署，Exchange UM 會將語音訊息與電子郵件合併到單一存放區，而該儲存體可以從電話 (，也就是 Outlook Voice Access) 或電腦。</span><span class="sxs-lookup"><span data-stu-id="697d4-107">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="697d4-108">Exchange UM 和 Lync Server 2013 共同合作，為 Enterprise Voice 的使用者提供呼叫回應、Outlook Voice Access 和自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="697d4-108">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="697d4-109">除了支援與 Exchange UM 內部部署的整合之外，Lync Server 2013 也支援與主控 Exchange UM 的整合。</span><span class="sxs-lookup"><span data-stu-id="697d4-109">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="697d4-110">如果您將部分或所有的使用者移轉至裝載的 Exchange 服務提供者 (如 Microsoft Exchange Online)，這項支援可讓您提供語音訊息給使用者。</span><span class="sxs-lookup"><span data-stu-id="697d4-110">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="697d4-111">Lync Server 2013 支援下列版本：</span><span class="sxs-lookup"><span data-stu-id="697d4-111">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="697d4-112">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="697d4-112">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="697d4-113">Microsoft Exchange Server 2010 (必要) 或 (建議的最新 service pack) </span><span class="sxs-lookup"><span data-stu-id="697d4-113">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="697d4-114">Microsoft Exchange Server 2007 Service Pack 1 (SP1) 所需 () 或最新的 service pack (建議) </span><span class="sxs-lookup"><span data-stu-id="697d4-114">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="697d4-115">您無法組合 Exchange UM 與 Lync Server 2013 或 Lync Server 2013 資料庫。</span><span class="sxs-lookup"><span data-stu-id="697d4-115">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="697d4-116">您可以在不同的樹系中安裝 Exchange UM 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="697d4-116">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="697d4-117">Exchange UM 可能不需要部署 PBX 的 Enterprise Voice 部署，因為 PBX 可以繼續為所有使用者提供語音信箱和相關服務。</span><span class="sxs-lookup"><span data-stu-id="697d4-117">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="697d4-118">如果您最後淘汰 PBX (例如，如果您在部署公用交換電話網路的 SIP 主幹 (PSTN) 連線) ，您必須重新設定 Exchange UM，以將語音信箱提供給先前使用 PBX 語音信箱系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="697d4-118">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="697d4-119">本章節內容</span><span class="sxs-lookup"><span data-stu-id="697d4-119">In This Section</span></span>

  - [<span data-ttu-id="697d4-120">Lync Server 2013 中內部部署整合通訊的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="697d4-120">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="697d4-121">Lync Server 2013 中的主控 Exchange UM 整合支援</span><span class="sxs-lookup"><span data-stu-id="697d4-121">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

