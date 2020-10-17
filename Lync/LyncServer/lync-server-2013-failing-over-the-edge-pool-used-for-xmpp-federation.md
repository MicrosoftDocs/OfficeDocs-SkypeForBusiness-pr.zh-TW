---
title: Lync Server 2013：容錯移轉用於 XMPP 同盟的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54230fb489a62ed5d7a80bfe871af3bc097e35e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530890"
---
# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

在您的組織中，有一個指定的 Edge 集區是用於 XMPP 同盟的集區。如果此集區失效，您必須先容錯移轉 XMPP 同盟以使用不同的 Edge 集區，讓 XMPP 同盟可以再次運作。

當您第一次安裝 Edge 集區並啟用 XMPP 同盟時，可以藉由為所有適用於 XMPP 同盟的 Edge 集區 (而不是只針對其中一個) 設定外部 DNS SRV 記錄，來簡化災害復原程序。 其中的每一個 SRV 記錄都必須設定不同的優先順序。 所有的 XMPP 同盟流量都會通過優先順序最高且含有 SRV 記錄的集區。 如需啟用及設定 XMPP 同盟的詳細資訊，請參閱 [在 Lync Server 2013 中設定 XMPP 同盟](lync-server-2013-setting-up-xmpp-federation.md)。

在下列程序中，EdgePool1 是原本裝載 XMPP 同盟的集區，而 EdgePool2 是現在裝載 XMPP 同盟的集區。

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>容錯移轉用於 XMPP 同盟的 Edge 集區

1.  如果您尚未部署其他 Edge 集區 (除了目前中斷的這一個集區)，請部署該集區。 如需詳細資訊，請參閱 [在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)。

2.  在現在將裝載 XMPP 同盟之新 Edge 集區 (EdgePool2) 中的每個 Edge Server 上，執行下列 Cmdlet：
    
        Stop-CsWindowsService

3.  執行下列 Cmdlet，將 XMPP 同盟路由重新指向 EdgePool2：
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    在此範例中，Site2 為包含現在將裝載 XMPP 同盟路由之 Edge 集區的網站，而 EdgeServer2.contoso.com 為該集區中 Edge Server 的 FQDN。

4.  在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。

5.  如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。
    
        _xmpp-server._tcp.contoso.com

6.  確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。

7.  在現在將裝載 XMPP 同盟之 Edge 集區中的所有 Edge Server 上啟動服務：
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

