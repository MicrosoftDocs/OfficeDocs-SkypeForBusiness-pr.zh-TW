---
title: Lync Server 2013： SIP trunk 的元件和拓撲
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
ms.openlocfilehash: 08961982f382e5b5c670f6a1640884a4540a4c20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502490"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中 SIP 主幹的元件和拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

下圖描述 Lync Server 中的 SIP 主幹拓撲。

**SIP 主幹拓撲**

![SIP 主幹拓撲](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 主幹拓撲")

如圖所示，在商業網路和公用交換電話網路 (PSTN) 服務提供者之間的連線中，會使用 IP 虛擬私人網路 (VPN) 。 此私人網路的目的在於提供 IP 連線功能、增強安全性，以及 (選擇性) 取得服務品質 (QoS) 保證。 由於 VPN 的性質，您不需要使用傳輸層安全性 (TLS) 以進行 SIP 信號流量或安全即時傳輸通訊協定 (SRTP) 的媒體流量。 企業和服務提供者之間的連線是由 SIP 和即時即時傳輸通訊協定的純 TCP 連線所組成 (RTP)  (透過 UDP) 透過 IP VPN 傳送媒體隧道。 確定所有 VPN 路由器間的防火牆皆已開啟埠，以允許 VPN 路由器通訊，而且 VPN 路由器外部邊緣的 IP 位址可公開路由傳送。

<div>


> [!IMPORTANT]  
> 請與您的服務提供者聯繫，以判斷其是否提供高可用性支援（包括容錯移轉）。 如果是的話，您將需要決定設定的程式。 例如，您只需要在每個轉送伺服器上設定一個 IP 位址和一個 SIP 主幹，還是需要在每個轉送伺服器上設定多個 SIP 主幹？<BR>如果您有多部中央網站，也請詢問服務提供者是否有能力啟用與其他中央網站之間的連線。



</div>

<div>


> [!NOTE]  
> 若為 SIP 主幹，強烈建議您部署獨立的轉送伺服器。 如需詳細資訊，請參閱部署檔中的部署中繼 <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">伺服器及定義 Lync Server 2013 中的對等</A> 專案。



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>保護 SIP 中繼的轉送伺服器

基於安全性的考慮，您應該為兩個 VPN 路由器間的每個連線設定虛擬 LAN (VLAN) 。 安裝 VLAN 的實際程式會因不同的路由器製造商而異。 如需詳細資訊，請與您的路由器廠商聯繫。

建議您遵循這些方針：

  - 在周邊網路中的轉送伺服器和 VPN 路由器之間設定虛擬 LAN (VLAN)  (也稱為 DMZ、隔離區域和遮罩式子網) 。

  - 不允許從路由器將廣播或多播封包傳輸至 VLAN。

  - 封鎖將流量從路由器路由傳送至任何地方（轉送伺服器）的路由規則。

如果您使用 VPN 伺服器，我們建議您遵循下列指導方針：

  - 在 VPN 伺服器與轉送伺服器之間設定 VLAN。

  - 不允許從 VPN 伺服器將廣播或多播封包傳輸至 VLAN。

  - 封鎖將 VPN 伺服器流量路由傳送至任何無所不在（轉送伺服器）的路由規則。

  - 使用一般路由封裝 (GRE) ，加密 VPN 上的資料。

</div>

</div>

<span> </span>

</div>

</div>

</div>

