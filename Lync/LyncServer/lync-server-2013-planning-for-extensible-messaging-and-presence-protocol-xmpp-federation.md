---
title: 針對可擴展訊息和目前狀態通訊協定（XMPP）同盟進行規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4e1d8f9b7f164dd9e83f556dcc57809619278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中規劃可擴展訊息和目前狀態通訊協定（XMPP）同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和目前狀態通訊協定（XMPP）閘道，可將其部署為個別的伺服器角色，以允許與 XMPP 部署進行聯盟。 在 Microsoft Lync Server 2013 中，您可以將 XMPP 功能部署為功能。 XMPP 功能是由兩個部分所安裝：在 Edge 伺服器上執行的 XMPP proxy，以及在前端伺服器上執行的 XMPP 閘道。

XMPP 的部署與設定在[Lync Server 2013 中的 [部署外部使用者存取權](lync-server-2013-deploying-external-user-access.md)] 中，您打算在防火牆上定義埠和通訊協定規則、設定憑證的設定，以及新增 DNS 記錄，以規劃支援組織中的 XMPP。 本節中的下列主題摘要說明為您的部署順利規劃 XMPP 同盟時所需的資訊。

<div>


> [!IMPORTANT]
> Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。 針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [認證摘要-Lync Server 2013 中的可擴展訊息和目前狀態通訊協定（XMPP）同盟](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [在 Lync Server 2013 中的埠摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [在 Lync Server 2013 中的 DNS 摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定 XMPP 同盟](lync-server-2013-setting-up-xmpp-federation.md)  
[在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[在 Lync Server 2013 中管理 XMPP 同盟夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))  
[CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))  
[CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

