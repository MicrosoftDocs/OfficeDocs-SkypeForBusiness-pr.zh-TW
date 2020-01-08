---
title: Lync Server 2013：外部使用者存取所需的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>外部使用者在 Lync Server 2013 中存取時所需的元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-29_

大部分的邊緣元件都是在周邊網路中部署。 下列元件構成周邊網路的邊緣拓撲。 除非另有說明，否則元件屬於[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)，且位於周邊網路中。 Edge 元件包括下列各項：

  - Edge 伺服器

  - 反向代理

  - 道

  - 控制器（可省略，且在內部網路上的邏輯位置）

  - 針對調整後的邊緣拓撲（DNS 負載平衡或硬體負載平衡器）進行負載平衡
    
    <div>
    

    > [!IMPORTANT]  
    > 在一個介面上使用 DNS 負載平衡，而另一個介面上的硬體負載平衡則不受支援。 您必須針對兩種介面或 DNS 負載平衡使用硬體負載平衡。

    
    </div>

<div>

## <a name="edge-servers"></a>Edge 伺服器

Edge 伺服器會傳送和接收外部使用者由內部部署所提供之服務的網路流量。 Edge 伺服器會執行下列服務：

  - **存取邊緣服務**   存取邊緣服務為輸出與輸入會話初始通訊協定（SIP）流量提供單一、受信任的連接點。

  - **網路會議 edge 服務**   ：網路會議 edge 服務可讓外部使用者加入託管在您內部 Lync Server 2013 部署上的會議。

  - **A/v 邊緣服務**   a/v 邊緣服務可讓外部使用者使用音訊、影片、應用程式共用和檔案傳輸。 您的使用者可以在包含外部參與者的會議中新增音訊和影片，而且他們可以使用音訊和/或影片，在點對點會話中直接使用外部使用者進行通訊。 A/V 邊緣服務也提供對桌面共用和檔案傳輸的支援。

  - **XMPP proxy 服務**   XMPP Proxy 服務會從已設定的 XMPP 聯盟夥伴中接收並傳送可擴展的訊息和目前狀態通訊協定（XMPP）訊息。

已授權的外部使用者可以存取邊緣伺服器以連線到您的內部 Lync Server 2013 部署，但 Edge 伺服器不提供任何其他存取內部網路的方法。

<div>


> [!NOTE]  
> 已部署邊緣伺服器來提供已啟用的 Lync 用戶端和其他 Microsoft Edge 伺服器（例如在同盟案例中）的連線。 它們不是用來允許來自其他端點用戶端或伺服器類型的連線。 XMPP 閘道伺服器可以部署，以允許與已設定 XMPP 夥伴的連線。 Edge 伺服器和 XMPP 閘道只能支援來自這些用戶端與同盟類型的端點連線。



</div>

</div>

<div>

## <a name="reverse-proxy"></a>反向 Proxy

下列情況需要反向 proxy：

  - 若要允許使用者使用簡單的 Url 連線至會議或電話撥入式會議

  - 若要讓外部使用者下載會議內容

  - 若要讓外部使用者展開通訊群組

  - 允許使用者取得以用戶端憑證為基礎的驗證的使用者憑證

  - 若要讓遠端使用者從通訊錄服務器下載檔案，或是將查詢提交至通訊錄網頁查詢服務

  - 讓遠端使用者取得用戶端和裝置軟體的更新

  - 讓行動裝置自動探索前端伺服器提供行動服務

  - 從 Office 365 或 Apple 推播通知服務啟用 [推播通知] 至行動裝置

如需有關反向代理與反向代理伺服器必須符合的其他資訊，請參閱[Lync Server 2013 中的反向 proxy 設定需求](lync-server-2013-configuration-requirements-for-reverse-proxy.md)的詳細資料。

<div>


> [!NOTE]  
> 外部使用者不需要虛擬私人網路（VPN）連線至您的組織，就能使用 Lync Server 2013 參與通訊。 如果您已在組織中實現 VPN 技術，且您的使用者使用的是 Lync 的 VPN，媒體流量（例如視訊會議）可能會受到負面影響。 您應該考慮提供媒體流量以直接連線到 AV 邊緣服務的方式，並繞過 VPN。 如需詳細資訊，請參閱 NextHop 博客文章：「啟用 Lync 媒體旁路 VPN 隧道」 <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>。



</div>

</div>

<div>

## <a name="firewall"></a>防火牆

您可以只使用外部防火牆或外部與內部防火牆來部署 edge 拓撲。 案例架構包含兩個防火牆。 使用兩個防火牆是一種建議的方法，因為它可確保嚴格地從一個網路邊緣路由到另一個網路邊緣，而且它會保護您的內部部署是在兩個層次的防火牆後。

</div>

<div>

## <a name="director"></a>Director

Director 是 Lync Server 2013 中的個別、選擇性的伺服器角色，不會家用使用者帳戶，或提供目前狀態或會議服務。 它是一種內部的下一個躍點伺服器，可讓邊緣伺服器路由發往內部伺服器的入站 SIP 流量。 Director preauthenticates 輸入要求，並將它們重新導向至使用者的主區或伺服器。 在導演 preauthenticating，您可以丟棄部署無法識別的使用者帳戶要求。

控制器可協助將企業版前端池中的標準版伺服器與前端伺服器與惡意流量（例如拒絕服務（DoS）攻擊）隔離。 如果網路充斥在攻擊中的無效外部通信量，通信量就會結束在 Director 上。 如需有關使用控制器的詳細資料，請參閱[Lync Server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 的硬體負載平衡器需求](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

