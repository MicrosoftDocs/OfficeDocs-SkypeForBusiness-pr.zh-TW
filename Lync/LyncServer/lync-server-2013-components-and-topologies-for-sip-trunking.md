---
title: Lync Server 2013： 元件和的 SIP 主幹拓撲
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
ms.openlocfilehash: a9e31b7cc0ea6e5acec0382ecd468a868152570d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 主幹的元件和拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

下圖說明 Lync Server 中的 SIP 主幹拓撲。

**SIP 主幹拓撲**

![SIP 主幹拓撲](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 主幹拓撲")

如圖所示，IP 虛擬私人網路 (VPN) 適用於企業網路與公用交換的電話網路 (PSTN) 服務提供者之間的連線。 此私人網路的用途是提供 IP 連線、 增強的安全性，以及 （選擇性） 取得服務品質 (QoS) 保證。 VPN 的性質，因為您不需要使用傳輸層安全性 (TLS) 的 SIP 訊號流量或媒體流量的安全即時傳輸通訊協定 (SRTP)。 企業與服務提供者之間的連線因此所組成的 SIP 和一般即時傳輸通訊協定 (RTP) （透過 UDP) 的通道透過 IP VPN 的媒體的純文字 TCP 連線。 請確定 VPN 路由器之間的所有防火牆都已開啟以允許 VPN 路由器，以進行通訊，連接埠和 IP 位址，在 [外部邊緣的 VPN 路由器上是可公開路由傳送。

<div>


> [!IMPORTANT]  
> 請連絡您的服務提供者，來判斷是否它提供支援的高可用性，包括容錯移轉。 如果是的話，您必須決定及其設定的程序。 例如，您需要在每個中繼伺服器上，設定只有一個 IP 位址和一個 SIP 主幹或您需要在每一部中繼伺服器上設定多個 SIP 主幹？<BR>如果您有多個中央網站，也請詢問服務提供者是否有能力啟用連線到及傳送自另一個中央網站。



</div>

<div>


> [!NOTE]  
> SIP 主幹，我們強烈建議您部署獨立中繼伺服器。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Lync Server 2013 中的定義同儕</A>。



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>SIP 主幹保護中繼伺服器

基於安全性考量，您應該設定設定虛擬 LAN (VLAN) 的每個連接兩個 VPN 路由器之間。 實際的程序設定 VLAN 因一個路由器製造商的不同而異。 如需詳細資訊，請連絡您的路由器供應商。

建議您遵循這些方針：

  - 設定設定虛擬 LAN (VLAN) 之間中繼伺服器和 VPN 路由器在周邊網路 （也稱為 DMZ、 非軍事區和遮蔽式子網路）。

  - 不允許將廣播或多點傳送封包從路由器傳輸至 VLAN。

  - 封鎖任何從路由器 anywhere 的流量路由傳送的路由規則，但中繼伺服器。

如果您使用 VPN 伺服器，建議您遵循以下指導方針：

  - 設定 VPN 伺服器和中繼伺服器之間 VLAN。

  - 不允許將廣播或多點傳送封包從 VPN 伺服器傳輸至 VLAN。

  - 封鎖任何將 VPN 伺服器流量路由傳送至任何位置的路由規則，但中繼伺服器。

  - 藉由使用 generic routing encapsulation (GRE) 加密 VPN 上的資料。

</div>

</div>

<span> </span>

</div>

</div>

</div>

