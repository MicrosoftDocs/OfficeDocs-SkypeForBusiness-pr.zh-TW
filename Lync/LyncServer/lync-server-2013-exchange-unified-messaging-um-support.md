---
title: Lync Server 2013：Exchange Unified Messaging (UM) 支援
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
ms.openlocfilehash: 8925bd8a07693800c49ff2d818d3677b33452b97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="dc4f2-102">Lync Server 2013 中的 Exchange Unified Messaging (UM) 支援</span><span class="sxs-lookup"><span data-stu-id="dc4f2-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc4f2-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dc4f2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dc4f2-104">Lync Server 2013 支援與 Exchange 整合通訊（UM）整合，以將語音訊息和電子郵件訊息結合到單一訊息基礎結構。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="dc4f2-105">在 Exchange 2013 中，Exchange UM 是由 Exchange UM 服務（在信箱伺服器上安裝並執行），以及在用戶端存取伺服器上安裝並執行的 UM 呼叫路由器所組成。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="dc4f2-106">針對 Lync Server 2013 企業版語音部署，Exchange UM 將語音訊息和電子郵件訊息結合成可從電話（也就是 Outlook 語音存取）或電腦存取的單一商店。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="dc4f2-107">Exchange UM 和 Lync Server 2013 共同合作，為企業語音的使用者提供呼叫應答、Outlook 語音存取及自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="dc4f2-108">除了支援與 Exchange UM 內部部署的整合之外，Lync Server 2013 還支援與託管 Exchange UM 的整合。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="dc4f2-109">這可讓您在將部分或所有專案遷移至託管 Exchange 服務供應商（例如 Microsoft Exchange Online）時提供語音訊息給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="dc4f2-110">Lync Server 2013 支援下列版本：</span><span class="sxs-lookup"><span data-stu-id="dc4f2-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="dc4f2-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="dc4f2-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="dc4f2-112">Microsoft Exchange Server 2010 （必要）或最新 service pack （建議使用）</span><span class="sxs-lookup"><span data-stu-id="dc4f2-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="dc4f2-113">Microsoft Exchange Server 2007 Service Pack 1 （SP1）（必要）或最新的 service pack （建議使用）</span><span class="sxs-lookup"><span data-stu-id="dc4f2-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="dc4f2-114">您無法 collocate 與 Lync Server 2013 或 Lync Server 2013 資料庫的 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="dc4f2-115">您可以在不同的林中安裝 Exchange UM 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc4f2-116">Exchange UM 可能不是部署 PBX 之企業語音部署所需的，因為 PBX 可以繼續為所有使用者提供語音信箱和相關服務。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="dc4f2-117">如果您最後是淘汰 PBX （例如，如果您要為公用交換電話網絡（PSTN）連線）部署 SIP 中繼，您必須重新設定 Exchange UM，才能向先前使用 PBX 語音信箱系統的使用者提供語音信箱。</span><span class="sxs-lookup"><span data-stu-id="dc4f2-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc4f2-118">本節內容</span><span class="sxs-lookup"><span data-stu-id="dc4f2-118">In This Section</span></span>

  - [<span data-ttu-id="dc4f2-119">Lync Server 2013 中內部部署 Unified Messaging 的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="dc4f2-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="dc4f2-120">Lync Server 2013 中的主控 Exchange UM 整合支援</span><span class="sxs-lookup"><span data-stu-id="dc4f2-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

