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
ms.openlocfilehash: 31091da9a80dc03c798cbf674c1c46e0ea7b901c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533110"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange UM 路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

Exchange UM 路由應用程式會在前端伺服器上執行，以將通話路由傳送至內部部署 Microsoft Exchange Server 整合通訊 (UM) 部署或主控 Exchange UM 服務。

<div>

## <a name="the-exum-routing-application"></a>ExUM Routing 應用程式

Lync Server 2013 Exchange UM 路由應用程式使用使用者帳戶設定中的資訊，以及來自裝載的語音信箱原則參數，來決定如何將來電路由傳送到所裝載的語音訊息，如下圖所示。

**混合部署 Exchange UM 路由範例**

![內部部署 Lync Server Exchange UM 部署](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")

Exchange UM 路由可以設定為將通話路由傳送給已啟用內部部署 Exchange UM 的使用者、已啟用主控 Exchange UM 的使用者，或是二者的組合。

例如，假設 Roy 的信箱和 Exchange UM 服務是駐留在內部部署 Exchange 部署中。

  - Roy 的使用者帳戶的 proxy 位址資訊，提供 ExUM 路由應用程式用來將來電路由傳送至內部部署 Exchange UM 伺服器的資訊。

Alice 的信箱和 Exchange UM 服務位於主控 Exchange 服務供應商的資料中心。 Exchange UM 通話的路由設定如下：

  - Alice 使用者帳戶之 msExchUCVoiceMailSettings 屬性中所設定的值，會告知 ExUM Routing 應用程式檢查裝載語音信箱原則中的路由詳細資料。
    
    <div>
    

    > [!NOTE]  
    > MsExchUCVoiceMailSettings 屬性的值可由 Exchange 服務供應商或 Lync Server 2013 系統管理員設定。 在上述圖表所示的範例中，Lync Server 2013 系統管理員已設定 CsHostedVoiceMail = 1)  (值，以便為 Alice 啟用主控語音信箱。 如需此屬性的詳細資訊，請參閱 <A href="lync-server-2013-hosted-exchange-user-management.md">在 Lync Server 2013 中主控 Exchange 使用者管理</A>。

    
    </div>

  - 指派給 Alice 使用者帳戶的裝載語音信箱原則提供路由詳細資料：
    
      - 目的地是主控 Exchange UM 服務提供者 (ls。ExUm。 \<hostedExchangeServer\>com 在這個範例中) 。
    
      - 組織是由租使用者識別 IDs，也就是位於 ls 上之 Exchange Server 租使用者的 SIP 郵件的路由 Fqdn。ExUm。 \<hostedExchangeServer\>在此範例中，com (corp.contoso.com 和 corp.litwareinc.com) 。
        
        <div>
        

        > [!NOTE]  
        > Exchange Online 的 FQDN 是 exap.um.outlook.com。

        
        </div>
        
        如需詳細資訊，請參閱 [Lync Server 2013 中的主控語音信箱原則](lync-server-2013-hosted-voice-mail-policies.md)。

<div>


> [!NOTE]  
> 如果使用者帳戶中同時存在 msExchUCVoiceMailSettings 屬性及 UM Proxy 位址設定，則會優先採用 msExchUCVoiceMailSettings 屬性。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

