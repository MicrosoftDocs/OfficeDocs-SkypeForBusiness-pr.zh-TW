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
ms.openlocfilehash: 9d1c76dc37ce1abb2d34c474d4144b0894d93a0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

在您的組織中，有一個 Edge 池指定為要用於 XMPP 同盟的池。 如果此池向下移動，您必須容錯移轉 XMPP 同盟，才能使用不同的邊緣池，然後 XMPP 同盟才能再次運作。

當您第一次安裝 Edge 池並啟用 XMPP 同盟時，您可以針對所有的邊緣池設定外部 DNS SRV 記錄（而不只是一個），來簡化災害復原程式。 這些 SRV 記錄中的每一個都必須設定不同的優先順序。 所有 XMPP 聯盟流量都是透過擁有最高優先順序的 SRV 記錄的池中進行。 如需啟用及設定 XMPP 同盟的詳細資訊，請參閱[在 Lync Server 2013 中設定 XMPP 同盟](lync-server-2013-setting-up-xmpp-federation.md)。

在下列程式中，EdgePool1 是最初託管 XMPP 同盟的池，而 EdgePool2 是該池，現在將託管 XMPP 同盟。

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>針對用於 XMPP 同盟的邊緣池進行容錯移轉

1.  如果您還沒有部署另一個 Edge 池（除了目前已停機），請部署該池。 如需詳細資訊，請參閱[在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)。

2.  在新 Edge 池中的每個 Edge 伺服器上，現在將會主控 XMPP 同盟（EdgePool2），請執行下列 Cmdlet：
    
        Stop-CsWindowsService

3.  執行下列 Cmdlet，以 repoint XMPP 同盟路由至 EdgePool2：
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    在這個範例中，Site2 是包含邊緣池的網站，現在將託管 XMPP 同盟路由，而 EdgeServer2.contoso.com 是該池中的邊緣伺服器的 FQDN。

4.  在外部 DNS 伺服器上，將 XMPP 同盟的 DNS A 記錄變更為指向 EdgeServer2.contoso.com。

5.  如果您還沒有可解析到 Edge 池的 XMPP 同盟的 DNS SRV 記錄，而該內容現在將託管 XMPP 同盟，您必須新增該記錄，如下列範例所示。 這個 SRV 記錄的埠值必須是5269。
    
        _xmpp-server._tcp.contoso.com

6.  確認現在將由 XMPP 同盟託管的邊緣池已在外部開啟埠5269。

7.  在邊緣池中的所有邊緣伺服器上啟動服務，現在將會託管 XMPP federation：
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

