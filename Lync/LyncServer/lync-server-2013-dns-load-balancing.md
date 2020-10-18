---
title: Lync Server 2013： DNS 負載平衡
description: Lync Server 2013： DNS 負載平衡。
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
ms.openlocfilehash: ba95604ca8f4007c76cedea9bf2a16dbd7db455c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574419"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 負載平衡

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-15_

Lync Server 可讓您在網路上大幅減少負載平衡之管理負荷的軟體解決方案，以進行 DNS 負載平衡。 DNS 負載平衡會平衡 Lync 伺服器特有的網路流量，例如 SIP 流量和媒體流量。

如果您部署 DNS 負載平衡，您組織的硬體負載平衡器的管理系統開銷將會降到最低。 此外，負載平衡器中針對 SIP 流量的設定錯誤問題所涉及的複雜疑難排解也得以排除。 您也可以防止伺服器連線，以便將伺服器離線。 DNS 負載平衡也可以確保硬體負載平衡器問題不會影響基本通話路由等這類 SIP 流量元素。

相較於將硬體負載平衡器用於全部的流量類型，如果使用 DNS 負載平衡也能讓您購買成本較低的硬體負載平衡器。 您應該使用已通過 Lync Server 的互通性驗證測試的負載平衡器。 如需負載平衡器互通性測試的詳細資訊，請參閱 at 中的「Lync Server 2010 負載平衡器合作夥伴」 [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) 。

DNS 負載平衡支援前端集區、Edge Server 集區、Director 集區和獨立中繼伺服器集區。

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>前端集區和 Director 集區上的 DNS 負載平衡

您可以針對前端集區和 Director 集區上的 SIP 流量使用 DNS 負載平衡。部署 DNS 負載平衡之後，這些集區還是需要使用硬體負載平衡器，但只限用戶端到伺服器的 HTTPS 流量。硬體負載平衡器會用於用戶端透過連接埠 443 和 80 送出的 HTTPS 流量。

雖然這些集區仍然需要硬體負載平衡器，但是其設定和系統管理主要是針對 HTTPS 流量，這也是硬體負載平衡器的系統管理員比較熟悉的領域。

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 負載平衡以及支援的舊版用戶端和伺服器

DNS 負載平衡只支援執行 Lync Server 2013 或 Lync Server 2010 的伺服器，以及 Lync 2013 和 Lync 2010 用戶端的自動容錯移轉。 較舊版本的用戶端和 Office 通訊伺服器仍然可以連線到執行 DNS 負載平衡的集區，但如果這些集區無法連線至 DNS 負載平衡所參照的第一部伺服器，則他們無法容錯移轉至集區中的另一部伺服器。

此外，如果您使用 Exchange UM，您必須至少使用 Exchange 2010 SP1 以取得 Lync Server DNS 負載平衡的支援。 如果您使用舊版的 Exchange，您的使用者將不會有這些 Exchange UM 案例的容錯移轉功能：

  - 在電話上播放企業語音語音信箱

  - 從 Exchange UM 自動語音應答轉接通話

所有其他 Exchange UM 案例則會正常運作。

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>在前端集區和 Director 集區上部署 DNS 負載平衡

在前端集區和 Director 集區上部署 DNS 負載平衡，需要您對 FQDN 和 DNS 記錄執行一些額外步驟。

  - 集區若要使用 DNS 負載平衡，必須要有兩個 FQDN：一個是供 DNS 負載平衡使用的一般集區 FQDN (如 pool01.contoso.com)，這會解析為集區中伺服器的實體 IP；另一個是集區的 Web 服務的 FQDN (如 web01.contoso.com)，這會解析為集區的虛擬 IP 位址。
    
    在 [拓撲產生器] 中，如果您想要為集區部署 DNS 負載平衡，若要為集區的 Web 服務建立額外的 FQDN，您必須選取 [覆 **寫內部 Web 服務集區 FQDN** ] 核取方塊，然後在 [ **指定 Web 服務 URLs 中為此集** 區] 頁面中輸入 FQDN。

  - 若要支援 DNS 負載平衡所使用的 FQDN，您必須佈建 DNS，以將集區 FQDN (如 pool01.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。您應該只包含目前部署之伺服器的 IP 位址。
    
    <div>
    

    > [!WARNING]  
    > 如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 <STRONG>pool01.contoso.com</STRONG>，則無法將 <STRONG>pool01.contoso.com</STRONG> 用於另一個前端集區或前端伺服器。 如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。 如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Edge Server 集區上的 DNS 負載平衡

您可以在 Edge Server 集區上部署 DNS 負載平衡。如果這麼做，則必須注意下列考量。

在 Edge Server 上使用 DNS 負載平衡，會導致下列案例喪失容錯移轉能力：

  - 與執行 Lync Server 2010 之前發行之 Office 通訊伺服器版本的組織同盟。

  - 與 \! XMPP 提供者和伺服器（如 Google 談話）以外的公開立即訊息使用者 (IM) Services AOLand Yahoo）的立即訊息交換。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google 交談目前是唯一支援的 XMPP 合作夥伴。</P>
    > <LI>
    > <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P></LI></UL>

    
    </div>

只要集區中的所有 Edge Server 都啟動並執行，這些案例就能運作，但是如果其中一個 Edge Server 無法使用，則在這些案例中任何傳送給該 Edge Server 的要求都會失敗，而不是路由至另一個 Edge Server。

如果您使用的是 Exchange UM，您必須至少使用 Exchange 2013，以取得對 Edge 的 Lync Server DNS 負載平衡的支援。 如果您使用舊版的 Exchange，您的遠端使用者將不會有這些 Exchange UM 案例的容錯移轉功能：

  - 在電話上播放企業語音語音信箱

  - 從 Exchange UM 自動語音應答轉接通話

所有其他 Exchange UM 案例則會正常運作。

內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>在 Edge Server 集區上部署 DNS 負載平衡

若要在 Edge Server 集區的外部介面上部署 DNS 負載平衡，您需要下列 DNS 項目：

  - 對於 Access Edge service，集區中的每一部伺服器都需要一個專案。 每個專案都必須解析 Access Edge service (的 FQDN，例如，sip.contoso.com) 到集區中某一部 Edge Server 上的 Access Edge service 的 IP 位址。

  - 針對 Web 會議 Edge service，集區中的每一部伺服器都需要一個專案。 每個專案都必須解析 Web 會議 Edge service (的 FQDN，例如，webconf.contoso.com) 至集區中某一部 Edge Server 上的 Web 會議 Edge service 的 IP 位址。

  - 針對 Audio/Video Edge service，集區中的每一部伺服器都需要一個專案。 每個專案都必須解析 Audio/Video Edge service 的 FQDN (例如，av.contoso.com) 至集區中某一部 Edge Server 上的 A/V Edge service 的 IP 位址。

若要在 Edge Server 集區的內部介面上部署 DNS 負載平衡，您必須新增一筆 DNS A 記錄，並讓它將 Edge Server 集區的內部 FQDN 解析為集區中每部伺服器的 IP 位址。

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>在中繼伺服器集區上使用 DNS 負載平衡

您可以在獨立中繼伺服器集區上使用 DNS 負載平衡，所有 SIP 和媒體流量都是透過 DNS 負載平衡進行平衡處理。

若要在中繼伺服器集區上部署 DNS 負載平衡，您必須佈建 DNS，以將集區 FQDN (例如，mediationpool1.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>使用 DNS 負載平衡封鎖伺服器的流量

如果您使用 DNS 負載平衡，而且需要封鎖特定電腦的流量，只是移除集區 FQDN 的 IP 位址專案是不夠的。 您也必須移除電腦的 DNS 專案。

請注意，針對伺服器對伺服器流量，Lync Server 2013 使用拓撲感知負載平衡。 伺服器讀取中央管理存放區中已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器間自動散佈流量。 若要封鎖伺服器接收伺服器對伺服器的流量，您必須從拓撲中移除伺服器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

