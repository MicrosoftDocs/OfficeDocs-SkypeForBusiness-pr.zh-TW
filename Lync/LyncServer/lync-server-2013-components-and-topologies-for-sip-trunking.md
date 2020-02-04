---
title: Lync Server 2013：SIP 主幹連線的元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30c589ff02717ad49ce89d0d4e3324f6fe993e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 主幹連線的元件與拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

下圖描繪了 Lync Server 中的 SIP 中繼拓撲。

**SIP 中繼拓撲**

![SIP 主幹拓撲](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 主幹拓撲")

如圖表中所示，IP 虛擬私人網路（VPN）是在商業網路與公用交換電話網絡（PSTN）服務提供者之間連線所使用。 這個私人網路絡的用途是提供 IP 連線、加強安全性，以及（選擇）取得服務品質（QoS）保證。 由於 VPN 的性質，您不需要針對媒體流量使用傳輸層安全性（TLS）來傳送 SIP 信號流量或安全即時傳輸通訊協定（SRTP）。 企業與服務提供者之間的連線是由針對 SIP 的純 TCP 連線和純時間傳輸通訊協定（RTP）（透過 UDP），透過 IP VPN 傳送媒體隧道。 確定 VPN 路由器之間的所有防火牆都已開啟埠，以允許 VPN 路由器進行通訊，以及 VPN 路由器外部邊緣的 IP 位址可公開路由。

<div>


> [!IMPORTANT]  
> 請與您的服務提供者聯繫，判斷它是否提供高可用性支援，包括容錯移轉。 如果是這樣，您將需要判斷設定的程式。 例如，您是否只需要在每個中繼伺服器上設定一個 IP 位址和一個 SIP 幹線，或者您是否需要在每個中繼伺服器上設定多個 SIP trunks？<BR>如果您有多個中心網站，也會詢問服務提供者是否能夠啟用與其他中心網站的連線。



</div>

<div>


> [!NOTE]  
> 針對 SIP 中繼，我們強烈建議您部署獨立的中繼伺服器。 如需詳細資訊，請參閱部署檔中的在<A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync Server 2013 中部署中繼伺服器和定義對等</A>。



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>保護 SIP 中繼的中繼伺服器

為安全起見，您應該針對兩個 VPN 路由器之間的每個連線設定虛擬 LAN （VLAN）。 設定 VLAN 的實際處理常式會因路由器製造商而異。 如需詳細資訊，請與您的路由器廠商聯繫。

我們建議您遵循下列指導方針：

  - 在中繼伺服器與周邊網路中的 VPN 路由器（也稱為 DMZ、網路隔離區域及遮罩子網）之間設定虛擬 LAN （VLAN）。

  - 請勿允許將廣播或多播封包從路由器傳輸到 VLAN。

  - 封鎖任何路由規則，可將流量從路由器路由到任何位置，而不是中繼伺服器。

如果您使用的是 VPN 伺服器，我們建議您遵循下列指導方針：

  - 在 VPN 伺服器與中繼伺服器之間設定 VLAN。

  - 請勿允許從 VPN 伺服器傳送廣播或多播資料包至 VLAN。

  - 封鎖將 VPN 伺服器流量路由到任何位置的任何路由規則，而是中繼伺服器。

  - 使用一般路由封裝（GRE）來加密 VPN 上的資料。

</div>

</div>

<span> </span>

</div>

</div>

</div>

