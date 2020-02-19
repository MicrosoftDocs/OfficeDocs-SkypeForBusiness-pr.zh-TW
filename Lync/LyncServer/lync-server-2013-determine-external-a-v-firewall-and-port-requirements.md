---
title: Lync Server 2013： 決定外部 A / V 防火牆和連接埠需求
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
ms.openlocfilehash: 30492bed8deeb2a24dd136355e8f21f82e28a903
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42132566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>決定外部 A / V 防火牆和連接埠需求 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

音訊/視訊 (A / V) 通訊可能的複數。 因使用中的通訊協定的本質 / V，以及如何用戶端和伺服器使用的通訊協定，特殊] 區段中已獲得保證來說明用戶端及伺服器版本之間的差異。

使用下列的 A / V 防火牆和連接埠表格至判斷防火牆需求，以及哪些若要開啟 [連接埠。 接著檢閱網路位址轉譯 (NAT) 術語，因為 NAT 可透過許多方式實作。 防火牆連接埠設定的詳細範例，請參閱參考架構中[的 Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>UDP 和 TCP 音訊/視訊和媒體流量的一般通訊協定使用量

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>音訊/視訊傳輸</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>音訊及視訊的慣用的傳輸層通訊協定</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>音訊及視訊的後援傳輸層通訊協定</p>
<p>共用 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013 的應用程式需要傳輸層通訊協定</p>
<p>檔案傳輸時必須使用 Lync Server 2010 和 Lync Server 2013 需要傳輸層通訊協定</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>外部使用者存取的外部 A/V 防火牆連接埠需求

外部 （及內部） 的防火牆連接埠需求 SIP 和會議的介面是一致的無論您的用戶端的版本或同盟協力廠商的版本。

A/V Edge 外部介面則不同。 同盟與 Office Communications Server 2007，A / V Edge 服務需要外部防火牆規則，允許透過 59,999 流向兩個方向的連接埠範圍 50000 中的 RTP/TCP 和 RTP/UDP 流量。 上表假設 Lync Server 2013 是主要的同盟協力廠商，而且正在設定與其他同盟協力廠商類型所列的其中一個通訊。

設定音訊/視訊連接埠範圍 50000-59999 的必須考慮到的連接埠範圍將包含通訊對同盟協力廠商來源的連接埠。 在詳細資料，請考慮通訊會起始從同盟協力廠商。 通訊從 A / V Edge service 連接埠 50000-59999 範圍中的會連線到預期的連接埠 TCP 443 的合作夥伴的 A / V Edge service。 相反地，輸入流量 A/V Edge service 連接埠 TCP 443 會有 50000-59，999 介於來源連接埠。

不同的防火牆和防火牆管理的原則可能需要只目的地規則進行的設定，或他們可能需要來源和目的地，以進行設定。 如果您的需求適用於僅目的地連接埠，音訊/視訊需求︰


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
<td><p>A / V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A / V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任何</p></td>
<td><p>A / V Edge service 介面</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任何</p></td>
<td><p>A / V Edge service 介面</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


如果您的原則需要兩個輸入和輸出的防火牆規則定義，音訊/視訊需求︰


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
<td><p>A / V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>TCP 50000-59999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A / V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任何</p></td>
<td><p>A / V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任何</p></td>
<td><p>A / V Edge service 介面</p></td>
<td><p>任何</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 需要稍有不同的設定。 輸入和輸出，則必須開啟 50000-59999 的 TCP 及 UDP 連接埠範圍。 僅適用於 Office Communicator 2007 是這項要求。 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013 只需要 TCP 範圍 50000-59999 開放輸出。



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Edge service 的 NAT 需求

如果您選擇設定 Edge service 的非路由傳送私人 IP 位址，適用下列 NAT 需求：

  - NAT 只可以搭配 DNS 負載平衡。 NAT 不支援使用硬體負載平衡 (HLB) Edge 拓撲。

  - 只能在外部 Edge 介面 NAT。 內部 Edge 介面不支援 NAT。

  - NAT 必須對稱的內送和外寄流量。
    
  - 來自網際網路的流量，NAT 必須變更的目的地 IP 位址從啟用 NAT 的公用 IP 位址的 A / V Edge service 為外部 IP 位址。 來源 IP 位址必須保持不變，以便在 A / V Edge service 可以找出最佳的媒體路徑。
  
  例如，以在下圖中輸入的方向，公用 IP 位址 131.107.155.30 已變更為外部 （私人） IP 位址 10.45.16.10。 來源 IP 位址將維持不變。
  
  - 流量從 A / V Edge service 至網際網路，NAT 必須變更來源 IP 位址從外部 IP 位址的 A / V Edge service 為啟用 NAT 的公用 IP 位址。

例如，在下圖中的輸出方向，外部 （私人） IP 位址 10.45.16.10 已變更為公用 IP 位址 131.107.155.30。

**下圖顯示如何 NAT 變更輸入流量的目的地 IP 位址和輸出流量的來源 IP 位址。**

![變更目的地/來源 IP 位址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "變更目的地/來源 IP 位址")

重點為：

  - 是輸入到伺服器執行 A / V Edge service 為來源 IP 位址不會變更的流量，但目的地 IP 位址從 131.107.155.30 變更要翻譯的 IP 位址 10.45.16.10。

  - 會從執行 A server 輸出的流量 / V Edge service 回到工作站、 來源 IP 位址從伺服器的公用 IP 位址變更為公用 IP 位址的伺服器執行 A / V Edge service。 目的地 ip 位址會維持工作站的公用 IP 位址。 NAT 裝置上的規則封包離開的第一個 NAT 裝置輸出之後，變更來源 IP 位址的伺服器執行 A / V Edge service 為公用 IP 位址 (131.107.155.30) 的外部介面 IP 位址 (10.45.16.10)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

