---
title: 'Lync Server 2013: Exchange 整合通訊 (UM) 支援'
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
ms.openlocfilehash: 0e906b6194572d0ed7f797a2be64c7b66982436b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="81fff-102">Lync Server 2013 中的 Exchange 整合通訊 (UM) 支援</span><span class="sxs-lookup"><span data-stu-id="81fff-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81fff-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="81fff-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="81fff-104">Lync Server 2013 支援整合與 Exchange 整合通訊 (UM) 來合併語音訊息與電子郵件訊息到單一郵件基礎結構。</span><span class="sxs-lookup"><span data-stu-id="81fff-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="81fff-105">在 Exchange 2013 中，Exchange UM 所組成的 Exchange UM 服務，以安裝以及 Mailbox server 及 UM 呼叫路由器，以安裝，以及用戶端存取伺服器上，執行上執行。</span><span class="sxs-lookup"><span data-stu-id="81fff-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="81fff-106">針對 Lync Server 2013 Enterprise Voice 部署，請 Exchange UM 結合了語音訊息與電子郵件訊息到可從電話 （亦即，Outlook 語音存取） 或電腦存取的單一儲存區。</span><span class="sxs-lookup"><span data-stu-id="81fff-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="81fff-107">Exchange UM 和 Lync Server 2013 共同運作以提供自動答錄服務，Outlook Voice Access 和自動語音應答服務給 Enterprise Voice 的使用者。</span><span class="sxs-lookup"><span data-stu-id="81fff-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="81fff-108">除了以在內部部署 Exchange UM 整合的支援，Lync Server 2013 支援與裝載 Exchange UM 整合。</span><span class="sxs-lookup"><span data-stu-id="81fff-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="81fff-109">如果您將部分或所有的使用者移轉至裝載的 Exchange 服務提供者 (如 Microsoft Exchange Online)，這項支援可讓您提供語音訊息給使用者。</span><span class="sxs-lookup"><span data-stu-id="81fff-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="81fff-110">Lync Server 2013 支援下列版本：</span><span class="sxs-lookup"><span data-stu-id="81fff-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="81fff-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="81fff-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="81fff-112">Microsoft Exchange Server 2010 （必要） 或最新的 service pack （建議使用）</span><span class="sxs-lookup"><span data-stu-id="81fff-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="81fff-113">Microsoft Exchange Server 2007 Service Pack 1 (SP1) （必要） 或最新的 service pack （建議）</span><span class="sxs-lookup"><span data-stu-id="81fff-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="81fff-114">您無法在 Exchange UM with Lync Server 2013 或 Lync Server 2013 資料庫組合。</span><span class="sxs-lookup"><span data-stu-id="81fff-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="81fff-115">您可以在不同樹系中安裝 Exchange UM 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="81fff-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81fff-116">Exchange UM 可能不需要有 PBX 部署，因為 PBX 可以繼續提供語音信箱和相關的服務給所有使用者的 Enterprise Voice 部署。</span><span class="sxs-lookup"><span data-stu-id="81fff-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="81fff-117">如果您最終淘汰 PBX （例如，如果您部署的公用交換的電話網路 (PSTN) 連線的 SIP 主幹），必須重新設定 Exchange UM to 先前已使用 PBX 語音信箱系統的使用者提供語音信箱。</span><span class="sxs-lookup"><span data-stu-id="81fff-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="81fff-118">本章節內容</span><span class="sxs-lookup"><span data-stu-id="81fff-118">In This Section</span></span>

  - [<span data-ttu-id="81fff-119">Lync Server 2013 中整合通訊的內部部署的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="81fff-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="81fff-120">主控 Exchange UM 整合的 Lync Server 2013 中的支援</span><span class="sxs-lookup"><span data-stu-id="81fff-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

