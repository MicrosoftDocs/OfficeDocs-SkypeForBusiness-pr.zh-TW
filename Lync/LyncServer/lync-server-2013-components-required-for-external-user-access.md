---
title: Lync Server 2013：外部使用者存取所需的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05c4b2845f4146c6394712951089750299ce60b7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取所需的元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-29_

大部分的 Edge 元件都是部署在周邊網路中。 周邊網路的 Edge 拓撲由下列元件組成。 除了另有說明之外，這些元件是[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)的一部分，且位於周邊網路中。 Edge 元件包括：

  - Edge Server

  - 反向 proxy

  - 防火牆

  - Director （選用，以及邏輯上位於內部網路）

  - 調整式 Edge 拓撲的負載平衡 (DNS 負載平衡或硬體負載平衡器)
    
    <div>
    

    > [!IMPORTANT]  
    > 不支援在一個介面上使用 DNS 負載平衡，而在另一個介面上使用硬體負載平衡。您必須同時針對這兩個介面使用硬體負載平衡或 DNS 負載平衡。

    
    </div>

<div>

## <a name="edge-servers"></a>Edge Server

Edge Server 會傳送和接收外部使用者內部部署所提供之服務的網路流量。 Edge Server 可執行下列服務：

  - **Access Edge service**    Access Edge service 會為輸出和輸入會話初始通訊協定（SIP）流量提供單一、受信任的連接點。

  - **Web 會議 Edge service**    Web 會議 Edge service 可讓外部使用者加入內部 Lync Server 2013 部署中所主控的會議。

  - **A/V Edge service**    A/V Edge service 可讓外部使用者使用音訊、影片、應用程式共用和檔案傳輸功能。 您的使用者可以在包含外部參與者的會議中新增音訊和影片，也可以使用音訊和/或影片直接透過點對點會話中的外部使用者進行通訊。 A/V Edge Service 也可支援桌面共用與檔案傳輸。

  - **XMPP Proxy 服務**    XMPP Proxy 服務會接受及傳送可延伸的訊息和顯示狀態通訊協定（XMPP）郵件，並從設定的 XMPP 同盟協力廠商傳送。

已授權的外部使用者可以存取 Edge Server，以連線至您的內部 Lync Server 2013 部署，但 Edge server 並未提供任何其他存取內部網路的方法。

<div>


> [!NOTE]  
> 部署 Edge server 是為了提供啟用的 Lync 用戶端和其他 Microsoft Edge server 的連線（如同在同盟案例中一樣）。 這些伺服器的設計，目的並非在於提供從其他端點用戶端或從其他伺服器類型進行連線的能力。 部署 XMPP 閘道伺服器可提供與設定的 XMPP 合作夥伴的進行連線的能力。 Edge Server 和 XMPP 閘道僅可支援從這些用戶端和同盟類型進行端點連線的能力。



</div>

</div>

<div>

## <a name="reverse-proxy"></a>反向 Proxy

下列作業需要反向 Proxy：

  - 讓使用者透過簡單 URL 連線至會議或電話撥入式會議

  - 讓外部使用者下載會議內容

  - 讓外部使用者能夠擴充通訊群組

  - 讓使用者取得可用於用戶端憑證式驗證的使用者式憑證

  - 讓遠端使用者從 Address Book Server 下載檔案，或送出查詢至通訊錄 Web 查詢服務

  - 讓遠端使用者取得用戶端與裝置軟體的更新

  - 讓行動裝置能夠自動探索前端伺服器提供行動服務

  - 從 Microsoft 365、Office 365 或 Apple push notification 服務，啟用行動裝置的推播通知

如需與反向 proxy 相關的其他資訊，以及反向 proxy 必須符合的需求，請參閱[Lync Server 2013 中的反向 proxy 設定需求](lync-server-2013-configuration-requirements-for-reverse-proxy.md)的詳細資料。

<div>


> [!NOTE]  
> 外部使用者不需要有虛擬私人網路（VPN）連線至您的組織，即可使用 Lync Server 2013 參加通訊。 如果您已在組織中實施 VPN 技術，且使用者使用的是 Lync 的 VPN，媒體流量（例如影片會議）可能會受到不良影響。 您應考慮提供一種方法，讓媒體流量直接連線至 AV Edge service，並略過 VPN。 如需詳細資訊，請參閱 NextHop 的博客文章：「啟用 Lync Media 旁路 VPN 隧道」 <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A> 。



</div>

</div>

<div>

## <a name="firewall"></a>防火牆

部署您的 Edge 拓撲時，您可以僅使用外部防火牆，也可以同時使用外部與內部防火牆。 案例架構包含兩個防火牆。 建議您使用兩個防火牆，因為這樣可確保從某個網路邊緣傳入另一個網路邊緣的流量嚴格遵守路由規則，且內部部署可受到兩層防火牆保護。

</div>

<div>

## <a name="director"></a>Director

Director 是 Lync Server 2013 中的個別非選用伺服器角色，不會家用使用者帳戶，也不會提供目前狀態或會議服務。 它充當內部的下一個躍點伺服器，Edge Server 會將傳入 SIP 流量路由傳送至內部伺服器。 Director preauthenticates 輸入要求並將其重新導向至使用者的主集區或伺服器。 透過 preauthenticating 在 Director 上，您可以丟棄部署無法識別之使用者帳戶的要求。

Director 可協助將 Enterprise Edition 前端集區中的 Standard Edition 伺服器和前端伺服器與惡意流量（如拒絕服務（DoS）攻擊）隔離。 如果網路在這類攻擊中以不正確外部流量淹沒，該流量會結束于 Director。 如需使用 Director 的詳細資訊，請參閱[Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 的硬體負載平衡器需求](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

