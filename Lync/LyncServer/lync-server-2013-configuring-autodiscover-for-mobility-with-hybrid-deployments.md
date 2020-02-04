---
title: 利用混合部署針對行動性設定自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd6c36afb89d1a8b354d072ee39ee3f6a2e7e93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>在 Lync Server 2013 中利用混合部署針對行動性設定自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-18_

混合式部署是使用 Microsoft Lync Online 雲端服務和內部部署部署的配置。 在此類型的設定中，自動探索服務必須能夠找出使用者實際所處的位置。 那就是說，「自動探索」會尋找使用者帳戶，以及主持使用者帳戶的伺服器所在的位置，而不考慮它是在內部部署還是在 Lync Online 部署中。

例如，如果使用者的帳戶是駐留在 Lync Online 的伺服器上，則在稱為「探索」的程式中，嘗試尋找使用者的操作會如下所*示：*

  - 使用者啟動到內部部署部署的連線嘗試，請**contoso.com**。

  - 該嘗試會傳送至 lyncdiscover.contoso.com，即與自動探索服務相關聯的 DNS 名稱。

  - 自動探索會參照 contoso.com 內部部署部署的假設註冊機構池，並提供使用者在 Lync Online 中託管之實際主伺服器的資訊。 自動探索接著會將對**lync.com** online 自動探索服務的參照傳送給使用者。

  - 使用者初始化 lync.com online 自動探索服務的連線嘗試，而且可以找到使用者的帳戶和使用者的主伺服器。

若要讓行動用戶端發現使用者主伺服器所在的部署，您必須使用新的統一資源定位器（URL）來設定自動探索服務。 請執行下列動作來設定自動探索服務。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>針對混合式部署設定自動探索

1.  您可以使用 CsHostingProvider 來取得屬性 ProxyFQDN 的值。

2.  從 Lync Server 管理命令介面輸入
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    使用\[共用\] SIP 位址空間的功能變數名稱取代身分識別的位置。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

