---
title: Lync Server 2013：主控 Exchange UM 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="9f50f-102">Lync Server 2013 中的主控 Exchange UM 路由</span><span class="sxs-lookup"><span data-stu-id="9f50f-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f50f-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9f50f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9f50f-104">Exchange UM 路由應用程式在前端伺服器上執行，以將呼叫路由至內部部署的 Microsoft Exchange Server 整合通訊（UM）部署或託管 Exchange UM 服務。</span><span class="sxs-lookup"><span data-stu-id="9f50f-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="9f50f-105">ExUM 路由應用程式</span><span class="sxs-lookup"><span data-stu-id="9f50f-105">The ExUM Routing Application</span></span>

<span data-ttu-id="9f50f-106">Lync Server 2013 Exchange UM 路由應用程式使用來自使用者帳戶設定的資訊，以及來自託管的語音信箱原則參數，以判斷如何路由託管語音訊息的呼叫，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="9f50f-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="9f50f-107">**混合式部署 Exchange UM 路由的範例**</span><span class="sxs-lookup"><span data-stu-id="9f50f-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="9f50f-108">內部部署 lync ![Server EXCHANGE um 部署](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "內部部署 LYNC server exchange um 部署")</span><span class="sxs-lookup"><span data-stu-id="9f50f-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="9f50f-109">Exchange UM 路由可以設定為將呼叫路由到已啟用內部部署 Exchange um 的使用者，或傳送給已啟用託管 Exchange UM 的使用者，或結合兩個使用者。</span><span class="sxs-lookup"><span data-stu-id="9f50f-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="9f50f-110">例如，假設 Roy 的信箱和 Exchange UM 服務是駐留在內部部署 Exchange 部署中。</span><span class="sxs-lookup"><span data-stu-id="9f50f-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="9f50f-111">來自 Roy 的使用者帳戶的 proxy 位址資訊，提供 ExUM 路由應用程式用來將自己的呼叫傳送到內部部署 Exchange UM 伺服器的資訊。</span><span class="sxs-lookup"><span data-stu-id="9f50f-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="9f50f-112">劉愛琳的信箱和 Exchange UM 服務位於託管 Exchange 服務供應商的資料中心。</span><span class="sxs-lookup"><span data-stu-id="9f50f-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="9f50f-113">Exchange UM 通話的路由設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="9f50f-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="9f50f-114">在 Alice 的使用者帳戶的 msExchUCVoiceMailSettings 屬性中設定的值，會告知 ExUM 路由應用程式在託管的語音信箱原則中檢查路由詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9f50f-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9f50f-115">MsExchUCVoiceMailSettings 屬性的值可由 Exchange 服務供應商或 Lync Server 2013 系統管理員來設定。</span><span class="sxs-lookup"><span data-stu-id="9f50f-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="9f50f-116">在前一個圖表所示的範例中，「CsHostedVoiceMail = 1」這個值是由 Lync Server 2013 系統管理員設定，以便為 Alice 啟用託管語音信箱。</span><span class="sxs-lookup"><span data-stu-id="9f50f-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="9f50f-117">如需此屬性的詳細資訊，請參閱<A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 中的託管 Exchange 使用者管理</A>。</span><span class="sxs-lookup"><span data-stu-id="9f50f-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="9f50f-118">已指派給劉愛琳使用者帳戶的託管語音信箱原則提供路由詳細資料：</span><span class="sxs-lookup"><span data-stu-id="9f50f-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="9f50f-119">[目的地] 是託管 Exchange UM 服務提供者（ls）。ExUm.\<在\>此範例中為 hostedExchangeServer）。</span><span class="sxs-lookup"><span data-stu-id="9f50f-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="9f50f-120">組織是由租使用者識別碼所標識，這些識別碼是位於 ls 上之 Exchange Server 租使用者的 SIP 訊息的路由 Fqdn。ExUm.\<hostedExchangeServer\>（在此範例中為 corp.contoso.com 和 corp.litwareinc.com）。</span><span class="sxs-lookup"><span data-stu-id="9f50f-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9f50f-121">Exchange Online 的 FQDN 是 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="9f50f-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="9f50f-122">如需詳細資訊，請參閱[Lync Server 2013 中託管的語音信箱原則](lync-server-2013-hosted-voice-mail-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9f50f-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f50f-123">如果 msExchUCVoiceMailSettings 屬性和 UM proxy 位址設定都存在於使用者帳戶中，則 msExchUCVoiceMailSettings 屬性優先使用。</span><span class="sxs-lookup"><span data-stu-id="9f50f-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

