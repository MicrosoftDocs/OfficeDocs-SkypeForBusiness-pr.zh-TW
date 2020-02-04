---
title: Lync Server 2013：主控 Exchange UM 路由
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
ms.openlocfilehash: e04198813f7bb0647671dbb23e12889b108ee846
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange UM 路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

Exchange UM 路由應用程式在前端伺服器上執行，以將呼叫路由至內部部署的 Microsoft Exchange Server 整合通訊（UM）部署或託管 Exchange UM 服務。

<div>

## <a name="the-exum-routing-application"></a>ExUM 路由應用程式

Lync Server 2013 Exchange UM 路由應用程式使用來自使用者帳戶設定的資訊，以及來自託管的語音信箱原則參數，以判斷如何路由託管語音訊息的呼叫，如下圖所示。

**混合式部署 Exchange UM 路由的範例**

![內部部署 Lync Server Exchange UM 部署](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")

Exchange UM 路由可以設定為將呼叫路由到已啟用內部部署 Exchange um 的使用者，或傳送給已啟用託管 Exchange UM 的使用者，或結合兩個使用者。

例如，假設 Roy 的信箱和 Exchange UM 服務是駐留在內部部署 Exchange 部署中。

  - 來自 Roy 的使用者帳戶的 proxy 位址資訊，提供 ExUM 路由應用程式用來將自己的呼叫傳送到內部部署 Exchange UM 伺服器的資訊。

劉愛琳的信箱和 Exchange UM 服務位於託管 Exchange 服務供應商的資料中心。 Exchange UM 通話的路由設定如下所示：

  - 在 Alice 的使用者帳戶的 msExchUCVoiceMailSettings 屬性中設定的值，會告知 ExUM 路由應用程式在託管的語音信箱原則中檢查路由詳細資料。
    
    <div>
    

    > [!NOTE]  
    > MsExchUCVoiceMailSettings 屬性的值可由 Exchange 服務供應商或 Lync Server 2013 系統管理員來設定。 在前一個圖表所示的範例中，「CsHostedVoiceMail = 1」這個值是由 Lync Server 2013 系統管理員設定，以便為 Alice 啟用託管語音信箱。 如需此屬性的詳細資訊，請參閱<A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 中的託管 Exchange 使用者管理</A>。

    
    </div>

  - 已指派給劉愛琳使用者帳戶的託管語音信箱原則提供路由詳細資料：
    
      - [目的地] 是託管 Exchange UM 服務提供者（ls）。ExUm.\<在\>此範例中為 hostedExchangeServer）。
    
      - 組織是由租使用者識別碼所標識，這些識別碼是位於 ls 上之 Exchange Server 租使用者的 SIP 訊息的路由 Fqdn。ExUm.\<hostedExchangeServer\>（在此範例中為 corp.contoso.com 和 corp.litwareinc.com）。
        
        <div>
        

        > [!NOTE]  
        > Exchange Online 的 FQDN 是 exap.um.outlook.com。

        
        </div>
        
        如需詳細資訊，請參閱[Lync Server 2013 中託管的語音信箱原則](lync-server-2013-hosted-voice-mail-policies.md)。

<div>


> [!NOTE]  
> 如果 msExchUCVoiceMailSettings 屬性和 UM proxy 位址設定都存在於使用者帳戶中，則 msExchUCVoiceMailSettings 屬性優先使用。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

