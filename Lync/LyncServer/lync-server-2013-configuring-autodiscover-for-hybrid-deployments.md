---
title: Lync Server 2013： 設定自動探索的混合式部署
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
ms.openlocfilehash: 2ec2e0653d9b9d6c8f5412c58895b7ec805c82db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Lync Server 2013 中設定自動探索的混合式部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12-12_

混合式部署是使用 Microsoft Lync Online 的雲端服務和內部部署的設定。 在這種組態，自動探索服務必須能夠找出使用者的實際所在的位置。 也就是說，自動探索可協助找出的使用者帳戶，而伺服器主控的使用者帳戶是，不論是否在內部部署或 Lync Online 部署中。

比方說，如果 Lync Online 中的伺服器所架設的使用者帳戶，則嘗試尋找使用者將會發生，如下所示，稱為*可測知性*程序中：

  - 從使用者起始的嘗試連線到內部部署， **contoso.com**。

  - 嘗試傳送至 lyncdiscover.contoso.com，自動探索服務相關聯的 DNS 名稱。

  - 自動探索指的是在內部部署 contoso.com 假定的登錄器集區，並提供使用者的實際的主伺服器裝載於 Lync Online 的詳細資訊。 自動探索再傳送使用者轉介**lync.com**線上自動探索服務。

  - 使用者會嘗試連線到 lync.com 線上自動探索服務，且能找出使用者的帳戶和使用者的主伺服器。

若要啟用用戶端探索使用者主伺服器所在的部署，您必須設定自動探索服務與新的統一資源定位器 (URL)。 依下列方式來設定自動探索服務。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>設定自動探索的混合式部署

1.  在主題[Lync Server 2013 的自動探索服務需求](lync-server-2013-autodiscover-service-requirements.md)，您可以使用 Get-cshostingprovider 擷取屬性 ProxyFQDN 的值。

2.  從 Lync Server 管理命令介面中，輸入
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    其中\[identity\]取代共用 SIP 位址空間的網域名稱。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-cshostingprovider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[設定 CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

