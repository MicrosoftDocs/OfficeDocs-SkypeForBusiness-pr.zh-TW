---
title: Lync Server 2013：主控 Exchange UM 路由
description: Lync Server 2013：主控 Exchange UM 路由傳送。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72fbdee5550ae53d5ff5e7513ea384cedad62c5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550129"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="fabe6-103">Lync Server 2013 中的主控 Exchange UM 路由</span><span class="sxs-lookup"><span data-stu-id="fabe6-103">Hosted Exchange UM routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fabe6-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fabe6-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fabe6-105">Exchange UM 路由應用程式會在前端伺服器上執行，以將通話路由傳送至內部部署 Microsoft Exchange Server 整合通訊 (UM) 部署或主控 Exchange UM 服務。</span><span class="sxs-lookup"><span data-stu-id="fabe6-105">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="fabe6-106">ExUM Routing 應用程式</span><span class="sxs-lookup"><span data-stu-id="fabe6-106">The ExUM Routing Application</span></span>

<span data-ttu-id="fabe6-107">Lync Server 2013 Exchange UM 路由應用程式使用使用者帳戶設定中的資訊，以及來自裝載的語音信箱原則參數，來決定如何將來電路由傳送到所裝載的語音訊息，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="fabe6-107">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="fabe6-108">**混合部署 Exchange UM 路由範例**</span><span class="sxs-lookup"><span data-stu-id="fabe6-108">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="fabe6-109">![內部部署 Lync Server Exchange UM 部署](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")</span><span class="sxs-lookup"><span data-stu-id="fabe6-109">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="fabe6-110">Exchange UM 路由可以設定為將通話路由傳送給已啟用內部部署 Exchange UM 的使用者、已啟用主控 Exchange UM 的使用者，或是二者的組合。</span><span class="sxs-lookup"><span data-stu-id="fabe6-110">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="fabe6-111">例如，假設 Roy 的信箱和 Exchange UM 服務是駐留在內部部署 Exchange 部署中。</span><span class="sxs-lookup"><span data-stu-id="fabe6-111">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="fabe6-112">Roy 的使用者帳戶的 proxy 位址資訊，提供 ExUM 路由應用程式用來將來電路由傳送至內部部署 Exchange UM 伺服器的資訊。</span><span class="sxs-lookup"><span data-stu-id="fabe6-112">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="fabe6-113">Alice 的信箱和 Exchange UM 服務位於主控 Exchange 服務供應商的資料中心。</span><span class="sxs-lookup"><span data-stu-id="fabe6-113">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="fabe6-114">Exchange UM 通話的路由設定如下：</span><span class="sxs-lookup"><span data-stu-id="fabe6-114">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="fabe6-115">Alice 使用者帳戶之 msExchUCVoiceMailSettings 屬性中所設定的值，會告知 ExUM Routing 應用程式檢查裝載語音信箱原則中的路由詳細資料。</span><span class="sxs-lookup"><span data-stu-id="fabe6-115">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fabe6-116">MsExchUCVoiceMailSettings 屬性的值可由 Exchange 服務供應商或 Lync Server 2013 系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="fabe6-116">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="fabe6-117">在上述圖表所示的範例中，Lync Server 2013 系統管理員已設定 CsHostedVoiceMail = 1)  (值，以便為 Alice 啟用主控語音信箱。</span><span class="sxs-lookup"><span data-stu-id="fabe6-117">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="fabe6-118">如需此屬性的詳細資訊，請參閱 <A href="lync-server-2013-hosted-exchange-user-management.md">在 Lync Server 2013 中主控 Exchange 使用者管理</A>。</span><span class="sxs-lookup"><span data-stu-id="fabe6-118">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="fabe6-119">指派給 Alice 使用者帳戶的裝載語音信箱原則提供路由詳細資料：</span><span class="sxs-lookup"><span data-stu-id="fabe6-119">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="fabe6-120">目的地是主控 Exchange UM 服務提供者 (ls。ExUm。 \<hostedExchangeServer\>com 在這個範例中) 。</span><span class="sxs-lookup"><span data-stu-id="fabe6-120">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="fabe6-121">組織是由租使用者識別 IDs，也就是位於 ls 上之 Exchange Server 租使用者的 SIP 郵件的路由 Fqdn。ExUm。 \<hostedExchangeServer\>在此範例中，com (corp.contoso.com 和 corp.litwareinc.com) 。</span><span class="sxs-lookup"><span data-stu-id="fabe6-121">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fabe6-122">Exchange Online 的 FQDN 是 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="fabe6-122">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="fabe6-123">如需詳細資訊，請參閱 [Lync Server 2013 中的主控語音信箱原則](lync-server-2013-hosted-voice-mail-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fabe6-123">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fabe6-124">如果使用者帳戶中同時存在 msExchUCVoiceMailSettings 屬性及 UM Proxy 位址設定，則會優先採用 msExchUCVoiceMailSettings 屬性。</span><span class="sxs-lookup"><span data-stu-id="fabe6-124">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

