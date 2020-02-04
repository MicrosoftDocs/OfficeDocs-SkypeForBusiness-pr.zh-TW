---
title: Lync Server 2013：決定外部 A/V 防火牆和連接埠需求
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
ms.openlocfilehash: 3d5519ef37ff334ddf196e94b40aa7df14d69d25
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

音訊/視頻（A/V）通訊可能是一個複雜的。 因為在 A/V 中使用的通訊協定以及用戶端和伺服器如何使用通訊協定，所以有一個特殊的章節可保證說明用戶端與伺服器版本之間的差異。

使用下列 A/V 防火牆和埠表來判斷防火牆需求和要開啟的埠。 然後，請查看網路位址轉譯（NAT）術語，因為 NAT 可以用許多不同的方式來實現。 如需防火牆埠設定的詳細範例，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)中的參考體系結構。

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>音訊/視頻和媒體流量中的 UDP 與 TCP 的一般通訊協定用法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>音訊/視頻傳輸</th>
<th>用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP-IN</p></td>
<td><p>音訊與影片的首選傳輸層通訊協定</p></td>
</tr>
<tr class="even">
<td><p>TCP-OUT</p></td>
<td><p>音訊與影片的回退傳輸層通訊協定</p>
<p>Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 適用的應用程式共用所需的傳輸層通訊協定</p>
<p>將檔案傳輸至 Lync Server 2010 和 Lync Server 2013 所需的傳輸層通訊協定</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>外部使用者存取的外部 A/V 防火牆埠需求

不論用戶端的版本或同盟夥伴版本為何，外部（以及內部） SIP 與會議介面的防火牆埠需求都是一致的。

音訊/視頻邊緣外部介面也不是如此。 針對使用 Office 通訊伺服器2007的同盟，A/V Edge 服務需要外部防火牆規則，才能在50000至59999埠範圍中啟用 RTP/TCP 和 RTP/UDP 流量，以雙向流動。 上表假設 Lync Server 2013 是主要同盟夥伴，且正在設定為與列出的其他其中一個聯盟夥伴類型進行通訊。

將音訊/視訊連接埠範圍設定為 50000-59999，必須考慮埠範圍將包含與同盟夥伴通訊的來源埠。 在詳細資料中，請考慮從同盟合作夥伴開始進行通訊。 來自 50000 59999 範圍中的 A/V 邊緣服務埠的通訊，會連線到合作夥伴的 A/V 邊緣服務的預期埠 TCP 443。 相反地，到 A/V 邊緣服務埠 TCP 443 的入站流量將會有 50000 59999 的來源埠。

防火牆管理的不同防火牆與原則可能只需要設定目的地規則，或者可能需要設定來源和目的地。 如果您的需求只適用于目的地埠，音訊/視頻需求如下：


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
<th>目的地埠</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V 邊緣服務介面</p></td>
<td><p>每</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V 邊緣服務介面</p></td>
<td><p>每</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>每</p></td>
<td><p>A/V 邊緣服務介面</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>每</p></td>
<td><p>A/V 邊緣服務介面</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


如果您的原則需要輸入和輸出防火牆規則定義，音訊/視頻需求如下：


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
<th>來源埠</th>
<th>目的地埠</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V 邊緣服務介面</p></td>
<td><p>每</p></td>
<td><p>TCP 50000-59999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V 邊緣服務介面</p></td>
<td><p>每</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>每</p></td>
<td><p>A/V 邊緣服務介面</p></td>
<td><p>每</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>每</p></td>
<td><p>A/V 邊緣服務介面</p></td>
<td><p>每</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office 通訊伺服器2007需要稍有不同的配置。 TCP 和 UDP 埠範圍為 50000-59999 必須開啟入站和出站。 這個需求只適用于 Office Communicator 2007。 Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 只需要 TCP 範圍 50000-59999 開啟輸出。



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Edge 服務的 NAT 需求

如果您選擇針對 Edge 服務設定無法路由的私人 IP 位址，則適用下列 NAT 需求：

  - NAT 只能與 DNS 負載平衡搭配使用。 NAT 在硬體負載平衡（HLB）邊緣拓撲中不受支援。

  - NAT 只能在外部邊緣介面上使用。 內部邊緣介面不支援 NAT。

  - NAT 必須針對內送和外寄流量進行對稱。
    
  - 對於來自網際網路的流量，NAT 必須將目的地 IP 位址從 A/V 邊緣服務的 NAT 啟用公用 IP 位址變更為其外部 IP 位址。 來源 IP 位址必須保持不變，因此 A/V Edge 服務可以找到最佳媒體路徑。
  
  例如，在下圖中的入站方向上，公用 IP 位址131.107.155.30 已變更為外部（私人） IP 位址10.45.16.10。 來源 IP 位址仍保持不變。
  
  - 對於從 A/V 邊緣服務到網際網路的流量，NAT 必須將來源 IP 位址從 A/V 邊緣服務的外部 IP 位址變更為啟用 NAT 的公用 IP 位址。

例如，在下圖中的輸出方向上，外部（私人） IP 位址10.45.16.10 已變更為公用 IP 位址131.107.155.30。

**下圖顯示 NAT 如何變更入站流量的目的地 IP 位址，以及輸出流量的來源 IP 位址。**

![變更目的地/來源 IP 位址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "變更目的地/來源 IP 位址")

重點如下：

  - 入站至執行 A/V 邊緣服務之伺服器的流量，來源 IP 位址不會變更，但目的地 IP 位址會從131.107.155.30 變更為10.45.16.10 的已翻譯 IP 位址。

  - 來源 IP 位址從伺服器的公用 IP 位址變更為執行 A/V 邊緣服務之伺服器的公用 IP 位址的流量（從伺服器的公用 IP 位址到工作站）。 目的地 IP 仍是工作站的公用 IP 位址。 在資料包離開第一個 NAT 裝置的輸出之後，NAT 裝置上的規則會將執行 A/V 邊緣服務外部介面 IP 位址（10.45.16.10）的伺服器來源 IP 位址變更為其公用 IP 位址（131.107.155.30）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

