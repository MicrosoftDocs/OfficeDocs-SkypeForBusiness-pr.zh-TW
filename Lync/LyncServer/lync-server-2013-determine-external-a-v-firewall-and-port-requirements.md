---
title: Lync Server 2013：判斷外部 A/V 防火牆和埠需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c7b117f68719230151fd19050dbb080f6acde14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522580"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>決定 Lync Server 2013 的外部 A/V 防火牆和埠需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

Audio/Video (A/V) 通訊可能是複雜的。 因為 A/V 所使用的通訊協定性質，以及用戶端和伺服器使用通訊協定的方式，所以特殊區段會保證用戶端與伺服器版本之間的差異。

使用下列 A/V 防火牆及埠表來判斷防火牆需求和要開啟的埠。 接著檢閱網路位址轉譯 (NAT) 術語，因為 NAT 可透過許多方式實作。 如需防火牆埠設定的詳細範例，請參閱 [Lync Server 2013 中的外部使用者存取案例案例](lync-server-2013-scenarios-for-external-user-access.md)中的參考架構。

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Audio/Video 和媒體流量中的 UDP 和 TCP 一般通訊協定用法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Audio/Video 傳輸</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Udp</p></td>
<td><p>音訊和影片的慣用傳輸層通訊協定</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>音訊和影片的 Fallback transport layer 通訊協定</p>
<p>Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的應用程式共用所需的傳輸層通訊協定</p>
<p>Lync Server 2010 和 Lync Server 2013 的檔案傳輸所需的傳輸層通訊協定</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>外部使用者存取的外部 A/V 防火牆連接埠需求

外部 (和內部) SIP 和會議介面的防火牆埠需求，不論您的用戶端版本為何，或是同盟協力廠商的版本，都是一致的。

A/V Edge 外部介面則不同。 若要使用 Office 通訊伺服器2007的同盟，A/V Edge service 需要外部防火牆規則允許 RTP/TCP 和 RTP/UDP 的50000到59999埠範圍中的流量，以流向這兩個方向。 上表假設 Lync Server 2013 是主要同盟協力廠商，且設定為與所列的其他其中一個同盟夥伴類型通訊。

設定 Audio/Video 的埠範圍 50000 59999 必須考慮，埠範圍會包含用於與同盟協力廠商通訊的來源埠。 詳細資訊，請考慮從同盟協力廠商發起通訊。 從 50000 59999 範圍中 A/V Edge service 埠的通訊，會連線至夥伴的 A/V Edge service 所期望的埠 TCP 443。 相反地，對您 A/V Edge service 埠 TCP 443 的輸入流量，其來源埠為 50000-59999。

防火牆管理的不同防火牆和原則可能只需要設定目的地規則，也可能需要設定來源和目的地。 如果您的需求只適用于目的地埠，則 Audio/Video 需求如下：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>來源 IP</th>
<th>目的地 IP</th>
<th>目的地連接埠</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任何</p></td>
<td><p>A/V Edge service 介面</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任何</p></td>
<td><p>A/V Edge service 介面</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


如果您的原則同時需要輸入和輸出防火牆規則定義，Audio/Video 需求如下：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>來源 IP</th>
<th>目的地 IP</th>
<th>來源連接埠</th>
<th>目的地連接埠</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>TCP 50000 59999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任何</p></td>
<td><p>A/V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任何</p></td>
<td><p>A/V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office 通訊伺服器2007需要稍有不同的設定。 59999的 TCP 和 UDP 埠範圍必須是開啟的輸入和輸出。 這項需求只適用于 Office Communicator 2007。 Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 只需要 TCP 範圍 50000 59999 開啟輸出。



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Edge service 的 NAT 需求

如果您選擇為 Edge service 設定不可路由的私人 IP 位址，則適用下列 NAT 需求：

  - NAT 只可搭配使用 DNS 負載平衡。 NAT 不支援硬體負載平衡 (HLB) Edge 拓撲。

  - NAT 只可用於外部 Edge 介面。 在內部 Edge 介面上不支援 NAT。

  - NAT 必須對稱傳入和傳出的流量。
    
  - 對於來自網際網路的流量，NAT 必須將 A/V Edge service 之已啟用 NAT 的公用 IP 位址的目的地 IP 位址變更為其外部 IP 位址。 來源 IP 位址必須保持不變，因此 A/V Edge service 可以找出最佳的媒體路徑。
  
  例如，在下圖的輸入方向中，公用 IP 位址131.107.155.30 已變更為外部 (私人) IP 位址10.45.16.10。 來源 IP 位址保持不變。
  
  - 若要從 A/V Edge service 到網際網路的流量，NAT 必須將來源 IP 位址從 A/V Edge service 的外部 IP 位址變更為已啟用 NAT 的公用 IP 位址。

例如，在下圖的輸出方向上，外部 (私人) IP 位址10.45.16.10 已變更為公用 IP 位址131.107.155.30。

**下圖顯示 NAT 如何變更輸入流量的目的地 IP 位址，以及輸出流量的來源 IP 位址。**

![變更目的地/來源 IP 位址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "變更目的地/來源 IP 位址")

重點為：

  - 輸入至執行 A/V Edge service 之伺服器的流量，來源 IP 位址不會變更，但目的地 IP 位址會從131.107.155.30 變更為10.45.16.10 的轉譯後的 IP 位址。

  - 從執行 A/V Edge service 的伺服器輸出到工作站的流量，來源 IP 位址會從伺服器的公用 IP 位址變更為執行 A/V Edge service 之伺服器的公用 IP 位址。 目的地 IP 會保留工作站的公用 IP 位址。 當封包保留第一個 NAT 裝置輸出後，NAT 裝置上的規則會將執行 A/V Edge service 外部介面 IP 位址 (10.45.16.10) 的伺服器來源 IP 位址變更為 (131.107.155.30) 的公用 IP 位址。

</div>

</div>

<span> </span>

</div>

</div>

</div>

