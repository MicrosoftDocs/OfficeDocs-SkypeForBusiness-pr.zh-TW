---
title: Lync Server 2013： DNS 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 負載平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-15_

Lync Server 可啟用 DNS 負載平衡，這是可大大減少網路上負載平衡之管理負荷的軟體解決方案。 [DNS 負載平衡] 會平衡 Lync Server 特有的網路流量，例如 SIP 流量及媒體流量。

如果您部署 DNS 負載平衡，貴組織的硬體負載平衡器的系統管理開銷將會最小化。 此外，對於與 SIP 流量的負載平衡程式配置錯誤相關的問題，複雜的疑難排解將會消失。 您也可以避免伺服器連線，以便讓伺服器離線。 DNS 負載平衡也可確保硬體負載平衡器問題不會影響 SIP 流量的元素，例如基本呼叫路由。

如果您使用 DNS 負載平衡，您可能也可以購買成本較低的硬體負載平衡器，而不是在所有類型的流量中使用硬體負載平衡器。 您應該使用與 Lync Server 經過互通性驗證測試的負載平衡器。 如需有關負載平衡程式互通性測試的詳細資料，請參閱「Lync [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)Server 2010 負載平衡器合作夥伴」。

前端池、邊緣伺服器池、控制器池和獨立的中繼伺服器池都支援 DNS 負載平衡。

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>前端池與控制器池上的 DNS 負載平衡

您可以針對前端池和控制器池上的 SIP 流量使用 DNS 負載平衡。 在部署 DNS 負載平衡的情況下，您仍然需要同時針對這些池使用硬體負載平衡器，但僅適用于用戶端到伺服器的 HTTPS 流量。 硬體負載平衡器用於來自埠443和80的用戶端的 HTTPS 流量。

雖然您仍需要這些池的硬體負載平衡器，但它們的設定和管理主要是針對 HTTPS 流量（硬體負載平衡器的系統管理員習慣）。

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 負載平衡及支援舊版用戶端和伺服器

DNS 負載平衡只支援執行 Lync Server 2013 或 Lync Server 2010 的伺服器以及 Lync 2013 和 Lync 2010 用戶端的自動容錯移轉。 較舊版本的用戶端和 Office 通訊伺服器仍可連線到執行 DNS 負載平衡的池，但如果它們無法連線到 DNS 負載平衡所參照的第一個伺服器，則它們無法容錯移轉至池中的另一台伺服器.

此外，如果您使用的是 Exchange UM，您必須至少使用 Exchange 2010 SP1，才能取得 Lync Server DNS 負載平衡的支援。 如果您使用的是舊版 Exchange，您的使用者將沒有這些 Exchange UM 案例的容錯移轉功能：

  - 在電話上播放企業語音信箱

  - 轉移來自 Exchange UM 自動語音應答的呼叫

所有其他 Exchange UM 案例都會正常運作。

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>在前端池和控制器池上部署 DNS 負載平衡

在前端池和控制器池上部署 DNS 負載平衡，您需要執行幾個額外步驟，使用 Fqdn 和 DNS 記錄。

  - 使用 DNS 負載平衡的池必須有兩個 Fqdn：由 DNS 負載平衡所使用的一般池 FQDN （例如 pool01.contoso.com），並解析成池中伺服器的實際 Ip，以及該池 Web 服務的另一個 FQDN （例如web01.contoso.com），可解析為池的虛擬 IP 位址。
    
    在拓撲建立器中，如果您想要為池的 Web 服務部署 DNS 負載平衡，您必須選取 [覆**寫內部 Web 服務池 FQDN** ] 核取方塊，然後在 [**指定適用于此池的 Web 服務 url** ] 頁面上輸入 FQDN。

  - 若要支援 DNS 負載平衡所使用的 FQDN，您必須提供 DNS，以將池 FQDN （例如 pool01.contoso.com）解析為池中所有伺服器的 IP 位址（例如，192.168.1.1、192.168.1.2 等等）。 您應該只包含目前已部署之伺服器的 IP 位址。
    
    <div>
    

    > [!WARNING]  
    > 如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端池或前端伺服器。 如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須與任何其他的前端池、控制器或主管池是唯一的。

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Edge 伺服器池中的 DNS 負載平衡

您可以在 Edge 伺服器池中部署 DNS 負載平衡。 如果您這樣做，您必須知道一些考慮。

在邊緣伺服器上使用 DNS 負載平衡，會造成下列案例中的容錯移轉能力損失：

  - 與執行 Lync Server 2010 之前發行之 Office 通訊伺服器版本之組織的同盟。

  - 與公用立即訊息（IM）服務 AOLand Yahoo\!的使用者，以及 Google 交談等 XMPP 提供者和伺服器以外的立即訊息交換。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google 交談目前是唯一支援的 XMPP 合作夥伴。</P>
    > <LI>
    > <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P></LI></UL>

    
    </div>

只要池中的所有邊緣伺服器都已啟動並執行，這些案例就能正常運作，但如果沒有一個 Edge 伺服器無法使用，傳送給它的這些案例的任何要求都會失敗，而不是路由到另一個 Edge 伺服器。

如果您使用的是 Exchange UM，您必須使用 Exchange 2013 的最低限度，才能在 Edge 上取得 Lync Server DNS 負載平衡的支援。 如果您使用的是舊版 Exchange，您的遠端使用者將沒有這些 Exchange UM 案例的容錯移轉功能：

  - 在電話上播放企業語音信箱

  - 轉移來自 Exchange UM 自動語音應答的呼叫

所有其他 Exchange UM 案例都會正常運作。

內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>在 Edge 伺服器池中部署 DNS 負載平衡

若要在 Edge 伺服器池的外部介面上部署 DNS 負載平衡，您需要下列 DNS 專案：

  - 針對存取邊緣服務，您需要為池中的每個伺服器加入一個專案。 每個專案都必須將存取邊緣服務（例如，sip.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的存取邊緣服務的 IP 位址。

  - 針對網路會議 Edge 服務，池中的每個伺服器都需要一個專案。 每個專案都必須將網路會議 Edge 服務（例如，webconf.contoso.com）的 FQDN 解析成池中某個邊緣伺服器的網路會議 Edge 服務的 IP 位址。

  - 針對音訊/視頻邊緣服務，池中的每個伺服器都需要一個專案。 每個專案都必須將音訊/視頻邊緣服務（例如，av.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的 A/V 邊緣服務的 IP 位址。

若要在 Edge 伺服器池的內部介面上部署 DNS 負載平衡，您必須加入一個 DNS A 記錄，該記錄會將 Edge 伺服器池的內部 FQDN 解析成池中每個伺服器的 IP 位址。

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>在中繼伺服器池中使用 DNS 負載平衡

您可以在獨立的中繼伺服器池上使用 DNS 負載平衡。 所有 SIP 和媒體流量都是透過 DNS 負載平衡來平衡。

若要在轉送伺服器池中部署 DNS 負載平衡，您必須建立 DNS，以將池 FQDN （例如，mediationpool1.contoso.com）解析成池中所有伺服器的 IP 位址（例如，192.168.1.1、192.168.1.2 等）。

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>使用 DNS 負載平衡封鎖伺服器的流量

如果您使用 DNS 負載平衡，而且您需要封鎖流量至特定電腦，則只需從池 FQDN 中移除 IP 位址專案是不夠的。 您也必須移除電腦的 DNS 專案。

請注意，對於伺服器到伺服器的流量，Lync Server 2013 使用拓撲感知負載平衡。 伺服器會在中央管理儲存體中讀取已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器之間自動散佈流量。 若要封鎖伺服器接收伺服器對伺服器流量，您必須從拓撲中移除伺服器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

