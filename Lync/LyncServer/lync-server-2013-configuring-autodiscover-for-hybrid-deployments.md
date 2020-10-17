---
title: Lync Server 2013：設定混合式部署的自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1b96727af805107e7101c395d7c545c4e4967b5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502190"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>在 Lync Server 2013 中設定自動探索以進行混合部署

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-12_

混合式部署是使用 Microsoft Lync Online cloud service 和內部部署的設定。 在此類型的設定中，自動探索服務必須能夠找到使用者實際所在的位置。 也就是說，「自動探索」會協助您尋找使用者帳戶，以及主控使用者帳戶之伺服器的所在位置，不論它位於內部部署或 Lync Online 部署中。

例如，如果使用者的帳戶是在 Lync Online 中的伺服器上主控，則嘗試尋找使用者的方法如下 *所示，* 在稱為「可探索」的程式中：

  - 使用者發起對內部部署 **contoso.com**的連線嘗試。

  - 嘗試會傳送至 lyncdiscover.contoso.com，這是與自動探索服務相關聯的 DNS 名稱。

  - 自動探索是指在 contoso.com 內部部署部署中假設的報名者集區，並且提供使用者實際主控伺服器主控于 Lync Online 的資訊。 自動探索接著會傳送使用者對 **lync.com** online 自動探索服務的參照。

  - 使用者對 lync.com 線上自動探索服務發起連線嘗試，而且可以尋找使用者的帳戶和使用者的主伺服器。

若要讓用戶端能夠探索使用者主伺服器所在的部署，您必須使用新的統一資源定位器 (URL) 來設定自動探索服務。 請執行下列動作來設定自動探索服務。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>設定混合部署的自動探索

1.  在 [ [Lync Server 2013 的自動探索服務需求](lync-server-2013-autodiscover-service-requirements.md)] 中，您可以使用 Get-CsHostingProvider 來 ProxyFQDN 屬性中取得屬性值。

2.  從 Lync Server 管理命令介面中，輸入
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    \[ \] 以共用 SIP 位址空間的功能變數名稱取代識別。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Get-cshostingprovider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

