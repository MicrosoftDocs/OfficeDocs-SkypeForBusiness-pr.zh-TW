---
title: Lync Server 2013：針對混合式部署設定自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc2c28d42569d2f52b55dd04a90f5a788969c3ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>在 Lync Server 2013 中設定自動探索以進行混合式部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-12_

混合式部署是使用 Microsoft Lync Online 雲端服務和內部部署部署的配置。 在此類型的設定中，自動探索服務必須能夠找出使用者實際所處的位置。 那就是說，「自動探索」會尋找使用者帳戶，以及主持使用者帳戶的伺服器所在的位置，而不考慮它是在內部部署還是在 Lync Online 部署中。

例如，如果使用者的帳戶是駐留在 Lync Online 的伺服器上，則在稱為「探索」的程式中，嘗試尋找使用者的操作會如下所*示：*

  - 使用者啟動到內部部署部署的連線嘗試，請**contoso.com**。

  - 該嘗試會傳送至 lyncdiscover.contoso.com，即與自動探索服務相關聯的 DNS 名稱。

  - 自動探索會參照 contoso.com 內部部署部署的假設註冊機構池，並提供使用者在 Lync Online 中託管之實際主伺服器的資訊。 自動探索接著會將對**lync.com** online 自動探索服務的參照傳送給使用者。

  - 使用者初始化 lync.com online 自動探索服務的連線嘗試，而且可以找到使用者的帳戶和使用者的主伺服器。

若要讓用戶端發現使用者主伺服器所在的部署，您必須使用新的統一資源定位器（URL）來設定自動探索服務。 請執行下列動作來設定自動探索服務。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>針對混合式部署設定自動探索

1.  在[Lync Server 2013 的自動探索服務需求](lync-server-2013-autodiscover-service-requirements.md)主題中，您可以使用 CsHostingProvider 來取得屬性 ProxyFQDN 的值。

2.  從 Lync Server 管理命令介面輸入
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    使用\[共用\] SIP 位址空間的功能變數名稱取代身分識別的位置。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

